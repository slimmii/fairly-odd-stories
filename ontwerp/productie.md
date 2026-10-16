# Fairly Odd Tales: productie (sprookje 1, Roodkapje)

Hoort bij het hoofdontwerp in [`README.md`](../README.md). Alle tijden en tellingen gaan over *De Zaak van de Rode Zakdoek* in de versie van ronde 2.

**Uitgangspunt:** alle filmpjes zijn **in-engine scènes** (dezelfde sprites, scriptcamera, geen aparte cinematics). Dat houdt de animatiecount laag en maakt elk filmpje per zin wegklikbaar.

---

## Art- en audiorichting

**Beeld**
- **Stijl:** handgeschilderd 2D met platte, ronde vormen en zichtbare penseelstreek, zoals *Return to Monkey Island*, maar warmer en meer prentenboek. Personages met grote silhouetten en duidelijke poses, leesbaar op een tablet van 8 inch.
- **Palet:** het bos in blauwgroen, mos en okergeel; het hol in warm hout en oranje lamplicht; oma's huisje in roze en crème. **Rood is gereserveerd voor bewijsstukken** (zakdoek, kap, schoentjes) en heeft altijd een eigen vorm (stippen, kwastje, strikje) en een afwijkende helderheid. Geen aanwijzing steunt op rood tegen groen.
- **Hotspots:** klikbare dingen hebben een iets dikkere contourlijn dan het decor, zodat kinderen ze ook zonder highlight zien.
- **Mist (scène 2):** drie lagen, per pad dunner; optrekken in ± 2 s, zonder flits.

**Muziek per scène**

| Scène | Sfeer | Instrumenten |
|---|---|---|
| Hol | gezellig, sloffend walsje | accordeon, klarinet, pizzicato |
| Kruispunt | mysterieus in de mist, opent naar licht als de mist optrekt | glockenspiel, lage strijkers → volle strijkers |
| Roodkapje-moment | snel en speels | **Roodkapje-thema** (pizzicato, houtblok) |
| Beek | werfritme van Bert | banjo, tuba, klotsend water |
| Huisje | spanning, op de tippen van je tenen | pizzicato, brushes |
| Oma's kamer / finale | **spionnenthema** dat langzaam opbouwt | contrabas, bongo's, gestopte trompet |
| Slot | spionnenthema + Roodkapje-thema samen | volle band |

Het **spionnenthema** wordt drie keer geplant voor het volledig speelt: twee maten bij Wanda's "geheime spionne", één basnoot onder het terugklopje (P8) en drie basnoten onder het slot van de kast.

**Belangrijke SFX:** klein klopje (hoog hout, *tok*) vs. grote BONK (diep, met trilling), gedempt terugklopje uit de kast, kast-rommel en "Mmmf!", *HATSJOE* als leitmotiv (telkens even herkenbaar), lantaarntje aan (*ting* + warme zoem), plank klikt vast, "tsjoeng" bij een foute schijf, emmer op hoofd, krekel die stopt.

---

## Assetlijst

### Decors (5 + 2 kleine)

| # | Decor | Varianten / lagen |
|---|---|---|
| 1 | Wolvenhol (woonkamer + open keuken, 1 scherm + lichte scroll) | tv: nieuws / breiprogramma / tekenfilm; bakplaat in oven / op aanrecht; Wiebe met mandje / met vergiet |
| 2 | Kruispunt | mist 3 lagen (per pad); 0–3 lantaarntjes aan; borden op de grond / aan de herkenningspunten; plank aanwezig / weg |
| 3 | Beek | brug 0–3 planken; **tweede uitsnede** van de andere kant met de stapstenen (Roodkapje-moment) |
| 4 | Huisje buiten | deur dicht / open; emmer; vogel; rozen dicht / opzij |
| 5 | Kamer van Grootmoeder | kast dicht / open; sjaal 0–4; bed met vermomde Roodkapje / leeg |
| 6 | *Griezelmuseum*: één stilstaand beeld met 4 kleine loops (na de aftiteling) | — |
| 7 | *Telefoon-inzetje* met Wiebe (portret, hergebruik) | — |

### Close-ups en minipuzzelschermen (6)
P3 symbolenslot · familiefoto · P5 kaart (strip met drie paden) · P8 deur met twee knoppen · P9 touwtjesdoolhof · P10 beschuldiging (4 portretten).

### UI
Startscherm met hulpniveau-keuze (pet / detectivehoed) · detectiveboekje (doelen, hints, klopsignaal, foto, sokkenteller, stickers) · inventaris · foto van Grootmoeder als hoekkader · spoorkaartje · tekening "Papa de held" (close-up) · pauzemenu · instellingen · ouderpagina.

### Voorwerpiconen (12)
briefje · afstandsbediening · tekening · mandje (leeg / met koekjes en want) · ovenwant · koekjes · kaart · foto · plank · sleutel · sok · bakplaat (alleen in het decor).

### Personages en animaties

| Personage | Animaties | # |
|---|---|---|
| **Walter** | lopen (3 richtingen + spiegelen), idle, praten, oppakken laag/hoog, geven, gebruiken, bekijken, au-poten, kloppen, emmer op hoofd, knielen (ridderslag), twee stappen het pad in en terug, duiken achter de breimand, cape-pose (tekening) · *overlays:* meel-wit, stuifmeel, ovenwant in zak, kokshoedje, sokkencape | 16 + 5 overlays |
| **Roodkapje** | idle, praten, schrijven, pad blokkeren, sprint, springen (stapstenen) · *vermomd:* idle in bed (schrijvend handje), praten, pruik-af-sprong · ontmaskerd: praten, schrijven klein | 11 |
| **Wanda** | breien, praten, kloppen op Walters hoofd, tegenhouden aan de deur | 4 |
| **Wiebe** | ridder-idle (mandje / vergiet), praten, ridderslag, tv kijken, koekje pikken, telefoonportret | 6 |
| **Bert** | knagen, praten, planken duwen, proeven | 4 |
| **Grootmoeder** | uit de kast stappen (spionnenpose, zonnebril), praten, koekje eten, sokkencape breien | 4 |
| **Ursula + Das** (op tv) | praten + knipoog / praten met zakdoek | 3 |
| **De Jager** | silhouet snuiven, niezen + hoed vliegt, wegstappen (en 1 loop in het museum) | 3 |
| **Bijfiguren** | vis (oordelen, sok spugen), vogel (boos), krekel, uil (sok gooien), kikker (plons), eend, slak (traag/snel) | 9 |
| | **Totaal** | **± 60 + 5 overlays** |

Grootste risico: het aantal animaties van Walter. Overlays (meel, want in zak, kokshoedje) zijn bewust losse sprites bovenop de bestaande animaties, geen nieuwe animaties.

---

## Ingesproken regels

Schatting per personage, één taalversie, inclusief hints en verkeerde-voorwerp-reacties.

| Personage | Regels | Waarvan |
|---|---|---|
| Walter | ± 290 | ~80 bekijk-zinnen, ~55 eigen verkeerd-voorwerp-reacties, ~15 standaardzinnen, ~56 hints (16 doelen × 3 + toestandsvarianten), ~70 verhaal en dialoog, ~14 P5-tochtjes en gekke extra's |
| Roodkapje (incl. oma-stem) | ± 85 | vragenspel, Roodkapje-moment (8), P10-antwoorden, ontmaskering, oudertoets, slot |
| Grootmoeder | ± 22 | kast, oudertoets, slot, sokken |
| Wanda | ± 20 | opening, doorvragen (= hint 1), deur per hulpniveau, telefoon |
| Bert | ± 20 | |
| Wiebe | ± 15 | incl. telefoon |
| Ursula + Das | ± 6 | |
| De Jager | ± 3 | + niesvarianten |
| Dieren (uil, kikker, eend, slak, vogel) | ± 6 | kan door een andere stem ingesproken worden |
| **Totaal** | **± 470** | ± 27 min ruwe audio (± 3,5 s per regel) |

**Studio:** Walter 2 dagen, Roodkapje 2 halve dagen (kindstem: korte sessies), de rest samen 1,5 dag. **± 4,5 opnamedagen per taalversie.** Een Nederlandse versie is een aparte opname met hetzelfde script op ± 30 woorden na (zie [seriebijbel](seriebijbel.md#taalkeuze)).

Eerste schrapknop voor VO: bekijk-grappen naar 3 per scène (−30 regels).

---

## Speelduurtoets

Gemiddeld kind van 8, eerste keer, klikt rond en probeert een paar keer fout. Tijden per onderdeel; filmpjes zijn al inbegrepen.

| Scène | Onderdelen | Doel | Marge (rondklikker) |
|---|---|---|---|
| **1 Hol** | opening 0:25 · Wanda 0:20 · P1 0:30 · P2 incl. ridderslag 0:25 · P3 1:30 · P4 0:40 · rondklikken 0:20 · vertrek 0:05 | **4:15** | +1:00 |
| **2 Kruispunt** | P5 incl. kaart en één fout tochtje 1:00 · mist, plank, sok 0:10 · vragenspel 0:30 · bloemen + mandje 0:20 · vergissing 0:20 · Roodkapje-moment 0:40 · rondklikken 0:10 | **3:10** | +0:45 |
| **3 Beek** | twijfel 0:10 · Bert 0:15 · plank geven 0:05 · planken leggen 0:40 · vis en rondklikken 0:10 | **1:20** | +0:30 |
| **4 Huisje** | aankomst 0:10 · P8 (één fout + juist) 0:35 · terugklopje 0:10 · rozen 0:15 · doolhof 0:25 · emmergrap 0:05 · rondklikken 0:10 | **1:50** | +0:30 |
| **5 Finale** | binnen + uithoren 0:15 · P10 details 1:05 · beschuldiging 0:15 · ontmaskering 0:25 · sleutel 0:15 · kast + oudertoets 0:30 · koekjes 0:10 · slot 0:55 · kast-grappen en sok 0:05 | **3:55** | +1:00 |
| **Totaal** | | **± 14:30** | **tot ± 18:15** |

**Spreiding:** een snelle speler (Meesterdetective, weinig rondklikken) doet ± 11 min, een rondklikker ± 18 min. Sokken, gekke extra's en het museum na de aftiteling zitten in de marge en nooit op het kritieke pad.

**Valideren (vóór de art start):**
1. **Papieren prototype** (week 2–3): alle puzzels op papier, een spelleider leest de zinnen voor, 6 kinderen van 8–9 jaar. Stopwatch per doel.
2. **Greybox** (week 6): alles speelbaar met placeholder-art en tijdelijke stemmen. De flag-timestamps meten de tijd per doel en het aantal hint-kliks.
3. **Criteria:** mediaan ≤ 14:30, 80 % van de kinderen ≤ 18 min, geen enkel doel met een mediaan boven 2 min (P10 boven 2:30). Wie daarboven gaat, schrapt volgens de lijst hieronder.

### Schraplijst

In deze volgorde, tot de mediaan binnen de 14:30 valt. Samen ± 2:30.

| # | Wat | Scène | Wint | Wat we verliezen |
|---|---|---|---|---|
| 1 | **Roodkapje-moment** weg; de sprint (0:05) komt terug in het vergissingsfilmpje | 2 | −0:35 | Lottes wens "Roodkapje spelen" (schuift naar sprookje 2) |
| 2 | P3: de eerste schijf (opa/maan) staat al juist en gloeit als voorbeeld | 1 | −0:30 | een deel van de denkpiek van scène 1 |
| 3 | Bekijk-grappen naar 3 per scène | alle | −0:20 | −30 regels VO |
| 4 | P6: vragenspel één ronde in plaats van twee | 2 | −0:15 | een grap |
| 5 | P7: drie planken in plaats van vier (geen te korte) | 3 | −0:15 | Berts protestgeknaag |
| 6 | P10: mandje-detail weg (drie vragen + kap; minimum blijft 2) | 5 | −0:10 | de callback "heel veel mandjes" |
| 7 | P9: doolhof met twee touwtjes (vogelhuisje weg) | 4 | −0:10 | de vogelgrap |
| 8 | Slot: museumuitleg van Grootmoeder één zin, De Jagers "Ach, het is vast mijn neus" weg | 5 | −0:08 | — |
| 9 | Wiebes ridderslag wordt één zin | 1 | −0:05 | — |

**Scope-schrappen (kosten, geen tijd):** spoorkaartje → sokkencape (alleen het boekje-sticker blijft) → museumbeeld na de aftiteling → telefoon-inzetje (Wiebe wordt een stem).

**Wat nooit geschrapt wordt:** P10 met de foto, de HELP-sjaal, de oudertoets-regels (P6, kast, toestemming), Wiebes tekening, De Jager aan het raam.

---

## Filmpjesbudget

Doel: **hoogstens 3 minuten** aan filmpjes. Alles in-engine en per zin wegklikbaar, behalve de eerste 5 seconden van het wauw-moment (de beloning).

| Filmpje | Duur |
|---|---|
| Opening (Walter ploft + nieuws) | 0:25 |
| Wanda + Wiebes vraag | 0:20 |
| De vergissing | 0:20 |
| Ontmaskering | 0:25 |
| Kast open (wauw) + oudertoets + sorry | 0:30 |
| Slot (De Jager, telefoon, partners) | 0:55 |
| **Totaal filmpjes** | **2:55** (ronde 1: 3:25) |
| *Korte momenten in het spel* (ridderslag, twijfel aan de beek, terugklopje, koekjes aan oma): de besturing blijft actief | *± 0:40* |
| *Roodkapje-moment* (speelbaar, telt als speeltijd) | *± 0:40* |
| *Sokkencape* (alleen bij 5 sokken) | *+ 0:08* |
| *Griezelmuseum na de aftiteling* (buiten de speelduur) | *0:15* |

---

## Wauw-moment

**Gekozen moment:** de ontmaskering plus de kast die opengaat. Dit is het trailershot en de beloning voor de denkpiek. Het spionnenthema is vooraf drie keer geplant (zie *Art- en audiorichting*).

### Shotlist

| Tijd | Camera | Animatie | Audio |
|---|---|---|---|
| **Ontmaskering** | | | |
| 0:00 | Portret Roodkapje gekozen → terug naar de kamer, snelle push-in op het bed | Walter wijst, detectivepose | Muziek valt stil. Eén klok-*tok* |
| 0:02 | Close-up Walter | *"Jij bent... ROODKAPJE!"* | Komisch "dun-dun-DUN" |
| 0:04 | Uitzoomen | Roodkapje springt rechtop op het bed, trekt muts en pruik in één ruk af, de kap **ploept open** (squash & stretch), het notitieboekje fladdert | *Poef* + papiergeritsel |
| 0:06 | Totaalbeeld | *"Oké! Ik ben het!"* | Roodkapje-thema (pizzicato) |
| 0:07–0:25 | Shot / tegenshot | Dialoog tot *"Wat is een sleutel eigenlijk?"*; kast BONK | *"Mmmf!"* |
| — | *speler zoekt de sleutel (P11)* | | |
| **Kast** | | | |
| K+0:00 | Sleutel in het slot → camera schuift traag naar de kast; licht iets gedimd, warme spot op de kast | De HELP-sjaal wordt met een *sssslurp* de kast in gezogen | 1 s stilte |
| K+0:02 | Statisch | Slot draait: *klik... klik... KLIK* (ritme ⬤ ● ● van het terugklopje) | Basnoot onder elke klik |
| K+0:04 | Kleine camera-schok (uit bij "minder beweging") | Deuren zwaaien open, een wolk **breiwol** (geen rook) dwarrelt eruit | **Spionnenthema volledig** |
| K+0:05 | Lage hoek, heldenshot | Grootmoeder stapt eruit in spionnenpose, zonnebril op; de sjaal ontrolt zich over de hele breedte: H-E-L-P | Trompetstoot |
| K+0:08 | Muziek stopt abrupt | Zonnebril af: *"Een kwartier. Ik zit al een KWARTIER in een kast."* | Krekel tjirpt (callback) |
| K+0:10–0:30 | Rustig tweeshot oma / Roodkapje | Oudertoets-regels en sorry; Roodkapje schrijft "Onderstreept" | Zachte versie van het spionnenthema |

- **Trailershot:** K+0:05 (sjaal over het hele scherm).
- Geen flitsen. K+0:00 tot K+0:05 is niet wegklikbaar (5 s); al de rest wel.

**Tweede, kleiner wauw:** de mist die optrekt op het kruispunt (P5): drie lantaarntjes, dan zonlicht en scherpe silhouetten, met de overgang naar volle strijkers.

---

## Team en planning

**Team:** 1 game designer/scenarist, 1 developer, 1 achtergrondartist, 1 personage-animator, freelance audio (VO-regie, SFX) en componist.

| Fase | Duur |
|---|---|
| Papieren prototype + greybox (alle puzzels speelbaar, placeholder-art) | 6 weken |
| Engine-tooling (dialoog, flags, hints, boekje, hulpniveaus) | 8 weken, parallel |
| Art + animatie | 12–14 weken |
| VO, muziek en SFX | 4 weken, parallel met art |
| Polish, speeltests met kinderen, bugfix | 6 weken |
| **Sprookje 1** | **± 7 maanden** |
| Volgende sprookjes (tooling en vaste cast herbruikbaar) | ± 4 maanden per stuk |

**Grootste risico's:** animatiecount van Walter, VO-telling (twee taalversies verdubbelen de studiotijd), speelduur van P10. Elk risico heeft een schrapknop hierboven.

---

## Systeemschermen en ouderpagina (kort)

**Hoofdmenu:** Verder spelen · Nieuw verhaal · Instellingen · Voor ouders. Grote plaatjes, alles ingesproken.

**Hulpniveau:** bij een nieuw verhaal (pet of detectivehoed); wisselbaar in het pauzemenu.

**Opslaan:** **automatisch** na elke opgeloste puzzel en bij elke scènewissel (de flags zijn de save). Hervatten zet je terug op de laatste plek, met een korte zin van Walter: *"Waar was ik? Oh ja."* Drie saveplaatsen (voor broers en zussen), elk met een tekening als naam.

**Pauzemenu:** verder · boekje · hulpniveau · instellingen · naar het hoofdmenu.

**Instellingen:** volume (muziek, stemmen, effecten apart) · spreeksnelheid (langzaam / normaal / vlot) · ondertitelgrootte (3 standen) · minder beweging · spoorkaartje aan/uit · linkshandige inventaris (tablet).

**Voor ouders** (achter een eenvoudig ouderslot: hou twee knoppen 3 s ingedrukt):
- Geen advertenties, geen in-app aankopen, geen account, geen internet nodig, geen gegevens verzameld. Speeltest-metingen bestaan alleen in testversies.
- Wat er in het verhaal gebeurt, in drie zinnen, en welke waarden erin zitten (niet meegaan met vreemden, eerlijk zijn, niemand opsluiten, een grote mens halen als je bang bent). Zie de [seriebijbel](seriebijbel.md#oudertoets-en-waarden).
- Speelduur (± 15 min), hulpniveaus uitgelegd, toegankelijkheidsopties.
- Credits.
