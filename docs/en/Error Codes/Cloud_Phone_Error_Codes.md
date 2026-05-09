Global
------
```
0 Success
40000 Unknown error
40001 Failed to read request body
40002 traceId is empty
40003 Signature verification failed
40004 Parameter validation failed
40005 Resource not found
40006 Partial success for batch operation
40009 Batch operation failed completely
40007 Request rate limited
40008 pageSize exceeds maximum/minimum limit
40010 Resource is occupied and cannot be deleted
40011 Available to paid users only
40012 API is deprecated, please use the latest version
40013 User not found
40014 API request exceeds hourly limit; locked for two hours
40015 Insufficient permissions
40016 The IP address is not within the whitelist
40017 Too many requests, please try again later
50000 Internal server error
```

* * *

Cloud Phone
-----------
```
42001 Cloud phone not found
43002 User is not on a Pro plan and cannot perform this operation
43004 Cloud phone has expired
43005 Cloud phone is executing a task; delete/refresh operations are not allowed
43006 Cloud phone is under remote control; delete/refresh operations are not allowed
43009 Cloud phone has already been opened; delete/refresh operations are not allowed
43010 Cloud phone is starting; delete/refresh operations are not allowed
43021 Cloud phone is in use; delete/refresh operations are not allowed
43008 Daily cloud phone open limit reached (UTC timezone)
43011 Cloud phone is performing a one-click new machine and cannot be operated
43012 Cloud phone GPS information error
43013 Cloud phone plugin installation task does not exist
43014 GPS is not set
43015 Cloud phone does not support one-click refresh
43016 Cloud phone does not support root temporarily
43017 No monthly subscription device available
43018 Cloud phone is not bound to a monthly subscription device
43019 Only monthly subscription type is supported
43020 Cloud phone backup data exception
43022 Cannot transfer profile to yourself
43023 Profile name is empty
43024 Brand and model do not match
43025 Language not supported
43026 System not supported
43027 Browser does not support transfer
43028 Sub-user profile group limitation
43029 Selected cloud phone model is under maintenance, please try again later
43036 Cloud phone is running and cannot perform this operation
43037 Accessibility hiding is not supported
43038 The device model has been deleted
43039 Currently unavailable; maintenance in progress
49001 ADB is not enabled
49002 Device model does not support ADB
50001 Device model does not support shell
52001 Device model does not support sending SMS
53001 Device model does not support installing patches
```

* * *

App
---
```
42002 Cloud phone is not in running state
42003 The specified app is being installed
42004 Installing a lower app version is not allowed
42005 The specified app is not installed
42006 The specified app does not exist
42007 Upload task not found
```

* * *

Tags
----
```
43020 Tag name is empty
43021 Tag already exists
43022 Tag does not exist
43023 Tag color does not exist
43024 Tag name does not exist

```

* * *

Groups
------
```
43030 Group name is empty
43031 Group already exists
43032 Group does not exist
43033 Group name does not exist
43034 Group remark does not exist
43035 Ungrouped items cannot be edited
```

* * *

Create Cloud Phone
------------------
```
44001 Pro plan limitation
44002 Profiles count has reached the plan limit
44003 User profiles count has reached the limit
44004 Daily profiles creation limit reached
44005 Group is not specified
44006 Cloud phone inventory is insufficient
```

* * *

Proxy
-----
```
43001 Related profiles exist; deletion is not allowed
45001 Proxy does not exist
45002 Proxy is unavailable
45003 Proxy is not supported (proxy server IP or Outbound IP is located in mainland China)
45004 Proxy validation failed
45005 Region not supported
45006 Invalid proxy information
45007 Duplicate proxy
45008 Proxy type not supported

```

* * *

Plan
----
```
46001 Plan has expired
46002 Team profiles count exceeds plan limit
46003 Owned profiles count exceeds plan limit

```

* * *

Device
------
```
47001 Device concurrency limit reached
47002 All devices are in use
47003 Related device has expired
47004 Related device does not exist

```

* * *

Task
----
```
42008 Invalid app version; only specified app versions are allowed for task creation
48000 Task retry limit exceeded; further retries are not allowed
48001 Task status is already success or failure; further operations are not allowed
48002 Task does not exist
48003 Task material has expired
48004 TikTok task requires a specific app version; only specified versions are allowed
41000 Insufficient task points
41001 Insufficient balance

```

* * *

Material Center
---------------
```
60001 Material library capacity exceeded
60002 Duplicate tag name
60003 Invalid URL
60004 File format not supported
60005 Material does not exist

```

* * *

Others
------

```
51001 User callback does not exist
```

* * *

Task failure error code
------

```
20002 The machine is performing other tasks
20003 Execution timeout. Please view the publication on TikTok.
20005 Task canceled
20006 The same task was canceled
20007 Unsupported task type
20008 Failed because the APP language was modified. You need to change the APP language to English and run it again.
20100 No network connection
20101 Agent parameter error
20102 Failed to set modification parameters
20103 Failed to restart device
20104 After successful login, an error occurs when saving login information to the service.
20105 Installation of tiktok failed
20106 Failed to install 163 mailbox
20107 Unable to load video
20108 No network connection
20109 Setting proxy via interface failed
20110 Failed to obtain proxy ip
20111 Installation of auxiliary apk failed
20112 Failed to start secondary apk
20113 The IP address is the same before and after setting the proxy
20114 The node_addr field is parsed into an entity class error
20115 Check login failure
20116 The account is not logged in
20117 No email account and password
20118 Failed to obtain IP before setting proxy
20119 Failed to bind NetService
20120 Failed to obtain tiktok cookie
20121 Failed to obtain tiktokInfo
20122 Failed to start tiktok
20123 Failed to obtain geoip
20124 The waiting time to enter the homepage is too long
20125 Login failed, too many attempts
20126 Login failed, email not found
20127 Login failed when switching to email username
20128 Login failure
20129 Device offline
20130 Account password is wrong
20131 Too many attempts
20132 Login loading time exceeds 2 minutes
20133 Slider loading time is too long
20134 No network when verifying slider
20135 Failed to obtain tiktok UserName
20136 Account blocked
20137 The account has been blocked and you can appeal.
20138 The circular verification code slider takes too long to load
20139 Circle slider validation failed
20140 Slider verification fails to obtain screenshots
20141 There is no network during circular verification
20142 Graphic validation failed
20143 Maximum number of attempts reached
20144 Incorrect account or password
20145 Your account has repeatedly violated community guidelines
20200 Failed to download file, please check the network or try again later
20201 Failed to upload video, please check whether the network is smooth or try again later
20202 Failed to upload the video. It has been 0% for five minutes. Please check the network or try again later.
20203 Failed to upload video, failed for 15 minutes, please check the network or try again later
20204 Video upload was rejected
20205 Failed to click the capture button on the main page
20206 Failed to upload when clicking on the album page
20207 Album file type click failed
20208 Failed to download the video file. The specified download file was not found. Please check the network or try again later.
20209 Failed to select video
20210 Album next step failed
20211 Next step of preview page failed
20212 Preview completed and click Next failed.
20213 Clicking Publish on the publish page fails
20214 Clicking Publish Now failed
20215 Preview completed and waiting for video processing failed
20216 Failed to push stream to camera
20217 Recording video from camera failed
20218 Green screen filter not found
20219 Failed to switch rear camera
20220 Download video file connection is empty
20221 Couldn't decode. select anther video
20222 Video sound is not available
20223 Can't select Stickers
20224 Stickers list not found
20225 Stickers list failed to load
20226 Failed to download MENTION stickers
20227 MENTION sticker input box not found
20228 Publish video@user list failed to load
20229 The specified user was not found
20230 Handle video timeout
20231 Add link control not found
20232 Add product control not found
20233 Failed to enter product page
20234 Product not found
20235 Modify product name control not found
20236 Failed to add product
20237 Product sold out
20238 Video source is not set for push streaming
20239 Audio source is not set for push streaming
20240 Camera recording video waiting timeout
20241 Product unavailable
20242 Failed to jump to video details
20243 Failed to click the Use Music button
20244 Video music removed
20245 Timeout waiting for video to load
20246 Video ID does not exist
20247 Failed to switch seconds
20248 Search button not found
20249 Product URL input box not found
20250 Add product button not found
20251 Video publishing failed, saved to drafts
20252 Background music infringement
20253 Background music is muted causing failure
20254 Failed to set default audience
20255 Your account is permanently restricted from selling products
20256 Failed to enter product title editing page
20257 Video upload timed out
20258 Element not found
20259 Mention user not found
20260 Mention user button not found
20261 User search not found
20262 When entering the product page, it prompts that there is no network connection.
20263 Product name contains inappropriate words
20264 Account temporarily restricted
20265 Shooting the same video had special effects, causing the mission to fail.
20266 Failed to add product name, please check whether the product name is compliant
20300 Registration slider verification failed
20301 Registration circular verification failed to obtain screenshots
20302 Failed to enter email verification code
20303 The email verification code was not found within the specified time.
20304 Failed to register account and create new password
20305 Failed to jump to homepage via email
20306 No clickable registration button found
20307 Date of birth is illegal or failed to obtain
20308 Registration failed by clicking on the email address
20309 Failed to enter email
20310 The next step after clicking to enter the email address fails.
20311 The next step after clicking Create Password fails.
20312 Verification countdown not found
20313 Resend verification code not found
20314 Failed to start mailbox app
20315 Verification code sent too many times
20316 Skip creation of username failed
20317 TikTok prompts you to try too many times when registering
20318 Email login failed
20319 Email login failed, account locked
20320 Email login failed, account password is wrong
20321 Email login failed
20322 Login password control not found
20323 Waiting too long after entering the verification code
20324 Account or password incorrect
20325 Fail to register
20326 Account has been registered
20327 Waiting too long after entering the verification code
20328 An error message appears after entering the password
20329 Email verification is required but currently only supports 163 email addresses
20330 Email is registered
20331 Birthday next step failed
20332 Determine the registration entrance failed
20333 Circular verification code processing exception
20334 Email verification required
20335 An exception occurred during registration
20336 Email verification code execution failed
20337 The email verification code has expired or timed out
20338 The input box control for filling in the email verification code was not found.
20339 The email verification code decoding interface returns an invalid verification code.
20340 Interests selection failed
20401 Failed to jump to me
20402 Failed to click to edit information
20403 Unable to edit data
20501 Failed to jump to user page
20502 There is no network when jumping to the user page
20503 The specified user could not be found
20504 An exception occurred when jumping to the user page
20505 Fan list page failed to load
20506 Fan list page loading timeout
20507 Fan list loading timeout
20508 Failed to load more fans list
20601 Failed to click window option
20602 Failed to jump to showcase page
20603 Failed to jump to add product page
20604 Failed to enter product URL page
20605 Failed to enter product URL
20606 Failed to add product
20607 This account does not have a shopping cart
20700 Unsupported type
20701 Failed to open developer tools
20702 TikTok Shop button does not exist
20703 Failed to enter TikTok Shop
20704 Failed to open shopping cart
20705 Failed to enter the invitation page
20706 Agree to invitation page exception
20707 Failed to click to agree to the invitation
20708 Invitation failed
20709 Failed to enter revenue page
20710 Authorization revenue page exception
20711 Authorization revenue failed
20712 Access data authorization failed
20713 Data authorization failed
20714 Failed to detect shopping cart permissions
20715 Click Account Settings Failed
20801 @ button not found
20802 List element not found
20803 No users mentioned were found
20804 Edit input box not found
20901 No delete button found
21001 Top button not found
20267 Custom error codes
29992 Environment startup failed, please try clearing the cache.
29993 System error, please restart the cloud phone and try again.
29994 Network unstable, please try again later.
29995 Currently unavailable; maintenance in progress
29996 Proxy detection failed
29997 Insufficient balance
29998 The cloud phone has been deleted
29999 Unknown error
```