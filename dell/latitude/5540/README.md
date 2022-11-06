# Dell Latitude 5540

## Hardware
- 4th Gen Intel® Core™  Core i5-4300U CPU @ 1.90GHz (3Mb cache, 2 cores, 4 threads, 1,90 to 2.9 Ghz Turbo)
- Intel® Haswell-ULT Integrated Graphics Controller
- Intel® Haswell-ULT HD Audio Controller
- Intel® Dual Band Wireless-AC 7260 & Ethernet Connection I218-LM
- 15.6" FHD (1920x1080) Non-Touch, Anti-Glare, 220nits
- 8GB, 2 x 4GB DDR3 1600MT/s
- Samsung® SSD 850 EVO 500GB
- Dimensions
	- Height: 1,11 in. (28,25 mm)
	- Width: 13,31 in. (338 mm)
	- Depth: 9,86 in. (250,50 mm)
	- Weight: 5,35 lbs. (2.42 kg)
- Power
  - 4 Cells, Battery DELL WGCW633 Li-ion 66.6 Wh
  - 65W Type-C EPEAT Adapter
- Ports
	- 1 RJ-45 Ethernet port
    - 2 USB 2 ports
	- 2 USB 3 ports
	- 1 HDMI 1.4 , 1 VGA
	- 1 Universal audio port

```shellsession
↳ lspci -nn
00:00.0 Host bridge [0600]: Intel Corporation Haswell-ULT DRAM Controller [8086:0a04] (rev 0b)
00:02.0 VGA compatible controller [0300]: Intel Corporation Haswell-ULT Integrated Graphics Controller [8086:0a16] (rev 0b)
00:03.0 Audio device [0403]: Intel Corporation Haswell-ULT HD Audio Controller [8086:0a0c] (rev 0b)
00:14.0 USB controller [0c03]: Intel Corporation 8 Series USB xHCI HC [8086:9c31] (rev 04)
00:16.0 Communication controller [0780]: Intel Corporation 8 Series HECI #0 [8086:9c3a] (rev 04)
00:16.3 Serial controller [0700]: Intel Corporation 8 Series HECI KT [8086:9c3d] (rev 04)
00:19.0 Ethernet controller [0200]: Intel Corporation Ethernet Connection I218-LM [8086:155a] (rev 04)
00:1b.0 Audio device [0403]: Intel Corporation 8 Series HD Audio Controller [8086:9c20] (rev 04)
00:1c.0 PCI bridge [0604]: Intel Corporation 8 Series PCI Express Root Port 1 [8086:9c10] (rev e4)
00:1c.3 PCI bridge [0604]: Intel Corporation 8 Series PCI Express Root Port 4 [8086:9c16] (rev e4)
00:1c.4 PCI bridge [0604]: Intel Corporation 8 Series PCI Express Root Port 5 [8086:9c18] (rev e4)
00:1d.0 USB controller [0c03]: Intel Corporation 8 Series USB EHCI #1 [8086:9c26] (rev 04)
00:1f.0 ISA bridge [0601]: Intel Corporation 8 Series LPC Controller [8086:9c43] (rev 04)
00:1f.2 RAID bus controller [0104]: Intel Corporation 82801 Mobile SATA Controller [RAID mode] [8086:282a] (rev 04)
00:1f.3 SMBus [0c05]: Intel Corporation 8 Series SMBus Controller [8086:9c22] (rev 04)
01:00.0 SD Host controller [0805]: O2 Micro, Inc. SD/MMC Card Reader Controller [1217:8520] (rev 01)
02:00.0 Network controller [0280]: Intel Corporation Wireless 7260 [8086:08b1] (rev 73)
```

## Firmware Upgrade Manager

_Dell Latitude 5540_ seems not to be supported by [fwupd](https://fwupd.org), as it isn't found in the [device list](https://fwupd.org/lvfs/devices/).

## Other Stuff

Here I list a few useful things from other configs. As I don't fully understand the implications I didn't enable them.

- `services.throttled.enable`: a fix for Intel CPU throttling
- `boot.blacklistedKernelModules = [ "psmouse" ];`: "touchpad goes over i2c" (whatever that means)
- `boot.blacklistedKernelModules = [ "firewire_ohci" ];`: fix for SD card reader (from the [Arch Wiki](https://wiki.archlinux.org/title/Dell_Latitude_E5540))
- `boot.kernelParams = [ "mem_sleep_default=deep" ];`: Force S3 sleep mode to preserve battery during sleep

