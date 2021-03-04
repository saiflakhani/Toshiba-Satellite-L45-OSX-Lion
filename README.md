# Toshiba-Satellite-L45-OSX-Lion
Instructions on how to Hackintosh the Toshiba Satellite L45

## Prerequisites
Access to a real mac or a hackintosh
Clone this repository


## Creating the USB Installer
This step is straightforward

- Grab iAtkos L2 (Plenty of sites where you'll find the torrent)
- Format a USB as MacOS Extended Journaled
- If you have the iAtkos ISO, convert it to a DMG, using this command: ```hdiutil convert /folder/folder/file.iso -format UDRW -o /folder/folder/file.dmg```
- Restore the DMG to the USB using Disk Utility
- Use the bootloader PKG in this repo to install Chameleon on the USB. Alternatively, you can also use Chimera
- That's it. Plug the USB in, and boot off it.

## Installing the OS

- iAtkos L2 will have customization options.
- Use the following:
  - SATA/IDE: INTEL SATA/IDE
  - 32 bit boot
  - 32 bit RTC
  - FakeSMC
  - Graphics Enabler = Yes
  - Sound: Voodoo HDA
  - PS/2
  - Generate P States
  - Laptop Hardware: Battery, Card Reader
  - Network: Wired Realtek 81xx
 
- Let it install. While it's installing, Grab the OS X 10.7.5 Combo Update
- When the install finishes, boot from the disk and you will get a garbled screen. Multiple boxes of display
- Make the resolution 800x600 and try and work with it, and get the combo update installed. DO NOT REBOOT
- Once the combo update finishes, Put the Graphics Drivers in a flash drive, and install all the packages, including the ethernet, but not WiFi.
- Now reboot.

## Post Install
- Now you should be greeted with a working QE/CI. Use the Kext Provided for WiFi, and install it using Kext Utility.
- Navigate to ```/System/Library/Extensions/RTL8187BI.kext``` --> Show package contents
- Use Plist Editor Pro to change all occurences of the number ```33161``` and replace it with ```33175```
- Use Kext utlity to fix permissions and rebuild cache, otherwise it won't load. 
- Reboot and you should have WiFi, PS2 and Graphics. Everything you need to work. 

## TODO
- Fix Sleep
