# ARTLINE Home G43 running Hackintosh

This repository serves the purpose of keeping track my configuration for the specific device I own, but it might be useful for someone who uses the same hardware.

NOTE: I have removed my serial number and other private info from SMBIOS section
of `config.plist`, please follow guides (e.g.
[1](https://www.tonymacx86.com/threads/guide-how-to-configure-your-systems-smbios-correctly.198155/),
[2](https://www.macobserver.com/tips/deep-dive/hackintosh-messages/)) to fill
those with "correct" values.

## Hardware Specifications

[ARTLINE Home G43](http://artline.ua/kompyutery-artline/%D0%BC%D0%BE%D0%BD%D0%BE%D0%B1%D0%BB%D0%BE%D0%BA-artline-home-g43-g43v03-detail)
is an All-in-One computer built by a local Ukrainian company (ARTLINE) from commodity hardware:

* Motherboard: [Asus H310T2](https://www.asus.com/Motherboards/PRIME-H310T-R2-0/)
* CPU: [Intel 6-Core i5-8400 2.8-4.0Ghz (Coffee Lake)](https://ark.intel.com/content/www/us/en/ark/products/126687/intel-core-i5-8400-processor-9m-cache-up-to-4-00-ghz.html)
* Graphics: Intel UHD Graphics 630 (UHD630)
* RAM: 16Gb DDR4-2666 SODIMM
* Wi-Fi: Intel ??? 802.11AC+BT4.0 (replaced with Broadcom DW1560 BCM94352Z M.2)
* Storage: 240GB M.2 SSD
* Display: LVDS ARTLINE Home AiO M6 23,8" IPS FullHD 1920*1080 ([PANDA LC238LF1L](http://www.panelook.com/LC238LF1L_PANDA_23.8_CELL_overview_28791.html))

## Hackintosh

I have successfully run this setup on Mojave (10.14) for a half a year, and
upgraded to Catalina (10.15) in October, 2019.

WARNING: My config is a compilation of a number of configs I found on the
Internet and it might have useless items, but it works for me. My EFI setup for
Mojave did not work well for Catalina (after OTA update I booted to a screen
with "striped" Apple logos), so I did many trials and errors to find the new
config (ended up basing on [@xiaooloong's asrock_deskmini310_hackintosh
EFI](https://github.com/xiaooloong/asrock_deskmini310_hackintosh) with some of
the config.plist customizations from my old Mojave config.plist)

My failing attempts were based on others work, which I want to mention:

* [Vanilla Desktop Guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/config.plist-per-hardware/coffee-lake)
* [@littlegtplr's Coffee Lake builds](https://github.com/littlegtplr/Hackintosh-Clover-folder-for-Coffee-Lake-builds)
* [@PoomSmart's ASUS-FX504GE](https://github.com/PoomSmart/ASUS-FX504GE-Hackintosh)
* [Ongoing Status of Designare Z390 with i7-9700K](https://www.tonymacx86.com/threads/success-ongoing-status-of-designare-z390-with-i7-9700k.266065/)

### Works

* [x] Accelerated Graphics (it was a hassle to get LVDS display working)
* [x] Ethernet (RealtekRTL8111 kext works like a charm)
* [x] Wi-Fi (I had to replace Intel chip with a supported Broadcom one)
* [x] Bluetooth (it is the same chip as Wi-Fi)
* [x] AirDrop
* [x] Audio
* [x] Built-in speaker (I had to spoof the layout-id and found that 2, 18, and 53 layouts work for me)
* [x] Sleep and wake (it was not reliable with my Mojave setup, but it seems to be working 100% in Catalina)
* [x] Shutdown

### Does not work

*Please, [drop me an issue](https://github.com/frol/hackintosh-ARTLINE-Home-G43-Asus-H310T2-UHD630/issues) if you have a suggestion on how to fix these.*

* [] Reboot hangs (a short power button push finishes it)
* [] Backlight control

### Not tested

* [] HDMI
* [] DisplayPort
* [] Card Reader
