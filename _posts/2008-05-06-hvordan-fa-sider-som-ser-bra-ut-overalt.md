---
wpid: 163
title: Hvordan få sider som ser bra ut, overalt
date: 2008-05-06T21:29:31+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=163
permalink: /163/hvordan-fa-sider-som-ser-bra-ut-overalt/
dsq_thread_id:
  - "6089091748"
categories:
  - Norsk
---
Veldig ofte ser jeg at forumer oversvømmes av nettsideproblemer som jeg finner ut av i løpet av sekunder på ren automatikk. Det slo meg at noen bør ta til orde for litt hjelp til selvhjelp på dette området. Så her har jeg samlet mine triks for problemfrie websider.

<!--more-->

## Hold deg unna Quirks mode

Quirks mode er et fenomen som oppsto når nettleserprodusentene begynte å innse at de måtte prøve å følge HTML-standarden før det brøt ut fullstendig kaos. Da lot de eldre sider bli tolket slik nettleserene fungerte på den tiden (quirks mode), mens nyere sider skulle tolkes på en mer standardisert (standard mode) måte.

Problemet er at mange ikke vet hvordan de skal identifisere sidene sine som &#8220;standardkompatible&#8221;, og derfor ender opp med sider som tolkes i quirks mode av nettlesere. Og quirks mode betyr i bunn og grunn at nettleseren går ut fra at siden din er skrevet for Netscape 4 / Internet Explorer 4. I tillegg er dette fra en tid nettlesere tolket sider VELDIG forskjellige, og dette gjør de fortsatt i dag. Quirks mode er en _garanti_ for at nettlesere vil tolke sidene dine forskjellig.

De fleste nettlesere slår av quirks mode hvis HTML-dokumentet inneholder en doctype-tag med link til en dtd-fil (som definerer hvilken versjon av HTML/XHTML-standarden siden er skrevet i). Et unntak verdt å merke seg (eller snarere et tillegg) er at Internet Explorer i tillegg krever at du ikke har noe whitespace (linjeskift, mellomrom eller tabulator) før doctype-taggen.

En kjapp oversikt over de vanligste nettleserenes håndtering av quirks mode finner du på [www.quirksmode.org](http://www.quirksmode.org/css/quirksmode.html). I tillegg finner du også en litt grundigere drøfting på [Wikipedia](http://en.wikipedia.org/wiki/Quirks_mode). Hvis du [Googler doctype](http://www.google.no/search?q=doctypes) finner du også en [kjekk liten artikkel på AListApart](http://www.alistapart.com/articles/doctype/) som lister de vanligste doctypene.

## Utvikle på laboratoriet først, test i felten etterpå

Når man skal utvikle en side er det kjappeste å gjøre utviklingen i en nettleser som følger standardene tettest mulig. Slik kan du benytte tiden til å konstruere en bra side, og ikke slåss med feil i nettlesere underveis. Hvis du i tillegg sørger for at du ikke har en side som vises i quirks mode, vil det ikke være så forferdelig mange bugs å lappe på til slutt.

Dette er en utprøvd teknikk alle profesjonelle webdesignere sverger til, og slettes ikke et &#8220;nerdepåfunn&#8221; for å verve flest mulig folk til sin nettleser. Faktisk driver jeg design og vanlig surfing i to helt forskjellige nettlesere (mer om dette senere). Hovedregelen her er at den siste utgaven av de mer populære nettleserene (Firefox, Safari, Opera e.l) holder lenge.

Internet Explorer gjør dessverre ikke det, ettersom Microsoft tok en mange år lang pause uten utvikling før de plutselig begynte igjen. Internet Explorer 9 ser ut til å kunne bli bra nok i den endelige utgaven til at den kan brukes til utvikling. Men når det er sagt er det viktig at du tester siden din i Internet Explorer før du legger den ut. Det er tross alt fortsatt den mest populære nettleseren, så man må ta høyde for at mange besøkende har den.

## Browser bugs

[gtalbot.org](http://www.gtalbot.org/BrowserBugsSection/) og [PositionIsEverything.net](http://www.positioniseverything.net/) inneholder veldig gode lister over kjente bugs i nettleserene, **og hvordan man fikser dem**. Jeg blir ofte oppgitt når jeg ser folk kaste ut spørsmål i blinde på forum istedenfor å slå opp bugen, finne fiksen og slippe å sitte og oppdatere forumtråden sin resten av kvelden. Men disse buglistene gjelder (selvfølgelig) kun for standard mode. Quirks mode er designet nettopp for å holde på gamle bugs. Om du bare bokmerker _en_ side fra dette avsnittet, la det bli [PositionIsEverything.net&#8217;s oversikt over Internet Explorer bugs](http://www.positioniseverything.net/explorer.html).

## Validering

Mange nybegynnere blir fort veldig oppgitte over maset fra &#8220;nerdene&#8221; om validering. Men det har en meget viktig misjon.

Hvis HTML-standarden beskriver hvordan nettlesere skal tolke HTML-dokumenter, og du lager et dokument som ikke bygger på hvordan HTML-standarden er bygget opp&#8230; Hva skal nettleserene gjøre? De har altså fått et dokument som de rett og slett ikke **vet** hvordan skal vises, fordi det ikke er beskrevet i standarden. De må altså _gjette_ på hvordan dokumentet skal vises. Bør noen bli overrasket over at nettleserene gjetter forskjellig? Neppe. Nettleserprodusenter har nok å gjøre med å følge standardene. Ugyldig kode blir overlatt til seg selv.

Validering sørger også for at feilsøking blir mye enklere, og utelukker veldig mange potensielle fallgruver. Vil du lese litt mer argumentasjon på området [har jeg oversatt en engelsk artikkel om temaet tidligere](http://fuzzy76.net/150/hvorfor-vi-ikke-hjelper-deg/). Det første jeg gjør når jeg opplever layout-bugs på mine egne sider er å validere.

## Verktøy

Safari og Opera har begge fått innebygde utviklerverktøy, og spesielt Operas [Dragonfly](http://www.opera.com/products/dragonfly/) ser spennende ut. Firefox har utvidelsene [Firebug](http://www.getfirebug.com/) og [Web developer toolbar](http://chrispederick.com/work/web-developer/) som er utrolig kraftige verktøy. Alle disse nettleserene har altså verktøy som enkelt viser deg om du er i quirks mode, hvilket CSS-regler som gjelder for ethvert element, hvordan elementene dine er tolket, hva som gjør at Javascriptet ditt stoppet opp, om siden din validerer og så videre. Hva du enn gjør, sett av en time eller to på å lære deg å bruke disse. Det vil spare deg for utrolig mye tid i det lange løp. Jeg ser alt for ofte at folk spør om ting som jeg finner ut av på 2 sekunder i Firebug.

## Når alt annet feiler

Men av og til ender man opp med ting man rett og slett ikke forstår seg på. Det skjer innimellom. Man sitter med en side som validerer perfekt, ser ypperlig ut i noen nettlesere, men ser forferdelig ut i andre og ingen kjente bugs i nettleserene høres ut som akkurat ditt problem. Da trenger man hjelp. Og da er det mer givende for oss med noen år på baken å hjelpe også.

Men om du har lest gjennom hele denne artikkelen skjønner du kanskje at det nesten er umulig å debugge en layout ut fra 4 linjer fra CSS-fila di. Skal jeg debugge en layout for noen vil jeg kunne undersøke sida med et av utviklerverktøyene i forrige avsnitt, og da er det kun live kode som gjelder. Last opp sida, og post en link. Hvis du virkelig ikke har lyst til å offentliggjøre siden din, kan du også prøve å redusere problemet ditt til et forenklet eksempel. Det kan også gjøre at du oppdager en løsning du ikke hadde tenkt på.

Men jeg (og mange med meg) er med i mange forumer. Og folk som vet hvordan HTML og CSS skal settes sammen har mye å gjøre. Hvis du ikke har gidda å gjøre din del (følge avsnittene over og prøve å finne ut av det selv, inkludert validering), er sjansen stor for at vi heller ikke orker å bruke tid på det. Se forøvrig siste del av [hvorfor vi ikke hjelper deg](http://fuzzy76.net/150/hvorfor-vi-ikke-hjelper-deg/).
