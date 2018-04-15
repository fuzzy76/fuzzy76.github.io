---
wpid: 147
title: Mac OS X tips
date: 2007-06-25T14:20:32+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=147
permalink: /147/mac-os-x-tips/
dsq_thread_id:
  - "6159256704"
categories:
  - English
---
A couple of things got me stumped when migrating to Mac, so I thought I&#8217;d just do a small post on them. :)

<!--more-->

Backspace won&#8217;t work through SSH
:   Insert `export TERM=linux` into ~/.profile. I dunno why Apple has decided to be retarded about this, but it REALLY bugged me.

System default encoding isn&#8217;t UTF-8
:   Norwegian input language is, for some reason, not enough. But there was an extended norwegian input locale that actually changed the default encoding to real UTF-8. Again a seemingly stupid default choice from Apple. It&#8217;s really about time you put the &#8220;Mac Roman&#8221; encoding to rest.

iChat can&#8217;t connect to MSN
:   I signed up for a Jabber server with MSN transport, and it works like a charm. :) [Jabber.no](http://www.jabber.no) comes highly recommended for norwegian users. The only downside is that you need to set the display names for the contacts manually. I just set the right address book vcard for my contacts.

I want pretty colors in the terminal
:   The OS X terminal is color-challenged by default. Add the following to ~/.profile:</p> 
    
        CLICOLOR=1
        LSCOLORS=ExFxCxDxBxegedabagacad
        export LSCOLORS CLICOLOR
    
    Source: [Mac1.no](http://mac1.no/switch)</dd> 
    
    Finder leaves .DS_Store files all over the place on remote servers.
    :   Just do a `defaults write com.apple.desktopservices DSDontWriteNetworkStores true` from the terminal and reboot.
    
    Mediacenters and home servers should never go to sleep
    :   My mediacenter would go to sleep if I wasn&#8217;t careful enough with the play button on the Apple Remote. And when I woke it up again, it wouldn&#8217;t always reconnect to the WLAN. `sudo pmset -a disablesleep 1` solved it. Sleep is now 100% disabled.
    
    OS X has completely broken support for pageup/pagedown/home/end
    :   The default behaviour for these keys are completely useless out of the box. Fix them by saving this to ~/Library/KeyBindings/DefaultKeyBinding.dict :</p> 
        
            {
                "\UF729"  = "moveToBeginningOfLine:";
                "$\UF729" = "moveToBeginningOfLineAndModifySelection:";
                "\UF72B"  = "moveToEndOfLine:";
                "$\UF72B" = "moveToEndOfLineAndModifySelection:";
                "\UF72C"  = "pageUp:";
                "\UF72D"  = "pageDown:";
            }
        
        Source: [Phatness.com](http://phatness.com/node/1661).</dd> 
        
        Proxy settings doesn&#8217;t work for command line tools
        :   Ryan Tomayko had a [partial solution](http://tomayko.com/writings/os-x-network-location-support-from-the-command-line) for this, which I&#8217;ve adapted slightly. Add this to ~/.profile :</p> 
            
                netloc=$(/usr/sbin/scselect 2>&1 | egrep '^ \* ' | sed 's:.*(\(.*\)):\1:')
                http_proxy=$(egrep "$netloc[ \t]*=" /etc/http_proxy | sed 's/.*=[ \t]*\(.*\)/\1/')
                if [ -n "$http_proxy" ]; then
                  export http_proxy="$http_proxy"
                  export HTTP_PROXY="$http_proxy"
                else
                  unset http_proxy
                  unset HTTP_PROXY
                fi
            
            Then add this in /etc/sudoers (needs sudo), right at then end of the lines starting with &#8220;Defaults&#8221;:
            
                Defaults	env_keep += "ALL_PROXY http_proxy HTTP_PROXY"
            
            From now on, all new terminals will use the proxy setting of the network location that was active when the terminal was started.</dd> </dl>
