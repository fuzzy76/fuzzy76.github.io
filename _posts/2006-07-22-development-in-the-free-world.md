---
wpid: 109
title: Development in the free world
date: 2006-07-22T20:26:00+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=109
permalink: /109/development-in-the-free-world/
categories:
  - English
---
Lately I&#8217;ve done some research for free (as in beer) development environments, both for web and Java. The result was, to put it blunt, a huge disappointment. What actually disappointed me more, was the [horrible pricing for commercial solutions](http://www.adobe.com/go/buydreamweaver) with no &#8220;personal use only&#8221; licenses available.

The &#8220;can do everything known to man but is like removing a lash in the eye with a shovel&#8221;-approach would ofcourse be [Eclipse](http://www.eclipse.org/) or [Netbeans](http://www.netbeans.org/), but after using them for a couple of days you loose all faith in using Java for creating large desktop applications. They&#8217;re essentially large and fancy texteditors with the possibility of launching external compilers. Why this task should need to require the good half of my 1 GB RAM is totally beyond me&#8230; Add to this a startup-time that matches that of the OS itself, and your productivity probably needs to be picked up from the floor by the time you&#8217;re ready to do some actual programming.

For smaller things I&#8217;ve found myself using [Notepad++](http://notepad-plus.sourceforge.net/) lately, and while it lacks a lot of automation it&#8217;s still the best Notepad replacement I&#8217;ve seen, so I advice you to give it a try none the less. But I was stilling missing some things in order to use it as a full IDE so I set out to test the competition. My wishlist went something like this:

  * Extendable
  * Open-source and actively developed
  * Syntax highlighting
  * Project- or filebrowser panel
  * Some sort of context-sensitive lookup
  * FTP support for web development
  * Shortcuts for build/run/preview
  * Should support the languages I use most (XML, Java, JSP (this one&#8217;s surprisingly rare!), PHP, HTML, CSS, JS and ideally Python)
  * [Subversion](http://subversion.tigris.org/) support

I don&#8217;t think I&#8217;m particularily picky, so why were there so few programs that managed to fill _half_ of these? I have no idea myself, but the only one that fitted the bill for me was [PSpad](http://www.pspad.com/). It supports a _ton_ of languages, but lets you define compilators, run commands and preview commands for each one yourself. The only things missing from my list are opensource (it&#8217;s closed but still freeware) and SVN support. But SVN updating isn&#8217;t something you do continously anyway, so [TortoiseSVN](http://tortoisesvn.tigris.org/) does the job fine for now. In addition you get macro support, chm-file help integration, class browser for several languages, integration against TopStyle CSS editor, direct FTP edit, template library, hex edit, export with highlight to RTF or HTML, HTML processor (tidy up or just compress), internal webbrowser and more. This one is truly my recommended download of the day! :)
