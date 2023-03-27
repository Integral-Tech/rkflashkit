rkflashkit
==========

rkflashkit is an open sourced (GPL v2) toolkit for flashing Linux kernel images (Picuntu) to rk3066/rk3188/rk3288 based devices. It's programmed with python and gtk3. The kernel program is adapted from Galland's rkflashtool_rk3066 which is in turn based on cyteen's rk3066-rkflashtool.

rkflashkit talks to the devices through vpelletier's python-libusb1 which is a python wrapper of libusb. For convenience the python-libusb1 programs are included in rkflashkit. Also included is binary created for Ubuntu.


Features
========
* Programmed with python, GTK3 and libusb1.
* Automatically detect device connection.
* Reboot device.
* Flash kernel image file to specified partition.
* Erase partition.
* Backup partition. (New)
* Compare a partition with a image file. (New)
* Command line support. (New)

Change logs:
============

Release 0.1.5-dev:
* Add support Python3.
* Add support GTK3.

Release 0.1.4:
* Add support for RK3128.
* Add last partition ('-' in size) operation support.
* Clean prompt and log messages.

Release 0.1.3:
* Add support for RK3026/RK3028/RK3168.

Release 0.1.2:
* Add command line support.

Release 0.1.1:
* Sticky scrollbar in log view: when appending logs keep scrollbar at the bottom if it's already there.
* Partition backup function.
* Validation for flashing image file to partition.
* Compare a partition with any image file.
* Colored log messages.


Release 0.1.0:
* Initial import.


Build
=====

$ ./waf debian


Installation
============

Before installing the deb file please install its dependency:

$ sudo apt-get install python3-gi python3-libusb1

then

$ sudo dpkg -i rkflashkit_0.1.5_all.deb

You should be able to find an icon in unity dasher or gnome menu.


Links
=====
    https://github.com/Galland/rkflashtool_rk3066
    https://github.com/cyteen/rk3066-rkflashtool
    https://github.com/vpelletier/python-libusb1


Command line usage
==================

* List NAND Partitions
>$ sudo rkflashkit part

* Flash image
>$ sudo rkflashkit flash @boot boot.img @resource resourse.img

* Compare partition with image file
>$ sudo rkflashkit cmp @boot boot.img

* Backup partition
>$ sudo rkflashkit backup @boot new_boot.img

* Erase Partition
>$ sudo rkflashkit erase @boot

* Reboot Device
>$ sudo rkflashkit reboot

Multiple commands can be specified at once:
>$ sudo rkflashkit flash @boot boot.img @resource resourse.img reboot
