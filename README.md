#ISP参数测试工具使用说明书#

##1 简介##
###1.1 工具简介###
ISP参数测试工具主要通过参数对比、抓图查看和录像查看来进行测试。具体为：

- 1. 所有ISP参数进行设置并检查是否生效。
- 2. 参数设置成功后可按需求保存抓图或录像，由测试人员自主查看预览效果是否生效。
- 3. 测试人员可以配置是否保存文件、是否保存SSH打印信息，可以在配置表中自定义码流、参数值、制式、抓图\录像。

###1.2 运行环境###
确保电脑中一键安装了hita环境和Python27。

##2 使用说明##
###2.1 运行方式###
建议使用runner一键批量运行，也可以使用ride单台运行。

###2.2 工具使用###
####2.2.1 操作步骤####

- 1. 打开工具下的“DevicesList.xls”文件。Sheet页“设备配置”中，可配置的数据如下：

|参数类别|参数名称|含义|默认值|
|:--|:--|:--|:--|
||Execute|是否执行(Y/N)|Y|
||Times|执行次数|1|
|设备参数|IP|设备IP|10.65.133.12|
||Port|端口号|8000|
||Username|用户名|admin|
||Password|密码|admin12345|
||Channel|通道号|1|
|文件保存|SaveImageEnable|是否保存抓图/录像(Y/N)|Y|
||SaveImageWaitingTime|抓图\录像等待时间，视设备性能而定|5|
||SaveImagePath|抓图/录像存放目录||
||SSHEnable|是否开启ssh打印|Y|
||SSHLogPath|日志目录||
|测试模块|IsTestImageAdjustment|是否测试图像调节|Y|
||IsTestExposureSettings|是否测试曝光|N|
||IsTestFocus|是否测试聚焦|N|
||IsTestDayNightSwitch|是否测试日夜转换|N|
||IsTestBacklightSettings|是否测试背光|N|
||IsTestWhiteBalance|是否测试白平衡|N|
||IsTestImageEnhancement|是否测试图像增强|N|
||IsTestVideoAdjust|是否测试视频调整|N|
||IsTestOther|是否测试其他|N|

- 2. Sheet页“参数配置”中，可配置具体功能的参数值，其中绿色列可修改，可设范围已在表中限定；
- 3. *注意：如果码流设置为main以外的值，则只能串行测试，即“一键运行.bat”中*client_no_limit只能设置为1；
- 4. *注意：设备不要接入后端，避免自动校时*；
- 5. 双击“一键运行.bat”，开始自动化测试。


####2.2.2 测试结果查看####

- 1.报告查看：

报告及日志存放于“D:\HITA_HOME\outputs\Log\ISP参数测试工具__xxxx”下，可以看到测试通过情况及错误信息。
 
- 2.图片\录像查看： 

图片或录像文件保存在制定路径下，未指定则保存在“工具目录\OutputFile\图片录像”下。图片先后按IP地址和功能分文件夹存放，命名中包含行数、参数名、参数值、日夜模式信息，如下：

    3_亮度=100(night).jpg 
  
- 3.日志查看：

SSH打印信息存储在用户指定路径下，若未指定，则放在“工具目录\OutputFile\SSHLog”中，命名为IP_日期.log，如：

    10.65.1.1_2017-01-01.log
 

使用中有任何问题，请联系**yinting5**，谢谢。






