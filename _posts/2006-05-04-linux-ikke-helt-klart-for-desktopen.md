---
wpid: 97
title: Linux ikke helt klart for desktopen
date: 2006-05-04T21:44:36+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=97
permalink: /97/linux-ikke-helt-klart-for-desktopen/
dsq_thread_id:
  - "6089092034"
categories:
  - Norsk
---
Ok, etter siste tiders <a href="http://www.aviransplace.com/index.php/archives/2006/04/22/microsoft-is-taking-wga-to-the-next-level/" target="_blank" rel="noopener">offensiv fra Microsoft gjennom WGA</a> bestemte jeg meg for nok en gang å prøve ut alternativer til Windows som desktop OS. Det eneste jeg har som er Windows-kritisk er Fokus nettbank (ja, de suger), Call of Duty og det lille jeg gjør av VB.Net-utvikling (jeg vet det kan gjøres under Linux, men verktøyene suger).

Jeg har hørt veldig mye skryt av Ubuntu, så jeg fant ut dette var det naturlige valget.

Ettersom jeg innså det ville bli mye switching mellom OS i begynnelsen (og for å ha ryggdekning i tilfelle alt gikk rett vest) fant jeg ut at jeg skulle flytte alle viktige dokumenter samt Firefox og Thunderbird profilene til en FAT32 partisjon slik at dette kunne deles mellom Linux og Windows.

**Forsøk en**

Siste releaseutgave av Ubuntu (v5 breezy) ble installert. Jeg gikk for stabilt og velprøvd. Etter at systemet var satt opp oppdaget jeg at nyeste Firefox i pakketreet var versjon 1.0.5. Ikke akkurat ideelt med mindre jeg ville degradere Windowsversjonen til samme utgave, noe som ikke var særlig aktuelt.

Jeg fant fort en tutorial for å gjøre in-place oppgradering til v6 (dapper) og denne fungerte utmerket og jeg kunne fort konstantere at Firefox 1.5.x var på plass.

Dessverre fant jeg ut jeg skulle resize Windows-partisjonene på disken, fikk mange kryptiske feilmeldinger fra PartitionMagic, kjørte et partisjonstabellrepareringsprogram (si _det_ fort etter hverandre et par ganger!) og endte plutselig opp med at hele Linuxdelen av disken endte opp som &#8220;unpartitioned space&#8221;. Nuvel.

**Forsøk to**

Med en &#8220;fikset&#8221; partisjonstabell bega jeg meg ut på en ny ferd mot uavhengighet. Etter å ha lest litt frem og tilbake fant jeg ut at KDE måtte være tøft. Altså, Kubuntu (som er Ubuntu med KDE som default istedenfor Gnome). Ny installasjon, med v6 dapper fra starten av.

Under installasjonen taster jeg inn SSID og WEP-nøkkel og alt går fint. Men så booter maskinen inn i desktopen og plutselig har jeg NULL trådløsnett! :O Nettverksverktøyet i desktopen sier at forbindelsen er &#8220;up&#8221;, men eksperimenter med ifconfig i konsollen sier meg at jeg ikke har IP. Ellers ingen direkte feilmeldinger, DNS-oppslag feiler og ping funker ikke. Etter MYE feilsøking går jeg inn på oppsett av trådløst og velger SSID&#8217;en min på nytt, og **halleluja** det funker plutselig! Problemet er rett og slett at tekstinstalleren til Ubuntu ikke er case-sensitiv (skiller ikke mellom store og små bokstaver) i SSID&#8217;en, mens det ferdig installerte systemet _er_ det. Logisk? Nei. Så jeg tastet SSID&#8217;en med feil case men det funket litt.

Så&#8230; moving on. Nyeste Firefox og Thunderbird på plass rett fra pakketreet. Men mailto-linker ble feil i Firefox (åpnet i KMail) og http-linker ble feil i Thunderbird (åpnet i Konqueror, KDE&#8217;s browser)! Selv om innstillingene var satt til å bruke Mozillaprogramvaren. Stønn.

Etter mye om og men fant jeg ut at dette var slik disse to programmene hadde oppført seg i KDE for mange brukere _lenge_ uten at det hadde blitt fikset. Jeg fant riktignok et js-hack for configfila til disse to, men den observante leser husker at jeg skulle dele profil mellom Windows og Linux for disse programmene og da funket den heller dårlig&#8230; Tilbake til square one.

**Forsøk tre**

Ubuntu 6 dapper. Her gir vi oss ikke så lett nei! Installerte. Tilpasset i øst og vest (deriblant oppsett av delte profiler). Testet grundig. Funket fint. Nå gjensto det bare å installere eventuell programvare jeg trenger til daglig. Kopete (MSN-klient) installeres og funker fint, veldig fint faktisk.

Neste skritt, finne en decent PHP/HTML/CSS editor. Etter å ha lest mye omtaler, sett på screenshots og sammenlignet egenskaper bestemmer jeg meg for <a href="http://www.screem.org/" target="_blank" rel="noopener">Screem</a>. Installerer, tester bittelitt og den ser fin ut.

Men hva skjer neste gang jeg trykker på en link i Kopete? Linken åpnes i Screem! I HTML-edit-visning! Jaja, tenker jeg, den har vel satt seg som standard nettleser da. Inn på brukervalg, finner nettleserinnstillingen, og&#8230; eh&#8230; finner ut at den fortsatt står på Firefox. Prøver å switche den til Konqueror og tilbake til Firefox igjen for syns skyld. Tester igjen. Nei. HTTP-linker funker ikke lenger, verken i Kopete eller i Thunderbird.

Så her står jeg nå, med et skakkjørt Linux for tredje gang på to uker, og jeg er dataingeniør. Og likevel finnes det folk som mener at alle bør bruke Linux istedenfor Windows?

Kyss meg i r&#8230;
