---
wpid: 98
title: No more spam!
date: 2006-05-12T12:41:19+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=98
permalink: /98/no-more-spam/
categories:
  - Norsk
---
De som har fulgt med i timen vet kanskje at jeg har vært plaget med veldig sære innlegg i gjesteboka mi i det siste. Meldingen &#8220;$(newmessage)&#8221; fra &#8220;$(newname)&#8221; og så videre&#8230;

Jeg har leita inntenst etter årsaken i månedvis. Det første jeg fant ut var at innleggene kom fra Googlebot, dvs Googles webspider for katalogisering av websider. Men utover det sto jeg leeenge blank. Det er nemlig et kraftig antispam-system på gjesteboka, så det skal være omtrent umulig for en maskin å etterlate seg innlegg av noe som helst slag der.

Men i går fant jeg feilen og den var todelt. Den første feilen er at hvis nettleseren/maskinen som aksesserer websiden min sier den _både_ støtter WAP og HTML vil den bli sendt til WAP-forsiden som standard. Gjett hva Googlebot gjør. :p Del to var kraftige feil i WAP-siden for gjestebokinnlegg som gjorde at enhver webspider som kommer innom WAP-siden vil etterlate seg slike teite innlegg.

Så nå er WAP-støtten slått av på websidene inntil videre og gjesteboka er igjen &#8220;trygg&#8221;. :-)

_Edit 130506:_ I tillegg har jeg lagt til favicon, link til rss (slik at Firefox og Opera gir deg feedknapp i adresselinja) og lagt til et statistikkscript så jeg kan finne ut hvor pinlig lite trafikk jeg har her. :p
