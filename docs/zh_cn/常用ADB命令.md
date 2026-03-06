## 常用命令

GeeLark云手机支持Andorid系统所有的ADB命令，以下是一些日常使用较多的命令，开启adb请参考：https://www.geelark.cn/knowledge-base/geelark-start-guide/#adb

### 从本地电脑上传文件到云手机

```shell
adb push /Users/geelark/Downloads/movie.mp4 /sdcard/movie.mp4
```
### 从云手机下载文件到本地电脑
```shell
adb pull /sdcard/movie.mp4 /Users/geelark/Downloads/movie.mp4 
```

### 获取云手机设备ID
```shell
//Android 13系统：
adb shell getprop ro.boot.serialno
//其他系统：
adb shell getprop ro.serialno

```

### 获取云手机环境ID
```shell
adb shell getprop ro.gl.serialno
```

### 截取云手机屏幕并保存到本地
```shell
adb exec-out screencap -p > /Users/geelark/Downloads/screenshot.png
```

### 云手机录屏并保存到本地
```shell
adb shell screenrecord /sdcard/demo.mp4
adb pull /sdcard/demo.mp4 /Users/geelark/Downloads/demo.mp4
```

### 安装App到云手机
```shell
//（-r:覆盖，-g:授权）
adb install -r -g /Users/geelark/Downloads/tiktok.apk
```

### 卸载App
```shell
adb uninstall com.ss.android.ugc.aweme
```

### 点击坐标
```shell
// 点击坐标(400,360)
adb shell input tap 400 360
// 长按坐标(400,360)
adb shell input swipe 400 360 400 360 1000
// 从坐标(400,1200)滑动到(400,100)
adb shell input swipe 400 1200 400 100 1000
```
