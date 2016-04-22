---
layout: post
category: article
title:  "Changing MBR to GPT in Mac OS X"
date: 2013-09-07 18:20:25 +0530
permalink: /article/changing-mbr-to-gpt-in-mac-os-x
author: Ritesh Shrivastav
tags:
  - mbr
  - gpt
  - gdisk
---

First for installing the windows operating system in Apple Macbooks, we must convert the partitioning scheme from GPT(GUID Partition Table) to MBR(Master Boot Record). The conversion can be carried out by the tool [gdisk](http://www.rodsbooks.com/gdisk/){:target="_blank"}. The documentation they have provided is well written for the particular operation. Now let's discuss, why do?

### What is the advantage of GPT disk?
GPT disks can grow to a very large size. Break the 2TB limit of MBR disk. GPT disks allow an almost unlimited number of partitions. Each GPT partition has a unique identification GUID and a partition content type. And you can have more primary partitions. However, the Windows implementation restricts this to 128 partitions.
Another purpose of mine is that, I wanted to resize and modify the partition with the [Disk Utility](http://en.wikipedia.org/wiki/Disk_Utility){:target="_blank"} tool but the options are disabled because my disk was in MBR partition.

### How to change MBR to GPT
I ended up using gdisk to convert the partition. I issued:

``` bash
  sudo gdisk /dev/disk0
```

And you might be greeted with this warning:

``` bash
  Partition table scan:
  MBR: MBR only
  BSD: not present
  APM: not present
  GPT: not present

  ***************************************************************
  Found invalid GPT and valid MBR; converting MBR to GPT format.
  THIS OPERATON IS POTENTIALLY DESTRUCTIVE! Exit by typing 'q' if
  you don't want to convert your MBR partitions to GPT format!
  ***************************************************************

  Command (? for help):
```

After backing up my data, I wrote the partition table with the changes gdisk made automatically, quit (w, then q), and rebooted.
Booting may be normal, but when you will try to resize the partition table with Disk Utility, you may get a minor volume header error.

``` bash
  Verifying volume "Mac OS X"
  Performing live verification.
  Checking Journaled HFS Plus Volume.
  Checking catalog file.
  Checking multi-linked files.
  Checking extended attributes file.
  Incorrect number of extended attributes
  (It should be 245871 instead of 245862)
  Checking volume bitmap.
  Checking volume information.
  The volume Mac OS X was found to be corrupt and needs to be repaird
  Error: This disk needs to be repaired...then use Disk Utility to repair this disk
```

Then reboot and used -s to boot into single user mode. From there, use following command string -

``` bash
  /sbin/fsck -fy
```

Now all is well. Eh!! have problems, can be posted in comments.