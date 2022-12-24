# Linux on Huawei MateBook 13 (2020)

> Brain dump: MateBook 13 (Wright-W19) running Debian heavily inspired by [lidel's documentation of running Linux on MateBook X](https://github.com/lidel/linux-on-huawei-matebook-x-2017).

## Background

Huawei MateBook 13, released in 2019, has at least two modifications (different CPUs, integrated vs. dedicated graphics). Both come with Microsoft Windows 10 and there initially was no information at all concerning Linux support.

I am running Debian on the more simple MateBook 13 variant, model Wright-W19. This repository documents what works and what does not.

[Reportedly](https://github.com/nekr0z/linux-on-huawei-matebook-13-2019/issues/21), it also holds true for at least one 2020 Huawei Matebook 13 (AMD Ryzen 5 3500) running Elementary OS.

If you like this page and want it to get even better and more useful, feel free to contribute issues and pull requests, or just [buy me a coffee](https://www.buymeacoffee.com/nekr0z).

## Linux Support Matrix

| Device | Model |  Works | Notes |
| --- | --- |  :---: | --- |
| Processor | Intel Core i5-10210U | ✅ Yes | 8 cores, power states etc seem to work out of the box |
| Graphics | Intel UHD Graphics 620 | ✅ Yes | via standard kernel driver |
| Graphics | Nvidia MX 250 | ✅ Yes | via standard kernel driver |
| Memory | 8192 MB | ✅ Yes |  |
| Display | 13 inch 2:3, 2160x1440 (2K) | ✅ Yes | resolution is correctly detected by `xrandr`, backlight control works via native function keys and can be controlled by KDE settings, see [below](#display) for details on scaling issues |
| Storage | Samsung SSD, 512 GB | ✅ Yes | via standard kernel driver |
| Wifi | Intel Wireless-AC 9462 (a/b/g/n/ac) | ✅ Yes |
| Bluetooth | Intel Bluetooth 5.0| ✅ Yes | works as expected |
| Soundcard  | Intel Cannon Point-LP High Definition Audio | ✅ Yes  | see [below](#soundcard) for details |
| Speakers  |  | ✅ Yes |  |
| Microphone | | ✅ Yes | out of the box |
| Webcam | HD Camera (13D3:56C6) | ✅ Yes | works out of the box, indicating light too |
| Ports | 2 × USB-C | ✔ Yes | charging works only via left port, external display only via right one, but it is a known hardware limitation of the laptop |
| Power button |  | ✔ Yes | needs to be pressed for at least a second to generate event |
| Fingerprint Reader | Goodix GXFP5187 | ❌ No | located on the power button, see [below](#fingerprint-reader) for details  |
| Battery | Dynapack HB4593J6ECW (42 Wh) | ✔ Yes | see [below](#battery) for details |
| Lid | ACPI-compliant |  ✅ Yes | works as expected, though ACPI complains in logs |
| Power management | | ✅ Yes | works, see [below](#power-management) for details |
| Keyboard |  | ✅ Yes | [see below](#keyboard) for details |
| Touchpad | ELAN962C:00 04F3:30D0 | ✔ Yes | touchpad is detected and works in KDE (though not in Debian installer), [see below](#touchpad) for details |
| Port Extender | MateDock 2 dongle included with the laptop | ✔ Yes | D-SUB, full-size HDMI, USB-C and USB-A work as expected |

## What's working  💻
  
Type | Status
:---------|:---------
Turbo boost and CPU frequency stage |  ✅  
Intel UHD Graphics 620              |  ✅  
Brightness control                  |  ✅  
HDMI                                |  ✅  
Audio Realtek ALC256            |  ✅  
Intel Wireless-AC 9462 Wi-Fi and Bluetooth, Handoff, iMessage...         |  ✅  
2 Type-C Port       |  ✅  
Touchpad (14 gestures are working)   |  ✅  
Battery status   |  ✅  
Shutdown / Reboot   |  ✅  
Fn shortcut keys   |  ✅  
S3 Sleep / Wake   |  ✅
S4 Hibernation / Wake   |  ✅

## What's not working 💻
  
Type | Info | Status
:---------|:---------|:----------
Fingerprint | Not supported in Linux | ❌
