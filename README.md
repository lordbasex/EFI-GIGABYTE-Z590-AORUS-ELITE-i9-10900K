# EFI-GIGABYTE-Z590-AORUS-ELITE-i9-10900K
Gigabyte Z590 Aorus Elite + i9 10900K + Graphic Gigabyte AMD Radeon RX 5600 XT + TP-Link UB400

![macOS01](https://github.com/lordbasex/EFI-GIGABYTE-Z590-AORUS-ELITE-i9-10900K/blob/main/images/macOS01.png)

Setup
![SETUP](https://github.com/lordbasex/EFI-GIGABYTE-Z590-AORUS-ELITE-i9-10900K/blob/main/images/setup.jpeg)

**Latest working macOS Monterey**: 12.6
<br>
**OpenCore**: [0.8.8](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.8)

## Complete hardware specs
- [Intel(R) Core(TM) i9-10900 CPU @ 2.80GHz](https://www.intel.com/content/www/us/en/products/sku/199328/intel-core-i910900-processor-20m-cache-up-to-5-20-ghz/specifications.html)
- [Gigabyte Z590 Aorus Elite @ BIOS F6a](https://www.gigabyte.com/Motherboard/Z590-AORUS-ELITE-rev-10#kf)
- [4x 32Gb DDR4 2400MHz Kingston HyperX HX436C18PB3/32](https://www.kingston.com/datasheets/HX436C18PB3_32.pdf?_=v1)
- [Gigabyte AMD Radeon RX 5600 XT](https://www.gigabyte.com/ar/Graphics-Card/GV-R56XTWF2OC-6GD#kf)
- [HD NVMe Western Digital WDC WDS100T2B0C-00PXH0](https://documents.westerndigital.com/content/dam/doc-library/en_us/assets/public/western-digital/product/internal-drives/wd-blue-nvme-ssd/data-sheet-wd-blue-sn550-nvme-ssd-idk.pdf)
- [Bluetooth 4.0 TP-Link UB400](https://www.tp-link.com/uk/home-networking/adapter/ub400/)

## SMBIOS

Model: iMacPro1,1

Note: Rebuild SMBIOS with *iMacPro1,1* to enable H264 and HEVC with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

![H264%2BHEVC](https://github.com/lordbasex/EFI-GIGABYTE-Z590-AORUS-ELITE-i9-10900K/blob/main/images/H264%2BHEVC.png)


```bash
#######################################################
#                      OCSysInfo                      #
#######################################################


─ CPU
  └── Intel(R) Core(TM) i9-10900 CPU @ 2.80GHz
      ├── Cores: 10 cores
      ├── Threads: 20 threads
      ├── SSE: SSE4.2
      ├── SSSE3: Supported
      └── Codename: Comet Lake

─ Vendor
  ├── Model: iMacPro1,1
  └── Manufacturer: Gigabyte Technology Co., Ltd.

─ GPU
  └── AMD Radeon RX 5600 XT
      ├── Vendor ID: 0x1002
      ├── Device ID: 0x731f
      ├── PCI Path: PciRoot(0x0)/Pci(0x1,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)
      └── Codename: Navi 10

─ Memory
  ├── KHX3600C18D4/32GX (Part-Number)
  │   ├── Type: DDR4
  │   ├── Slot
  │   │   ├── Bank: BANK 0
  │   │   └── Channel: Controller0-ChannelA
  │   ├── Frequency (MHz): 2400 MHz
  │   ├── Manufacturer: Kingston
  │   └── Capacity: 32768MB
  ├── KHX3600C18D4/32GX (Part-Number)
  │   ├── Type: DDR4
  │   ├── Slot
  │   │   ├── Bank: BANK 0
  │   │   └── Channel: Controller0-ChannelA
  │   ├── Frequency (MHz): 2400 MHz
  │   ├── Manufacturer: Kingston
  │   └── Capacity: 32768MB
  ├── KHX3600C18D4/32GX (Part-Number)
  │   ├── Type: DDR4
  │   ├── Slot
  │   │   ├── Bank: BANK 1
  │   │   └── Channel: Controller0-ChannelB
  │   ├── Frequency (MHz): 2400 MHz
  │   ├── Manufacturer: Kingston
  │   └── Capacity: 32768MB
  └── KHX3600C18D4/32GX (Part-Number)
      ├── Type: DDR4
      ├── Slot
      │   ├── Bank: BANK 1
      │   └── Channel: Controller0-ChannelB
      ├── Frequency (MHz): 2400 MHz
      ├── Manufacturer: Kingston
      └── Capacity: 32768MB

─ Network
  └── RTL8125 2.5GbE Controller
      ├── Device ID: 0x8125
      ├── Vendor: 0x10ec
      ├── PCI Path: PciRoot(0x0)/Pci(0x1b,0x2)/Pci(0x0,0x0)
      └── ACPI Path: \_SB.PC00.RP19.D070

─ Audio
  └── Navi 10 HDMI Audio
      ├── Device ID: 0xab38
      ├── Vendor: 0x1002
      └── PCI Path: PciRoot(0x0)/Pci(0x1,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x1)

─ Input
  ├── USB Receiver (USB)
  │   ├── Device ID: 0xc52b
  │   └── Vendor: 0x46d
  └── ITE Device (USB)
      ├── Device ID: 0x5702
      └── Vendor: 0x48d

─ Storage
  └── WDC WDS100T2B0C-00PXH0
      ├── Type: Non-Volatile Memory Express (NVMe)
      ├── Connector: PCI-Express
      └── Location: Internal
```

## ChipSet:
- Video: Intel UHD Graphics 630
- Network: RTL8125 2.5GbE Controller

## ACPI/DSDT:
- SSDT-AWAC.aml
- SSDT-EC.aml
- SSDT-USBX.aml

## SSDT Cuscom
- SSDT-PC00-SBUS [Fixing SMBus support (SSDT-SBUS-MCHC)](https://dortania.github.io/Getting-Started-With-ACPI/Universal/smbus.html)
- 
```
lordbasex@xxxx ~ % kextstat | grep -E "AppleSMBusController|AppleSMBusPCI"
Executing: /usr/bin/kmutil showloaded
No variant specified, falling back to release
  125    0 0xffffff7f95eb5000 0x1000     0x1000     com.apple.driver.AppleSMBusPCI (1.0.14d1) EBE57D74-99FA-3C49-B052-F1500A67430B <17 7 6 3>
  158    1 0xffffff7f95ea9000 0x6ffd     0x6ffd     com.apple.driver.AppleSMBusController (1.0.18d1) 9DFAA286-BAED-3143-93F5-A990A2DA7E95 <157 17 16 7 6 3>
```

## Kexts used:
- AppleALC.kext
- BlueToolFixup.kext
- Lilu.kext
- LucyRTL8125Ethernet.kext
- NVMeFix.kext
- RadeonSensor.kext
- SMCProcessor.kext
- SMCRadeonGPU.kext
- SMCSuperIO.kext
- USBToolBox.kext
- UTBMap.kext
- VirtualSMC.kext
- WhateverGreen.kext

## Doc:
- https://dortania.github.io/OpenCore-Install-Guide/
- https://github.com/KernelWanderers/OCSysInfo/releases/tag/v1.0.8
- https://ark.intel.com/content/www/us/en/ark/products/199328/intel-core-i910900-processor-20m-cache-up-to-5-20-ghz.html
- https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.IntelHD.en.md

## Special thanks to Aníbal Akalzir [@akalzir](https://t.me/+Oyp3zVEBKkZiZTkx)

