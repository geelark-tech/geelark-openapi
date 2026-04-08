### 2026.04.08
#### Cloud Phone
- Creating and modifying cloud phone information supports setting proxy detection channels.
- Google's auto-sign-in task supports 2fa
- Added API for posting tasks to hide all TikTok videos
- Added API for posting tasks to hide all TikTok videos (Asia)
- Added API for posting tasks to delete all TikTok videos
- Added API for posting tasks to delete all TikTok videos (Asia)

#### Browser
- Browser API interfaces require token verification.
- Added API for Facebook posting tasks
- Added API for Twitter retweeting and posting tasks
- Added API for Cookie bot tasks
- Added API for YouTube video viewing tasks
- Added API for browsing and liking Instagram profile tasks
- Added API for TikTok video search, liking, and commenting tasks
- Added API for Instagram topic search and post browsing tasks
- Added API for browsing and liking Reddit keyword search posts tasks
- Added API for TikTok video likes and comments
- Added API for Facebook friend recommendation tasks
- Added API for TikTok video likes
- Added API for liking all Facebook profiles
- Added API for Twitter tweet likes and retweets
- Added API for Facebook profile creation tasks

#### Proxy Management
- Creating and modifying proxy supports setting proxy detection channels.

### 2026.04.07
#### Billing
- Added billing transaction detail interface

### 2026.04.03
#### Cloud Phone
- TikTok releases photo gallery task to support product settings

### 2026.03.30
#### Browser
- Create and update interfaces now support setting time zone, language, and resolution
- List interface now returns time zone, language, and resolution settings

#### Cloud Phone
- Added Import/Export custom task flow interfaces

### 2026.03.25
#### Cloud Phone
- Added Instagram edit profile task interface
- Added page parameter to Facebook Reels video publishing interface

#### Browser
- Added "resume last visit" parameter to browser creation and update interfaces
- Added "open specified URL" parameter to browser creation and update interfaces

### 2026.03.18
#### Cloud Phone
- Added US region for Android 15; set region parameter to 'us' when creating a new cloud phone via Create Cloud Phone / Create Cloud Phone V2

#### Browser
- Browser now supports 2FA secret keys
- Added set browser bookmarks interface
- Added get browser bookmarks interface

### 2026.03.11
#### Cloud Phone
- TikTok random like and TikTok AI random comment now support probability parameter
- Added create TikTok random follow task interface

#### Browser
- Added get browser task detail interface
- Added check browser status interface
- Added clear browser cache interface
- Added move browser group interface
- Added get environment cookies interface

### 2026.02.27
#### Other
- Added response parameter `availableMonthlyRentals` to get current subscription info interface

### 2026.02.25
#### Cloud Phone
- Added `fileName` parameter to add asset interface
- Added `ids` parameter to get assets interface

#### Other
- Added get current subscription info interface

### 2026.02.10
#### Cloud Phone
- Added post parameter to Instagram Reels album publishing interface

### 2026.02.06
#### Other
- Added get subscription list and change subscription interfaces

### 2026.02.04
#### Cloud Phone
- Android 14 now supports app keep-alive
- TikTok AI random comment now supports specified links

#### Browser
- Added browser task interface

### 2026.01.27
#### Cloud Phone
- Added request parameter `proxyIds` to get cloud phone list interface

### 2026.01.26
#### Cloud Phone
- Added response parameters `deviceName`, `netType`, `language`, `province`, `city` to get cloud phone list interface

### 2026.01.23
#### Cloud Phone
- Added parameter `energySavingMode` to start cloud phone interface

### 2026.01.21
#### Cloud Phone
- Added device name parameter to create cloud phone interface
- Instagram Reels video and album publishing interfaces now support AI tags
- Added set team app keep-alive and set team app auto-start interfaces
- Added app installation callback

### 2026.01.20
#### Cloud Phone
- Added batch import contacts to cloud phone interface

### 2026.01.19
#### Cloud Phone
- Added cloud phone [error code](https://open.geelark.cn/api/cloud-phone-error-codes) summary

### 2026.01.14
#### Cloud Phone
- Added move cloud phone group interface

### 2026.01.12
#### Cloud Phone
- Added `toolBarSettings` parameter to OEM custom settings

### 2026.01.08
#### Cloud Phone
- One-click new device interface now supports retaining phone number, region, language, and network type

### 2026.01.07
#### Cloud Phone
- Instagram Reels video publishing interface now supports "use same audio" URL and volume parameters
- Instagram Reels album publishing interface now supports "use same audio" URL parameter
- Added app hide accessibility service interface

### 2026.01.04
#### Cloud Phone
- Update cloud phone info interface now supports custom phone number
- Create cloud phone now supports custom language

### 2025.12.29
#### Cloud Phone
- Added `mirrorUrl` parameter to cloud phone custom settings

### 2025.12.25
#### Cloud Phone
- Create cloud phone now supports setting region

### 2025.12.24
#### Cloud Phone
- Power on/off callbacks now return username, IP, and event time
- Added `hideMirror` parameter to start cloud phone interface
- Start cloud phone interface now returns billing type
- Added device maintenance error codes to start cloud phone and create cloud phone V2 interfaces
- Added task creation and task completion callbacks
- Added update data assistant account interface

### 2025.12.19
#### Cloud Phone
- Added environment tag change callback
- Added batch app operations interface

### 2025.12.18
#### Cloud Phone
- Added environment name change and environment deletion callbacks

### 2025.12.16
#### Cloud Phone
- Added `openStatus` filter parameter to `/open/v1/phone/list`
- Added get team app list interface
- Added remove team app interface
- Added set team app auto-install interface
- Added set team app authorization interface
- Added set team app ROOT interface
- Create cloud phone now supports Proxyma, DECODO, NodeMaven, IPIDEAMobile, and kookeeyMobile proxies
- Batch query tasks interface now supports filtering by task ID
- Added `rpaStatus` to cloud phone list response

### 2025.12.15
#### Cloud Phone
- Added `hideLibrary` parameter to start cloud phone interface

### 2025.12.12
#### Cloud Phone
- Added `center` parameter to start cloud phone interface

### 2025.12.11
#### Cloud Phone
- Added common ADB commands documentation for cloud phone
- Send SMS to cloud phone interface now supports Android 14

### 2025.12.10
#### Browser
- Create and update browser interfaces now support passing startup parameters

### 2025.12.03
#### Cloud Phone
- Added `width` parameter to start cloud phone interface

### 2025.11.28
#### Cloud Phone
- Added data assistant account data retrieval interface

### 2025.11.26
#### Cloud Phone
- Added custom template task publishing failure to task failure reasons

### 2025.11.12
#### Cloud Phone
- Attachments can now be transferred when transferring environments
- Instagram AI account nurturing now supports configurable number of videos to browse and search keywords

### 2025.11.03
#### Other
- Added proxy detection interface

### 2025.10.29
#### Cloud Phone
- Added Threads video publishing task interface
- Added Threads post publishing task interface

### 2025.10.22
#### Cloud Phone
- Added `hideSideBar` and `displayTimer` parameters to start cloud phone interface
- Added shutdown callback for cloud phone
- Added get app list interface
- Added add app to team app interface

### 2025.10.21
#### Cloud Phone
- Added TikTok AI random comment (Asia) task interface
- ADB is now available for cloud phone Android 9

### 2025.10.16
#### Cloud Phone
- Create cloud phone now supports passing phone number
- Reddit account nurturing now supports passing search keywords

#### Browser
- Added browser interface documentation
- Added create browser interface
- Added update browser interface
- Added delete browser interface
- Added get browser interface
- Added start browser interface
- Added close browser interface
- Added transfer browser interface

### 2025.10.15
#### Cloud Phone
- Cloud phone list interface now returns monthly subscription expiration time

### 2025.08.26
#### Cloud Phone
- Cloud phone list now supports filtering by billing mode; added billing mode field to response
- Create TikTok add video/album/nurturing tasks now support adding notes

### 2025.08.20
#### Cloud Phone
- Create cloud phone now supports setting network type
- Added set cloud phone network type interface
- Added Pinterest video publishing interface
- Added Pinterest post publishing interface
- Added update cloud phone logo/brand name interface

### 2025.08.19
#### Cloud Phone
- Keybox upload interface

### 2025.07.24
#### Cloud Phone
- TikTok video and album publishing tasks can now retrieve share links
- Task query interface now returns share link
- Added Instagram auto-login interface

### 2025.07.21
#### Cloud Phone
- Uninstall app now supports uninstalling by package name

### 2025.07.14
#### Cloud Phone
- Added batch query tasks interface

### 2025.07.10
#### Cloud Phone
- TikTok video publishing task now supports setting cover image
- Added batch import contacts to cloud phone interface
- Added upload keybox to cloud phone interface
- Added TikTok random like (Asia) interface
- Added TikTok send direct message (Asia) interface
- Added Instagram Reels album publishing interface

### 2025.07.04
#### Cloud Phone
- YouTube Shorts publishing interface: "use same audio" URL is now optional

### 2025.07.01
#### Cloud Phone
- Proxy query interface now returns proxy sequence number
- Added create cloud phone V2 interface

### 2025.06.26
#### Cloud Phone
- Added Reddit AI account nurturing interface
- Added Reddit video publishing interface
- Added Reddit post publishing interface
- Added Google download app interface
- Added Google open app browse interface
- Added TikTok send direct message interface
- Added Facebook send direct message interface
- Added Instagram send direct message interface
- Added transfer cloud phone interface
- Added asset center related interfaces

### 2025.06.12
#### Cloud Phone
- Added error code for disallowed proxy type to create cloud phone interface
- Added error code for disallowed proxy type to update proxy interface
- Added error code for disallowed proxy type to update cloud phone info interface
- Added get task detail interface
- Added token authentication support

### 2025.05.29
#### Cloud Phone
- TikTok video and album publishing tasks now support marking AI-generated content

### 2025.05.15
#### Cloud Phone
- TikTok add video/album/nurturing task interfaces no longer have time interval restrictions
- Environment group notes now support up to 500 characters
- Create cloud phone interface now returns cloud phone device information

### 2025.04.25
#### Cloud Phone
- Get cloud phone list now supports querying by ID and returns proxy information

### 2025.04.24
#### Cloud Phone
- TikTok video and album publishing now support setting volume
- Added task workflow query interface
- Added create custom task interface
- Added Instagram AI account nurturing interface

### 2025.04.10
#### Cloud Phone
- Added "in use" error code to delete cloud phone interface
- Task query interface now returns duration field

### 2025.04.09
#### Cloud Phone
- For TikTok add video/album/nurturing tasks, if the scheduled time is earlier than the current time, the current time will be used.

### 2025.04.07
#### Cloud Phone
- Modified TikTok account nurturing task parameters

### 2025.04.01
#### Cloud Phone
- Added create X (Twitter) post and batch upload files to cloud phone task interfaces

### 2025.03.25
#### Cloud Phone
- ADB now supports Android 14

### 2025.03.24
#### Cloud Phone
- Added new field `changeBrandModel` to one-click new device V2 interface to control whether to randomize cloud phone brand and model

### 2025.03.20
#### Cloud Phone
- Added automation module, including automation tasks for multiple platforms

### 2025.03.13
#### Cloud Phone
- Added get cloud phone brand list interface
- Create cloud phone interface now supports passing brand and model

### 2025.03.06
#### Cloud Phone
- Running tasks can now be canceled
- When adding tasks, the scheduled time interval for the same cloud phone cannot be less than 10 minutes
- Video and album publishing tasks now support specifying retry count and timeout
- Execute shell and create cloud phone now support Android 14

### 2025.02.28
#### Cloud Phone
- Added album title field to TikTok automation add task for album publishing

### 2025.02.12
#### Other
- Added payment-related interfaces

### 2025.02.10
#### Cloud Phone
- Get cloud phone list now returns device information fields: brand, model

### 2025.02.07
#### Cloud Phone
- Added interface: send SMS to cloud phone

### 2025.01.14
#### Cloud Phone
- Added video publishing task parameter fields to TikTok automation add task interface

### 2024.12.25
#### Cloud Phone
- Launched get cloud phone device ID interface

### 2024.12.19
#### Cloud Phone
- Launched set ROOT status interface

### 2024.11.25
#### Cloud Phone
- Launched screenshot-related interfaces

### 2024.11.21
#### Cloud Phone
- Get cloud phone list now returns cloud phone device information fields

### 2024.10.28
#### Cloud Phone
- Launched download file to cloud phone interface
- Launched one-click new device V2 interface; the original one-click new device interface will no longer rely on callbacks

### 2024.10.09
#### Cloud Phone
- Launched file upload related interfaces
- Added video publishing task parameter fields to TikTok automation add task interface
- Fixed ADB get ADB information retrieval issue

### 2024.09.25
#### Cloud Phone
- Launched one-click new device related interfaces

### 2024.08.28
#### Cloud Phone
- Launched tag related interfaces
- Launched set/get cloud phone GPS interfaces
- Launched group related interfaces

### 2024.08.13
#### Cloud Phone
- Launched app management related interfaces

### 2024.08.09
#### Cloud Phone
- Launched ADB related interfaces

### 2024.06.04
#### Cloud Phone
- API interfaces launched