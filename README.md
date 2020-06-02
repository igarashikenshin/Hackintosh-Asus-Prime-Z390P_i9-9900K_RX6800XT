# Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT

交流QQ群：1071120659 \
因本人显卡更换为RX5700XT \
故从该版本后更新的版本测试项目不再包含RX580 \
RX580用户仍可以继续使用该EFI，但在使用前需要将“DeviceProperties-Add-PciRoot(0x0)/Pci(0x1,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)”删除。

配置 \
主板: ASUS PRIME Z390-P \
BIOS版本：2804 \
CPU: Intel® Core™ i9-9900K Processor \
核显: Intel® UHD Graphics 630 \
独显: Gigabyte RX5700XT 8GB GDDR6 Gaming OC \
板载网卡: Realtek® RTL8111H Gigabit LAN Controller  \
WiFi/蓝牙: BCM943602CS \
声卡: Realtek® ALC 887 8-Channel High Definition Audio \
固态硬盘: Samsung SSD 970 EVO Plus 500GB \
 \
BIOS设置 \
高级-CPU设置--Intel(VMX) Virtualization Technology -enable \
高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-128M，RC6-enable \
高级-USB Configuration--XHCI Hand-off -enable \
高级-内置设备-Serial Port Configuration-Serial Port -off \
 \
启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable，设置模式-高级模式 \
 \
可适用操作系统版本：macOS Catalina 10.15.1～10.15.5 Beta3 \
OpenCore版本：0.5.8\
Clover版本：不再提供Clover版本\
CPU变频：正常。\
UHD630：正常。\
RX5700XT：正常。原生驱动。\
3.5mm声音 & HDMI：均正常使用，使用AppleALC驱动。\
USB：正常。\
有线网卡：正常。使用了RealtekRTL8111.kext\
睡眠唤醒：正常。\
关机开机：正常。\
iCloud & App Store & iMessage & FaceTime：请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM。\
AirDrop & HandOff & Continuity：正常。\
 \
Tips：\
 \
1.机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。\
 \
2.该config默认为无verbose模式。\
如需启用verbose模式，config.plist需要修改以下几项：\
Misc-Debug-DisplayLevel，值为2147483714 指在屏幕上显示所有 Debug 信息。\
Misc-Debug-Target，值为3，指允许屏幕输出日志。\
Misc-Debug-DisableWatchDog，值为true（plist编辑器中为YES），指排除干扰显示。\
NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v，开启啰嗦模式。\
 \
3.该config启动盘策略为仅搜索APFS及HFS分区。\
对应参数为ScanPolicy 值设置为3080963。\
如需引导Windows或Other OS（Linux、Unix）可将值设置为0，如需指定搜索分区类型，可参考OC配置手册。\
 \
4.该config默认为不显示OC Picker菜单。\
如需开启菜单显示，设置如下：\
Misc-Boot-ShowPicker 值为true（plist编辑器中为YES）。

5.RX580可通过刷写VBIOS增加运行流畅度，可参见https://github.com/igarashikenshin/AMD-RX-Series-VBIOS-macOS

目前已知问题：\
1、若打开节能选项中的唤醒以供网络访问，则睡眠唤醒后网络缓慢。\
2、从Windows切换至macOS或重启macOS后，主显示器DP音频丢失，需要开关显示器才可找回。（或是技嘉5700XT的输出端口顺序问题？）\
3、启动磁盘中无法设定Windows为启动磁盘（提示Bless工具无法将此磁盘设定为启动磁盘）。\
4、启动转换助理不可用（应该是多硬盘问题，单硬盘据查该功能可正常使用）。

