---
wpid: 250
title: A gameserver ping plugin for Munin
date: 2010-04-22T21:11:29+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=250
permalink: /250/a-gameserver-ping-plugin-for-munin/
dsq_thread_id:
  - "6089092207"
categories:
  - English
---
My personal server has been acting up lately, to be precise; the Call of Duty (1) gameserver that runs on it. I installed [Munin](http://munin-monitoring.org/) for monitoring it, but really wanted something that would show the actual slowdown the players experienced.

So I did a Munin plugin. In PHP ofcourse. ;) It&#8217;s my first Munin plugin, and I wouldn&#8217;t be surprised if it turns out to be the only one written in PHP. It&#8217;s available for download at [Munin Exchange](http://muninexchange.projects.linpro.no/?search&cid=40&pid=566), and the code is here for those that just want a quick look.

**Update 27.04.10:** Updated the plugin to v1.1.

**Update 03.07.15:** Updated the plugin to v1.11 and moved to GitHub.

**The code is now at <https://github.com/fuzzy76/munin_qstatping>**
