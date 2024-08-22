# Asus_X542UAR_Hackintosh
This repository and project hosts the files necessary to boot macOS Mojave, Catalina and BigSur successfully on the Asus Vivobook X542UAR Laptop

# DISCLAIMER
THIS INFORMATION/RESEARCH HAS BEEN DONE AND SHARED PURELY FOR EXPERIMENTAL AND RESEARCH PURPOSES, AND IS IN NO MAY MEANT TO PROMOTE CIRCUMVENTING OF ANYTHING THAT IS SOMEONE ELSE'S CORPORATE PRIVATE PROPERTY. THE INFORMATION LISTED HERE IS PURELY FOR EDUCATIONAL PURPOSES AND SHOULD YOU CHOOSE TO UTILIZE IT IN ANY WAY, I AM IN NO WAY RESPONSIBLE FOR ANY INJUNCTIONS/PROBLEMS THAT MAY OR MAY NOT ARISE AND/OR BE BROUGHT AGAINST ANOTHER FOR THEIR CHOOSING TO HAVE DONE SO.

# Acknowledgements
- Acidanthera for [OpenCore Bootloader](https://github.com/acidanthera/OpenCorePkg)
- Dortania for [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide)
- Corpnewt for [SSDT Time](https://github.com/corpnewt/SSDTTime) & [UnPlugged](https://github.com/corpnewt/UnPlugged)
- USBToolbox for [USBToolbox](https://github.com/USBToolBox)
- And many more awesome people in the hackintosh community
  
# Deployment
To deploy this project properly, please obtain the EFI folder from this repository, edit the config.plist to generate new serial number, rom, UUID, etcetera, then save config.plist, and place the files onto the appropriate ESP EFI partition in order to boot using OpenCore bootloader and proceed with your installation of macOS.

# Documentation
_The hardware in this Machine is as follows_:
- CPU: Intel Core i5-8250U (KabyLake-Refresh)
- GPU: Intel UHD Graphics 620
- Monitor resolution: 1366x768
- Mobo: Asus X542UAR (Chipset: Kaby Lake; Southbridge: Coffee Lake-U/Y PCH)
- Memory: 2x4GB DDR4 2400MHz (Samsung M471A5244CB0-CRC)
- Drive: M.2 NGFF Vaseky V820/256GB
- Keyboard & Touchpad: PS2 Keyboard & ELAN 1200 I2C Touchpad
- Ethernet: RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller
- Wifi & Bluetooth: Qualcomm Atheros AR9565
- Audio: Realtek ALC294
- Microphone: Realtek HD Audio
- Camera: USB2.0 VGA UVC WebCam
- SD Card Reader: Unknown (and broken)
- BIOS version: 306
> [!IMPORTANT]
> BIOS version must be 306 or older. Lastest BIOS (version 309) has issues with VoodooI2C.kext. Luckily, downgrading Asus BIOS is super easy. [Here's the instruction on downgrading ASUS BIOS using Asus Winflash (Windows)](https://github.com/BluePurplePro/Asus_X542UAR_Hackintosh/blob/main/Downgrade_ASUS_BIOS_using_Winflash.md)  
# Drivers & Essential Kernel Extensions
| Required Drivers | Essential Kexts |
| ------------- | ------------- |
| [HfsPlus.efi](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi) | [Lilu.kext](https://github.com/acidanthera/Lilu) |
| [OpenRuntime.efi](https://github.com/acidanthera/OpenCorePkg) | [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) |

# Kernel Extensions corresponding to hardware
| Hardware  | Kext(s) |
| ------------- | ------------- |
| Intel UHD Graphics 620  | [Whatevergreen.kext](https://github.com/acidanthera/WhateverGreen)  |
| M.2 NGFF Vaseky V820/256GB  | No kernel extension needed  |
| PS2 Keyboard  | [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2)  |
| ELAN 1200 I2C  | [VoodooI2C.kext and its satellite VoodooI2CHID.kext](https://github.com/VoodooI2C/VoodooI2C)  |
| RTL8111/8168/8411  | [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X)  |
| Qualcomm Atheros AR9565  | [HS80211Family.kext & AirPortAtheros40.kext](https://github.com/FIRSTPLATO/opencore-atheros-kext) |
| Realtek ALC294  | [AppleALC.kext using layout-id 28 or 66](https://github.com/acidanthera/AppleALC)  |
| Camera  | [USBToolBox.kext](https://github.com/USBToolBox/kext) & [UTBMap.kext](https://github.com/USBToolBox/tool)  |
| Brightness Keys  | [BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys)  |

# Result
_Working_:
- iGPU
- Audio (Both speakers and 3.5mm Audio Jack)
- Ethernet
- Bluetooth
- Keyboard
- USB ports
- Brightness
- Battery Status
- Camera
- Microphone

_Partially working_:
- Wifi (AR9565 is super slow outside Windows, the only usable feature is location services. It is recommended to replace AR9565 with Intel card or Fenvi card)
- Touchpad (Double tap to drag is not reliable, it is recommended to use three finger drag instead)

_Not working_:
- Airdrop
- Power Management (CFG-Lock)

_Not tested_:
- Sleep (I don't carry this laptop around, always plug an ethernet cable. Feel free to fix sleep function)
- SD Card Reader (Mine is broken)
- HDMI (Audio; 4K@60 output)

_Known issue(s)_:
- Rebooting from Windows might break Audio in MacOS. The solution is turn off (shutdown) the laptop and turn it on, boot straight to MacOS

# BIOS Settings (F7 Advanced Mode)
- **Advanced**
  - Intel Virtualization Technology ~> Enabled
  - USB Configuration ~> Legacy USB Support ~> Auto/Disabled
  - Graphics Configuration ~> DVMT Pre-Allocated ~> 64M
  - SATA Configuration ~> SATA Mode Selection ~> AHCI
- **Security**
  - Secure Boot Control ~> Disabled
- **Boot**
  - Fast Boot ~> Disabled
  - CSM Support ~> Disabled
