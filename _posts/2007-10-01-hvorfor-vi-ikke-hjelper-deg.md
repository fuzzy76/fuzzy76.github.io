---
wpid: 150
title: Hvorfor vi ikke hjelper deg
date: 2007-10-01T18:45:05+00:00
author: Håvard Pedersen
layout: post
guid: http://fuzzy76.net/?p=150
permalink: /150/hvorfor-vi-ikke-hjelper-deg/
dsq_thread_id:
  - "6292039087"
categories:
  - Norsk
---
_This is a norwegian translation of [Why we won&#8217;t help you](http://diveintomark.org/archives/2003/05/05/why_we_wont_help_you) by [Mark Pilgrim](http://diveintomark.org/about)._<!--more-->

Det er et scenario jeg ser om og om igjen på forum og epostlister med temaet css og webdesign. Fersk nybegynner poster en link til en testside, og ber om hjelp fordi den ikke ser ut som forventet i en eller annen nettleser. Designerguru svarer, og forteller ferskingen at siden ikke validerer og at den [bør valideres](http://validator.w3.org/) før man ber om hjelp med problemet. Det skjer ingen videre diskusjon; ingen flere svar; ingen flere vil hjelpe.

Hvorfor skjer dette? Hvorfor vil vi ikke hjelpe deg?

Det smarte og dype svaret er at vi faktisk hjelper deg, du har bare ikke skjønt det enda. Det fulle svaret er slik:

  1. **Validering kan avsløre problemet ditt.** Veldig mange tilfeller av &#8220;det virker i en nettleser, men ikke i en annen&#8221; skyldes glipper av forfatteren. Skrivefeiler som manglende attributtverdier [kan forårsake totalhavari i nettleseren](http://diveintomark.org/archives/2003/05/03/the_importance_of_humanreadable_markup), og validering fanger opp slike feil. Enkle feil som manglende sluttagger (slik som </table> eller <div>) eller manglende elementer (slik som <tr>) kan forårsake forskjellige problemer i forskjellige nettlesere. Små feil som dette er vanskelig å se i sin egen kode, men validering vil avdekke disse med en gang.Jeg påstår ikke at siden din, når den er validert, automatisk vil se rett ut i alle nettlesere &#8211; det motsatte kan skje. Jeg påstår heller ikke at det ikke finnes talentfulle designere som kan lage gammeldags &#8220;tagsuppe&#8221; som fungerer feilfritt i alle nettlesere, for de finnes. Men validatoren er et automatisk verktøy som kan avsløre små men viktige feil som er vanskelige å finne for hånd. Hvis du lager gyldig kode mesteparten av tiden, kan du dra nytte av denne automatikken for å finne uhellene når de forekommer. Men hvis oppmerkingsspråket ditt ikke er i nærheten av å være gyldig flyver du totalt i blinde når ting går galt. Validatoren vil spy ut dusinvis eller hundrevis av feil på siden din, og å finne den ene feilen som faktisk forårsaker problemet ditt blir som å finne en nål i en høystakk.
  2. **Validering kan løse problemet ditt.** HTML er ikke &#8220;hva som helst funker&#8221; &#8211; det er regler for hvordan elementer kan brukes og kombineres. Nettlesere er skrevet for å tolke disse reglene og tegne opp nettsidene etter disse. Nettlesere har logikk for å håndtere forskjellige typer ugyldig kode inkludert nettleser-spesifikke tagger og attributter, ugyldige kombinasjoner av block-level og inline elementer og overlappende elementer. Forskjellige nettlesere gjør forskjellige interne tolkninger av denne såkalte &#8220;tagsuppen&#8221;, og dette kan igjen føre til uventede varierende resultater når de prøver å bruke stilark eller script på det resulterende dokument-treet.[Ian Hickson illustrerer disse forskjellene](http://ln.hixie.ch/?start=1037910467&count=1). Dave Hyatt, en av utviklerene bak Apples Safari nettleser, snakker om [&#8220;stil til overs&#8221;-problemet](http://weblogs.mozillazine.org/hyatt/archives/2003_03.html#002904) forårsaket av feilnøstede elementer. Som Daves eksempel viser, påvirker det ikke bare CSS-baserte sider. Det påvirker sider skrevet i utelukkende HTML også. 
    Jeg sier ikke at validering er en vidunderkur som automatisk vil løse alle dine webdesign-problemer &#8211; for det er det ikke. Designere må fortsatt forholde seg til mange kompatibilitetsproblemer i gyldig kode på tvers av nettlesere og plattformer. Men å validere sidene dine eliminerer en rekke potensielle problemer, og etterlater oss med en mye mindre (og derfor mer håndterbar) liste over problemer å jobbe med. Hvilket igjen bringer oss til mitt neste poeng:</li> 
    
      * **Gyldig kode er vanskelig nok å finne feil i.** Å finne feil i &#8220;tagsuppe&#8221; er mange ganger vanskeligere. Det er heller ikke spesielt givende. Noen av oss er flinke til det, og en del av oss har holdt på lenge nok til at vi har vært nødt til å håndtere det på et eller annet punkt. Men det er ikke det vi har lyst til å bruke energien vår på. Det er ingenting estetisk givende eller intellektuelt tilfredsstillende ved å hjelpe en &#8220;gutteromskoder&#8221; å justere sin elendige kode og å denge noen nettlesere inn i underkastelse. Vi vet det hele kommer til å skjære seg i neste uke, vi har prøvd det selv, vi vet hvordan det går. Vi vet at koden din lever på lånt tid.Og nevnte jeg at å feilsøke slik kode er vanskelig? Det er mye å holde styr på, selv når du gjør alt rett. Det er [bugs i Windows-nettlesere](http://css.nu/pointers/bugs.html), [bugs i Mac-nettlesere](http://www.macedition.com/cb/resources/macbrowsercsssupport.html), [bugs i nye og gamle nettlesere](http://www.richinstyle.com/bugs/), [bugs i Opera](http://www.positioniseverything.net/op-omnibus.html), [bugs i Firefox](http://www.positioniseverything.net/gecko.html) og [bugs i Internet Explorer](http://www.positioniseverything.net/explorer.html) også. André Bjerke kunne laget et dikt av alle buggene vi må håndtere bare i våre gyldige, standard-baserte nettsider. Og på toppen av dette vil du at vi skal prøve å finne ut av det tilnærmet uendelige antall bugs som kan forårsakes av din &#8220;tagsuppe&#8221;? Så god tid har vi rett og slett ikke, og den tiden vi har er bedre investert andre plasser. Som igjen bringer meg til det siste poenget:
      * **Validering er en indikator på at du har peiling.** Det er veldig mange mennesker som trenger vår hjelp, og det er relativt få av oss som har den kombinasjonen av tid, ekspertise og vilje til å søke etter feil i andre folks layout gratis. Det er ganske elementert egentlig: vi kan rett og slett ikke hjelpe alle som spør. Akkurat som en personalavdeling som får 500 søknader for en utlyst stilling, må også vi filtrere ut på et kriterium, og gyldig kode har vist seg å være et bra kriterium. Det er mulig, til og med uunngåelig, at dette igjen vil føre til at vi overser en og annen lovende designer som kunne visst seg å bli både en god venn eller en profesjonell kompanjong senere i livet, men det er bare sånn det må være. Det kan også hende at blant de 500 søkerene, var det den med 5 skrivefeil i søknaden som var den beste kandidaten. Men du kan ikke intervjue alle. Du må finne et kriterium å filtrere på.Hvorfor er gyldig kode et godt kriterium? Fordi ingen lager gyldig kode ved et uhell. Hvis du kommer til oss og sier &#8220;Jeg har denne siden hvor både HTML og CSS validerer, men har dette spesifikke problemet&#8221; så har du tydeligvis lagt ned litt arbeid i den, du har møtt oss på mer enn halvveien, la oss se hva vi kan få til. Men hvis du kommer til oss og sier &#8220;Hei, jeg slengte sammen denne siden som virker i nettleser X men så sier klienten min at den ikke fungerer i W, Y og Z, det må da være noen drittnettlesere&#8221;, så kan det hende du må se et godt stykke etter hjelp.</ol>