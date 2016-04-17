---
layout: post
category: article
title:  "How to view HFS+ hard drives from Windows"
date: 2013-08-16 02:39:25 +0530
permalink: /article/how-to-view-hfs-hard-drives-from-windows
author: Ritesh Shrivastav
---
If you dual-boot your Hackintosh, you've probably noticed that Windows can't read hard drive partitions used by Mac OS X. Mac OS X uses the HFS+ hard drive format, which Windows doesn't support. Luckily, you can enable HFS+ support on Windows with the help of one or two Windows drivers (depending on your budget). Read past the break for a tutorial on how to access your Hackintosh's Mac OS X hard drive partition from Windows.
Having read/write access for your Mac partition on Windows will come in handy if your Hackintosh becomes unbootable, because you'll be able to boot into Windows to recover your files (and possibly fix your Hackintosh's boot problem). On top of that, it's simply convenient.

### Paragon HFS+ ($20)
[Paragon HFS+](http://www.paragon-software.com/home/hfs-windows/){:target="_blank"} ($20) is a Windows application that mounts all of your Mac hard drives in Windows Explorer (a.k.a. My Computer) and gives you read and write access. There's a 10-day trial available. Paragon HFS+ runs in the background and automatically starts on bootup, so accessing your Mac drives will feel exactly like accessing normal Windows drives.
Paragon is the same company that makes NTFS+ for Mac OS X , my recommended solution for enabling NTFS write support on Mac OS X Lion. If you're looking for an alternative to Paragon HFS+, then you can also consider [MacDrive](http://www.mediafour.com/products/macdrive){:target="_blank"} ($50; 5-day trial), which is the solution that I'm currently using on my own Hackintosh. It has a higher price tag and doesn't offer much more than Paragon HFS+, but it's an option. If purchasing apps is not an option for you, check out the following section.

### Apple Boot Camp Drivers (Free)
Apple's Boot Camp software is designed to help you run Windows on real Macs. Among other things, Boot Camp includes built-in HFS+ drivers for Windows. These drivers will mount your Mac hard drives in Windows Explorer and give you read access (but no write access). If you don't need to write any files to your Mac hard drives, using them is a free and relatively pain-free solution.
While the HFS+ drivers are normally packaged as part of Apple's Boot Camp Assistant software, you can download them separately.

### Notes
  - This method has only been confirmed to work with Windows 7 and Windows 8.
  - You must uninstall Paragon HFS+ or MacDrive from your computer before installing Apple's HFS+ drivers.
  - To uninstall Apple's HFS+ drivers, delete the two driver files from C:\Windows\System32\drivers. Restart your computer. Then, double-click on the "Remove_AppleHFS.reg" file to remove the drivers from your Windows registry.