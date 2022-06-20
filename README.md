# Mobile-Diagnostics-Research
 
 ------------
### Samsung / Android
------------
#### AT Commands (Hayes Command Set)
https://en.wikipedia.org/wiki/Hayes_command_set

##### Device Identification

"AT+DEVCONINFO" - Check Basic Information
"AT+REACTIVE=1,0,0" - Check Factory Reset Protection
"AT+SIZECHECK=?" - Check Storage Size
"AT+SVCIFPGM=1,4" - Check Network Lock
"AT+VERSNAME=3,2,3" - Check Android Version
"AT+BATGETLEVEL?" - Check Battery Information
"AT+IMEINUM" - Check IMEI Information
"AT+SWVER" - Check Software Information

##### Device Functions

"AT+SUDDLMOD=0,0" - Download Mode
"AT+FACTORST=0,0" - Factory Reset
"AT+CTSA=2,500,500" - Single Tap Screen
"AT+CTSA=3,500,500" - Double Tap Screen
"AT+CTSA=1,500,500;+CTSA=0,1000,1000" - Swipe Screen

#### ADB Commands (Android Debug Bridge)
https://developer.android.com/studio/command-line/adb

##### Device Identification

##### Device Functions
------------
### Samsung / Tizen
------------
#### SDB Commands (Smart Development Bridge)
https://developer.tizen.org/development/tizen-studio/web-tools/running-and-testing-your-app/sdb

##### Device Identification

##### Device Functions
------------
### Apple / iOS
------------
#### iMobileDevice Commands (libimobiledevice)
https://libimobiledevice.org

##### Device Identification

##### Device Functions
