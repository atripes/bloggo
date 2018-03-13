---
layout: post
title: Lineage to Moto G5
description: A new phone means work. At least it should.
permalink: :title
---

I hate bloatware. All stock vendor software is spying bloatware that only exists for the benefit of the company selling the device. This is the description of countermeasure.

## Unlock Bootloader / Install Team Win Recovery Project

Requirements:
  * [adb and fastboot](http://d-h.st/n5I) (OSX version)
  * [TWRP](https://twrp.me/Devices/)

Connect your device and activate USB Debugging (in Developer Mode).
I had to find out a specific unlock key to provide to Lenovo in order to unlock my boot loader. If someone could tell me why the hell Lenovo is interested in shit that only and ONLY concerns me and my own property, please indulge me.

```
user@machine:~$ ./adb devices
user@machine:~$ ./adb reboot bootloader
user@machine:~$ ./fastboot oem get_unlock_data
user@machine:~$ ./fastboot oem unlock MY_OWN_PRIVATE_CODE
```
From here on it's getting the twrp recovery image flashed onto the device:
```
user@machine:~$ cp ~/Downloads/twrp-3.2.1-0-cedric.img ./recovery.img
user@machine:~$ ./fastboot flash recovery recovery.img
```
That's it, now the device reboots into TWRP.

## Install LineAge and GApps
Requirements:
  * [Lineage](https://download.lineageos.org/)
  * [GApps](http://opengapps.org/)

I used [Android File Transfer](https://www.android.com/filetransfer/) to move the zip files onto my sdcard (moto g5 hdd). Once on the device you can Install them using the TWRP GUI.

## Titanium Backup with Synology DSM

Get and pay for Titanium Backup. Setup a Synology DiskStation in your home and install CloudStation on your mobile device. Once you have that you can Backup all user settings and all applications to that CloudStation and have it synced with your home NAS. Which again can be (or should be) backed up to an encrypted offsite backup location. gl & hf.
