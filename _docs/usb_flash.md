---
layout: docs
status: publish
published: true
permalink: /docs/usb_flash/
title: Bootable USB Flash Drive Creation
author:
  display_name: demm
  login: demm
  email: demm@kaosx.us
  url: ''
author_login: demm
author_email: demm@kaosx.us
wordpress_id: 362
wordpress_url: http://www.kde-os.tk/?page_id=362
date: '2013-07-16 15:50:31 -0400'
date_gmt: '2013-07-16 15:50:31 -0400'
categories: []
tags: []
comments: []
---
### ![Drive - USB](/wp-content/uploads/2013/07/Drive-USB-150x150.png){: .alignleft .size-thumbnail} Preparation

In order to put a KaOS ISO image onto an USB flash drive, you will need a drive capable of storing 1.4 Gb, a system with USB ports and some specialized software.

Make sure the system where you will boot the USB flash drive from, has USB ports and can boot USB flash drives.  Before following any steps, make sure the device is plugged in but not mounted.

### Windows

#### ROSA Image Writer

[ROSA Image Writer](http://wiki.rosalab.com/en/index.php/Blog:ROSA_Planet/ROSA_Image_Writer){: .button-link .button target="_blank"} is one option for Windows, follow the instructions from this Wiki, and get the actual application [here](http://wiki.rosalab.com/en/images/6/65/RosaImageWriter-2.6.1-win.zip).

#### SUSE Studio ImageWriter

[ImageWriter](https://github.com/downloads/openSUSE/kiwi/ImageWriter.exe){: .button-link .button target="_blank"}

Another option for Windows is ImageWriter. Open the SUSE Studio ImageWriter and either drag the KaOS ISO image into it, or press the Select button and find the KaOS ISO image.<br />
Select your USB stick and click the Write button.</p>

#### From Windows command line
[dd](http://www.chrysocome.net/downloads/dd-0.5.zip){: .button-link .button target="_blank"}

You need to download dd which is a common program with the primary purpose of low-level copying of raw data.

Once installed, open the command prompt and type (substitute the correct path):

```
dd.exe if=/path/to/the/downloaded/iso of=/path/to/the/USB/device
```

### Linux Distributions

#### SUSE Studio ImageWriter

The application to use is [ImageWriter](/packages/index.php?act=search&amp;subdir=&amp;sortby=date&amp;order=descending&amp;searchpattern=imagewriter), available in the KaOS repository and installed by default. **Unetbootin is NOT compatible with KaOS.** After opening SUSE Studio ImageWriter:

* Drag the downloaded ISO into imagewriter, or browse to the directory containing the ISO
* Connect your USB stick
* Check the shown path is correct
* <span style="font-size: 13px;">Click the Write button.</span>

#### Using the command line

In order to create a bootable USB flash drive, you will need `coreutils` (which provides `dd`). Most GNU distributions have `coreutils` already installed.

To use dd, open a terminal and write (substitute the correct path):

```
sudo dd if=/path/to/the/downloaded/iso of=/path/to/the/USB/device
```

To check if the creation of the bootable USB stick was successful, use `fdisk` as root to check it. You should see an asterisk (*) like this in your USB line:

```
Device Boot Start End Blocks Id System
/dev/sdb1 * 1 697 713728 17 Hidden HPFS/NTFS
```