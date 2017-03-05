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
  * Make some research on STM32F4 Discovery(I already have one, but haven't used.)
    * http://www.emcraft.com/som/stm32f7-usb-storage
  * Some changes from legacy gadget to configfs
    * https://events.linuxfoundation.org/sites/events/files/slides/LinuxConNA2013-andrzej.pietrasiewicz-usb-gadget-configfs_0.pdf
    * https://wiki.tizen.org/wiki/USB/Linux_USB_Layers/Configfs_Composite_Gadget/General_configuration
    * There are still many things I should study on......
  * I will try the STM32F4 tomorrow.
- 2017/2/5
  * Setup the environment on linux for STM32F4 Discovery
    * http://www.wolinlabs.com/blog/linux.stm32.discovery.gcc.html
  * Find some resources about STM32F4 and make it as USB device
    * I got some example, but cannot build sucessfully.
      * https://github.com/mfauzi/STM32F4/tree/master/STM32F4%20Discovery%20Software%20Examples/STM32F4xx_USB_Example/Project/USB_Device_Examples/MSC
      * (Maybe it is develop with STM32CUBE) http://www.keil.com/download/docs/362.asp
    * There is an example of USB mass storage host and descriptions of both.
      * http://wiki.csie.ncku.edu.tw/embedded/USB#usb-host-and-device
    * Still working on it......
- 2017/2/6
  * Another choice - STM32CUBE
    * Integerated many libraries and middleware for STM32 series.
    * Including USB device and WIFI module.
      * TCP/IP: http://www.st.com/content/ccc/resource/technical/document/user_manual/65/e8/20/db/16/36/45/f7/DM00103685.pdf/files/DM00103685.pdf/jcr:content/translations/en.DM00103685.pdf
      * USB device: http://www.st.com/content/ccc/resource/technical/document/user_manual/cf/38/e5/b5/dd/1d/4c/09/DM00108129.pdf/files/DM00108129.pdf/jcr:content/translations/en.DM00108129.pdf
      * IAP: http://www.st.com/content/ccc/resource/technical/document/user_manual/79/6e/5f/d4/5c/25/43/96/DM00103145.pdf/files/DM00103145.pdf/jcr:content/translations/en.DM00103145.pdf
      
- 2017/3/5
  * Since my linux notebook was broken, I haven't updated this note for a long time. In these days, I have tried STM32F429ZI nucleo, and successfully let it become a usb disk, however, since there wasn't an OS on it, it is difficult for me to develop more multitask applications on it. Though the problem might be solved by using mbed or FreeRTOS, I prefered to use linux gadget API framework. The question is to find a develop board with otg support and also with the driver support. Fortunately, I found a board that was given by a friend of mine two years ago totally fit the requirements! And it is Zedboard! As the result, I start to be familier to this board and build the system on it.
  * I will update the steps in detail later.
