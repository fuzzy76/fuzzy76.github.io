---
wpid: 145
title: 'Reorganizing my life&#8230; again'
date: 2007-04-28T14:09:20+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=145
permalink: /145/reorganizing-my-life-again/
categories:
  - English
---
During the last couple of months, GMail has had several hiccups. And when [Google homepage](http://hp.fuzzy76.net/archives/134-Google-Homepage-revisited.html) suddenly lost all my gadgets for two days recently, I figured I might look into the desktop application approach to organizing my life again. I&#8217;ve also experienced that having &#8220;tools&#8221; in the same browser that contains tabs with social networks and news is pretty counter-productive in the long run. :)

<!--more-->

For quite a while, I&#8217;ve been using a free service called [ScheduleWorld](http://www.scheduleworld.com/) for syncing the calendar on my mobile phone against my Google Calendar. It&#8217;s a service that provides sync for calendars, notes, todo-items and contacts. It supports all of this through a J2ME app for mobile phones, SyncML (which most new phones support, including my Nokia N80), Google Calendar integration and a dedicated Mozilla Thunderbird plugin (there are SyncML plugins for Thunderbird, but the SyncML protocol is hard to get a perfect implementation of). The page also has a webinterface for all your data, so it&#8217;s easy to view your &#8220;stuff&#8221; even if all of your clients are unavailable.

It suddenly occured to me that I might as well move my data completely to this service instead of relying on several third parties for this. I installed [Mozilla Thunderbird](http://www.mozilla.com/en-US/thunderbird/), [Mozilla Lightning](http://www.mozilla.org/projects/calendar/lightning/) (a calendar/todo extension for Thunderbird) and the SW Thunderbird plugin and I was ready to go!

Ofcourse, once I set up my phone to synchronize contacts and imported the GMail address book into SW as well and they both showed up in Thunderbird, there was a lot of cleaning up to do. Thanks to the [Duplicate Contact Manager extension for Thunderbird](http://addons.mozilla.org/en-US/thunderbird/addon/2505) it didn&#8217;t took me long to clean it all up. Granted, I had to do 4-5 syncs between the phone and Thunderbird before the list was completely cleaned up, but it was definitely worth it. :)

And for mail, you might wonder? I still route all mail through GMail, but I&#8217;ve gone back to my old setup of [using my own Courier IMAP-server, which uses fetchmail to automatically fetch all GMail](http://hp.fuzzy76.net/archives/98-3-Horde.html). Importing everything back from GMail into the IMAP server was relatively easy, I just started fetchmail again and it churned away for an hour. Thankfully it started from the last date the account was accessed through POP3, which was when I stopped fetchmail on my server last autumn. :) Unfortunately, I did get quite a bit of duplicate messages after the import, but it was easily remedied by the [Remove Duplicate Messages extension for Thunderbird](http://addons.mozilla.org/en-US/firefox/addon/956) (2.0-compatible version available in the comments for the extension).

As an extra tip, I figured out a way to share config files between work and home aswell. I set up a folder in my home directory called &#8220;share&#8221;, which essentially is a [Subversion](http://subversion.tigris.org/) working copy. I keep my mail signatures there, so if I edit them at home, all I need to do is commit the changes and perform a update the next time I log in at work. :) Program settings can also be stored there, and all I need to do to get it working is symlinking the real config file to the one in my share folder. :)

So there you have it! Signatures, todo-items, calendars, address books and mail &#8211; all shared across home computer, work computer and mobile phone! :) If I&#8217;m on someone else&#8217;s computer I still have Horde to fall back on for reading email (or my WLAN-enabled Nokia N80 which comes with an IMAP reader), and ScheduleWorld&#8217;s web interface for my organizer.

_Warning:_ At the time of writing, ScheduleWorlds Thunderbird extension is not tested for Thunderbird 2.0. It worked for me (some phone numbers were &#8220;invisible&#8221; in Thunderbird, but were still present in both the web interface and on the phone), but other people have had problems with the combination.

_Alternative 1:_ Ofcourse, the snappiest way to get mail from GMail is to set GMail itself to forward the mails instead of using fetchmail. This also let you use any IMAP server (for instance if you company provided you with an IMAP account). Unfortunately, this wasn&#8217;t an option for me as my server can&#8217;t accept incoming mail traffic (so it&#8217;s purely a dummy server).

_Alternative 2:_ If you do not trust a third party with your calendar and mobile sync isn&#8217;t an issue for you, [Sync Kolab](http://www.gargan.org/extensions/synckolab.html) promises to sync all information across Thunderbird installations by using an IMAP folder. A pretty smart concept. :)
