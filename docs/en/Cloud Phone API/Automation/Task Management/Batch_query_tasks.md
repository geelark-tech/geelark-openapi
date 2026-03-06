## API Description

Query all tasks scheduled within the past 7 days.

## Request URL

* `https://openapi.geelark.com/open/v1/task/historyRecords`

## Request Method

* POST

## Request Parameters

### Query Parameters (Ignore if empty)

| Parameter   | Required | Type   | Description                       | Example               |
| --- | --- | --- | --- | --- |
| size         | No       | int     | Number of records per page, maximum is 100 | 100                   |
| lastId       | No       | string | The `id` of the last item from the previous page’s `data.items` array | "574376043897425896" |
| ids | No | array[string] | Task IDs, maximum 100 | ["574376043897425896"] |

## Request Example

```json
{
 "size": 10,
 "lastId": "574376043897425896"
}
```

## Response Data Description

| Parameter Name | Type | Description |
| --- | --- | --- |
| total | integer | Total number of tasks |
| items | array\[Task\] | Array of tasks |

### Task

| Parameter Name | Type | Description |
| --- | --- | --- |
| id | string | Task ID |
| planName | string | Task plan name |
| taskType | integer | Task type&lt;br&gt;1 TikTok video posting&lt;br&gt;2 TikTok AI account warmup&lt;br&gt;3 TikTok carousel posting&lt;br&gt;4 TikTok account login&lt;br&gt;6 TikTok profile editing&lt;br&gt;42 Custom(Including Facebook, YouTube and other platforms) |
| serialName | string | Cloud phone name |
| envId | string | Cloud phone ID |
| scheduleAt | integer | Scheduled time, timestamp in seconds |
| status | integer | Task status&lt;br&gt;1 Waiting&lt;br&gt;2 In progress&lt;br&gt;3 Completed&lt;br&gt;4 Failed&lt;br&gt;7 Cancelled |
| failCode | integer | Failure code, refer to task failure codes and reasons |
| failDesc | string | Failure reason, refer to task failure codes and reasons |
| cost | integer | The time a task takes to complete or fail (in seconds)|

### Task Failure Codes and Reasons

| Failure Code | Failure Reason |
| - | - |
| 20002 | The machine is performing other tasks |
| 20003 | Execution timeout. Please view the publication on TikTok. |
| 20005 | Task canceled |
| 20006 | The same task was canceled |
| 20007 | Unsupported task type |
| 20008 | Failed because the APP language was modified. You need to change the APP language to English and run it again. |
| 20100 | No network connection |
| 20101 | Agent parameter error |
| 20102 | Failed to set modification parameters |
| 20103 | Failed to restart device |
| 20104 | After successful login, an error occurs when saving login information to the service. |
| 20105 | Installation of tiktok failed |
| 20106 | Failed to install 163 mailbox |
| 20107 | Unable to load video |
| 20108 | No network connection |
| 20109 | Setting proxy via interface failed |
| 20110 | Failed to obtain proxy ip |
| 20111 | Installation of auxiliary apk failed |
| 20112 | Failed to start secondary apk |
| 20113 | The IP address is the same before and after setting the proxy |
| 20114 | The node_addr field is parsed into an entity class error |
| 20115 | Check login failure |
| 20116 | The account is not logged in |
| 20117 | No email account and password |
| 20118 | Failed to obtain IP before setting proxy |
| 20119 | Failed to bind NetService |
| 20120 | Failed to obtain tiktok cookie |
| 20121 | Failed to obtain tiktokInfo |
| 20122 | Failed to start tiktok |
| 20123 | Failed to obtain geoip |
| 20124 | The waiting time to enter the homepage is too long |
| 20125 | Login failed, too many attempts |
| 20126 | Login failed, email not found |
| 20127 | Login failed when switching to email username |
| 20128 | Login failure |
| 20129 | Device offline |
| 20130 | Account password is wrong |
| 20131 | Too many attempts |
| 20132 | Login loading time exceeds 2 minutes |
| 20133 | Slider loading time is too long |
| 20134 | No network when verifying slider |
| 20135 | Failed to obtain tiktok UserName |
| 20136 | Account blocked |
| 20137 | The account has been blocked and you can appeal. |
| 20138 | The circular verification code slider takes too long to load |
| 20139 | Circle slider validation failed |
| 20140 | Slider verification fails to obtain screenshots |
| 20141 | There is no network during circular verification |
| 20142 | Graphic validation failed |
| 20143 | Maximum number of attempts reached |
| 20144 | Incorrect account or password |
| 20145 | Your account has repeatedly violated community guidelines |
| 20200 | Failed to download file, please check the network or try again later |
| 20201 | Failed to upload video, please check whether the network is smooth or try again later |
| 20202 | Failed to upload the video. It has been 0% for five minutes. Please check the network or try again later. |
| 20203 | Failed to upload video, failed for 15 minutes, please check the network or try again later |
| 20204 | Video upload was rejected |
| 20205 | Failed to click the capture button on the main page |
| 20206 | Failed to upload when clicking on the album page |
| 20207 | Album file type click failed |
| 20208 | Failed to download the video file. The specified download file was not found. Please check the network or try again later. |
| 20209 | Failed to select video |
| 20210 | Album next step failed |
| 20211 | Next step of preview page failed |
| 20212 | Preview completed and click Next failed. |
| 20213 | Clicking Publish on the publish page fails |
| 20214 | Clicking Publish Now failed |
| 20215 | Preview completed and waiting for video processing failed |
| 20216 | Failed to push stream to camera |
| 20217 | Recording video from camera failed |
| 20218 | Green screen filter not found |
| 20219 | Failed to switch rear camera |
| 20220 | Download video file connection is empty |
| 20221 | Couldn&#039;t decode. select anther video |
| 20222 | Video sound is not available |
| 20223 | Can&#039;t select Stickers |
| 20224 | Stickers list not found |
| 20225 | Stickers list failed to load |
| 20226 | Failed to download MENTION stickers |
| 20227 | MENTION sticker input box not found |
| 20228 | Publish video@user list failed to load |
| 20229 | The specified user was not found |
| 20230 | Handle video timeout |
| 20231 | Add link control not found |
| 20232 | Add product control not found |
| 20233 | Failed to enter product page |
| 20234 | Product not found |
| 20235 | Modify product name control not found |
| 20236 | Failed to add product |
| 20237 | Product sold out |
| 20238 | Video source is not set for push streaming |
| 20239 | Audio source is not set for push streaming |
| 20240 | Camera recording video waiting timeout |
| 20241 | Product unavailable |
| 20242 | Failed to jump to video details |
| 20243 | Failed to click the Use Music button |
| 20244 | Video music removed |
| 20245 | Timeout waiting for video to load |
| 20246 | Video ID does not exist |
| 20247 | Failed to switch seconds |
| 20248 | Search button not found |
| 20249 | Product URL input box not found |
| 20250 | Add product button not found |
| 20251 | Video publishing failed, saved to drafts |
| 20252 | Background music infringement |
| 20253 | Background music is muted causing failure |
| 20254 | Failed to set default audience |
| 20255 | Your account is permanently restricted from selling products |
| 20256 | Failed to enter product title editing page |
| 20257 | Video upload timed out |
| 20258 | Element not found |
| 20259 | Mention user not found |
| 20260 | Mention user button not found |
| 20261 | User search not found |
| 20262 | When entering the product page, it prompts that there is no network connection. |
| 20263 | Product name contains inappropriate words |
| 20264 | Account temporarily restricted |
| 20265 | Shooting the same video had special effects, causing the mission to fail. |
| 20266 | Failed to add product name, please check whether the product name is compliant |
| 20300 | Registration slider verification failed |
| 20301 | Registration circular verification failed to obtain screenshots |
| 20302 | Failed to enter email verification code |
| 20303 | The email verification code was not found within the specified time. |
| 20304 | Failed to register account and create new password |
| 20305 | Failed to jump to homepage via email |
| 20306 | No clickable registration button found |
| 20307 | Date of birth is illegal or failed to obtain |
| 20308 | Registration failed by clicking on the email address |
| 20309 | Failed to enter email |
| 20310 | The next step after clicking to enter the email address fails. |
| 20311 | The next step after clicking Create Password fails. |
| 20312 | Verification countdown not found |
| 20313 | Resend verification code not found |
| 20314 | Failed to start mailbox app |
| 20315 | Verification code sent too many times |
| 20316 | Skip creation of username failed |
| 20317 | TikTok prompts you to try too many times when registering |
| 20318 | Email login failed |
| 20319 | Email login failed, account locked |
| 20320 | Email login failed, account password is wrong |
| 20321 | Email login failed |
| 20322 | Login password control not found |
| 20323 | Waiting too long after entering the verification code |
| 20324 | Account or password incorrect |
| 20325 | Fail to register |
| 20326 | Account has been registered |
| 20327 | Waiting too long after entering the verification code |
| 20328 | An error message appears after entering the password |
| 20329 | Email verification is required but currently only supports 163 email addresses |
| 20330 | Email is registered |
| 20331 | Birthday next step failed |
| 20332 | Determine the registration entrance failed |
| 20333 | Circular verification code processing exception |
| 20334 | Email verification required |
| 20335 | An exception occurred during registration |
| 20336 | Email verification code execution failed |
| 20337 | The email verification code has expired or timed out |
| 20338 | The input box control for filling in the email verification code was not found. |
| 20339 | The email verification code decoding interface returns an invalid verification code. |
| 20340 | Interests selection failed |
| 20401 | Failed to jump to me |
| 20402 | Failed to click to edit information |
| 20403 | Unable to edit data |
| 20501 | Failed to jump to user page |
| 20502 | There is no network when jumping to the user page |
| 20503 | The specified user could not be found |
| 20504 | An exception occurred when jumping to the user page |
| 20505 | Fan list page failed to load |
| 20506 | Fan list page loading timeout |
| 20507 | Fan list loading timeout |
| 20508 | Failed to load more fans list |
| 20601 | Failed to click window option |
| 20602 | Failed to jump to showcase page |
| 20603 | Failed to jump to add product page |
| 20604 | Failed to enter product URL page |
| 20605 | Failed to enter product URL |
| 20606 | Failed to add product |
| 20607 | This account does not have a shopping cart |
| 20700 | Unsupported type |
| 20701 | Failed to open developer tools |
| 20702 | TikTok Shop button does not exist |
| 20703 | Failed to enter TikTok Shop |
| 20704 | Failed to open shopping cart |
| 20705 | Failed to enter the invitation page |
| 20706 | Agree to invitation page exception |
| 20707 | Failed to click to agree to the invitation |
| 20708 | Invitation failed |
| 20709 | Failed to enter revenue page |
| 20710 | Authorization revenue page exception |
| 20711 | Authorization revenue failed |
| 20712 | Access data authorization failed |
| 20713 | Data authorization failed |
| 20714 | Failed to detect shopping cart permissions |
| 20715 | Click Account Settings Failed |
| 20801 | @ button not found |
| 20802 | List element not found |
| 20803 | No users mentioned were found |
| 20804 | Edit input box not found |
| 20901 | No delete button found |
| 21001 | Top button not found |
| 20267 | Custom template task publishing failed |
| 29997 | Insufficient balance |
| 29998 | The cloud phone has been deleted |
| 29999 | Unknown error |

## Response Example

```json
{
    "traceId": "123456ABCDEF",
    "code": 0,
    "msg": "success",
    "data": {
        "total": 1,
        "items": [
            {
                "id": "123456ABCDEF",
                "planName": "plan123456ABCDEF",
                "taskType": 2,
                "serialName": "test",
                "envId": "123456654321",
                "scheduleAt": 1718744459,
                "status": 3
            }
        ]
    }
}
```

Error Codes
-----------

For error codes, please refer to  [Cloud Phone Error Codes](https://open.geelark.com/api/cloud-phone-error-codes)


