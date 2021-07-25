# LILIN-LPR-Camera-SDK

## Overview
This document, LILIN IP camera automatic number plate recognition (LPR) protocol SDK, specifies the integrations of using number plate database of LILIN IP camera. 

## VIDEO DEMO

![image](https://github.com/LILINOpenGitHub/LILIN-LPR-Camera-SDK/blob/main/images/byq65-g2ii7.gif)

## PORT NUMBER
There are two series of camera S series and 7 series (AI).  For the port number: please use correct port number for HTTP communicatioin.

S series: 80 port <BR>
7 series (Aida): 8592 port <BR>

## GET LPR EVENT LIST <BR>
### Get all LPR log list <BR>

Get all detected number plates including denial, allowed, and visitor lists. <BR>
```
Syntax:
http://<serverIP>/get_search_info?list=log
```
Return: 
  
{"LPR_COUNT": 47,"INFORMATION": [{"INDEX":1,"TS":"1523329437899288","MOD_TS":"2018-04-10 03:03:57 GMT","CAR_ID":"44","LPR":"30U9874","RTIME":"1038.0","ACTION":"0","ACT_PARAM":"denial","THRESHOLD":"0.795461475849152","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"1167","LP_Y":"120","LP_W":"612","LP_H":"108",
"LP_BMP":"images/20180410030357_899297lp_30U9874_1685.png","ROI_BMP":"","COUNTRY":"TUR","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""},

{"INDEX":2,"TS":"1523329162878730","MOD_TS":"2018-04-10 02:59:22 GMT","CAR_ID":"43","LPR":"7336GN","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"allowed","THRESHOLD":"0.74889463186264","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"693","LP_Y":"303","LP_W":"264","LP_H":"51",
"LP_BMP":"images/20180410025922_878744lp_7336GN_1238.png","ROI_BMP":"","COUNTRY":"KGZ","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""},


| Parameter	| Values	| Description |
| --- | --- | --- |
| LPR_COUNT	| 1~1000	| Log list: max.1000, Denial list: max.100, Allowed list: max.1000, Visitor list: max. 1000 |
| LPR_COUNT	| 1~1000 | Log list: max.1000, Denial list: max.100, Allowed list: max.1000, Visitor list: max. 1000 | 
| INDEX	| Number	| Index value | 
| TS	| Number	| Detected License plate time value (TS/1000=MOD_TS) | 
| MOD_TS	| YYYY-MM-DD hh:mm:ss	| Detected license place time | 
| CAR_ID	| Number	| Car index value | 
| LPR	| Text & number	| License Plate Number | 
| RTIME	| N/A	| Undefined | 
| ACTION	| N/A	| Undefined | 
| ACT_PARAM	| denial, allowed, visitor	| List Type | 
| THRESHOLD	| Number	| Detected license plate threshold value | 
| ROI_X: ROI_Y: ROI_W: ROI_H:	| Number	| License plate detection region size. | 
| LP_X: LP_Y: LP_W: LP_H:	| Number	| Detected license plate location.| 
| LP_BMP	| Number	| License plate saved file path. Max.100 | 
| ROI_BMP	| N/A	| Undefined | 
| COUNTRY	| Text	| License plate country.(Inaccurate) | 
| LPR_USER	| Text	| Denial & Allowed list user name | 
| LPR_PHONE	| N/A	| Reserved | 
| LPR_ADDRESS	| N/A	| Reserved | 
|  LPR_PAYSTATUS	| 0~3	| Detect level (Supported: Denial & Allowed list) 0: Very Weak 1: Weak 2: Normal 3: Strong | 
| LPR_EXIST	| N/A	| Empty | 
| LPR_SCHEDULE_S	| 00:00~23:59	Detection Start Time (Supported: Denial & Allowed list) | 
| LPR_SCHEDULE_E	00:00~23:59	Detection End Time (Supported: Denial & Allowed list) | 
| LPR_OTHER | 	Text	| Remarks Others on Denial & Allowed list | 
| LPR_DETECT_ENDTIME	| YYYY-MM-DD_hh:mm	| License Plate Detection Time Limit (Supported: Denial & Allowed list) | 
| LIST_TYPE	| black, white, customer	| List Type | 
### Get LPR denial list
Get all detected number plates including denial list.
```
Syntax:
http://<serverIP>/get_search_info?list=black
```
Return: 

{"LPR_COUNT": 2,"INFORMATION": [{"INDEX":1,"TS":"1523329437899288","MOD_TS":"2018-04-10 03:03:57 GMT","CAR_ID":"44","LPR":"30U9874","RTIME":"1038.0","ACTION":"0","ACT_PARAM":"denial","THRESHOLD":"0.795461475849152","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"1167","LP_Y":"120","LP_W":"612","LP_H":"108","LP_BMP":"images/20180410030357_899297lp_30U9874_1685.png","ROI_BMP":"","COUNTRY":"TUR","LPR_USER":"AAA","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2018-12-31_23:59"},
{"INDEX":2,"TS":"","MOD_TS":"","CAR_ID":"","LPR":"YP8549","RTIME":"","ACTION":"","ACT_PARAM":"black","THRESHOLD":"","ROI_X":"","ROI_Y":"","ROI_W":"","ROI_H":"","LP_X":"","LP_Y":"","LP_W":"","LP_H":"",
"LP_BMP":"","ROI_BMP":"","COUNTRY":"","LPR_USER":"CCC","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2018-12-31_23:59"}],"LIST_TYPE": "black"}

### Get LPR allowed list
```
Syntax:
http://<serverIP>/get_search_info?list=white
```
Return:

{"LPR_COUNT": 1,"INFORMATION": [{"INDEX":1,"TS":"1523329162878730","MOD_TS":"2018-04-10 02:59:22 GMT","CAR_ID":"43","LPR":"7336GN","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"allowed","THRESHOLD":"0.74889463186264","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"693","LP_Y":"303","LP_W":"264","LP_H":"51",

"LP_BMP":"images/20180410025922_878744lp_7336GN_1238.png","ROI_BMP":"","COUNTRY":"KGZ","LPR_USER":"BBB","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"2","LPR_EXIST":"","LPR_SCHEDULE_S":"00:00","LPR_SCHEDULE_E":"23:59","LPR_OTHER":"","LPR_DETECT_ENDTIME":"2019-12-31_23:59"}],"LIST_TYPE": "white"}

### Get LPR visitor list
```
Syntax:
http://<serverIP>/get_search_info?list= customer
```
Return: 

{"LPR_COUNT": 1,"INFORMATION": 
[{"INDEX":1,"TS":"1523337311508978","MOD_TS":"2018-04-10 13:15:11 GMT","CAR_ID":"45","LPR":"B0692","RTIME":"1035.0","ACTION":"0","ACT_PARAM":"visitor","THRESHOLD":"0.722453415393829","ROI_X":"96","ROI_Y":"54","ROI_W":"1728","ROI_H":"972","LP_X":"918","LP_Y":"423","LP_W":"372","LP_H":"84",

"LP_BMP":"images/20180410131511_508987lp_B0692_3153.png","ROI_BMP":"","COUNTRY":"ROU","LPR_USER":"","LPR_PHONE":"","LPR_ADDRESS":"","LPR_PAYSTATUS":"","LPR_EXIST":"","LPR_SCHEDULE_S":"","LPR_SCHEDULE_E":"","LPR_OTHER":"","LPR_DETECT_ENDTIME":""}],"LIST_TYPE": "customer"}

### Get LPR engine detail
```
Syntax:
http://<serverIP>/server
```
Return: 

device name=SG1122LPR-HT MAC address=00-0f-fc-45-03-21 logoEnable=1 Software Version=2.7.94 Model=516 TVSYSTEM=0 Language=0 DhcpEnable=0 SysFeature=328720255 aaa=1 IrisMode=0 IrisLevel=1 PTZ_CAM_ID=1 INTERNAL=516 staus:94:28:44: 0:25: 0: 0: 0:41 StreamStatus=1 Model Name=SG1122LPR-HT DDRTiming=1 OVDriver=1 IVS=0 network_recover=1 SVN_VERSION=7969 profiles=1 SE=1 RecordExtension=avi LPR_KIND=LPR_TW_FAST

### Delete LPR event lists

Delete all LPR log lists.
```
Syntax:
http://<serverIP>/set_search_info?clean=log
```
Return: clean ok

Delete the LPR denial list.
```
Syntax:
http://<serverIP>/set_search_info?clean=black
```
Return: clean ok

Delete the LPR allowed list.
```
Syntax:
http://<serverIP>/set_search_info?clean=white
```
Return: clean ok

Delete the LPR visitor list.
```
Syntax:
http://<serverIP>/set_search_info?clean=customer
```
Return: clean ok

## GET RUN-TIME LPR EVENT LIST
```
Syntax:
http://<serverIP>/getalarmmotion
```
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

Parameters:<BR>

## HTTP POST NOTIFICATION
 
For JPEG
```
Syntax:
http://<serverIP>/eventhttppost?channel=<ch>&servername=<servename>&server=<dns>&port=<port>&account=<username>&password=<password>&am_http_jpeg=<sendjpeg>&streaminx=<encoder>&filemode=<filenameformat>&filename=<filename>urlinfo=%2F<url>
```
For text
```
http://<serverIP>/eventhttppost?channel=<ch>&servername=<servename>&server=<dns>&port=<port>&account=<username>&password=<password>&am_http_jpeg=<sendjpeg>&jsoninfo=<json>&urlinfo=%2F<url>
```
Example:
For JPEG:
```
/eventhttppost?channel=1&servername=httpservername&server=192.168.3.88&port=8080&account=1&password=1&am_http_jpeg=1&streaminx=3&filemode=0&filename=snap&urlinfo=%2FTEST
```
For text:
```
eventhttppost?channel=1&servername=httpservername&server=192.168.3.88&port=8080&account=1&password=1&am_http_jpeg=0&jsoninfo=CAMERA%25CAM_NAME%25&urlinfo=%2FTEST
```
Parameters: <BR>

## DELETE LPR EVENT LIST 
### 5.1 Delete all LPR list
Get all detected number plates including denial, allowed, and visitor lists..
```
Syntax:
http://<serverIP>/set_search_info?clean=<type>
```
Examples:

/set_search_info?clean=log
/set_search_info?clean=black
/set_search_info?clean=white
/set_search_info?clean=customer

### Delete items of an LPR list
Get all detected number plates including denial, allowed, and visitor lists.
```
Syntax:
http://<serverIP>/set_search_info?delete=<type>&lprcount=<count>&lpr_oplate=<plate>
```
Examples: <BR>
/set_search_info?delete=black&lprcount=1&lpr_oplate=ABC123
/set_search_info?delete=white&lprcount=1&lpr_oplate=ABC123
/set_search_info?delete=customer&lprcount=1&lpr_oplate=ABC123

Return: 
<?xml version="1.0" encoding="UTF-8"?>
-<lprinfo>
<lpr_res>0</lpr_res>
</lprinfo>

## SET LPR DB LIST
Set number plates into a database
For adding
```
Syntax:
http://<serverIP>/set_search_info?<act>=<type>&lprcount=<count>&lpr_plate=<platenum>&lpr_user=<user>&lpr_paystatus=<paystatus>&lpr_schedule_s=<schedule_s>&lpr_schedule_e=<schedule_e>&lpr_other=<other>&lpr_detect_endtime=<endtime>
```
For updating;
```
http://<serverIP>/set_search_info?<act>=<type>&lprcount=<count>&lpr_plate=<platenum>&lpr_oplate=<platenum>&lpr_user=<user>&lpr_paystatus=<paystatus>&lpr_schedule_s=<schedule_s>&lpr_schedule_e=<schedule_e>&lpr_other=<other>&lpr_detect_endtime=<endtime>
```
Parameters: <BR>
| Parameter	| Values	| Description |
| --- | --- | --- |
| act	| Text	| add: add number plate to a db, update: update number plate to a db |
| type	| Text	| black, white |
| count	| Number | 	Number of items |
| platenum	| Text 	| The number plate |
| user	| Text	| The username |
| schedule_s	| HH:mm	HH: | hour, mm: minute, ex 07:00 |
| schedule_e	| HH:mm	HH: | hour, mm: minute, ex 17:00 |
| endtime	| YYYY-MM-DD_HH:mm	| 2018-02-12_10:25 |

Examples of adding a number plate to a db:
```
/set_search_info?add=black&lprcount=1&lpr_plate=ABC123&lpr_user=TEST123&lpr_paystatus=0&lpr_schedule_s=01:00&lpr_schedule_e=07:00&lpr_other=other123&lpr_detect_endtime=2018-02-12_10:25
```
```
/set_search_info?add=white&lprcount=1&lpr_plate=ABC123&lpr_user=TEST123&lpr_paystatus=0&lpr_schedule_s=01:00&lpr_schedule_e=07:00&lpr_other=other123&lpr_detect_endtime=2018-02-12_10:25
```
Return: 
<?xml version="1.0" encoding="UTF-8"?>
-<lprinfo>
<lpr_res>0</lpr_res>
</lprinfo>

Examples of updating a number plate into a db:
```
/set_search_info?update=black&lprcount=1&lpr_plate=ABC123&lpr_oplate=ABC123&lpr_user=test123&lpr_paystatus=0&lpr_schedule_s=05:03&lpr_schedule_e=06:12&lpr_other=other567&lpr_detect_endtime=2018-02-12_10:25
```
```
/set_search_info?update=white&lprcount=1&lpr_plate=ABC123&lpr_oplate=ABC123&lpr_user=test123&lpr_paystatus=0&lpr_schedule_s=05:03&lpr_schedule_e=06:12&lpr_other=other567&lpr_detect_endtime=2018-02-12_10:25
```
Return: 
<?xml version="1.0" encoding="UTF-8"?>
-<lprinfo>
<lpr_res>0</lpr_res>
</lprinfo>

## IMPORT & EXPORT DENIAL & ALLOWED LISTS
Import a CSV file into LPR DB. 
```
Syntax:
http://<serverIP>/import_lpr_list
```
Note: This command has to be used by POST, and attach the listinfo.csv file.
Note: The file should be utf8 with Bom format.
Note: The file name needs to be listinfo.csv.

Export a CSV file from LPR DB.
```
Syntax:
http://<serverIP>/get_search_info?download=ALL
```
listinfo.csv data format

## GET THE NUMBER PLATE SNAPSHOT

http://192.168.123.223/LPR_IMAGE/20180214001246_566983lp_AFY8385_34092.png
Note: The path and file name of images, please refer to Chapter 2.1 Get All LPR log list.

## RESTART RECOGNITION SYSTEM
To restart recognition, send the CGI for enabling recognition. 
```
Syntax:
http://<serverIP>/set_search_info?restart=detect
```

## ENABLE or DISABLE DENIAL or ALLOWED DETECTION
To active LPR, denial and allowed detection lists.  Send the CGI for enabling or disabling. 

For LPR detection
```
Syntax:
http://<serverIP>/lpr_info?set=status&LPR_FLAG=<act>
```
For Denial and Allowed detection
```
Syntax:
http://<serverIP>/lpr_info?set=status&LPR_FLAG=<act>
```
Example:

/lpr_info?set=status&LPR_FLAG=0
/lpr_info?set=status&LPR_BLACK_FLAG=0
/lpr_info?set=status&LPR_WHITE_FLAG=0


Parameters:
Chapter 12.  IMPORT & EXPORT Mapping Table
Import a CSV file into LPR DB. 
```
Syntax:
http://<serverIP>/import_lpr_map_list
```
Note: This command has to be used by POST, and attach the mapping_info.csv file.
Note: The file should be utf8 with Bom format.
Note: The file name needs to be mapping_info.csv

Export a CSV file from LPR MAPPING DB.
```
Syntax:
http://<serverIP>/get_search_info?download=mapping
```
mapping_info.csv data format

