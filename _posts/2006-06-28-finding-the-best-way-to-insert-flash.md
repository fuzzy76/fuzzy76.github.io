---
wpid: 106
title: Finding the best way to insert Flash
date: 2006-06-28T10:05:02+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=106
permalink: /106/finding-the-best-way-to-insert-flash/
dsq_thread_id:
  - "6089092038"
categories:
  - English
---
In my earlier days (before I switched from Opera to Firefox, now I use the AdBlock Plus Firefox extension to block ads) I used to surf the web with Flash disabled. I was actually quite shocked to notice how many websites that just didn&#8217;t display _anything_ when read though a browser without Flash support. This might be fixed by what I am about to discuss here, but it&#8217;s not my main point.

Have you ever tried validating a page with Flash in it? Chances are it didn&#8217;t validate. Even [Adobes official material on how to embed Flash](http://www.adobe.com/cfusion/knowledgebase/index.cfm?id=tn_4150) encourages use of the <embed> tag, which is **not** a valid tag in any of the W3C specs for markup languages on the web. It&#8217;s a Netscape invention, and it actually took quite some time until the Mozilla-based browsers managed to support the <object> tag in a satisfactory fashion. Frustrated with this fact, I started Googling, and this opened up a can of worms, as Internet Explorer didn&#8217;t fully support the <object> tag in a standard-conforming way either&#8230;

All I really wanted was a way that&#8230;

  * Was completely valid (X)HTML.
  * Sent the user to the Flash download center if the Flash plugin is missing or out of date.
  * Did not require JavaScript running in the browser in order to display the Flash. More and more people (mostly geeks) actually surf with JavaScript disabled.
  * Didn&#8217;t use the IE-specific conditional construct <!&#8211;[if !IE]> <&#8211;> (I don&#8217;t like browser-specific coding, even if it doesn&#8217;t break the standard).

<!--more-->

The first solution I found was called [Flash Satay by Drew McLellan](http://alistapart.com/articles/flashsatay/). He basically started tweaking the object tag until all major browers managed to display the Flash content. While this sounds nice at first look, it does have several limitations. Internet Explorer won&#8217;t stream the Flash but insists on reading the entire contents before starting it. If the user doesn&#8217;t have Flash or an outdated Flash player, it just comes out blank. The last problem can be fixed by adding a blank &#8220;dummy&#8221; Flash file with a IE-specific construct that will do auto-install.

The second one was [a piece of code by Ian Hickson](http://ln.hixie.ch/?start=1081798064&count=1) that looked nice and clean, but unfortunately was very poorly documented (he doesn&#8217;t mention what browsers it has been tested in at all) and did use the IE specific comment-conditionals that I was set to avoid if at all possible.

The third (and last) returned solution was [a small JavaScript thingy called SWFObject by Geoff Stearns](http://blog.deconcept.com/swfobject/). While my employer doesn&#8217;t have statistics on JavaScript usage among its users, I absolutely will not go for a solution that requires JavaScript in order to display anything. I&#8217;ve burned myself before on a similar choice before. ;)

But if you combine these, you will get a fairly nice setup. The big plus for SWFObject is that you define a <div> with content, and that content will be replaced with the Flash file if and only if SWFObject manages to do so. So if the <div> contains the Flash Satay method wrapped inside <noscript> I will have a nice fall-back for users without JavaScript. I&#8217;m also guessing that people likely to turn off JavaScript are likely to have an up to date Flash player anyway, if they haven&#8217;t disabled Flash as well.

And for people with Flash completely disabled, the <object> tag itself has a nice fallback builtin. The _content_ of an <object> tag is rendered in place of the object if the object can&#8217;t be displayed. So any animated gif or textual message I want shown to those users is placed within the Flash Satay code which in turn is within the <div> that SWFObject operates on!

Example code (assumes swfobject.js is included in your header):

<pre>&lt;div id="myflash_container"&gt;
  &lt;script type="text/javascript"&gt;
    &lt;![CDATA[
    // This is shown if we have JS support, but swfobject couldn't find a Flash plugin
    document.write('&lt;div style="width: 150px; height: 150px;
background-color: #000000;"&gt;');
    document.write('&lt;a href="http://www.adobe.com/go/gntray_dl_getflashplayer"&gt;');
    document.write('Get Flash player to view this content&lt;/a&gt;&lt;/div&gt;');
    ]]&gt;
  &lt;/script&gt;
  &lt;noscript&gt;
    &lt;!-- For browsers without JS support use Flash Satay for fallback --&gt;
    &lt;object type="application/x-shockwave-flash" data="testflash.swf" width="150"
height="150"&gt;
      &lt;param name="movie" value="testflash.swf" /&gt;
      &lt;div style="width: 150px; 
height: 150px; background-color: #000000;"&gt;
        &lt;a href="http://www.adobe.com/go/gntray_dl_getflashplayer"&gt;
          Get Flash player to view this content
        &lt;/a&gt;
      &lt;/div&gt;
    &lt;/object&gt;
  &lt;/noscript&gt;
&lt;/div&gt;
&lt;script type="text/javascript"&gt;
  var so = new SWFObject("testflash.swf", "myflash", "150", "150", "7", "#000000");
  so.write("myflash_container");
&lt;/script&gt;

</pre>

If you wonder why I have to use the <nocscript> tag the reason is simple. Otherwise Flash Satay would display the Flash content on load, only to have it instantly replaced with the same Flash by SWFObject. This would without doubt put some strain on the clients at load.

I haven&#8217;t tested this extensively, but Firefox 1.5 (with and without JS), Opera 8.5 (with and without JS), IE 5.0, IE 5.5 and IE 6 all showed the Flash in all its glory. If you have problems making it work, feel free to let me know.

Since most of the development at my current job is done in JSP, I will (in due time) make my own taglib for using this technique. Doesn&#8217;t <flash:insert name=&#8221;myflash&#8221; file=&#8221;testflash.swf&#8221; width=&#8221;150&#8243; height=&#8221;150&#8243; version=&#8221;7&#8243; background=&#8221;#000000&#8243; /> sound good to you too? ;) A small PHP function would probably take a couple of minutes to whip up.

_Addendum:_ If you want SWFObject to work in IE4 and NS4 you need to add the following (before you include swfobject.js in the header is probably a good bet):

<pre>&lt;script language="JavaScript" type="text/javascript"&gt;
  if(document.all && !document.getElementById) { /*ie4*/
    document.getElementById= function(id) {
      return(document.all(id));
    }
    document.getElementsByTagName= function(id) {
      return(document.all.tags(id));
    }
  }

  if(document.layers) { /*ns4*/
    document.getElementById= function(id) {
      return(document.layers[id]);
    }
  }
&lt;/script&gt;

</pre>
