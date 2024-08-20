# Asus_X542UAR_Hackintosh
This repository and project hosts the files necessary to boot macOS Ventura successfully on the HP Envy13-AQ0026TU Laptop

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
- Mobo: (Intel 300 Series Chipset)
- Memory: 2x4GB DDR4 2400MHz (Samsung M471A5244CB0-CRC)
- Drive: M.2 NGFF Vaseky V820/256GB
- Keyboard & Touchpad: PS2 Keyboard & ELAN 1200 I2C Touchpad
- Ethernet: RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller
- Wifi & Bluetooth: Qualcomm Atheros AR9565
- Audio: Realtek ALC294 (working layout-id: 28 and 66)
- Microphone: Unknown
- Camera: USB2.0 VGA UVC WebCam
- SD Card Reader: Unknown (and broken)

| Required Drivers | Essential Kernel Extensions |
| ------------- | ------------- |
| [HfsPlus.efi](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi) | [Lilu.kext](https://github.com/acidanthera/Lilu) |
| [OpenRuntime.efi](https://github.com/acidanthera/OpenCorePkg) | [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) |

| Hardware  | Kernel Extension for hardware |
| ------------- | ------------- |
| Intel UHD Graphics 620  | [Whatevergreen.kext](https://github.com/acidanthera/WhateverGreen)  |
| M.2 NGFF Vaseky V820/256GB  | No kernel extension needed  |
| PS2 Keyboard  | [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2)  |
| ELAN 1200 I2C  | [VoodooI2C.kext](https://github.com/VoodooI2C/VoodooI2C)  |
| RTL8111/8168/8411  | [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X)  |
| Qualcomm Atheros AR9565  | [HS80211Family.kext & AirPortAtheros40.kext](https://github.com/FIRSTPLATO/opencore-atheros-kext) |
| Realtek ALC294  | [AppleALC.kext](https://github.com/acidanthera/AppleALC)  |
| Microphone  | [USBToolBox.kext](https://github.com/USBToolBox/kext) & [UTBMap.kext](https://github.com/USBToolBox/tool]  |
| Camera  | [USBToolBox.kext](https://github.com/USBToolBox/kext) & [UTBMap.kext](https://github.com/USBToolBox/tool]  |
| Brightness Keys  | [BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys)  |


_Working_:
- iGPU
- Internal Sound
- Ethernet
- Wifi & Bluetooth
- Keyboard
- Touchpad
- USB ports
- Brightness
- Battery Status
- Camera
- Microphone

_Not working_:
- Airdrop
- Power Management (CFG-Lock)

_Not tested_:
- Sleep (I don't carry this laptop around, always plug an ethernet cable. Feel free to fix sleep function)

# BIOS Settings
- **Security**
  - 
- **Configuration**
  - 
- **Boot Options**

Still writing...
  - 
 
