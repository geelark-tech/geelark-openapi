# GeeLark OpenAPI

[中文版本请参考这里](#中文文档-api-reference)

Welcome to the official GeeLark API documentation. This repository contains comprehensive API references for GeeLark's cloud-based services.

## Request Instructions

### Base URL

```
https://openapi.geelark.com
```

### Authentication

All API requests require authentication via an API Token. Include your API Token in the request header:

```
Authorization: Bearer YOUR_API_TOKEN
```

### Request Format

- All request bodies should be in JSON format
- Set `Content-Type: application/json` header for POST requests
- All timestamps are in UTC (RFC 3339 format)

### Response Format

All responses follow a consistent structure:

```json
{
  "traceId": "string",
  "code": integer,
  "msg": "string",
  "data": object
}
```

| Field | Type | Description |
|-------|------|-------------|
| traceId | string | Unique request identifier for debugging |
| code | integer | Status code (0 = success) |
| msg | string | Status message |
| data | object | Response data (null on error) |

### Error Handling

When an error occurs, the response will include an error code and message. For detailed error information, refer to:
- [Cloud Phone Error Codes](./docs/en/Error%20Codes/Cloud_Phone_Error_Codes.md)
- [Browser Error Codes](./docs/en/Error%20Codes/Browser_Error_Codes.md)

---

## API Reference

### Cloud Phone API

#### Cloud Phone Management

- [Create new V2](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Create_new_V2.md)
- [One-click new machine V2](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/One-click_new_machine_V2.md)
- [Delete cloud phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Delete_cloud_phone.md)
- [Clone cloud phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Clone_cloud_phone.md)
- [Get all cloud phones](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_all_cloud_phones.md)
- [Modify cloud phone information](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Modify_cloud_phone_information.md)
- [Get cloud phone network settings](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_cloud_phone_network_settings.md)
- [Modify cloud phone network settings](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Modify_cloud_phone_network_settings.md)
- [Transfer Cloud Phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Transfer_Cloud_Phone.md)
- [Move Group](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Move_Group.md)
- [Start cloud phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Start_cloud_phone.md)
- [Stop cloud phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Stop_cloud_phone.md)
- [Query status](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Query_status.md)
- [Screen Shot](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Screen_Shot.md)
- [Get screen shot result](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_screen_shot_result.md)
- [Set GPS](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Set_GPS.md)
- [Get GPS](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_GPS_.md)
- [Set net type](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Set_net_type.md)
- [Set Root Status](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Set_Root_Status.md)
- [Hide Accessibility](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Hide_Accessibility.md)
- [Send SMS to cloud phone](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Send_SMS_to_cloud_phone.md)
- [Get device ID](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_device_ID.md)
- [List of cloud mobile phone brands](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/List_of_cloud_mobile_phone_brands.md)
- [Batch Import Contacts](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Batch_Import_Contacts.md)
- [Get Batch Import Contacts Result](./docs/en/Cloud%20Phone%20API/Cloud%20Phone%20Management/Get_Batch_Import_Contacts_Result.md)

#### ADB

- [Common ADB Commands](./docs/en/Cloud%20Phone%20API/ADB/Common_ADB_Commands.md)
- [Get ADB information](./docs/en/Cloud%20Phone%20API/ADB/Get_ADB_information.md)
- [Set ADB Status](./docs/en/Cloud%20Phone%20API/ADB/Set_ADB_Status.md)

#### Analytics

- [Accounts List](./docs/en/Cloud%20Phone%20API/Analytics/Accounts_List.md)
- [Add Accounts](./docs/en/Cloud%20Phone%20API/Analytics/Add_Accounts.md)
- [Get account data](./docs/en/Cloud%20Phone%20API/Analytics/Get_account_data.md)
- [Update Account](./docs/en/Cloud%20Phone%20API/Analytics/Update_Account.md)
- [Delete Account](./docs/en/Cloud%20Phone%20API/Analytics/Delete_Account.md)

#### Application Management

- [Get available applications](./docs/en/Cloud%20Phone%20API/Application%20Management/Get_available_applications.md)
- [Get installed applications](./docs/en/Cloud%20Phone%20API/Application%20Management/Get_installed_applications.md)
- [Install application](./docs/en/Cloud%20Phone%20API/Application%20Management/Install_application.md)
- [Uninstall application](./docs/en/Cloud%20Phone%20API/Application%20Management/Uninstall_application.md)
- [Start application](./docs/en/Cloud%20Phone%20API/Application%20Management/Start_application.md)
- [Stop application](./docs/en/Cloud%20Phone%20API/Application%20Management/Stop_application.md)
- [Batch Operate Cloud Phone App](./docs/en/Cloud%20Phone%20API/Application%20Management/Batch_Operate_Cloud_Phone_App.md)
- [Upload Application](./docs/en/Cloud%20Phone%20API/Application%20Management/Upload_Application.md)
- [Query Application Upload Status](./docs/en/Cloud%20Phone%20API/Application%20Management/Query_Application_Upload_Status.md)
- [Get Team App List](./docs/en/Cloud%20Phone%20API/Application%20Management/Get_Team_App_List.md)
- [Add to Team Applications](./docs/en/Cloud%20Phone%20API/Application%20Management/Add_to_Team_Applications.md)
- [Set Team App Authorization](./docs/en/Cloud%20Phone%20API/Application%20Management/Set_Team_App_Authorization.md)
- [Set Team App Auto Start](./docs/en/Cloud%20Phone%20API/Application%20Management/Set_Team_App_Auto_Start.md)
- [Set Team App Keep Alive](./docs/en/Cloud%20Phone%20API/Application%20Management/Set_Team_App_Keep_Alive.md)
- [Set Team App ROOT Access](./docs/en/Cloud%20Phone%20API/Application%20Management/Set_Team_App_ROOT_Access.md)
- [Set Team Apps to Install Automatically](./docs/en/Cloud%20Phone%20API/Application%20Management/Set_Team_Apps_to_Install_Automatically.md)
- [Remove Team Apps](./docs/en/Cloud%20Phone%20API/Application%20Management/Remove_Team_Apps.md)
- [Get the application list](./docs/en/Cloud%20Phone%20API/Application%20Management/Get_the_application_list.md)

#### Automation

##### Task Management

- [Query task](./docs/en/Cloud%20Phone%20API/Automation/Task%20Management/Query_task.md)
- [Batch query tasks](./docs/en/Cloud%20Phone%20API/Automation/Task%20Management/Batch_query_tasks.md)
- [Cancel task](./docs/en/Cloud%20Phone%20API/Automation/Task%20Management/Cancel_task.md)
- [Retry Task](./docs/en/Cloud%20Phone%20API/Automation/Task%20Management/Retry_Task.md)
- [Task Detail](./docs/en/Cloud%20Phone%20API/Automation/Task%20Management/Task_Detail.md)

##### Custom Task

- [Create custom task](./docs/en/Cloud%20Phone%20API/Automation/Custom%20Task/Create_custom_task.md)
- [Task flow query](./docs/en/Cloud%20Phone%20API/Automation/Custom%20Task/Task_flow_query.md)
- [Export custom task flow](./docs/en/Cloud%20Phone%20API/Automation/Custom%20Task/Export_custom_task_flow.md)
- [Import custom task flow](./docs/en/Cloud%20Phone%20API/Automation/Custom%20Task/Import_custom_task_flow.md)

##### TikTok

- [TikTok login](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_login.md)
- [TikTok profile edit](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_profile_edit.md)
- [TikTok follow](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_follow.md)
- [TikTok follow (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_follow_-_Asia.md)
- [TikTok star](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_star.md)
- [TikTok star (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_star_-_Asia.md)
- [TikTok AI comment](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_AI_comment.md)
- [TikTok AI comment (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/TikTok_AI_comment_-_Asia.md)
- [Send private message on TikTok](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Send_private_message_on_TikTok.md)
- [Send private message on TikTok (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Send_private_message_on_TikTok_-_Asia.md)
- [Delete all TikTok videos](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Delete_all_TikTok_videos.md)
- [Delete all TikTok videos (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Delete_all_TikTok_videos_-_Asia.md)
- [Hide all TikTok videos](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Hide_all_TikTok_videos.md)
- [Hide all TikTok videos (Asia)](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Hide_all_TikTok_videos_-_Asia.md)
- [Add video image warmup task](./docs/en/Cloud%20Phone%20API/Automation/TikTok/Add_video_image_warmup_task.md)

##### Facebook

- [Facebook auto login](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Facebook_auto_login.md)
- [Facebook maintenance](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Facebook_maintenance.md)
- [Facebook post content](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Facebook_post_content.md)
- [Facebook publish Reels video](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Facebook_publish_Reels_video.md)
- [Facebook auto comment](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Facebook_auto_comment.md)
- [Send private messages on Facebook](./docs/en/Cloud%20Phone%20API/Automation/Facebook/Send_private_messages_on_Facebook.md)

##### Instagram

- [Instagram auto login](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Instagram_auto_login.md)
- [Edit Instagram profile](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Edit_Instagram_profile.md)
- [Instagram AI account warmup](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Instagram_AI_account_warmup.md)
- [Instagram publish Reels image](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Instagram_publish_Reels_image.md)
- [Instagram publish Reels video](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Instagram_publish_Reels_video.md)
- [Send private messages on Instagram](./docs/en/Cloud%20Phone%20API/Automation/Instagram/Send_private_messages_on_Instagram.md)

##### YouTube

- [YouTube maintenance](./docs/en/Cloud%20Phone%20API/Automation/YouTube/YouTube_maintenance.md)
- [YouTube publish Video](./docs/en/Cloud%20Phone%20API/Automation/YouTube/YouTube_publish_Video.md)
- [YouTube publish Short](./docs/en/Cloud%20Phone%20API/Automation/YouTube/YouTube_publish_Short.md)

##### X (Twitter)

- [Publish content on X (Twitter)](./docs/en/Cloud%20Phone%20API/Automation/X(Twitter)/Publish_content_on_X(Twitter).md)

##### Google

- [Google auto login](./docs/en/Cloud%20Phone%20API/Automation/Google/Google_auto_login.md)
- [Download apps on Google](./docs/en/Cloud%20Phone%20API/Automation/Google/Download_apps_on_Google.md)
- [Open the app on Google for browsing](./docs/en/Cloud%20Phone%20API/Automation/Google/Open_the_app_on_Google_for_browsing.md)

##### Pinterest

- [Publish pictures and texts on Pinterest](./docs/en/Cloud%20Phone%20API/Automation/Pinterest/Publish_pictures_and_texts_on_Pinterest.md)
- [Publish video on Pinterest](./docs/en/Cloud%20Phone%20API/Automation/Pinterest/Publish_video_on_Pinterest.md)

##### Reddit

- [Reddit AI account warmup](./docs/en/Cloud%20Phone%20API/Automation/Reddit/Reddit_AI_account_warmup.md)
- [Publish pictures and texts on Reddit](./docs/en/Cloud%20Phone%20API/Automation/Reddit/Publish_pictures_and_texts_on_Reddit.md)
- [Publish video on Reddit](./docs/en/Cloud%20Phone%20API/Automation/Reddit/Publish_video_on_Reddit.md)

##### Threads

- [Publish pictures and texts on Threads](./docs/en/Cloud%20Phone%20API/Automation/Threads/Publish_pictures_and_texts_on_Threads.md)
- [Publish video on Threads](./docs/en/Cloud%20Phone%20API/Automation/Threads/Publish_video_on_Threads.md)

##### SHEIN

- [SHEIN auto login](./docs/en/Cloud%20Phone%20API/Automation/Shein/SHEIN_auto_login.md)

##### Other Task

- [Batch import contacts to cloud phone](./docs/en/Cloud%20Phone%20API/Automation/Other%20Task/Batch_import_contacts_to_cloud_phone.md)
- [Multichannel video distribution](./docs/en/Cloud%20Phone%20API/Automation/Other%20Task/Multichannel_video_distribution.md)
- [Upload files to the cloud machine in batches](./docs/en/Cloud%20Phone%20API/Automation/Other%20Task/Upload_files_to_the_cloud_machine_in_batches.md)
- [Upload Keybox to the cloud phone](./docs/en/Cloud%20Phone%20API/Automation/Other%20Task/Upload_Keybox_to_the_cloud_phone.md)

#### File Management

- [Upload files to the cloud phone](./docs/en/Cloud%20Phone%20API/File%20Management/Upload_files_to_the_cloud_phone.md)
- [Query the upload status of files to the cloud phone](./docs/en/Cloud%20Phone%20API/File%20Management/Query_the_upload_status_of_files_to_the_cloud_phone.md)
- [Upload temporary files to GeeLark](./docs/en/Cloud%20Phone%20API/File%20Management/Upload_temporary_files_to_GeeLark.md)
- [Upload the keybox file](./docs/en/Cloud%20Phone%20API/File%20Management/Upload_the_keybox_file.md)
- [Query the upload keybox file task result](./docs/en/Cloud%20Phone%20API/File%20Management/Query_the_upload_keybox_file_task_result.md)

#### Library

- [Create material](./docs/en/Cloud%20Phone%20API/Library/Create_material.md)
- [Delete material](./docs/en/Cloud%20Phone%20API/Library/Delete_material.md)
- [Search material](./docs/en/Cloud%20Phone%20API/Library/Search_material.md)
- [Upload files to the Library](./docs/en/Cloud%20Phone%20API/Library/Upload_files_to_the_Library.md)
- [Create tag](./docs/en/Cloud%20Phone%20API/Library/Create_tag.md)
- [Delete tag](./docs/en/Cloud%20Phone%20API/Library/Delete_tag.md)
- [Search material tag](./docs/en/Cloud%20Phone%20API/Library/Search_material_tag.md)
- [Set material tag](./docs/en/Cloud%20Phone%20API/Library/Set_material_tag.md)

#### Shell

- [Execute shell command](./docs/en/Cloud%20Phone%20API/Shell/Execute_shell_command.md)

#### Webhook

- [Set Webhook URL](./docs/en/Cloud%20Phone%20API/Webhook/Set_Webhook_URL.md)
- [Get Webhook URL](./docs/en/Cloud%20Phone%20API/Webhook/Get_Webhook_URL.md)
- [Instruction](./docs/en/Cloud%20Phone%20API/Webhook/Instruction.md)
- [Callback Type](./docs/en/Cloud%20Phone%20API/Webhook/Callback_Type.md)

#### OEM White Label

- [OEM White Label](./docs/en/Cloud%20Phone%20API/OEM_White%20Label/OEM_White_Label.md)

---

### Proxy Management

- [Add proxy](./docs/en/Proxy%20Management/Add_proxy.md)
- [Delete proxy](./docs/en/Proxy%20Management/Delete_proxy.md)
- [Get all proxies](./docs/en/Proxy%20Management/Get_all_proxies.md)
- [Update proxy](./docs/en/Proxy%20Management/Update_proxy.md)
- [Proxy Detection](./docs/en/Proxy%20Management/Proxy_Detection.md)

---

### Group Management

- [Create group](./docs/en/Group%20Management/Create_group.md)
- [Delete group](./docs/en/Group%20Management/Delete_group.md)
- [Modify group](./docs/en/Group%20Management/Modify_group.md)
- [Query group](./docs/en/Group%20Management/Query_group.md)

---

### Tag Management

- [Create tag](./docs/en/Tag%20Management/Create_tag.md)
- [Delete tag](./docs/en/Tag%20Management/Delete_tag.md)
- [Modify tag](./docs/en/Tag%20Management/Modify_tag.md)
- [Query tag](./docs/en/Tag%20Management/Query_tag.md)

---

### Billing

- [Balance Inquiry](./docs/en/Billing/Balance_Inquiry.md)
- [Billing transaction detail](./docs/en/Billing/Billing_transaction_detail.md)
- [Change plan](./docs/en/Billing/Change_plan.md)
- [Get plan list](./docs/en/Billing/Get_plan_list.md)
- [Get the current subscription plan information](./docs/en/Billing/Get_the_current_subscription_plan_information.md)
- [Renew plan](./docs/en/Billing/Renew_plan.md)

---

### Browser API

#### Browser Management

- [Create new browser](./docs/en/Browser%20API/Browser%20Management/Create_new_browser.md)
- [Edit browser](./docs/en/Browser%20API/Browser%20Management/Edit_browser.md)
- [Delete browser](./docs/en/Browser%20API/Browser%20Management/Delete_browser.md)
- [Launch browser](./docs/en/Browser%20API/Browser%20Management/Launch_browser.md)
- [Close browser](./docs/en/Browser%20API/Browser%20Management/Close_browser.md)
- [Get browser list](./docs/en/Browser%20API/Browser%20Management/Get_browser_list.md)
- [Check browser status](./docs/en/Browser%20API/Browser%20Management/Check_browser_status.md)
- [Check API interface status](./docs/en/Browser%20API/Browser%20Management/Check_API_interface_status.md)
- [Clear browser cache](./docs/en/Browser%20API/Browser%20Management/Clear_browser_cache.md)
- [Clone browser](./docs/en/Browser%20API/Browser%20Management/Clone_browser.md)
- [Browser Mobile Grouping](./docs/en/Browser%20API/Browser%20Management/Browser_Mobile_Grouping.md)
- [Transfer browsers](./docs/en/Browser%20API/Browser%20Management/Transfer_browsers.md)
- [Get browser bookmarks](./docs/en/Browser%20API/Browser%20Management/Get_browser_bookmarks.md)
- [Set browser bookmarks](./docs/en/Browser%20API/Browser%20Management/Set_browser_bookmarks.md)
- [Query environment cookies](./docs/en/Browser%20API/Browser%20Management/Query_environment_cookies.md)

#### Automation

##### Task Management

- [Query task](./docs/en/Browser%20API/Automation/Task%20Management/Query_task.md)
- [Query task details](./docs/en/Browser%20API/Automation/Task%20Management/Query_task_details.md)
- [Cancel task](./docs/en/Browser%20API/Automation/Task%20Management/Cancel_task.md)
- [Retry Task](./docs/en/Browser%20API/Automation/Task%20Management/Retry_Task.md)

##### Custom Task

- [Create custom task](./docs/en/Browser%20API/Automation/Custom%20Task/Create_custom_task.md)
- [Task flow query](./docs/en/Browser%20API/Automation/Custom%20Task/Task_flow_query.md)

##### TikTok

- [TikTok search videos, likes and comments](./docs/en/Browser%20API/Automation/TikTok/TikTok_search_videos,_likes_and_comments.md)
- [TikTok like specified videos](./docs/en/Browser%20API/Automation/TikTok/TikTok_like_specified_videos.md)
- [TikTok like and comment on videos](./docs/en/Browser%20API/Automation/TikTok/TikTok_like_and_comment_on_videos.md)

##### Facebook

- [Facebook Post a Status](./docs/en/Browser%20API/Automation/Facebook/Facebook_Post_a_Status.md)
- [Facebook account creates a homepage](./docs/en/Browser%20API/Automation/Facebook/Facebook_account_creates_a_homepage.md)
- [Facebook add recommended friends](./docs/en/Browser%20API/Automation/Facebook/Facebook_add_recommended_friends.md)
- [Facebook like all on the first screen](./docs/en/Browser%20API/Automation/Facebook/Facebook_like_all_on_the_first_screen.md)

##### Instagram

- [Browse and like Instagram feed](./docs/en/Browser%20API/Automation/Instagram/Browse_and_like_Instagram_feed.md)
- [Instagram search hashtags and browse posts](./docs/en/Browser%20API/Automation/Instagram/Instagram_search_hashtags_and_browse_posts.md)

##### X (Twitter)

- [X (Twitter) Retweet and Post a Tweet](./docs/en/Browser%20API/Automation/X(Twitter)/X(Twitter)_Retweet_and_Post_a_Tweet.md)
- [X (Twitter) like and retweet tweets](./docs/en/Browser%20API/Automation/X(Twitter)/X(Twitter)_like_and_retweet_tweets.md)

##### YouTube

- [YouTube Watch Videos](./docs/en/Browser%20API/Automation/YouTube/YouTube_Watch_Videos.md)

##### Reddit

- [Browse and like Reddit posts searched by keywords](./docs/en/Browser%20API/Automation/Reddit/Browse_and_like_Reddit_posts_searched_by_keywords.md)

##### Other Task

- [Cookie Bot](./docs/en/Browser%20API/Automation/Other%20Task/Cookie_Bot.md)

---

### Proxy Detection

- [Proxy Detection](./docs/en/Proxy%20Detection/Proxy_Detection.md)

---

### Error Codes

- [Cloud Phone Error Codes](./docs/en/Error%20Codes/Cloud_Phone_Error_Codes.md)
- [Browser Error Codes](./docs/en/Error%20Codes/Browser_Error_Codes.md)

---

### User Guide

#### Cloud Phone

- [Request Instructions](./docs/en/User%20Guide/Cloud%20Phone/Request_Instructions.md)
- [Request example](./docs/en/User%20Guide/Cloud%20Phone/Request_example.md)
- [Create automated tasks](./docs/en/User%20Guide/Cloud%20Phone/Create_automated_tasks.md)

#### Browser

- [Request Instructions](./docs/en/User%20Guide/Browser/Request_Instructions.md)
- [Request example](./docs/en/User%20Guide/Browser/Request_example.md)

---

## Change Log

- [Change Log](./docs/en/Change_log.md)

---

## 中文文档 API Reference

## 请求说明

### 基础地址

```
https://openapi.geelark.cn
```

### 认证方式

所有 API 请求都需要通过 API Token 进行认证。请在请求头中包含您的 API Token：

```
Authorization: Bearer YOUR_API_TOKEN
```

### 请求格式

- 所有请求体应使用 JSON 格式
- POST 请求请设置 `Content-Type: application/json` 请求头
- 所有时间戳均为 UTC 时间（RFC 3339 格式）

### 响应格式

所有响应均遵循统一结构：

```json
{
  "traceId": "string",
  "code": integer,
  "msg": "string",
  "data": object
}
```

| 字段 | 类型 | 描述 |
|------|------|------|
| traceId | string | 请求唯一标识符，用于调试 |
| code | integer | 状态码（0 = 成功） |
| msg | string | 状态消息 |
| data | object | 响应数据（错误时为 null） |

### 错误处理

当发生错误时，响应将包含错误码和错误信息。详细错误信息请参考：
- [云手机错误码](./docs/zh_cn/错误码/云手机错误码.md)
- [浏览器错误码](./docs/zh_cn/错误码/浏览器错误码.md)

---

### 云手机API

#### 云手机管理

- [一键新机V2](./docs/zh_cn/云手机API/云手机管理/一键新机V2.md)
- [云手机品牌列表](./docs/zh_cn/云手机API/云手机管理/云手机品牌列表.md)
- [修改云手机信息](./docs/zh_cn/云手机API/云手机管理/修改云手机信息.md)
- [修改云手机网络设置](./docs/zh_cn/云手机API/云手机管理/修改云手机网络设置.md)
- [克隆云手机](./docs/zh_cn/云手机API/云手机管理/克隆云手机.md)
- [关闭云手机](./docs/zh_cn/云手机API/云手机管理/关闭云手机.md)
- [删除云手机](./docs/zh_cn/云手机API/云手机管理/删除云手机.md)
- [发送短信到云手机](./docs/zh_cn/云手机API/云手机管理/发送短信到云手机.md)
- [启动云手机](./docs/zh_cn/云手机API/云手机管理/启动云手机.md)
- [应用隐藏辅助服务](./docs/zh_cn/云手机API/云手机管理/应用隐藏辅助服务.md)
- [截图](./docs/zh_cn/云手机API/云手机管理/截图.md)
- [截图结果获取](./docs/zh_cn/云手机API/云手机管理/截图结果获取.md)
- [批量导入联系人](./docs/zh_cn/云手机API/云手机管理/批量导入联系人.md)
- [新建云手机(已弃用)](./docs/zh_cn/云手机API/云手机管理/新建云手机(已弃用).md)
- [新建云手机V2](./docs/zh_cn/云手机API/云手机管理/新建云手机V2.md)
- [查询云手机状态](./docs/zh_cn/云手机API/云手机管理/查询云手机状态.md)
- [移动分组](./docs/zh_cn/云手机API/云手机管理/移动分组.md)
- [获取云手机GPS](./docs/zh_cn/云手机API/云手机管理/获取云手机GPS.md)
- [获取云手机列表](./docs/zh_cn/云手机API/云手机管理/获取云手机列表.md)
- [获取云手机网络设置](./docs/zh_cn/云手机API/云手机管理/获取云手机网络设置.md)
- [获取云手机设备ID](./docs/zh_cn/云手机API/云手机管理/获取云手机设备ID.md)
- [获取批量导入联系人结果](./docs/zh_cn/云手机API/云手机管理/获取批量导入联系人结果.md)
- [设置ROOT状态](./docs/zh_cn/云手机API/云手机管理/设置ROOT状态.md)
- [设置云手机GPS](./docs/zh_cn/云手机API/云手机管理/设置云手机GPS.md)
- [设置云手机联网方式](./docs/zh_cn/云手机API/云手机管理/设置云手机联网方式.md)
- [转让云手机](./docs/zh_cn/云手机API/云手机管理/转让云手机.md)

#### ADB

- [常用ADB命令](./docs/zh_cn/云手机API/ADB/常用ADB命令.md)
- [获取ADB信息](./docs/zh_cn/云手机API/ADB/获取ADB信息.md)
- [设置ADB状态](./docs/zh_cn/云手机API/ADB/设置ADB状态.md)

#### 数据助手

- [删除账号](./docs/zh_cn/云手机API/数据助手/删除账号.md)
- [数据列表](./docs/zh_cn/云手机API/数据助手/数据列表.md)
- [更新账号](./docs/zh_cn/云手机API/数据助手/更新账号.md)
- [添加账号](./docs/zh_cn/云手机API/数据助手/添加账号.md)
- [账号列表](./docs/zh_cn/云手机API/数据助手/账号列表.md)

#### 应用管理

- [上传应用](./docs/zh_cn/云手机API/应用管理/上传应用.md)
- [关闭应用](./docs/zh_cn/云手机API/应用管理/关闭应用.md)
- [卸载应用](./docs/zh_cn/云手机API/应用管理/卸载应用.md)
- [启动应用](./docs/zh_cn/云手机API/应用管理/启动应用.md)
- [安装应用](./docs/zh_cn/云手机API/应用管理/安装应用.md)
- [应用批量操作](./docs/zh_cn/云手机API/应用管理/应用批量操作.md)
- [查询上传应用状态](./docs/zh_cn/云手机API/应用管理/查询上传应用状态.md)
- [添加到团队应用](./docs/zh_cn/云手机API/应用管理/添加到团队应用.md)
- [移除团队应用](./docs/zh_cn/云手机API/应用管理/移除团队应用.md)
- [获取云手机可安装应用列表](./docs/zh_cn/云手机API/应用管理/获取云手机可安装应用列表.md)
- [获取云手机应用列表](./docs/zh_cn/云手机API/应用管理/获取云手机应用列表.md)
- [获取团队应用列表](./docs/zh_cn/云手机API/应用管理/获取团队应用列表.md)
- [获取应用列表](./docs/zh_cn/云手机API/应用管理/获取应用列表.md)
- [设置团队应用ROOT](./docs/zh_cn/云手机API/应用管理/设置团队应用ROOT.md)
- [设置团队应用保活](./docs/zh_cn/云手机API/应用管理/设置团队应用保活.md)
- [设置团队应用授权](./docs/zh_cn/云手机API/应用管理/设置团队应用授权.md)
- [设置团队应用自动安装](./docs/zh_cn/云手机API/应用管理/设置团队应用自动安装.md)
- [设置团队应用自启动](./docs/zh_cn/云手机API/应用管理/设置团队应用自启动.md)

#### 自动化

##### 任务管理

- [取消任务](./docs/zh_cn/云手机API/自动化/任务管理/取消任务.md)
- [批量查询任务](./docs/zh_cn/云手机API/自动化/任务管理/批量查询任务.md)
- [查询任务](./docs/zh_cn/云手机API/自动化/任务管理/查询任务.md)
- [查询任务详情](./docs/zh_cn/云手机API/自动化/任务管理/查询任务详情.md)
- [重试任务](./docs/zh_cn/云手机API/自动化/任务管理/重试任务.md)

##### 自定义任务

- [创建自定义任务](./docs/zh_cn/云手机API/自动化/自定义任务/创建自定义任务.md)
- [导入自定义任务](./docs/zh_cn/云手机API/自动化/自定义任务/导入自定义任务.md)
- [导出自定义任务](./docs/zh_cn/云手机API/自动化/自定义任务/导出自定义任务.md)
- [自定义流程查询](./docs/zh_cn/云手机API/自动化/自定义任务/自定义流程查询.md)

##### TikTok

- [TikTok AI随机评论](./docs/zh_cn/云手机API/自动化/TikTok/TikTok%20AI随机评论.md)
- [TikTok AI随机评论-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok%20AI随机评论-亚洲.md)
- [TikTok删除所有视频](./docs/zh_cn/云手机API/自动化/TikTok/TikTok删除所有视频.md)
- [TikTok删除所有视频-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok删除所有视频-亚洲.md)
- [TikTok发送私信](./docs/zh_cn/云手机API/自动化/TikTok/TikTok发送私信.md)
- [TikTok发送私信-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok发送私信-亚洲.md)
- [TikTok登录账号](./docs/zh_cn/云手机API/自动化/TikTok/TikTok登录账号.md)
- [TikTok编辑资料](./docs/zh_cn/云手机API/自动化/TikTok/TikTok编辑资料.md)
- [TikTok随机关注](./docs/zh_cn/云手机API/自动化/TikTok/TikTok随机关注.md)
- [TikTok随机关注-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok随机关注-亚洲.md)
- [TikTok随机点赞](./docs/zh_cn/云手机API/自动化/TikTok/TikTok随机点赞.md)
- [TikTok随机点赞-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok随机点赞-亚洲.md)
- [TikTok隐藏所有视频](./docs/zh_cn/云手机API/自动化/TikTok/TikTok隐藏所有视频.md)
- [TikTok隐藏所有视频-亚洲](./docs/zh_cn/云手机API/自动化/TikTok/TikTok隐藏所有视频-亚洲.md)
- [添加视频_图集_养号任务](./docs/zh_cn/云手机API/自动化/TikTok/添加视频_图集_养号任务.md)

##### Facebook

- [Facebook养号](./docs/zh_cn/云手机API/自动化/Facebook/Facebook养号.md)
- [Facebook发布Reels视频](./docs/zh_cn/云手机API/自动化/Facebook/Facebook发布Reels视频.md)
- [Facebook发布内容](./docs/zh_cn/云手机API/自动化/Facebook/Facebook发布内容.md)
- [Facebook发送私信](./docs/zh_cn/云手机API/自动化/Facebook/Facebook发送私信.md)
- [Facebook自动登录](./docs/zh_cn/云手机API/自动化/Facebook/Facebook自动登录.md)
- [Facebook自动评论](./docs/zh_cn/云手机API/自动化/Facebook/Facebook自动评论.md)

##### Instagram

- [Instagram AI养号](./docs/zh_cn/云手机API/自动化/Instagram/Instagram%20AI养号.md)
- [Instagram发布Reels图集](./docs/zh_cn/云手机API/自动化/Instagram/Instagram发布Reels图集.md)
- [Instagram发布Reels视频](./docs/zh_cn/云手机API/自动化/Instagram/Instagram发布Reels视频.md)
- [Instagram发送私信](./docs/zh_cn/云手机API/自动化/Instagram/Instagram发送私信.md)
- [Instagram编辑资料](./docs/zh_cn/云手机API/自动化/Instagram/Instagram编辑资料.md)
- [Instagram自动登录](./docs/zh_cn/云手机API/自动化/Instagram/Instagram自动登录.md)

##### YouTube

- [YouTube养号](./docs/zh_cn/云手机API/自动化/YouTube/YouTube养号.md)
- [YouTube发布Short](./docs/zh_cn/云手机API/自动化/YouTube/YouTube发布Short.md)
- [YouTube发布Video](./docs/zh_cn/云手机API/自动化/YouTube/YouTube发布Video.md)

##### X (Twitter)

- [X(Twitter)发布内容](./docs/zh_cn/云手机API/自动化/X(Twitter)/X(Twitter)发布内容.md)

##### Google

- [Google下载 app](./docs/zh_cn/云手机API/自动化/Google/Google下载%20app.md)
- [Google打开 app 浏览](./docs/zh_cn/云手机API/自动化/Google/Google打开%20app%20浏览.md)
- [Google自动登录](./docs/zh_cn/云手机API/自动化/Google/Google自动登录.md)

##### Pinterest

- [Pinterest 发布图文](./docs/zh_cn/云手机API/自动化/Pinterest/Pinterest%20发布图文.md)
- [Pinterest 发布视频](./docs/zh_cn/云手机API/自动化/Pinterest/Pinterest%20发布视频.md)

##### Reddit

- [Reddit AI养号](./docs/zh_cn/云手机API/自动化/Reddit/Reddit%20AI养号.md)
- [Reddit 发布图文](./docs/zh_cn/云手机API/自动化/Reddit/Reddit%20发布图文.md)
- [Reddit 发布视频](./docs/zh_cn/云手机API/自动化/Reddit/Reddit%20发布视频.md)

##### Threads

- [Threads 发布图文](./docs/zh_cn/云手机API/自动化/Threads/Threads%20发布图文.md)
- [Threads 发布视频](./docs/zh_cn/云手机API/自动化/Threads/Threads%20发布视频.md)

##### SHEIN

- [SHEIN自动登录](./docs/zh_cn/云手机API/自动化/Shein/SHEIN自动登录.md)

##### 其他任务

- [上传Keybox到云手机](./docs/zh_cn/云手机API/自动化/其他任务/上传Keybox到云手机.md)
- [多渠道分发视频](./docs/zh_cn/云手机API/自动化/其他任务/多渠道分发视频.md)
- [批量上传文件到云机](./docs/zh_cn/云手机API/自动化/其他任务/批量上传文件到云机.md)
- [批量导入联系人到云手机](./docs/zh_cn/云手机API/自动化/其他任务/批量导入联系人到云手机.md)

#### 文件管理

- [Keybox文件上传](./docs/zh_cn/云手机API/文件管理/Keybox文件上传.md)
- [Keybox文件上传结果](./docs/zh_cn/云手机API/文件管理/Keybox文件上传结果.md)
- [上传临时文件到GeeLark](./docs/zh_cn/云手机API/文件管理/上传临时文件到GeeLark.md)
- [上传文件到云手机](./docs/zh_cn/云手机API/文件管理/上传文件到云手机.md)
- [查询云手机上传文件状态](./docs/zh_cn/云手机API/文件管理/查询云手机上传文件状态.md)

#### 素材中心

- [上传文件到素材中心](./docs/zh_cn/云手机API/素材中心/上传文件到素材中心.md)
- [删除素材](./docs/zh_cn/云手机API/素材中心/删除素材.md)
- [删除素材标签](./docs/zh_cn/云手机API/素材中心/删除素材标签.md)
- [查询素材](./docs/zh_cn/云手机API/素材中心/查询素材.md)
- [查询素材标签](./docs/zh_cn/云手机API/素材中心/查询素材标签.md)
- [添加素材](./docs/zh_cn/云手机API/素材中心/添加素材.md)
- [添加素材标签](./docs/zh_cn/云手机API/素材中心/添加素材标签.md)
- [设置素材标签](./docs/zh_cn/云手机API/素材中心/设置素材标签.md)

#### Shell

- [执行shell命令](./docs/zh_cn/云手机API/Shell/执行shell命令.md)

#### 回调管理(Webhook)

- [使用指南](./docs/zh_cn/云手机API/回调管理(Webhook)/使用指南.md)
- [回调类型](./docs/zh_cn/云手机API/回调管理(Webhook)/回调类型.md)
- [获取回调URL](./docs/zh_cn/云手机API/回调管理(Webhook)/获取回调URL.md)
- [设置回调URL](./docs/zh_cn/云手机API/回调管理(Webhook)/设置回调URL.md)

#### OEM

- [OEM 自定义设置](./docs/zh_cn/云手机API/OEM/OEM%20自定义设置.md)

#### Xposed支持

- [卸载补丁](./docs/zh_cn/云手机API/Xposed支持/卸载补丁.md)
- [安装补丁](./docs/zh_cn/云手机API/Xposed支持/安装补丁.md)
- [查询补丁安装状态](./docs/zh_cn/云手机API/Xposed支持/查询补丁安装状态.md)
- [补丁sdk](./docs/zh_cn/云手机API/Xposed支持/补丁sdk.md)
- [补丁列表](./docs/zh_cn/云手机API/Xposed支持/补丁列表.md)

---

### 代理管理

- [代理检测](./docs/zh_cn/代理管理/代理检测.md)
- [修改代理](./docs/zh_cn/代理管理/修改代理.md)
- [删除代理](./docs/zh_cn/代理管理/删除代理.md)
- [查询代理](./docs/zh_cn/代理管理/查询代理.md)
- [添加代理](./docs/zh_cn/代理管理/添加代理.md)

---

### 分组管理

- [修改分组](./docs/zh_cn/分组管理/修改分组.md)
- [创建分组](./docs/zh_cn/分组管理/创建分组.md)
- [删除分组](./docs/zh_cn/分组管理/删除分组.md)
- [查询分组](./docs/zh_cn/分组管理/查询分组.md)

---

### 标签管理

- [修改标签](./docs/zh_cn/标签管理/修改标签.md)
- [创建标签](./docs/zh_cn/标签管理/创建标签.md)
- [删除标签](./docs/zh_cn/标签管理/删除标签.md)
- [查询标签](./docs/zh_cn/标签管理/查询标签.md)

---

### 支付

- [余额查询](./docs/zh_cn/支付/余额查询.md)
- [充值](./docs/zh_cn/支付/充值.md)
- [更换套餐](./docs/zh_cn/支付/更换套餐.md)
- [查询当前套餐信息](./docs/zh_cn/支付/查询当前套餐信息.md)
- [查询计费流水](./docs/zh_cn/支付/查询计费流水.md)
- [续期套餐](./docs/zh_cn/支付/续期套餐.md)
- [获取套餐列表](./docs/zh_cn/支付/获取套餐列表.md)

---

### 浏览器API

#### 浏览器管理

- [修改浏览器](./docs/zh_cn/浏览器API/浏览器管理/修改浏览器.md)
- [关闭浏览器](./docs/zh_cn/浏览器API/浏览器管理/关闭浏览器.md)
- [删除浏览器](./docs/zh_cn/浏览器API/浏览器管理/删除浏览器.md)
- [启动浏览器](./docs/zh_cn/浏览器API/浏览器管理/启动浏览器.md)
- [新建浏览器](./docs/zh_cn/浏览器API/浏览器管理/新建浏览器.md)
- [查询浏览器书签](./docs/zh_cn/浏览器API/浏览器管理/查询浏览器书签.md)
- [查询环境cookies](./docs/zh_cn/浏览器API/浏览器管理/查询环境cookies.md)
- [检查API接口状态](./docs/zh_cn/浏览器API/浏览器管理/检查API接口状态.md)
- [检查浏览器状态](./docs/zh_cn/浏览器API/浏览器管理/检查浏览器状态.md)
- [浏览器移动分组](./docs/zh_cn/浏览器API/浏览器管理/浏览器移动分组.md)
- [清除浏览器缓存](./docs/zh_cn/浏览器API/浏览器管理/清除浏览器缓存.md)
- [克隆浏览器](./docs/zh_cn/浏览器API/浏览器管理/克隆浏览器.md)
- [获取浏览器列表](./docs/zh_cn/浏览器API/浏览器管理/获取浏览器列表.md)
- [设置浏览器书签](./docs/zh_cn/浏览器API/浏览器管理/设置浏览器书签.md)
- [转让浏览器](./docs/zh_cn/浏览器API/浏览器管理/转让浏览器.md)

#### 自动化

##### 任务管理

- [取消任务](./docs/zh_cn/浏览器API/自动化/任务管理/取消任务.md)
- [查询任务](./docs/zh_cn/浏览器API/自动化/任务管理/查询任务.md)
- [查询任务详情](./docs/zh_cn/浏览器API/自动化/任务管理/查询任务详情.md)
- [重试任务](./docs/zh_cn/浏览器API/自动化/任务管理/重试任务.md)

##### 自定义任务

- [创建自定义任务](./docs/zh_cn/浏览器API/自动化/自定义任务/创建自定义任务.md)
- [自定义流程查询](./docs/zh_cn/浏览器API/自动化/自定义任务/自定义流程查询.md)

##### TikTok

- [TikTok 搜索视频、点赞评论](./docs/zh_cn/浏览器API/自动化/TikTok/TikTok%20搜索视频、点赞评论.md)
- [TikTok 点赞、评论视频](./docs/zh_cn/浏览器API/自动化/TikTok/TikTok%20点赞、评论视频.md)
- [TikTok 点赞指定视频](./docs/zh_cn/浏览器API/自动化/TikTok/TikTok%20点赞指定视频.md)

##### Facebook

- [Facebook 发布帖子](./docs/zh_cn/浏览器API/自动化/Facebook/Facebook%20发布帖子.md)
- [Facebook 添加推荐好友](./docs/zh_cn/浏览器API/自动化/Facebook/Facebook%20添加推荐好友.md)
- [Facebook 账号创建主页](./docs/zh_cn/浏览器API/自动化/Facebook/Facebook%20账号创建主页.md)
- [Facebook 首屏全部点赞](./docs/zh_cn/浏览器API/自动化/Facebook/Facebook%20首屏全部点赞.md)

##### Instagram

- [Instagram 搜索话题、浏览帖子](./docs/zh_cn/浏览器API/自动化/Instagram/Instagram%20搜索话题、浏览帖子.md)
- [浏览、点赞 Instagram 主页](./docs/zh_cn/浏览器API/自动化/Instagram/浏览、点赞%20Instagram%20主页.md)

##### X (Twitter)

- [X(Twitter) 推文点赞，转发](./docs/zh_cn/浏览器API/自动化/X(Twitter)/X(Twitter)%20推文点赞，转发.md)
- [X(Twitter) 转发推文，发布推文](./docs/zh_cn/浏览器API/自动化/X(Twitter)/X(Twitter)%20转发推文，发布推文.md)

##### YouTube

- [YouTube 观看视频](./docs/zh_cn/浏览器API/自动化/YouTube/YouTube%20观看视频.md)

##### Reddit

- [浏览、点赞 Reddit 关键词搜索帖子](./docs/zh_cn/浏览器API/自动化/Reddit/浏览、点赞%20Reddit%20关键词搜索帖子.md)

##### 其他任务

- [Cookie 机器人](./docs/zh_cn/浏览器API/自动化/其他任务/Cookie%20机器人.md)

---

### 代理检测

- [代理检测](./docs/zh_cn/代理检测/代理检测.md)

---

### 错误码

- [云手机错误码](./docs/zh_cn/错误码/云手机错误码.md)
- [浏览器错误码](./docs/zh_cn/错误码/浏览器错误码.md)

---

### 使用指南

#### 云手机

- [接口调用说明](./docs/zh_cn/使用指南/云手机/接口调用说明.md)
- [请求示例](./docs/zh_cn/使用指南/云手机/请求示例.md)
- [创建自动化任务](./docs/zh_cn/使用指南/云手机/创建自动化任务.md)

#### 浏览器

- [接口调用说明](./docs/zh_cn/使用指南/浏览器/接口调用说明.md)
- [请求示例](./docs/zh_cn/使用指南/浏览器/请求示例.md)

---

### 更新日志

- [更新日志](./docs/zh_cn/更新日志.md)
