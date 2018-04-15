---
wpid: 107
title: Remove Windows Genuine Advantage Notification
date: 2006-06-29T14:15:28+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=107
permalink: /107/remove-windows-genuine-advantage-notification/
categories:
  - English
---
After Microsoft pushed the [Windows Genuine Advantage Notification](http://support.microsoft.com/?kbid=905474) (hereafter refered to as WGAN) tool out using Windows Update a lot of people cried out in despair. While I actually sympathize with Microsoft for trying to protect their intellectual property, there were several things that didn&#8217;t quite sound right:

  * Microsoft originally assured the press that the tool could easily be uninstalled, but this was clearly not the case.
  * Without mentioning it in any documentation WGAN [send information about you and your computer to Microsoft once a day](http://www.windowssecrets.com/comp/060615/#story1).
  * Microsoft itself states in the user-agreement that WGAN is _beta_ software. Forcing users to install beta software doesn&#8217;t sound like anything a qualityminded software company would do. The fact that many people has received false notifications underscores this fact.
  * [The description of Automatic Update](http://www.microsoft.com/athome/security/protect/update.mspx) clearly states that it only installs high-priority updates crucial for the security of your computer, but this is clearly not how anyone would describe WGAN.

Luckily, I have set Automatic Update to notify me _before_ installing any updates, and I always select custom install so I can review the updates prior to installing them. This made me able to unselect WGAN for installation. Therefore my laptop is still free from spyware and beta software. I strongly advice everyone to do the same.

If however, you were one of the unlucky ones to get this piece of deceitful software on your system, I have the cure for you. Firewallleaktester.com has made [a utility called RemoveWGA](http://www.ghacks.net/2009/02/10/remove-wga-2/) which helps you remove the update from your system.
