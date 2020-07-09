# HP OMEN 15-DC007-NL MAC-OSX CATALINA GUIDE

<img width="256" src="https://upload.wikimedia.org/wikipedia/it/9/94/MacOS_Catalina_logo.png">

This guide for now is Clover based, it will be updated to OpenCore when it will be released on its final version. For the most part i used the [OpenCore Dortania Guide](https://dortania.github.io/vanilla-laptop-guide/) and adapted it to work with Clover.

#### Laptop Specs

- Intel Core i5-8300H Coffe Lake Intel HM370
- Intel UHD 630
- Nvidia GeForce GTX 1050
- Intel(R) Dual Band Wireless-AC 9560
- NVME and Sata hdd

#### What works:
- [x] Intel GPU.
- [x] 144hz-display.
- [x] Keyboard + Trackpad.
- [x] Ports: HDMI, USB3/2, USB C.
- [x] Wifi + Bluetooth features //with intel!.
- [x] Battery.
- [x] Power management.
- [x] Webcam.
- [x] Audio.
- [x] Sleep.

#### Create the installer
For [Windows](https://dortania.github.io/vanilla-laptop-guide/preparations/online-installer.html) and [Mac](https://dortania.github.io/vanilla-laptop-guide/preparations/offline-installer.html)

#### Kext
Kexts in **Bold** are required to boot to the installer:
- ── **VirtualSMC**
- ── **Lilu**
- ── **WhateverGreen**
- ── RealtekRTL8111.kext (for ethernet)
- ── SATA-100-series-unsupported (for the second hard drive)
- ── **VoodooPS2Controller** (Rehabman Kext for the mouse and keyboard)
- ── AppleALC (with codec injection number 3)
- ── SMCBatteryManager.kext
- ── SMCSuperIO
- ── SMCProcessor.kext 
- ── NoTouchID
- ── [IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
- ── [WIFI](https://github.com/OpenIntelWireless/itlwm) (You have to build it yourself)

You can download them [here](https://dortania.github.io/vanilla-laptop-guide/OpenCore/ktext.html)

#### Clover Setup

Use the lastest version of Clover (version i am using is v5.0 r5119)
- ── Clover UEFI
- ── AptioMemoryFix
- ── EmuVariableUEFI
- ── Script to target volume
- ── APFS and HFS+ Driver

For the config.plist you can use the one I pubblished: it should be compatible and there isn't much i changed from the original.

#### ACPI

You can go [here](https://dortania.github.io/vanilla-laptop-guide/OpenCore/ktext.html) and check what you need, but to get up and running you can use only: 
- [SSDT-EC-USBX-LAPTOP.aml](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-EC-USBX-LAPTOP.aml)
- For battery managment and to not get the bios message "Battery Faulty" you can dump the DSDT and then apply G6 2221ss patch and uncommenting the first line using the Rehabman guide

#### Useful Programs

[Hackintool](https://github.com/headkaze/Hackintool), [CloverConfigurator](https://mackie100projects.altervista.org/download-clover-configurator/), [Clover](https://github.com/CloverHackyColor/CloverBootloader)
