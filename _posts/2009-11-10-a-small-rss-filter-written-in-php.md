---
wpid: 209
title: A small RSS filter written in PHP
date: 2009-11-10T16:53:07+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=209
permalink: /209/a-small-rss-filter-written-in-php/
dsq_thread_id:
  - "6089092163"
categories:
  - English
---
Nearly all news sources has some posts I&#8217;m not interested in. I can&#8217;t believe no RSS readers has implemented good enough filters yet. But I anyway I wrote my own. :) I don&#8217;t think my server can handle too much usage, so I&#8217;m just giving you the code as is.
  
<!--more-->

**edit:** The code is now on [GitHub](https://github.com/fuzzy76/rssfilter)!

Install to a PHP5 server and use like this (fictional example):

`http://yourserver.com/rssfilter/index.php?input=http%3A%2F%2Fvg.no%2Ffeed&categories%5B%5D=Sport&categories%5B%5D=Rampelys`

The script returns a RSS feed with only entries in one of the chosen categories. It does no caching or header support, so it uses much more resources than necessary. That&#8217;s why I don&#8217;t tell where my personal installation is. :)
