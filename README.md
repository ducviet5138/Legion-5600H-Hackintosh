<p align="center">
 <img width="129px" src="https://rallybr.com.br/logo-hacklegion.png" align="center" />
 <h2 align="center">MacOS on Lenovo Legion 5-15ACH6 - Ryzen 5600H &amp; GeForce RTX 3050 🇻🇳</h2>
</p>
<p align="center"><img src="https://img.shields.io/badge/Bios-HHCN37WW-blue?logo=lenovo&amp;logoColor=%23fff" alt="" />&nbsp;<img src="https://img.shields.io/badge/Opencore-1.0.0-black" alt="" />&nbsp;<img src="https://img.shields.io/badge/MacOS-Sonoma%2014.2.1-green?logo=apple&amp;logoColor=%23fff" alt="" /></p>
<p align="center"><img src="https://github.com/ducviet5138/Hackintosh-Legion-5/assets/99721942/3e39478f-e998-431d-9b92-e9d99c350563" alt="" /></p>

## Considerations

_Information available only for possible references. I do not recommend following all the information presented here._

## Table of Contents

*   [Specifications](#specifications)
*   [What's Working](#whats-working)
*   [What's not Working](#whats-not-working)
*   [Bios Options](#bios-options)
*   [Kexts Used](#kexts-used)
*   [SSDTs Used](#ssdts-used)
*   [Credits](#credits)

## Specifications

| Item  | Info  |
| ------------ | ------------ |
| Model  | Legion 5-15ACH6 Type 82JW  |
| Bios Version  | HHCN37WW  |
| CPU  |  AMD Ryzen™ 5 5600H Processor |
| DGPU | GeForce RTX 3050 4GB |
| RAM  | 2x 16GB Kingston DDR4 2400/3200 MHz  |
| NVMe  | SK Hynix 500GB / Western Digital SN550 1TB |
| WIFI  | Intel® Wi-Fi 6E AX210 (need to make a replacement)|
| Bluetooth  | With Intel wifi combo card  |
| Ethernet  | Realtek RTL8111  |
| Audio  | Realtek ALC287  |
| LCD Panel  | 15.6 FHD IPS 165Hz  |
| Opencore Version  | 1.0.0 |
| SMBIOS used  | MacBookPro16,3 (Need to enter your information generated by [GenSMBIOS](http://https://github.com/corpnewt/GenSMBIOS "GenSMBIOS"))  |
| Target MacOS Version  | macOS Sonoma 14.2 |

## What's Working

| Item | Status | Notes |
| --- | --- | --- |
| CPU | ✅ | AMD Vanilla Kernel Patches ([Modify according to yours Core Count](https://github.com/AMD-OSX/AMD_Vanilla)) |
| DGPU | ✅ | With some DeviceProperties |
| USB | ✅ | All ports working with **[GUX-RyzenXHCIFix](https://github.com/RattletraPM/GUX-RyzenXHCIFix "GUX-RyzenXHCIFix")** / [USBMap](https://github.com/corpnewt/USBMap "USBMap")|
| Keyboard | ✅ | Voodoops2controller Kext + [Karabiner-Elements app](https://karabiner-elements.pqrs.org/ "Karabiner-Elements app") for mapping |
| Audio/Mic | ✅ | AppleALC kext working with layout-id 13 |
| Trackpad | ✅ | VoodooI2C |
| Ethernet | ✅ | RealtekRTL8111 Kext |
| Intel WIFI | ✅ | AirportItlwm Kext |
| Bluetooth | ✅ | From Intel AX210 with IntelBluetoothFirmware.kext + BlueToolFixup Kext |
| Battery | ✅ | SMCBatteryManager Kext |
| Shutdown/Reboot | ✅ |   |
| Sleep/Wake | ✅ | By using ForgedInvariant|

## What's not Working

| Item | Status | Notes |
| --- | --- | --- |
| dGPU | ❌ | GeForce RTX 3050 |
| HDMI A/V out | ❌ | Because HDMI connects directly to the dGPU, which has been disabled |
| NVMe SKHynix | ❌ | Disable it because it causes panic on macOS |
| Brightness Control | ⚠️ | Using Windows brightness to adjust macOS brightness.
| iServices | ❓ |   |
| AppleTV+ DRM | ❓ | Untested yet |

## Bios Options

*   **Only Discrete** GPU
*   Device Guard **Disabled**
*   Secure Boot **Disabled**

## Kexts Used

| Kext | Description |
| --- | --- |
| [AirportItlwm.kext](https://github.com/OpenIntelWireless) | Adds Intel WIFI support |
| [AMDRyzenCPUPowerManagement.kext](https://github.com/trulyspinach/SMCAMDProcessor) | Power management and monitoring of AMD processors |
| [AppleALC.kext](https://github.com/acidanthera/AppleALC) | Native macOS HD audio for not officially supported codecs |
| [AppleMCEReporterDisabler.kext](https://files.amd-osx.com/AppleMCEReporterDisabler.kext.zip) | Disables AppleIntelMCEReporter which causes panics on AMD CPUs |
| [BlueToolFixup.kext](https://github.com/acidanthera/BrcmPatchRAM) | Patches Bluetooth stack to allow non-Apple Bluetooth |
| [ForgedInvariant](https://github.com/ChefKissInc/ForgedInvariant) | The plug & play kext for syncing the TSC on AMD & Intel. It should solve some wake issues for AMD Mobile |
| [HoRNDIS.kext](https://github.com/jwise/HoRNDIS) | Android USB tethering driver for Mac OS X |
| [IntelBTPatcher.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) | Intel Bluetooth Kernel Extensions for macOS |
| [IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) | Intel Bluetooth Kernel Extensions for macOS |
| [GUX-RyzenXHCIFix](https://github.com/RattletraPM/GUX-RyzenXHCIFix) | A fork of GenericUSBXHCI aimed at analyzing and fixing the USB3 |
| [NootedRed.kext](https://github.com/ChefKissInc/NootedRed) | Lilu plugin for AMD Vega iGPUs |
| [NVMeFix.kext](https://github.com/acidanthera/NVMeFix) | Improve compatibility with non-Apple SSDs |
| [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X) | Open source driver for the Realtek RTL8111/8168 family |
| [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents) | Blocking unwanted processes causing compatibility issues on different hardware and unlocking the support for certain features restricted to other hardware |
| [SMCProcessorAMD.kext](https://github.com/Lorys89/SMCProcessorAMD) | VirtualSMC plugin for AMD processors (View temperature) |
| [SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC) | Enables battery readings |
| [USBMap](https://github.com/corpnewt/USBMap "USBMap") | Python script for mapping USB ports in macOS and creating a custom injector kext |
| [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) | Advanced Apple SMC emulator in the kernel |
| [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2) | Fixes keyboard |
| [VoodooI2C.kext & VoodooU2CHID.kext](https://nootinc.github.io/Extras/Kexts/VoodooI2C.zip) | Fixes trackpad |


## SSDTs Used

Done with [SSDTTime](https://github.com/corpnewt/SSDTTime) in Windows 11

| Table | Description |
| --- | --- |
| [SSDT-EC](https://github.com/corpnewt/SSDTTime) | Adds a fake Embedded Controller device |
| [SSDT-PLUG-ALT](https://github.com/corpnewt/SSDTTime) | Fixes CPU definitions |
| [SSDT-USBX](https://github.com/corpnewt/SSDTTime) | Enables USB Power Management |
| [SSDT-XOSI](https://github.com/corpnewt/SSDTTime) | Spoof macOS to Windows for some ACPI features |
| SSDT-GPU-OFF | Disable discrete card (Author: ExtremeXT) |
| SSDT-NVME-OFF | Disable unsupportted NVMe SSD |

## Credits

*   [OC-Little-Translated](https://github.com/5T33Z0/OC-Little-Translated) Guides.
*   [AMD-OSX](https://forum.amd-osx.com/) Forum and the [dedicated Thread](https://forum.amd-osx.com/threads/amd-rayon-r7-5800h-install-monterey-kernel-panic.2725) users.
*   ExtremeXT for help in disable dGPU.
*   zxc2689963 for EFI references.
*   [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) for the guides.
*   [Apple](https://www.apple.com/) for macOS.
*   [Acidanthera](https://github.com/acidanthera) for OpenCore and most Kexts.
*   Anyone else that helped to develop and improve hackintoshing.
