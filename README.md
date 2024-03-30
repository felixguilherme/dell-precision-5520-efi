# Dell Precision 5520
## Hardware & Info
- CPU: Intel Core i7-7820HQ
- GPU: Intel HD Graphics 630
- dGPU: NVIDIA Quadro M1200 (disabled)
- RAM: 32GB (2x Micron 16GB DDR4 2400MHz)
- SSD: PC401 NVMe SK Hynix 512GB
- Audio: Realtek ALC298
- Display: no-touch 15.6-inch, 1920×1080@60
- OS: Ventura 13.6.6 (22G630)
- OpenCore Version: 0.9.9


>[!CAUTION]
> This EFI was built manually and specifically for this laptop. It can save you some time if you are experienced, but you should always use the official [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/).

>[!IMPORTANT]
> The `config.plist` file doesn't contain any SMBIOS info. You need to modify it to make this EFI work.
> [Click here to check out how to generate the SMBIOS info](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html#platforminfo).

>[!NOTE]
> My SSD didn't appear the first time I tried to install Ventura. I solved this by installing Catalina first, then installing Ventura. Keep in mind that you will need a different EFI for the Catalina install.

## Working
- Wifi / Bluetooth
- iServices
- Audio
- Touchpad & gestures
- USB ports

## Not Tested
- External displays
- Airdrop (should work just fine)

## Not Working
- Didn't find anything yet

## BOOT Structure
- BOOTx64.efi - required to boot

## OC Structure
### ACPI
- SSDT-EC-USBX-LAPTOP.aml (prebuilt)
- SSDT-PLUG-DRTNIA.aml (prebuilt)
- SSDT-PNLF.aml (prebuilt)
- SSDT-XOSI.aml (prebuilt)

### Drivers
- HfsPlus.efi
- OpenRuntime.efi

### Kexts
- AirportItlwm
- AppleALC
- BrightnessKeys (couldn't make it work yet)
- CtlnaAHCIPort (for unsupported SATA drives)
- IntelBluetoothFirmware
- IntelBTPatcher
- Lilu
- NVMeFix
- SMCBatteryManager
- SMCDellSensors
- SMCLightSensor
- SMCProcessor
- SMCSuperIO
- USBToolBox
- UTBDefault
- VirtualSMC
- VoodooI2C
- VoodooI2CHID
- VoodooPS2Controller
- WhateverGreen

### config.plist
- All the changes specified in the OpenCore Guide
- Disabled verbose booting (OpenCore logs still enabled)
