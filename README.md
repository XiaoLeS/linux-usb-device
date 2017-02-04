# linux-usb-device
This is a record of my research on making an embedded device be recognized as an USB disk for other devices.

## Platform
- The Embedded Device
  * ~~Raspberry Pi 3 (Model B)~~
    [UPDATE: It can not be used. https://www.raspberrypi.org/forums/viewtopic.php?f=63&t=15696]
  * Looking for a possible choice [EX: Raspberry Pi Zero]

## Daily Record
- 2017/2/3
  * Found a Linux-USB Gadget API Framework
    * http://www.linux-usb.org/gadget
  * Found that the Raspberry Pi 3 (Model B) cannot be used.
    * https://www.raspberrypi.org/forums/viewtopic.php?f=63&t=15696
  * Looking for other device...
  * New Keywords
    * What I want to do is called "USB gadget" or "USB slave"
- 2017/2/4
  * Found that the Raspberry Pi 3 (Model A) may be used, but it is hard. And the Raspberry Pi Zero might be a choice.
    * https://gist.github.com/gbaman/50b6cca61dd1c3f88f41
  * There are several steps to make the device become a Mass Storage Gadget.
    * http://www.linux-usb.org/gadget/file_storage.html
    * I've followed the steps with my laptop(Ubuntu 16.04), it seems to be lack of sth.(http://bugs.launchpad.net/ubuntu/+source/linux/+bug/1073089 the bottom reply)
    * I follow the steps to rebuild kernel, but failed.
      * http://wiki.openmoko.org/wiki/Building_Gadget_USB_Module
  * Make some research on Raspberry Pi Zero
    * http://blog.gbaman.info/?tag=g_mass_storage
  * Make some research on STM32F7 (I already have one, but haven't used.)
    * http://www.emcraft.com/som/stm32f7-usb-storage
  * Some changes from legacy gadget to configfs
    * https://events.linuxfoundation.org/sites/events/files/slides/LinuxConNA2013-andrzej.pietrasiewicz-usb-gadget-configfs_0.pdf
    * https://wiki.tizen.org/wiki/USB/Linux_USB_Layers/Configfs_Composite_Gadget/General_configuration
    * There are still many things I should study on......
  * I will try the STM32F7 tomorrow.
    
  * STM32F7

