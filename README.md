# Mobile-Diagnostics-Research

## Samsung / Android
### AT Commands (Hayes Command Set)
https://en.wikipedia.org/wiki/Hayes_command_set

UPDATE 7/19/23
There is a program floating around that I made called Bellatrix that will automate this for you. Search for it on github and you will find someone who grabbed it before I removed it. There are current combinations that work with newer phones (the newest models at the time of writing this). Thats all the help I can give you.

#### Device Identification

- **Check Basic Information**  
"AT+DEVCONINFO"  
- **Check Factory Reset Protection**  
"AT+REACTIVE=1,0,0"  
- **Check Storage Size**  
"AT+SIZECHECK=?"  
- **Check Network Lock**  
"AT+SVCIFPGM=1,4"  
- **Check Android Version**  
"AT+VERSNAME=3,2,3"  
- **Check Battery Information**  
"AT+BATGETLEVEL?"  
- **Check IMEI Information**  
"AT+IMEINUM"  
- **Check Software Information**  
"AT+SWVER"  

#### Device Functions

- **Download Mode**  
"AT+SUDDLMOD=0,0"  
- **Factory Reset**  
"AT+FACTORST=0,0"  
- **Single Tap Screen**  
"AT+CTSA=2,500,500"  
- **Double Tap Screen**  
"AT+CTSA=3,500,500"  
- **Swipe Screen**  
"AT+CTSA=1,500,500;+CTSA=0,1000,1000"   
- **Enable Dialer Codes**  
"AT+SYSSCOPE=1,0"  
"AT+SWATD=0"  
"AT+ACTIVATE=0,0,0"  
"AT+SWATD=1"  
"AT+KSTRINGB=0,3"  
- **Enable ADB**  
!*Must type \*#0\*# on dialer and enter test mode*!  
!*"AT+DUMPCTRL=1,0" must be used before "AT+SWATD=0" on older models*!  
"AT+SYSSCOPE=1,0"  
"AT+SWATD=0"  
"AT+ACTIVATE=0,0,0"  
"AT+SWATD=1"  
"AT+DEBUGLVC=0,5"  

#### Touch Scripts

- **SM-G781 | SM-G981**  
**Android 10/11/12 Open Dialer & Accept ADB**  
"AT+CTSA=2,100,2300" (Open Dialer)  
or "AT+CTSA=2,600,2100" For Android 11/12 Dialer  
"AT+CTSA=2,100,1825" (\*)  
"AT+CTSA=2,750,1825" (\#)    
"AT+CTSA=2,600,1825" (0)    
"AT+CTSA=2,100,1825" (\*)    
"AT+CTSA=2,750,1825" (\#)  
"AT+CTSA=2,600,2100" (Accept ADB Prompt)  

- **SM-G950**  
**Android 8/9 Open Dialer & Accept ADB**  
"AT+CTSA=2,600,2100" (Open Dialer)  
or "AT+CTSA=2,300,2100" For Android 9 Dialer  
"AT+CTSA=2,300,1700" (\*)  
"AT+CTSA=2,750,1700" (\#)    
"AT+CTSA=2,500,1700" (0)    
"AT+CTSA=2,300,1700" (\*)    
"AT+CTSA=2,750,1700" (\#)  
"AT+CTSA=2,900,1450" (Accept ADB Prompt)  
or "AT+CTSA=2,750,1300" For Android 9 Accept ADB  

- **SM-G970 | SM-G973 | SM-G975**  
**Android 9/10/11 Open Dialer & Accept ADB**  
"AT+CTSA=2,100,2100" (Open Dialer)  
or "AT+CTSA=2,600,1900" For Android 11 Dialer  
"AT+CTSA=2,300,1800" (\*)  
"AT+CTSA=2,900,1800" (\#)    
"AT+CTSA=2,600,1800" (0)    
"AT+CTSA=2,300,1800" (\*)    
"AT+CTSA=2,900,1800" (\#)  
"AT+CTSA=2,900,2000" (Accept ADB Prompt)  

### ADB Commands (Android Debug Bridge)  
https://developer.android.com/studio/command-line/adb

#### Device Identification

- **Check Serial Number**  
"get-serialno"  

#### Device Functions

- **Reboot**  
"reboot"  
- **Recovery Mode**  
"reboot-recovery"  
- **Remove Factory Reset Protection**  
"shell content insert --uri content://settings/secure --bind name:s:user_setup_complete --bind value:s:1"  

## Samsung / Tizen  
### SDB Commands (Smart Development Bridge)  
https://developer.tizen.org/development/tizen-studio/web-tools/running-and-testing-your-app/sdb

#### Device Identification

- **Check Serial Number**  
"shell cat /csa/imei/serialno.dat"  
- **Check Model Number**  
"shell cat /csa/imei/prodcode.dat"  
- **Check Carrier**  
"shell cat /csa/csc/csc-active-customer.inf"  
- **Check Maximum Capacity**  
"shell cat /sys/class/power_supply/battery/batt_capacity_max"  
- **Check Current Capacity**  
"shell cat /sys/class/power_supply/battery/batt_capacity"  

#### Device Functions

## Apple / iOS  
### iMobileDevice Commands (libimobiledevice)
https://libimobiledevice.org

#### Device Identification

- **Check IMEI (Using ideviceinfo)**  
"-k InternationalMobileEquipmentIdentity"  
- **Check Serial Number (Using ideviceinfo)**  
"-k SerialNumber"  
- **Check Model Number (Using ideviceinfo)**  
"-k ModelNumber"  
- **Check Firmware (Using ideviceinfo)**  
"-k ProductVersion"  
- **Check Factory Reset Protection (Using ideviceactivation)**  
"activate"  
- **Check Mobile Device Management Lock (Using ideviceinfo)**  
"-q com.apple.mobile.chaperone -k DeviceIsChaperoned" 

#### Device Functions
