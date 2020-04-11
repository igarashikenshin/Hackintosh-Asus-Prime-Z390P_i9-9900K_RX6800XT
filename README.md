# Hackintosh-Asus-Prime-Z390P_i9-9900K_RX580

交流QQ群：1071120659

配置 \
主板: ASUS PRIME Z390-P \
BIOS版本：2603 \
更新：经测试，在BIOS版本2606下，会有偶发性卡顿问题，可降级至2603解决。\
CPU: Intel® Core™ i9-9900K Processor \
核显: Intel® UHD Graphics 630 \
独显: SAPPHIRE PULSE Radeon RX 580 8GB GDDR5 \
板载网卡: Realtek® RTL8111H Gigabit LAN Controller  \
WiFi/蓝牙: BCM943602CS \
声卡: Realtek® ALC 887 8-Channel High Definition Audio \
固态硬盘: Samsung SSD 970 EVO Plus 500GB \
 \
BIOS设置 \
高级-CPU设置--Intel(VMX) Virtualization Technology -enable \
高级-北桥--VT-D-disable，大于4G地址空间解码-enable \
高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-Enable，DVMT Pre-Allocated-256M，RC6-enable \
高级-USB Configuration--XHCI Hand-off -enable \
 \
启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable，设置模式-高级模式 \
 \
可适用操作系统版本：macOS Catalina 10.15.1～10.15.5 Beta1 \
OpenCore版本：0.56\
Clover版本：5103（目前仅支持到10.15.4 beta2，暂停更新一段时间。）\
CPU变频：正常。\
UHD630：正常。\
RX580：正常。原生驱动。\
3.5mm声音 & HDMI：均正常使用，使用AppleALC驱动。\
USB：正常。\
有线网卡：正常。使用了RealtekRTL8111.kext\
睡眠唤醒：正常。\
关机开机：正常。\
iCloud & App Store & iMessage & FaceTime：请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM。\
AirDrop & HandOff & Continuity：正常。\
 \
Tips：\
1.机型设定为iMAC19.1。\
 \
2.该config默认为无verbose模式。\
如需启用verbose模式，config.plist需要修改以下几项：\
Misc-Debug-DisplayLevel 值为2147483714 指在屏幕上显示所有 Debug 信息。\
Misc-Debug-Target 值为3 指允许屏幕输出日志。\
Misc-Debug-DisableWatchDog 值为ture（plist编辑器中为YES） 指排除干扰显示。\
NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args 添加-v 开启啰嗦模式。\
 \
3.该config启动盘策略为仅搜索APFS及HFS分区。\
对应参数为ScanPolicy 值设置为3080963。\
如需引导Windows或Other OS（Linux、Unix）可将值设置为0，如需指定搜索分区类型，可参考OC配置手册。\
 \
4.该config默认为不显示OC Picker菜单。\
如需开启菜单显示，设置如下：\
Misc-Boot-ShowPicker 值为ture（plist编辑器中为YES）。\

