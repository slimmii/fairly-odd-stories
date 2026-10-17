# Fairly Odd Tales: productie (sprookje 1, Roodkapje)

Hoort bij het hoofdontwerp in [`README.md`](../README.md). Alle tijden en tellingen gaan over *De Zaak van de Rode Zakdoek* in de versie van ronde 3.

**Uitgangspunt:** alle filmpjes zijn **in-engine scènes** (dezelfde sprites, scriptcamera, geen aparte cinematics). Dat houdt de animatiecount laag en maakt elk filmpje per zin wegklikbaar. Ook de opening (0:25) is zo'n in-engine scène: er is geen apart openingsfilmpje.

---

## Technische uitgangspunten

Aanbevolen keuzes, zodat de developer de tooling kan plannen. Wat nog open is, staat onderaan en wordt beslist vóór het einde van week 2.

| Onderwerp | Aanbevolen keuze | Waarom |
|---|---|---|
| **Platform** | **Tablet** (iPad, Android-tablet) **en pc/Mac**, tegelijk uitgebracht | De besturing is al voor muis én aanraking ontworpen; tablet is waar kinderen van 8 spelen, pc is goedkoop mee te nemen. |
| **Stores** | App Store, Google Play, Steam | Drie stores, één build-pipeline. |
| **Minimale hardware** | iPad 9e generatie (2021) of nieuwer · Android 10+ met 3 GB RAM · Windows 10 / macOS 12 met geïntegreerde grafische kaart | 2D met lagen en mist vraagt weinig; we testen op het traagste toestel. |
| **Beeld** | Art op 1920 × 1080 (16:9) met een **veilige zone voor 4:3** (iPad): geen hotspot of aanwijzing buiten die zone | iPads zijn 4:3, pc's 16:9. |
| **Engine** | **Godot 4** (2D), eigen tooling voor dialoog, flags, hints en boekje | Geen licentiekosten of runtime-fees, sterke 2D, export naar alle drie de stores. Ons flagmodel en het boekje zijn toch maatwerk. |
| **Animatie** | Personages als **cut-out/skeletanimatie** (bv. Spine of de 2D-skeletten van de engine), decors als lagen | Overlays (meel, want in zak, cape) en hergebruik van bewegingen worden goedkoop. |
| **Opslag** | Lokaal, één klein JSON-bestand per saveplaats (de flags), automatisch opgeslagen. Optioneel iCloud/Steam Cloud via het platform, **zonder eigen account** | Past bij "geen account, geen internet nodig". |
| **Grootte** | ≤ 1 GB per aflevering, beide taalversies inbegrepen (VO als gecomprimeerde audio, ± 30 MB per taal) | Past op een gedeelde gezinstablet. |
| **Verdienmodel** | **Premium:** één keer betalen per aflevering, **geen advertenties, geen in-app aankopen, geen account**. Elke aflevering is een losse app/titel; zodra er twee zijn, komt er een **bundel** (App Store-appbundel, Steam-bundel) met korting | Eerlijk voor ouders, geen aankoopknoppen voor kinderen. Losse titels kunnen omdat er geen state over afleveringen heen gaat (zie [seriebijbel](seriebijbel.md#sokken-en-de-cape-in-de-reeks)). |
| **Privacy** | Geen analytics of tracking in de uitgebrachte versie; speeltest-metingen (flag-timestamps) alleen in testbuilds. Externe links (credits, website) achter het ouderslot | Vereist voor kindercategorieën in de stores en voor de ouderpagina. |

**Open beslispunten** (eigenaar: product owner, deadline einde week 2)
1. **Engine definitief:** twee weken spike in Godot 4 (dialoog + flags + één scène met tikken en slepen). Valt die tegen, dan Unity met een bestaand point-&-click-framework (bv. Adventure Creator); dat bespaart tooling, maar kost licenties en meer maatwerk voor het boekje.
2. **Losse apps of één app** waarin later afleveringen bijkomen (vooraf betaald seizoen). Losse apps zijn eenvoudiger; één app geeft één icoon op de tablet.
3. **Prijs** per aflevering en van de bundel; eventueel een gratis proefversie (scène 1) als aparte app, niet als ontgrendeling.
4. **Kindercategorie** in de App Store (strengere regels, betere vindbaarheid) of gewoon "Familie".
5. **Console** (Switch) later: alleen als port, niet in deze planning.
6. Wanneer de **Nederlandse versie** wordt opgenomen (zie [seriebijbel](seriebijbel.md#taalkeuze)).

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

**Belangrijke SFX:** klein klopje (hoog hout, *tok*) vs. grote BONK (diep, met trilling), gedempt terugklopje uit de kast, kast-gemopper (verstaanbaar, boos en niet bang) met tikkende breinaalden, *HATSJOE* als leitmotiv (telkens even herkenbaar), lantaarntje aan (*ting* + warme zoem), plank klikt vast, "tsjoeng" bij een foute schijf, emmer op hoofd, krekel die stopt.

---

## Assetlijst

### Decors (5 + 2 kleine)

| # | Decor | Varianten / lagen |
|---|---|---|
| 1 | Wolvenhol (woonkamer + open keuken, 1 scherm + lichte scroll) | tv: nieuws / breiprogramma / tekenfilm; bakplaat in oven / op aanrecht; Wiebe met mandje / met vergiet |
| 2 | Kruispunt | mist 3 lagen (per pad); 0–3 lantaarntjes aan; borden op de grond / aan de herkenningspunten; plank aanwezig / weg |
| 3 | Beek | brug 0–3 planken; **tweede uitsnede** van de andere kant met de stapstenen (Roodkapje-moment: kikker, slak, slapende eend) |
| 4 | Huisje buiten | deur dicht / open; emmer op het dak / weg; vogel; rozen dicht / opzij |
| 5 | Kamer van Grootmoeder | kast dicht / open; sjaal 0–4; bed met vermomde Roodkapje / leeg |
| 6 | *Griezelmuseum*: één stilstaand beeld met 4 kleine loops (na de aftiteling) | — |
| 7 | *Telefoon-inzetje* met Wiebe (portret, hergebruik) | — |

### Close-ups en minipuzzelschermen (6)
P3 symbolenslot · familiefoto · P5 kaart (strip met drie paden + stippellijn van het sluippad) · P8 deur met twee knoppen · P9 touwtjesdoolhof · P10 beschuldiging (4 portretten: Roodkapje, Ursula, Das, muis; Ursula en Das hergebruikt van de tv).

### UI
Startscherm met hulpniveau-keuze (pet / detectivehoed) · detectiveboekje (doelen, hints, klopsignaal, foto, sokkenteller, stickers) · inventaris · foto van Grootmoeder als hoekkader · spoorkaartje · tekening "Papa de held" (close-up) · drempelkeuze sok / deur (twee plaatjes) · voorwerpvakje van Roodkapje (één vak) · pauzemenu · instellingen · ouderpagina.

### Voorwerpiconen (13)
briefje · afstandsbediening · tekening · mandje (leeg / met koekjes en want / met bloemen) · ovenwant · koekjes · kaart · foto · plank · sleutel · sok · emmer · bakplaat (alleen in het decor).

### Personages en animaties

| Personage | Animaties | # |
|---|---|---|
| **Walter** | 1 lopen (3 richtingen + spiegelen) · 2 idle · 3 praten · 4 oppakken laag · 5 oppakken hoog · 6 geven · 7 gebruiken · 8 bekijken · 9 au-poten · 10 kloppen · 11 emmer op hoofd · 12 knielen (ridderslag) · 13 twee stappen het pad in en terug · 14 duiken achter de breimand · 15 cape-pose (tekening bekijken) · 16 **graven** (P1) · 17 **in de zetel ploffen + thee laten vallen** (opening) · 18 **wijzen / detectivepose** (ontmaskering) · *overlays:* meel-wit, stuifmeel, **natte pantoffels**, ovenwant in zak, kokshoedje, sokkencape | 18 + 6 overlays |
| **Roodkapje** | idle, praten, schrijven, pad blokkeren, sprint, springen (stapstenen), kietelen met bloem (eend) · *vermomd:* idle in bed (schrijvend handje), praten, pruik-af-sprong · ontmaskerd: praten, schrijven klein | 12 |
| **Wanda** | breien, praten, kloppen op Walters hoofd, tegenhouden aan de deur | 4 |
| **Wiebe** | ridder-idle (mandje / vergiet), praten, ridderslag, tv kijken, koekje pikken, telefoonportret | 6 |
| **Bert** | knagen, praten, planken duwen, proeven | 4 |
| **Grootmoeder** | uit de kast stappen (spionnenpose, zonnebril), praten, koekje eten, sok aanreiken (onder het bed vandaan), sokkencape breien | 5 |
| **Ursula + Das** (op tv) | praten + knipoog / praten met zakdoek | 3 |
| **De Jager** | silhouet snuiven, niezen + hoed vliegt, wegstappen (en 1 loop in het museum) | 3 |
| **Bijfiguren** | vis (oordelen, sok spugen), vogel (boos), krekel, uil (sok gooien), kikker (plons), eend (slapen, niezen + wegvliegen), slak (traag/snel) | 10 |
| | **Totaal** | **± 65 + 6 overlays** (ronde 2 telde ± 60 + 5; graven, zetelplof en detectivepose ontbraken) |

Grootste risico: het aantal animaties van Walter. Overlays (meel, stuifmeel, natte pantoffels, want in zak, kokshoedje, cape) zijn bewust losse sprites bovenop de bestaande animaties, geen nieuwe animaties. De emmer in de inventaris hergebruikt "emmer op hoofd".

---

## Ingesproken regels

Schatting per personage, één taalversie, inclusief hints en verkeerde-voorwerp-reacties.

| Personage | Regels | Waarvan |
|---|---|---|
| Walter | ± 296 | ~81 bekijk-zinnen (+ stippellijn op de kaart), ~56 eigen verkeerd-voorwerp-reacties (+ emmer), ~15 standaardzinnen, ~56 hints (16 doelen × 3 + toestandsvarianten), ~70 verhaal en dialoog, ~14 P5-tochtjes en gekke extra's, ~4 drempel-waarschuwing (3 scènes Speurneus + 1 Meesterdetective) |
| Roodkapje (incl. oma-stem) | ± 90 | vragenspel, weigering, lenen, Roodkapje-moment (11, met de eend), P10-antwoorden, ontmaskering, oudertoets, slot, emmer |
| Grootmoeder | ± 26 | kast (5 verstaanbare mopperzinnen i.p.v. "Mmmf!"), oudertoets, slot, sok 5 aanreiken |
| Wanda | ± 20 | opening, doorvragen (= hint 1), deur per hulpniveau, telefoon |
| Bert | ± 20 | |
| Wiebe | ± 15 | incl. telefoon |
| Ursula + Das | ± 6 | |
| De Jager | ± 3 | + niesvarianten |
| Dieren (uil, kikker, eend, slak, vogel) | ± 8 | eend: snurken, kwak, niezen; kan door een andere stem ingesproken worden |
| **Totaal** | **± 485** | ± 28 min ruwe audio (± 3,5 s per regel); in het slot vervallen ± 4 regels |

**Studio:** Walter 2 dagen, Roodkapje 2 halve dagen (kindstem: korte sessies), de rest samen 1,5 dag. **± 4,5 opnamedagen per taalversie.** Een Nederlandse versie is een aparte opname met hetzelfde script op ± 30 woorden na (zie [seriebijbel](seriebijbel.md#taalkeuze)).

Eerste schrapknop voor VO: bekijk-grappen naar 3 per scène (−30 regels).

### Spreeksnelheid

**Beslissing:** alle stemmen worden **op natuurlijk verteltempo** opgenomen (regie: rustig, duidelijk, voor kinderen van 8). De instelling *spreeksnelheid* verandert **nooit de opname zelf**: geen time-stretch en geen pitch-shift, want een kinderstem (Roodkapje) en komische timing verdragen dat slecht.

| Stand | Pauze tussen twee zinnen | Wat verandert er nog |
|---|---|---|
| Langzaam | ± 0,9 s | ondertitel blijft na de zin nog even staan |
| Normaal (standaard) | ± 0,4 s | — |
| Vlot | ± 0,15 s | volgende zin start zonder wachten; filmpjes blijven per zin wegklikbaar |

- **Pipeline:** één audiobestand per zin, met het script-ID als naam. Een regel van twee zinnen wordt dus als twee bestanden opgenomen (of geknipt). Het dialoogsysteem plakt de pauzes ertussen; de mond-animatie volgt het bestand.
- **Kosten:** geen extra studiodagen; wel ± 10 % meer knipwerk.
- **Speelduur:** de speelduurtoets meet op *normaal*. *Langzaam* voegt ± 0:30 toe aan een speelbeurt, *vlot* haalt er ± 0:15 af.

---

## Speelduurtoets

Gemiddeld kind van 8, eerste keer, klikt rond en probeert een paar keer fout. Tijden per onderdeel; filmpjes zijn al inbegrepen.

| Scène | Onderdelen | Doel | Marge (rondklikker) |
|---|---|---|---|
| **1 Hol** | opening 0:25 · Wanda 0:20 · P1 0:30 · P2 incl. ridderslag 0:25 · P3 1:30 · P4 0:40 · rondklikken 0:20 · vertrek 0:05 | **4:15** | +1:00 |
| **2 Kruispunt** | P5 incl. kaart en één fout tochtje 1:00 · mist, plank, sok 0:10 · vragenspel + weigering 0:30 · bloemen + mandje lenen 0:20 · vergissing 0:20 · Roodkapje-moment incl. eend 0:45 · rondklikken 0:10 | **3:15** | +0:45 |
| **3 Beek** | twijfel 0:10 · Bert 0:15 · plank geven 0:05 · planken leggen 0:40 · vis en rondklikken 0:10 | **1:20** | +0:30 |
| **4 Huisje** | aankomst 0:10 · P8 (één fout + juist) 0:35 · terugklopje 0:10 · rozen 0:15 · doolhof 0:25 · emmergrap 0:05 · rondklikken 0:10 | **1:50** | +0:30 |
| **5 Finale** | binnen + uithoren 0:15 · P10 details 1:05 · beschuldiging (vier plausibele portretten) 0:20 · ontmaskering 0:25 · sleutel 0:15 · kast + oudertoets 0:30 · koekjes (+ sok 5 van oma) 0:10 · slot 0:45 · kast-grappen en sok 0:05 | **3:50** | +1:00 |
| **Totaal** | | **± 14:30** | **tot ± 18:15** |

**Spreiding:** een snelle speler (Meesterdetective, weinig rondklikken) doet ± 11 min, een rondklikker ± 18 min. Sokken, gekke extra's (ook de emmer), de drempel-waarschuwing en het museum na de aftiteling zitten in de marge en nooit op het kritieke pad.

**Valideren (vóór de art start):**
1. **Papieren prototype** (week 2–3): alle puzzels op papier, een spelleider leest de zinnen voor, 6 kinderen van 8–9 jaar. Stopwatch per doel.
2. **Greybox** (week 6): alles speelbaar met placeholder-art en tijdelijke stemmen. De flag-timestamps meten de tijd per doel en het aantal hint-kliks.
3. **Criteria:** mediaan ≤ 14:30, 80 % van de kinderen ≤ 18 min, geen enkel doel met een mediaan boven 2 min (P10 boven 2:30). Wie daarboven gaat, schrapt volgens de lijst hieronder.

### Schraplijst

In deze volgorde, tot de mediaan binnen de 14:30 valt. Samen ± 2:25. Het Roodkapje-moment staat niet meer bovenaan (Lottes lievelingsstuk); het gaat er pas in twee stappen uit als de rest niet volstaat.

| # | Wat | Scène | Wint | Wat we verliezen |
|---|---|---|---|---|
| 1 | Bekijk-grappen naar 3 per scène | alle | −0:20 | −30 regels VO |
| 2 | P3: de eerste schijf (opa/maan) staat al juist en gloeit als voorbeeld | 1 | −0:30 | een deel van de denkpiek van scène 1 |
| 3 | P6: vragenspel één ronde in plaats van twee | 2 | −0:15 | een grap |
| 4 | P7: drie planken in plaats van vier (geen te korte) | 3 | −0:15 | Berts protestgeknaag |
| 5 | P10: mandje-detail weg (drie vragen + puntje; minimum blijft 2) | 5 | −0:10 | de callback "heel veel mandjes" |
| 6 | P9: doolhof met twee touwtjes (vogelhuisje weg) | 4 | −0:10 | de vogelgrap |
| 7 | Wiebes ridderslag wordt één zin | 1 | −0:05 | — |
| 8 | Roodkapje-moment: eend-denkstapje weg (de eend vliegt weg op de eerste vraag) | 2 | −0:10 | het slimme moment van Roodkapje |
| 9 | **Roodkapje-moment** helemaal weg; de sprint (0:05) komt terug in het vergissingsfilmpje | 2 | −0:30 | Lottes wens "Roodkapje spelen" (schuift naar sprookje 2) |

De museumuitleg in het slot is in ronde 3 al ingekort (de oude schrap 8). Als De Jagers *"Ach, het is vast mijn neus"* nog weg moet: −0:03.

**Scope-schrappen (kosten, geen tijd):** sokkenteller met scène-indicatie (alleen nog "3/5"; de drempel-waarschuwing gebruikt dan de Meesterdetective-zin) → spoorkaartje → sokkencape (alleen het boekje-sticker blijft) → museumbeeld na de aftiteling → telefoon-inzetje (Wiebe wordt een stem).

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
| Slot (De Jager, telefoon, partners) | 0:45 |
| **Totaal filmpjes** | **2:45** (ronde 1: 3:25, ronde 2: 2:55) |
| *Korte momenten in het spel* (ridderslag, twijfel aan de beek, terugklopje, koekjes aan oma): de besturing blijft actief | *± 0:40* |
| *Roodkapje-moment* (speelbaar, telt als speeltijd) | *± 0:45* |
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
| 0:07–0:25 | Shot / tegenshot | Dialoog tot *"Wat is een sleutel eigenlijk?"*; de kastdeur rammelt één keer | Oma, luid en verstaanbaar: *"Roodkapje! Ik zei toch dat die wolf oké is!"* |
| — | *speler zoekt de sleutel (P11)* | | |
| **Kast** | | | |
| K+0:00 | Sleutel in het slot → camera schuift traag naar de kast; licht iets gedimd, warme spot op de kast | De HELP-sjaal wordt met een *sssslurp* de kast in gezogen | 1 s stilte |
| K+0:02 | Statisch | Slot draait: *klik... klik... KLIK* (ritme ⬤ ● ● van het terugklopje) | Basnoot onder elke klik |
| K+0:04 | Kleine camera-schok (uit bij "minder beweging") | Deuren zwaaien open, een wolk **breiwol** (geen rook) dwarrelt eruit | **Spionnenthema volledig** |
| K+0:05 | Lage hoek, heldenshot | Grootmoeder stapt eruit in spionnenpose, zonnebril op; de sjaal ontrolt zich over de hele breedte: H-E-L-P | Trompetstoot |
| K+0:08 | Muziek stopt abrupt | Zonnebril af: *"Een kwartier. Ik zit al een KWARTIER in een kast."* | Krekel tjirpt (callback) |
| K+0:10–0:30 | Rustig tweeshot oma / Roodkapje | Roodkapje bladert in haar boekje, vindt de regel zelf terug, sorry; "Onderstreept" | Zachte versie van het spionnenthema |

- **Trailershot:** K+0:05 (sjaal over het hele scherm).
- Geen flitsen. K+0:00 tot K+0:05 is niet wegklikbaar (5 s); al de rest wel.

**Tweede, kleiner wauw:** de mist die optrekt op het kruispunt (P5): drie lantaarntjes, dan zonlicht en scherpe silhouetten, met de overgang naar volle strijkers.

---

## Team en planning

**Team:** 1 game designer/scenarist, 1 developer, 1 achtergrondartist, 1 personage-animator, **1 UI-ontwerper (freelance)**, **1 QA-tester (deeltijds, voltijds tijdens polish)**, freelance audio (VO-regie, SFX) en componist.

| Fase | Duur |
|---|---|
| Engine-spike en open beslispunten (zie *Technische uitgangspunten*) | week 1–2 |
| Papieren prototype + greybox (alle puzzels speelbaar, placeholder-art) | 6 weken |
| Engine-tooling (dialoog, flags, hints, boekje, hulpniveaus) | 8 weken, parallel |
| **UI-ontwerp**: boekje, inventaris, hulpniveau-keuze, drempelkeuze, menu's, instellingen, ouderpagina; eerst als wireframe in de greybox, daarna in de eindstijl | ± 10 weken verspreid, vanaf week 3, parallel |
| Art + animatie | 12–14 weken |
| VO, muziek en SFX | 4 weken, parallel met art |
| **QA**: testplan uit de softlock-tabel, het flagmodel en de verkeerde-voorwerp-tabel; testmatrix 2 hulpniveaus × muis/tablet × 3 spreeksnelheden × saveplaatsen; elke build een volledige speelbeurt + sokkenroute | deeltijds vanaf de greybox (week 6), voltijds in de polishfase |
| Polish, speeltests met kinderen, bugfix | 6 weken |
| **Sprookje 1** | **± 7 maanden** (UI en QA lopen parallel en verlengen de planning niet) |
| Volgende sprookjes (tooling en vaste cast herbruikbaar) | ± 4 maanden per stuk |

**Grootste risico's:** animatiecount van Walter, VO-telling (twee taalversies verdubbelen de studiotijd), speelduur van P10, en de testmatrix (hulpniveaus, toestellen, instellingen). Elk risico heeft een schrapknop hierboven; voor de testmatrix is dat de eerste scope-schrap (sokkenteller met scène-indicatie).

---

## Systeemschermen en ouderpagina (kort)

**Hoofdmenu:** Verder spelen · Nieuw verhaal · Instellingen · Voor ouders. Grote plaatjes, alles ingesproken.

**Hulpniveau:** bij een nieuw verhaal (pet of detectivehoed); wisselbaar in het pauzemenu.

**Opslaan:** **automatisch** na elke opgeloste puzzel en bij elke scènewissel (de flags zijn de save). Hervatten zet je terug op de laatste plek, met een korte zin van Walter: *"Waar was ik? Oh ja."* Drie saveplaatsen (voor broers en zussen), elk met een tekening als naam. Er is per saveplaats maar één save, dus het ontwerp zorgt dat geen enkele autosave iets optioneels onbereikbaar maakt: sok 1 komt automatisch, op de drempel van oma's kamer waarschuwt Walter één keer voor ontbrekende sokken (de keuze wordt pas daarna opgeslagen), en sok 5 is gegarandeerd vóór het slot.

**Pauzemenu:** verder · boekje · hulpniveau · instellingen · naar het hoofdmenu.

**Instellingen:** volume (muziek, stemmen, effecten apart) · spreeksnelheid (langzaam / normaal / vlot: pauzes tussen zinnen, zie *Spreeksnelheid*) · ondertitelgrootte (3 standen) · minder beweging · spoorkaartje aan/uit · linkshandige inventaris (tablet).

**Voor ouders** (achter een eenvoudig ouderslot: hou twee knoppen 3 s ingedrukt):
- Geen advertenties, geen in-app aankopen, geen account, geen internet nodig, geen gegevens verzameld. Speeltest-metingen bestaan alleen in testversies.
- Wat er in het verhaal gebeurt, in drie zinnen, en welke waarden erin zitten (niet meegaan met vreemden, geen cadeaus van vreemden aannemen, vreemden niet vertellen waar je naartoe gaat, eerlijk zijn, niemand opsluiten, een grote mens halen als je bang bent). In het spel komen ze uit grappige dialoog en uit wat de personages zelf ontdekken; hier staan ze voluit. Zie de [seriebijbel](seriebijbel.md#oudertoets-en-waarden).
- Speelduur (± 15 min), hulpniveaus uitgelegd, toegankelijkheidsopties.
- Credits.
