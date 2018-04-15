---
wpid: 90
title: Google Homepage plugins
date: 2006-03-23T15:44:31+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=90
permalink: /90/google-homepage-plugins/
dsq_thread_id:
  - "6089091836"
categories:
  - Norsk
---
Og der var min første modul for Google Homepage et faktum! :) Den viser status (inkludert spilleliste) for spilleserveren min og kan testes ut ved hjelp av knappen nederst på statussida på spilleserveren min (fjernet, pga bytte av CMS).

En modul er i utgangspunktet en xml-fil med inline html og Javascript.

Problem nummer en er at de fleste nettlesere av sikkerhetshensyn ikke lar Javascript sendte http-forespørsler til andre servere enn serveren HTML-sida hentes fra. Greit i mange situasjoner, men min modul leses jo fra <a href="http://www.google.com/" target="_blank" rel="noopener">Google</a> (siden Google må parse og wrappe modulen), og da begrenses mulighetene fort. Nå har Google tenkt så langt og gitt deg en Javascript funksjon som heter \_IG\_FetchContent(). Fine greier, tenkte jeg. Men dessverre cacher denne funksjonen responser i timevis, så den blir totalt ubrukelig til det _meste_ av dynamiske løsninger. Dette måtte jeg løse ved å legge til ?randomshit=12345 i URL&#8217;en, hvor 12345 er et slags hjemmelagd timestamp som er garantert unikt over en periode på 28 dager. Ikke pent, men det duger inntil Google kan tilby noe bedre.

Problem nummer 2 var selvfølgelig at spilleserveren min i utgangspunktet bare rapporterer via rå TCP, men dette løste jeg ved å lage et lite PHP-script på serveren som modulen min spør. Dette scriptet kontakter igjen spilleserveren direkte og konverterer infoen til HTML før den returneres.

Ellers kan jeg nevne at modulen min krever å kjøres inline (div istedenfor iframe) siden den har variabel høyde og oppdaterer seg hvert 30. sekund uten å reloade siden (bytter bare ut innerHTML for div-taggen).

Jeg vurderte selvfølgelig å lage en åpnere og konfigurerbar løsning så flere kunne implementere dette på sine servere, men jeg følte meg litt i det egoistiske hjørnet. ;) Hvis Google gir meg en skikkelig fetch-funksjon så jeg slipper å bruke stygge triks skal jeg muligens revurdere saken&#8230;
