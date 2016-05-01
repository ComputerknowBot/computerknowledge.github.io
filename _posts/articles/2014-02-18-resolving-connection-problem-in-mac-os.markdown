---
layout: post
category: article
title:  "Resolving the connection problem in Mac OS X to any website"
date: 2014-02-18 05:25:25 +0530
permalink: /article/resolving-connection-problem-in-mac-os
author: Ritesh Shrivastav
---
While you are updating your website, or due to any reason if you are unable to open your website on your laptop or system. Is it not a funny situation? Developers may get frustrated with finding the bug that where is the problem. When they opened their website on any others system (using any other network connection) then they got surprise, that oh my website is working.

I'll suggest to trying each of the following steps, in order, until you’re able to connect again.

### Try another site or app
To make sure the problem isn’t restricted to just one website, try visiting another—preferably one that’s highly reliable, such as [Google.com](http://www.google.com/).

Similarly, to make sure the problem isn’t just your current app (such as your email program or Web browser), try connecting to the Internet with another app. If only one site seems to be having problems, try visiting [Down For Everyone Or Just Me](http://www.isitdownorjust.me/) and entering the problematic site’s URL. The service will tell you whether computers elsewhere on the Internet can successfully connect to the site.

### Use Network Diagnostics
Certain types of network problems may cause your browser to display a Network Diagnostics button. This is OS X’s way of offering to help debug your connection problem, and I suggest accepting that help. (If you don’t see a button, you can launch Network Diagnostics manually. To do this, choose Apple menu > System Preferences and click Network. Click Assist me, and then click Diagnostics.)
The Network Diagnostics utility will guide you through a series of questions and tests, ranging from checking your ethernet or Wi-Fi connection to network configuration and DNS servers. Sometimes the utility can repair problems itself; when it can’t, it usually provides more detailed information about the nature of the problem and offers suggestions for solving it.

### Nudge Wi-Fi back to life
If your Mac connects to the Internet via Wi-Fi, check the Wi-Fi menu (at the top right of your screen) to make sure you’re connected to the network you intend to be. Macs have been known to hop onto less-desirable networks at inconvenient times.

If the menu’s icon has an exclamation point, indicating that it can’t successfully connect to any network, try choosing Turn Wi-Fi Off from the menu, waiting about 30 seconds, and then choosing Turn Wi-Fi On. If that still doesn’t work, restart your Mac. Sometimes that’s the only way to clear wacky errors that prevent Wi-Fi from connecting.

### Try another device
If you have access to another computer or mobile device that uses the same Internet connection, check to see if you can connect to a website on that device. If not, you can at least rule out your Mac as the source of the problem and look elsewhere for a solution. But if the other device can connect and your Mac can’t, even after a restart, skip ahead to the step “Check your DNS settings.”

### Reset your router
For network problems that lie beyond your Mac, if you own or control the network device your Mac connects to (such as an AirPort base station, Time Capsule, router, switch, or hub), turn that device off, wait about 10 seconds, and turn it back on again. Wait for it to power on completely (sometimes a multistep process that can take several minutes) and try connecting again.
If there’s more than one such device between you and the Internet—for example, an AirPort Express connected to a cable modem—start with the one closest to the Internet and then work your way back to your Mac, cycling the power on each one as you go.

### Check your DNS settings
The Domain Name System (DNS) enables your Mac to convert domain names (like [apple.com](https://apple.com)) into IP addresses (like 17.172.224.47). If the DNS server your Mac uses is offline, slow, or faulty, you may be unable to connect to any site or service by name. Here’s an easy way to check whether DNS is functional if no websites, such as google.com, respond. In your browser, type in this URL: http://74.125.230.243. That should bring up the Google website. If it does, then you know your Internet connection itself is fine and the problem is merely looking up domain names.

To fix that problem, open the Network pane of System Preferences and select your network connection in the list on the left. Click Advanced followed by DNS. In the DNS Servers field, you should see one or more IP addresses. If those addresses are enabled (black, as opposed to gray), select each one in turn and click the minus-sign (-) button. Then, regardless of whether there are already addresses there in gray, click the plus-sign (+) button and enter 208.67.222.220; repeat with 208.67.222.222.
Or furthermore, OpenDNS provides IPv6 DNS servers too. Your list of DNS Servers, should be the following -

```
208.67.222.222
2620:0:ccc::2
208.67.220.220
2620:0:ccd::2
```

or if your prefer using IPv6

```
2620:0:ccc::2
208.67.222.222
2620:0:ccd::2
208.67.220.220
```

(These addresses point to OpenDNS, a free DNS service that’s often more reliable than the default servers your ISP uses.) Click OK and then click Apply. Now try connecting again.

### Getting back online
Even after following all these steps, success isn’t guaranteed, because some outages could be beyond your control. Because of the distributed nature of the Internet, an equipment failure at an ISP can affect more than just that ISP’s customers. And on a larger scale, accidental damage to a major fiber optic cable can (and occasionally does) wipe out Internet access to a large region. So, sometimes the only solution to an Internet outage is to wait for it to be fixed. But if the problem lies beyond your local network, your ISP should at least be able to tell you the nature of the problem and an expected repair time.