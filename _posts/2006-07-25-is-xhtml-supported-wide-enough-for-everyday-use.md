---
wpid: 115
title: Is XHTML supported wide enough for everyday use?
date: 2006-07-25T11:23:22+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=115
permalink: /115/is-xhtml-supported-wide-enough-for-everyday-use/
dsq_thread_id:
  - "6089091882"
categories:
  - English
---
Today I stumbled upon [an article by Lachlan Hunt which lists some of the problems with using XHTML for webpages](http://lachy.id.au/log/2005/12/xhtml-beginners). After having read through it, I was nearly ready to reimplement my XHTML pages in HTML&#8230; The main cause for this was IE&#8217;s lack of support for application/xhtml+xml content. It won&#8217;t render it, but instead provides you with a standard download dialog. Serving XHTML as text/html, like most people do nowadays is actually fooling older user agents (like IE) to treat the page as good ole&#8217; HTML. But there were a lot of other issues with XHTML I didn&#8217;t like the sound of either.

This would actually make my employer have to use HTML Transitional, since some of the ad serving is done using <iframe>, which isn&#8217;t allowed in the strict doctypes. [You can read more on the differences between strict and transitional markup here](http://24ways.org/advent/transitional-vs-strict-markup). I might be arrogant, but HTML4 Transitional sounds a bit too nineties for me to accept, even if it _is_ an acknowledged standard. ;-)

Luckily, the XHTML specs states that [text/html is ok to use for XHTML documents](http://www.w3.org/TR/xhtml1/#media), and they even included [a thorough appendix on how to make sure your XHTML document renders correctly in browsers that treat it like HTML](http://www.w3.org/TR/xhtml1/#guidelines). Very good reading, and it contained several implications I weren&#8217;t aware of!

_Edit 1:_ There&#8217;s [an article over at workingwith.me.uk about sending mime headers depending on what the user agent supports](http://www.workingwith.me.uk/articles/scripting/mimetypes). Highly recommended reading. Works like a charm here. :) Though I was a bit shocked to notice that W3C&#8217;s validator doesn&#8217;t send the correct ACCEPT-headers.

_Edit 2:_ W3C has [a table with the definitive overview of contenttypes for the differenct specs](http://www.w3.org/TR/xhtml-media-types/#summary).

_Edit 3:_ The code from www.workingwith.me.uk har some bugs if a browser explicitly states it does NOT want application/xhtml+xml. I rewrote my handling using some code from [www.autisticcuckoo.net](http://www.autisticcuckoo.net/archive.php?id=2004/11/03/content-negotiation) which seems to work more reliably (setting Q to 1 as default).
