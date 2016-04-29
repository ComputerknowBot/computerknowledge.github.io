---
layout: post
category: article
title:  "The real story of Stuxnet"
date: 2013-07-28 15:26:25 +0530
meta: "Stuxnet is a computer worm discovered in June 2010 that is believed to have been created by the United States and Israel to attack Iran's nuclear facilities."
image: 2013/07/28/stuxnet-c.jpg
permalink: /article/the-real-story-of-stuxnet
author: Ritesh Shrivastav
tags:
  - "computer-virus"
---
<div class="row">
  <div class="col-sm-6">
    Stuxnet is a computer worm discovered in June 2010 that is believed to have been created by the United States and Israel to attack Iran's nuclear facilities. Stuxnet initially spreads via Microsoft Windows, and targets Siemens industrial control systems. While it is not the first time that hackers have targeted industrial systems, it is the first discoveredmalware that spies on and subverts industrial systems, and the first to include a programmable logic controller (PLC) rootkit.
  </div>
  <div class="col-sm-6">
    <img src="{{ site.url }}/resources/2013/07/28/stuxnet.jpg" alt="" class="img-responsive">
  </div>
</div>

Stuxnet is a computer worm that targets the types of industrial control systems (ICS) that are commonly used in infrastructure supporting facilities (i.e. power plants, water treatment facilities, gas lines, etc).

Stuxnet is designed to programmatically alter Programmable Logic Controllers (PLCs) used in those facilities. In an ICS environment, the PLCs automate industrial type tasks such as regulating flow rate to maintain pressure and temperature controls.

For security reasons, many of the hardware devices used in industrial control systems (ICS) are not Internet-connected (and often not network connected). To counter this, the Stuxnet worm incorporates several sophisticated means of propagation with the goal of eventually reaching and infecting STEP 7 project files used to program the PLC devices.

But stuxnet could spread stealthily between computers running Windows—even those not connected to the Internet. If a worker stuck a USB thumb drive into an infected machine, Stuxnet could, well, worm its way onto it, then spread onto the next machine that read that USB drive. Because someone could unsuspectingly infect a machine this way, letting the worm proliferate over local area networks, experts feared that the malware had perhaps gone wild across the world.

For initial propagation purposes, the worm targets computers running the Windows operating systems. However, the PLC itself is not a Windows-based system but rather a proprietary machine-language device. Hence Stuxnet simply traverses Windows computers in order to get to the systems that manage the PLCs, upon which it renders its payload. (For specific information on the Windows spread of the worm, see How Does Stuxnet Spread?).

To reprogram the PLC, the Stuxnet worm seeks out and infects STEP 7 project files. STEP 7 project files are used by Siemens SIMATIC WinCC, A supervisory control and data acquisition (SCADA) and human-machine interface (HMI) system used to program the PLCs.

Stuxnet contains various routines to identify the specific PLC model. This model check is necessary as machine level instructions will vary on different PLC devices. Once the target device has been identified and infected, Stuxnet gains the control to intercept all data flowing into or out of the PLC, including the ability to tamper with that data.

The serious nature of the Stuxnet worm has led to no end of speculation and conjecture.