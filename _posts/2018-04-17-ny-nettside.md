---
title: Ny nettside
date: 2018-04-17 10:42:12+02:00
categories:
  - Norsk
---
Testing, testing... 1, 2, 3... Funker denne enda? Fant ut jeg ville teste ny teknologi mens jeg samtidig oppdaterte nettsida mi, så her er vi altså.

Jeg har jo hatt denne nettsiden liggende mer eller mindre brakk i årevis nå. Jeg har aldri hatt noe skikkelig fokus med bloggingen min heller, så jeg har vært litt usikker på hva som egentlig hørte hjemme her. Det har nok igjen økt terskelen litt for å skrive noe her.

Siden min teori er at de fleste innlegg blir lest via sosiale medier som Facebook og Twitter fant jeg ut at jeg like gjerne kunne endre forsiden til et slags "visittkort" ment for folk som er mer interessert i hvem jeg er enn å lese alt mulig rart jeg har skrevet i årenes løp.

Og når det gjelder selve skribleriene mine har jeg vel egentlig slått meg selv konkurs på kategorisering. Alle gamle kategorier er borte, og den eneste oppdelingen jeg har nå går på språk. Jeg tror nok fremover at jeg kan finne på å bruke den norske delen mest, med kanskje ett og annet teknisk innslag i den engelske. Noen "kjære dagbok"-innlegg er fjernet fra utlistingene, men direktelenker til dem skal fortsatt fungere fint.

## Teknisk

<img class="img-fluid" alt="Den gamle nettsiden" src="{{ "/wp-content/uploads/2018/04/fuzzy76_net_old.png"}}" />

Den gamle nettsiden min begynte opprinnelig i et veldig simpelt CMS som het PHP-update. Faktisk så gammelt at det nesten ikke dukker opp noe relevant når man Googler det. Men det viste seg å være usikkert som fy, og etterhvert som scriptkiddies lærte seg injection ble alt hacket i småbiter og jeg tror fyren bak ga opp å tette det. Etter en stund migrerte jeg til bloggmotoren Serendipity. Den var ganske lovende den lille stunden den var konkurransedyktig, men utviklingen sakket akterut mens Wordpress tok fart.

Wordpress-oppsettet som jeg så gikk over til og har brukt siden brukte et gammelt minimalistisk tredjepartstheme jeg fant på nett og en god samling tredjeparts-plugins for ymse småtterier (blant annet få bloggen til å fremstå som to separate – en gammel og en ny). I forkant av bytte av backend flyttet jeg kommentarene fra Wordpress til Disqus.

Dagens oppsett bruker Github Pages for å publisere automatisk fra et Git-repository, Jekyll (Ruby) for generering, et selvlaget theme basert på Bootstrap 4 (minimalistisk – sånn jeg liker det) og et klientside-basert søk. Mer detaljer finner du i [Git-repositoriet](https://github.com/fuzzy76/fuzzy76.github.io/). :) HTTPS-support kommer når Github Pages får det (de har visstnok allerede begynt en gradvis utrulling), det vil kreve en liten manuell migreringsjobb med Disqus-oppsettet mitt.

I konverteringen har jeg beholdt permalenker (tror formatet på disse henger igjen fra Serendipity) og RSS-feed på samme adresse som for Wordpress, så forhåpentligvis skal RSS-lesere fungere som før. Det var overraskende mye knoting for å generere samme Disqus post-id som Wordpress-plugin'en gjorde.

Jeg håper at terskelen for å oppdatere skal bli litt lavere fremover. Og har du tilbakemeldinger tar jeg gladelig i mot!
