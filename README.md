# LILIN-LPR-Camera-SDK

## Overview
This document, LILIN IP camera automatic number plate recognition (LPR) protocol SDK, specifies the integrations of using number plate database of LILIN IP camera. 

## GET LPR EVENT LIST <BR>
### Get all LPR log list <BR>

Get all detected number plates including denial, allowed, and visitor lists. <BR>
  
Syntax:
http://<serverIP>/get_search_info?list=log

Return: 
  
{"LPR_COUNT": 47,"INFORMATION": [{"INDEX":1,"TS":"1523329437899288","MOD_TS":"2018-04-10 03:03:57 GMT","CAR_ID":"44","LPR":"30U9874","RTIME":"1038.0","ACTION":"0","ACT_PARAM":"denial","THRESHOLD":"0.795461475849152","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"1167","LP_Y":"120","LP_W":"612","LP_H":"108",
"LP_BMP":"images/20180410030357_899297lp_30U9874_1685.png","ROI_BMP":"","COUNTRY":"TUR","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""},

{"INDEX":2,"TS":"1523329162878730","MOD_TS":"2018-04-10 02:59:22 GMT","CAR_ID":"43","LPR":"7336GN","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"allowed","THRESHOLD":"0.74889463186264","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"693","LP_Y":"303","LP_W":"264","LP_H":"51",
"LP_BMP":"images/20180410025922_878744lp_7336GN_1238.png","ROI_BMP":"","COUNTRY":"KGZ","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""},

### 2.2 Get LPR denial list
Get all detected number plates including denial list.
Syntax:
http://<serverIP>/get_search_info?list=black

Return: 

{"LPR_COUNT": 2,"INFORMATION": [{"INDEX":1,"TS":"1523329437899288","MOD_TS":"2018-04-10 03:03:57 GMT","CAR_ID":"44","LPR":"30U9874","RTIME":"1038.0","ACTION":"0","ACT_PARAM":"denial","THRESHOLD":"0.795461475849152","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"1167","LP_Y":"120","LP_W":"612","LP_H":"108","LP_BMP":"images/20180410030357_899297lp_30U9874_1685.png","ROI_BMP":"","COUNTRY":"TUR","LPR_USER":"AAA","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2018-12-31_23:59"},
{"INDEX":2,"TS":"","MOD_TS":"","CAR_ID":"","LPR":"YP8549","RTIME":"","ACTION":"","ACT_PARAM":"black","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","LP_X":"","LP_Y":"","LP_W":"","LP_H":"",
"LP_BMP":"","ROI_BMP":"","COUNTRY":"","LPR_USER":"CCC","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2018-12-31_23:59"}],"LIST_TYPE": "black"}

### 2.3 Get LPR allowed list
Syntax:
http://<serverIP>/get_search_info?list=white

Return:

{"LPR_COUNT": 1,"INFORMATION": [{"INDEX":1,"TS":"1523329162878730","MOD_TS":"2018-04-10 02:59:22 GMT","CAR_ID":"43","LPR":"7336GN","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"allowed","THRESHOLD":"0.74889463186264","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"693","LP_Y":"303","LP_W":"264","LP_H":"51",

"LP_BMP":"images/20180410025922_878744lp_7336GN_1238.png","ROI_BMP":"","COUNTRY":"KGZ","LPR_USER":"BBB","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2019-12-31_23:59"}],"LIST_TYPE": "white"}

###  2.4 Get LPR visitor list
Syntax:
http://<serverIP>/get_search_info?list= customer

Return: 

{"LPR_COUNT": 1,"INFORMATION": 
[{"INDEX":1,"TS":"1523337311508978","MOD_TS":"2018-04-10 13:15:11 GMT","CAR_ID":"45","LPR":"B0692","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"visitor","THRESHOLD":"0.722453415393829","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"918","LP_Y":"423","LP_W":"372","LP_H":"84",

"LP_BMP":"images/20180410131511_508987lp_B0692_3153.png","ROI_BMP":"","COUNTRY":"ROU","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""}],"LIST_TYPE": "customer"}

Chapter 2.5 Get LPR engine detail
Syntax:
http://<serverIP>/server

Return: 

device name=SG1122LPR-HT MAC address=00-0f-fc-45-03-21 logoEnable=1 Software Version=2.7.94 Model=516 TVSYSTEM=0 Language=0 DhcpEnable=0 SysFeature=328720255 aaa=1 IrisMode=0 IrisLevel=1 PTZ_CAM_ID=1 INTERNAL=516 staus:94:28:44: 0:25: 0: 0: 0:41 StreamStatus=1 Model Name=SG1122LPR-HT DDRTiming=1 OVDriver=1 IVS=0 network_recover=1 SVN_VERSION=7969 profiles=1 SE=1 RecordExtension=avi LPR_KIND=LPR_TW_FAST

### 2.6 Delete LPR event lists

Delete all LPR log lists.
Syntax:
http://<serverIP>/set_search_info?clean=log

Return: clean ok

Delete the LPR denial list.
Syntax:
http://<serverIP>/set_search_info?clean=black

Return: clean ok

Delete the LPR allowed list.
Syntax:
http://<serverIP>/set_search_info?clean=white

Return: clean ok

Delete the LPR visitor list.
Syntax:
http://<serverIP>/set_search_info?clean=customer

Return: clean ok

## 3.  GET RUN-TIME LPR EVENT LIST
Syntax:
http://<serverIP>/getalarmmotion
Return:
--myboundary
Content-Type: text/plain
CamTime:2018-04-10 14:24:08

MotionDetect=0
AlarmInputDetect=0
AlarmInput2Detect=0
AlarmInput3Detect=0
AlarmInput4Detect=0
AlarmInput5Detect=0
AlarmInput6Detect=0
AudioDetect=0
TemperDetect=0
FaceDetectNumber=0
AlarmOutputStatus=0
AlarmOutput2Status=0
PIRDetect=0
DoorBell=0
LUX=0
Day=0
LPR0=647CBA,ACT_PARAM0=Visitor,ROI_X0=96,ROI_Y0=54,ROI_W0=1728,ROI_H0=972,LP_X0=1108,LP_Y0=420,LP_W0=440,LP_H0=144,LPR_TIME0=2019-06-24 16:58:44 GMT,LP_BMP0=LPR_IMAGE/20190624165844_95798lp_647CBA_132.png
LPR1=,ACT_PARAM1=,ROI_X1=,ROI_Y1=,ROI_W1=,ROI_H1=,LP_X1=,LP_Y1=,LP_W1=,LP_H1=,LPR_TIME1=,LP_BMP1= LPR2=,ACT_PARAM2=,ROI_X2=,ROI_Y2=,ROI_W2=,ROI_H2=,LP_X2=,LP_Y2=,LP_W2=,LP_H2=,LPR_TIME2=,LP_BMP2= LPR3=,ACT_PARAM3=,ROI_X3=,ROI_Y3=,ROI_W3=,ROI_H3=,LP_X3=,LP_Y3=,LP_W3=,LP_H3=,LPR_TIME3=,LP_BMP3=

Parameters:

## 4.  HTTP POST NOTIFICATION

Syntax:

For JPEG
http://<serverIP>/eventhttppost?channel=<ch>&servername=<servename>&server=<dns>&port=<port>&account=<username>&password=<password>&am_http_jpeg=<sendjpeg>&streaminx=<encoder>&filemode=<filenameformat>&filename=<filename>urlinfo=%2F<url>

For text
http://<serverIP>/eventhttppost?channel=<ch>&servername=<servename>&server=<dns>&port=<port>&account=<username>&password=<password>&am_http_jpeg=<sendjpeg>&jsoninfo=<json>&urlinfo=%2F<url>
Example:
For JPEG:
/eventhttppost?channel=1&servername=httpservername&server=192.168.3.88&port=8080&account=1&password=1&am_http_jpeg=1&streaminx=3&filemode=0&filename=snap&urlinfo=%2FTEST

For text:
eventhttppost?channel=1&servername=httpservername&server=192.168.3.88&port=8080&account=1&password=1&am_http_jpeg=0&jsoninfo=CAMERA%25CAM_NAME%25&urlinfo=%2FTEST

Parameters:



