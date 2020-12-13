# *Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT*

[中文](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT/blob/master/README.md)｜[English](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT/blob/master/README-EN.md)

Because my graphics card is replaced by RX5700XT, the updated version test items after this version no longer include RX580. RX580 users can still continue to use the EFI, but before using it, you need to drop "DeviceProperties-Add-PciRoot(0x0)/Pci(0x1) ,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)" delete.

![System Info](https://i.imgur.com/4mjqmdM.png)

### Configuration
1. Motherboard: ASUS PRIME Z390-P
1. BIOS version: 2808
1. CPU: Intel® Core™ i9-9900K Processor
1. Core display: Intel® UHD Graphics 630
1. Exclusive display: Gigabyte RX5700XT 8GB GDDR6 Gaming OC
1. Onboard network card: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/Bluetooth: BCM94360CD
1. Sound Card: Realtek® ALC 887 8-Channel High Definition Audio
1. Solid State Drive: Samsung SSD 970 EVO Plus 500GB

### BIOS settings
1. Advanced-CPU settings-Intel(VMX) Virtualization Technology -enable
1. Advanced-North Bridge-Display Settings-preferred graphics card-Auto, initialize IGPU-enable, DVMT Pre-Allocated-128M, RC6-auto
1. Advanced-USB Configuration--XHCI Hand-off -enable
1. Advanced-Built-in Device-Serial Port Configuration-Serial Port -off
1. Start-start settings-quick start-disable, if there is an error, wait for the F1 key-disable
1. Setting mode-advanced mode

**Applicable operating system version: macOS Catalina 10.15.1～11.1 RC**

1. OpenCore version: 0.6.4
1. Clover version: Clover version is no longer available
1. CPU frequency conversion: Working.
1. UHD630: Working.
1. RX5700XT: Working, native driver.

![Graphics Card](https://i.imgur.com/9MrmeoC.png)
1. 3.5mm sound & HDMI: both are used Working, using AppleALC driver.
1. USB: Working.
1. Wired network card: Working, RealtekRTL8111.kext is used.
1. Wake up from sleep: Working.

![Power Saver](https://i.imgur.com/wZ7IZjm.png)
1. Turn off and turn on: Working.
1. iCloud & App Store & iMessage & FaceTime: Please generate the Board Serial Number, serial number, and SmUUID by yourself, and modify the "Custom UUID" in the SysPrameter system parameters, and the MLB and ROM in the RtVariables variable settings accordingly.
1. AirDrop & HandOff & Continuity: Working.

![Wi-Fi en0](https://i.imgur.com/daoSzyJ.png)
![BlueTooth](https://i.imgur.com/Cgr8AJv.png)
![Apple Watch](https://i.imgur.com/iYimFue.png)

### Tips:

1. The model needs to be set to iMAC19.1 (now preset, please modify it after installation).
1. The config defaults to no verbose mode. To enable verbose mode, config.plist needs to modify the following one: NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args, add -v.
1. The ScanPolicy value of the config boot disk policy is set to 0. Bootable Windows or Other OS (Linux, Unix) If you need to specify the search partition type, please refer to the OC configuration manual.
1. The config defaults to not display the OC Picker menu. To turn on the menu display, set as follows: Misc-Boot-ShowPicker is true (YES in the plist editor).
1. RX580 can increase the running smoothness by flashing VBIOS, see [https://github.com/igarashikenshin/AMD-RX-Series-VBIOS-macOS]()

### Currently known issues:

1. If the wake-up in the energy-saving option is turned on for network access, the network will be slow after wake-up from sleep. (Or the problem of the device ID of the network card, which appears on the device with the device ID 0x43a0) (I'm glad that this problem has been fixed in macOS 11.0 Beta1)
1. In the dual-monitor state, after switching from Windows to macOS or restarting macOS, the DP audio of the main display is lost, and you need to switch the display to retrieve it. (Or the output port order of Gigabyte 5700XT?)
1. Windows cannot be set as the startup disk in the startup disk (it prompts that the Bless tool cannot set this disk as the startup disk). Update-the problem has been resolved,you can view [Windows Bootcamp.pdf](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT/blob/master/Boot%20Camp%E6%95%99%E7%A8%8B/Windows%20Bootcamp.pdf)
1. The boot conversion assistant is unavailable (it should be a problem with multiple hard drives, the function can be used normally according to the single hard drive). Update-This issue has been resolved, you can view [Windows Bootcamp.pdf](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX5700XT/blob/master/Boot%20Camp%E6%95%99%E7%A8%8B/Windows%20Bootcamp.pdf)

![Boot Camp](https://i.imgur.com/O9nsdYV.png)
