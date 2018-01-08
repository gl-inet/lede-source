Overview
========

This repo adding patches for GL-B1300.

Prerequisites
=============

To build your own firmware you need to have access to a Linux, BSD or
MacOSX system (case-sensitive filesystem required). Cygwin will not be
supported because of the lack of case sensitiveness in the file system.
Ubuntu is usually recommended. Examples of package installations:

```bash  
$ sudo apt-get update
$ sudo apt-get install build-essential subversion libncurses5-dev zlib1g-dev gawk gcc-multilib flex git-core gettext libssl-dev
```

Download Sources
================

```
$ git clone https://github.com/gl-inet/lede-source.git && cd lede-source
$ ./scripts/feeds update -a
$ ./scripts/feeds install -a
```

Make Image
==========

Use "make menuconfig" to configure your image.

Choose the following target:
Target System (Qualcomm Atheros IPQ806X)  --->
Target Profile (GL.iNet GL-B1300)  --->

Simply running "make" will build your firmware. It will download all sources,
build the cross-compile toolchain, the kernel and all choosen applications.

Note that if you have all the source already, just put them in your *lede-source/dl*
folder and you save time to download resource.

Flash Image
===========
Method 1:
- use serial port to stop uboot
- uboot command: run lf

Method 2:
- push down reset button and power on
- wait until three leds constantly on then release
- upgrade by uboot web at http://192.168.1.1

Note: the sysupgrade image is 
bin/targets/ipq806x/generic/openwrt-ipq806x-GL-B1300-squashfs-sysupgrade.bin
it need to be renamed to **lede-gl-b1300.bin**

