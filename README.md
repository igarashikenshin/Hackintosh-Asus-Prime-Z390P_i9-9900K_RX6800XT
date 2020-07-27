# *Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT*

## *交流QQ群：1071120659*

因本人显卡更换为RX5700XT，故从该版本后更新的版本测试项目不再包含RX580，RX580用户仍可以继续使用该EFI，但在使用前需要将“DeviceProperties-Add-PciRoot(0x0)/Pci(0x1,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)”删除。

### 配置
1. 主板: ASUS PRIME Z390-P
1. BIOS版本：2804
1. CPU: Intel® Core™ i9-9900K Processor
1. 核显: Intel® UHD Graphics 630
1. 独显: Gigabyte RX5700XT 8GB GDDR6 Gaming OC
1. 板载网卡: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/蓝牙: BCM943602CS
1. 声卡: Realtek® ALC 887 8-Channel High Definition Audio
1. 固态硬盘: Samsung SSD 970 EVO Plus 500GB

### BIOS设置
1. 高级-CPU设置--Intel(VMX) Virtualization Technology -enable
1. 高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-128M，RC6-enable
1. 高级-USB Configuration--XHCI Hand-off -enable
1. 高级-内置设备-Serial Port Configuration-Serial Port -off
1. 启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable，设置模式-高级模式

**可适用操作系统版本：macOS Catalina 10.15.1～11.0 Beta3**

1. OpenCore版本：0.6.0 Debug
1. Clover版本：不再提供Clover版本
1. CPU变频：正常。
1. UHD630：正常。
1. RX5700XT：正常，原生驱动。
1. 3.5mm声音 & HDMI：均正常使用，使用AppleALC驱动。
1. USB：正常。
1. 有线网卡：正常，使用了RealtekRTL8111.kext。
1. 睡眠唤醒：正常。
1. 关机开机：正常。
1. iCloud & App Store & iMessage & FaceTime：请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM。
1. AirDrop & HandOff & Continuity：正常。


### Tips：

1. 机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。
1. 该config默认为无verbose模式。如需启用verbose模式，config.plist需要修改以下一项：NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v。
1. 该config启动盘策略 ScanPolicy 值设置为0。可引导Windows或Other OS（Linux、Unix）如需指定搜索分区类型，可参考OC配置手册。
1. 该config默认为不显示OC Picker菜单。如需开启菜单显示，设置如下：Misc-Boot-ShowPicker 值为true（plist编辑器中为YES）。
1. RX580可通过刷写VBIOS增加运行流畅度，可参见[https://github.com/igarashikenshin/AMD-RX-Series-VBIOS-macOS]()

### 目前已知问题：

1. 若打开节能选项中的唤醒以供网络访问，则睡眠唤醒后网络缓慢。（或为网卡设备ID问题，在设备ID 0x43a0的设备上出现）（很高兴，在macOS 11.0 Beta1中，这个问题得到了修复）
1. 在双显示器状态下，从Windows切换至macOS或重启macOS后，主显示器DP音频丢失，需要开关显示器才可找回。（或是技嘉5700XT的输出端口顺序问题？）
1. 启动磁盘中无法设定Windows为启动磁盘（提示Bless工具无法将此磁盘设定为启动磁盘）。 更新-该问题已解决，可查看Windows Bootcamp.pdf
1. 启动转换助理不可用（应该是多硬盘问题，单硬盘据查该功能可正常使用） 。更新-该问题已解决，可查看[Windows Bootcamp.pdf](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT/blob/master/Boot%20Camp%E6%95%99%E7%A8%8B/Windows%20Bootcamp.pdf)

