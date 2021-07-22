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



