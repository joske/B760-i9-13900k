# B760-i9-13900k

OpenCore config for Raptor Lake desktop

OpenCore version: 1.0.0

## Hardware

- ASUS prime B760-PLUS
- i9 13900k with Noctua NH-D15 (this cooled better and much more quiet than the Be Quiet pure loop AIO)
- be quiet! Pure Power 12 850W PSU
- AMD Radeon RX 580
- Samsung 990 pro M.2 NVMe 2TB (Arch Linux)
- WD Black SN850X M.2 NVMe 1TB (macOS Sonoma)
- Samsung 850 EVO SATA 500 GB (FreeBSD)
- Kingston SATA 128 GB (win 10)
- 32 GB corsair DDR5-5600 RAM
- ASUS DRW-24D5MT
- be quiet! PURE BASE 600 case

All OSes boot via GRUB2

## BIOS settings

BIOS version: 1656 (2024/4/19)

- AI Tweaker -> AI Overclock Tuner -> XMP II
- Advanced -> SA -> VT-D enabled
- Advanced -> SA -> IOMMU enable during boot
- Advanced -> SA -> Memory Configuration -> Memory Remap enabled
- Advanced -> SA -> Graphics -> Primary Display PCIE
- Advanced -> Trusted Computing -> Security Device Support disabled
- Advanced -> PCI -> Above 4G decoding enabled
- Advanced -> PCI -> Resize BAR disabled
- Advanced -> USB -> XHCI Handoff enabled
- Advanced -> Onboard Devices -> Serial Port enabled
- Boot -> CSM disabled
- Boot -> Secure boot other OS, custom
- Boot -> Boot Configuration -> Fast Boot disabled

## Kexts

- AppleALC.kext
- CPUFriend.kext
- CPUFriendDataProvider.kext
- CpuTopologyRebuild.kext
- CpuTscSync.kext
- Lilu.kext
- LucyRTL8125Ethernet.kext
- NVMeFix.kext
- RestrictEvents.kext
- SMCProcessor.kext
- SMCSuperIO.kext
- USBToolBox.kext
- UTBMap.kext
- VirtualSMC.kext
- WhateverGreen.kext

## Working

- the machine boots, and show both displays
- accelerated graphics with native AMD driver
- sound works with alcid 11 (jack, USB audio, HDMI/DP audio)
- on board ethernet (RTL 8125) works with LucyRTL8125Ethernet.kext
- all USB ports work
- appletv+ playback with shikigva=128
- sleep/resume with following pmset options:

```
$ sudo pmset -g
Password:
System-wide power settings:
Currently in use:
 standby              0
 Sleep On Power Button 1
 womp                 0
 hibernatefile        /var/vm/sleepimage
 proximitywake        0
 powernap             0
 gpuswitch            2
 networkoversleep     0
 disksleep            0
 standbydelayhigh     86400
 sleep                0
 hibernatemode        0
 ttyskeepawake        0
 displaysleep         15
 tcpkeepalive         0
 highstandbythreshold 50
```

## Not Working

- nothing as far as I know.

I don't know about apple services like handover and stuff as I don't use those. As far as I know, these require WiFi and this machine doesn't have/need WiFi.
