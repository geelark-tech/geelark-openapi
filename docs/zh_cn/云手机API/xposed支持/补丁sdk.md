
补丁sdk用于生成补丁模块，可以通过安装补丁接口安装到云手机，实现系统及app适配能力，目前仅支持Android 12、Andorid 13、Andorid 15系统。

补丁模块安装后会实时生效，**无需**修改系统源码，**无需**设备重启，**无需**应用重启。

下载最新版本sdk及demo: [点击下载](https://germany-upgrade.geelark.com/xposed/latest.zip "点击下载")


**工作原理**
--------

补丁apk会在指定进程（支持系统及app进程）app启动前加载，并执行其中的入口方法: com.android.hp.Entry.init(Context context, Bundle params)

您可以在这个方法中实现自己的逻辑，sdk会提供基础的Xposed风格的api用于拦截，干预各类方法。

流程图如下：

 +---------+
 | 进程启动 ｜
 +---------+
 ↓
 +---------+
 | 获取补丁 ｜&lt;----------------
 +---------+ ｜
 ↓ ｜
 +---------+ ｜
 | 加载补丁 ｜ |
 +---------+ ｜
 ↓ ｜
 +---------+ ｜
 | 应用运行 ｜ |
 +---------+ ｜
 ↓ ｜
 ／ ＼ |
 ／ ＼ 是 +---------+
 |更新补丁？|-----------&gt;｜ 卸载补丁 ｜
 ＼ ／ +---------+
 ＼ ／
 | 
 ↓ 
 +---------+
 | 进程退出 ｜
 +---------+

 


**准备工作**
--------


* 您需要准备一个Android Studio开发环境，并下载Android sdk及ndk，请尽量使用最新版本： [Android Studio官网](https://www.android.com/)
* 如果您需要使用hook-api，请先了解Xposed风格的hook-api，并熟悉如何使用： [Xposed-api](https://api.xposed.info/reference/de/robv/android/xposed/XposedHelpers.html)

 

**开始开发**
--------

1. 打开Android Studio, 创建一个新的Android app项目，这里您可以直接拷贝demo项目。
2. 将sdk目录拷贝到**项目根目录**中(注意不要更改该目录下的任何文件)，并在项目根目录中的build.gradle文件后边添加如下配置：

 ```config 
 // 项目配置
 ext {
 // 这里设置各类android sdk/ndk等版本信息，建议直接使用如下默认的配置。请使用Android SDK Manager下载对应版本的sdk/ndk/cmake等工具
 minSdkVersion = 23
 compileSdkVersion = 33
 targetSdkVersion = 33
 buildToolsVersion = "33.0.0"
 javaVersion = JavaVersion.VERSION_1_8
 ndkVersion = "24.0.8215888"
 cmakeVersion = "3.22.1"

 // 这里填写sdk目录所在的路径，demo中是放在项目根目录下的sdk目录
 patchSdkDir = "$rootDir/sdk"
 patchGradle = "$patchSdkDir/patch.gradle"
 }
	```

3. 修改**app项目**的build.gradle文件为如下内容：

	```config
 buildscript {
 dependencies {
 classpath fileTree(dir: "$rootProject.ext.patchSdkDir", include: &#039;agp_*.jar&#039;)
 }
 }
 // 只修改这里的配置即可
 ext.patch = [
 // 补丁id，作为确认补丁的唯一标识，注意不要冲突！
 id: "sdktest",
 // 补丁版本，如果为0，则自动根据当前的epoch时间戳生成，例如1696822576
 version: 0,
 // 可以加载补丁的包名正则表达式，如果存在pkg.txt文件，则忽略这里的配置
 targetPattern: &#039;&#039;,
 // 补丁加载优先级， 数越小越先加载，默认为0
 priority: 0,
 // 是否支持热加载，热加载可以在一次进程的生命周期中多次加载，卸载，加载...
 hotpatch: true,
 // 补丁描述
 description: "补丁测试demo",
 // 补丁负责方，这里可以写你的公司的名字，用于排查问题
 owner: "unknown"
 ]
 apply from: "$rootProject.ext.patchGradle"
	 ```

4. 在**app项目中**定义如下类：com.android.hp.Entry，并分别根据业务需求实现init和deInit方法

	```code
 package com.android.hp;

 import android.content.Context;
 import android.content.pm.PackageInfo;
 import android.content.pm.PackageManager;
 import android.os.Bundle;
 import com.android.server.dexguard.DGLog;
 import de.robv.android.xposed.XC_MethodHook;
 import de.robv.android.xposed.XposedHelpers;

 /**
 * 补丁模块的入口类，固定使用com.android.hp.Entry。
 * 注意： 请不要修改这个类文件的路径及类名！！！
 */
 public class Entry {
 private static final String TAG = "Entry";

 /**
 * 在补丁加载时会调用，调用时机：
 * 1. 进程启动时。
 * 2. 进程已启动，补丁首次安装或升级后。
 *
 * @param appContext 进程的应用Context
 * @param params 其它信息，一般不会使用，具体参考文档。
 */
 public static void init(Context appContext, Bundle params) {
 // 在补丁中，可以使用DGLog工具类来打印log，注意log分级
 DGLog.i(TAG, "init() loaded pkg = %s", appContext.getPackageName());

 // 使用例子1：干预系统获取应用api(android.app.ApplicationPackageManager.getPackageInfoAsUser(String, int, int))，禁止返回com.abc的应用包
 try {
 // 通过反射获取 "android.app.ApplicationPackageManager" 类
 Class&lt;?&gt; pmClass = Class.forName("android.app.ApplicationPackageManager", true, appContext.getClassLoader());

 // 使用 xposed-api，hook "android.app.ApplicationPackageManager.getPackageInfoAsUser" 方法
 // 这个方法是PackageManager.getPackageInfo()的底层实现，所以这里hook这个方法即可
 // 注意：xposed的部分api是会抛出异常的，请注意处理异常！！！
 XposedHelpers.findAndHookMethod(pmClass, "getPackageInfoAsUser", String.class, int.class, int.class, new XC_MethodHook() {
 @Override
 protected void afterHookedMethod(MethodHookParam param) throws Throwable {
 super.afterHookedMethod(param);

 // 获取查询的包名
 String pkg = (String) param.args[0];

 // 如果查询的包名是 "com.abc"，那么抛出异常来隐藏这个应用
 if ("com.abc".equals(pkg)) {
 DGLog.d(TAG, "hide app %s from %s", pkg, param.method.getName());

 // 抛出 NameNotFoundException，使其看起来像这个包没有安装在设备上
 param.setThrowable(new PackageManager.NameNotFoundException(pkg));
 }
 }
 });

 // 记录成功的日志
 DGLog.d(TAG, "hide app by pms api success!");
 } catch (Throwable t) {
 // 如果有任何异常，记录异常日志
 DGLog.e(TAG, "init package manager guard error", t);
 }
 }

 /**
 * 在补丁卸载时会调用，调用时机：
 * 1. 如果该进程加载过补丁，补丁被卸载后会触发。
 *
 * @param appContext 进程的应用Context
 * @param params 其它信息，一般不会使用，具体参考文档。
 */
 public static void deInit(Context appContext, Bundle params) {
 DGLog.i(TAG, "deInit() loaded pkg = %s", appContext.getPackageName());
 }
 }

 	```

5. **设定覆盖应用**： 写在**app项目目录**的**pkg.txt**文件中，每行一个包名，支持正则匹配，具体格式如下：

	```format
 # 补丁只会在如下设置的目标包名的应用进程中加载，注意覆盖范围尽量小，只针对特定应用即可
 com.example.abc
 com.example.def

 # 正则方式，匹配所有com.facebook.开头的包名
 com\.facebook\..*

 # 如果需要干预system_server，填写android
 android
	```

6. **编译补丁**：在**项目根目录**中，执行如下命令生成补丁apk：

	```build
 # linux或mac环境
 ./gradlew clean app:assembleRelease

 # windows环境
 gradlew clean app:assembleRelease
	```
7. **安装补丁**：将生成的apk（一般在app/build/outputs/apk/目录中）上传到存储空间，
 可调用上传临时文件到GeeLark接口
 然后调用安装补丁接口
 查看补丁安装信息可调用查询补丁安装状态接口，补丁id为你在app项目中build.gradle的设置的
 ![](http://showdoc.geelark.com/server/index.php?s=/api/attachment/visitFile&amp;sign=e2713d9b578da69a6e6f58b185943583)

