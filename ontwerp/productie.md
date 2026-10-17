# Fairly Odd Tales: productie (sprookje 1, Roodkapje)

Hoort bij het hoofdontwerp in [`README.md`](../README.md). Alle tijden en tellingen gaan over *De Zaak van de Rode Zakdoek* in de versie van ronde 4.

**Uitgangspunt:** alle filmpjes zijn **in-engine scènes** (dezelfde sprites, scriptcamera, geen aparte cinematics). Dat houdt de animatiecount laag en maakt elk filmpje per zin wegklikbaar. Ook de opening (0:08) is zo'n in-engine scène: er is geen apart openingsfilmpje, en het nieuws loopt op de achtergrond terwijl het kind al speelt.

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
| **Animatie** | Personages als **cut-out/skeletanimatie** (bv. Spine of de 2D-skeletten van de engine), decors als lagen | Overlays (meel, want in zak, cape, sokjes rond het hoofd) en hergebruik van bewegingen (één valsysteem voor heel het spel) worden goedkoop. |
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
- **Slapstick:** vallen zijn snel en rond (squash & stretch), zonder pijngezicht. Sokjes rond het hoofd in plaats van sterretjes; een klein stofwolkje bij V2.

**Muziek per scène**

| Scène | Sfeer | Instrumenten |
|---|---|---|
| Hol | gezellig, sloffend walsje (onder het nieuws gedempt) | accordeon, klarinet, pizzicato |
| Kruispunt | mysterieus in de mist, opent naar licht als de mist optrekt | glockenspiel, lage strijkers → volle strijkers |
| Roodkapje-moment | snel en speels | **Roodkapje-thema** (pizzicato, houtblok) |
| Beek | werfritme van Bert | banjo, tuba, klotsend water |
| Huisje | spanning, op de tippen van je tenen | pizzicato, brushes |
| Oma's kamer / finale | **spionnenthema** dat langzaam opbouwt | contrabas, bongo's, gestopte trompet |
| Slot | spionnenthema + Roodkapje-thema samen | volle band |
| Bonus: museum | het spionnenthema als gegromd wolvenkoortje | vijf wolvenstemmen (één stemacteur, gestapeld), contrabas |

Het **spionnenthema** wordt drie keer geplant voor het volledig speelt: twee maten bij Wanda's "Spionne", één basnoot onder het terugklopje (P8) en drie basnoten onder het slot van de kast.

**Belangrijke SFX:** klein klopje (hoog hout, *tok*) vs. grote BONK (diep, met trilling), gedempt terugklopje uit de kast, kast-gemopper (verstaanbaar, boos en niet bang) met tikkende breinaalden, *HATSJOE* als leitmotiv (telkens even herkenbaar), lantaarntje aan (*ting* + warme zoem), plank klikt vast, **valset** (struikel-*wah*, *floep* + stofwolk, plons + *blub*, *bonk* + sokjes-tinkel), lade-klem, scheetkussen (één keer; terugvaloptie zetelveer *BOIIING*), huil + verre honden, radiokraak, *tik* van de waarom-teller, confettipuf, emmer op hoofd, lachende vis in bubbels, krekel die stopt.

---

## Assetlijst

### Decors (5 + 2 kleine)

| # | Decor | Varianten / lagen |
|---|---|---|
| 1 | Wolvenhol (woonkamer + open keuken, 1 scherm + lichte scroll) | tv: nieuws / breiprogramma / tekenfilm; bakplaat in oven / op aanrecht; Wiebe met mandje / met vergiet; scheetkussen achter de zetel / weg |
| 2 | Kruispunt | mist 3 lagen (per pad); 0–3 lantaarntjes aan; borden op de grond / aan de herkenningspunten; plank aanwezig / weg |
| 3 | Beek | brug 0–3 planken; planken drijvend (plons); **tweede uitsnede** van de andere kant met de stapstenen (Roodkapje-moment: kikker, slak, slapende eend) |
| 4 | Huisje buiten | deur dicht / open; emmer op het dak / weg; vogel; rozen dicht / opzij |
| 5 | Kamer van Grootmoeder | kast dicht / open; sjaal 0–4; bed met vermomde Roodkapje (krullen recht / achterstevoren, deken hoog / laag, kussen op het mandje) / leeg; breimand |
| 6 | *Griezelmuseum* (bonus): één beeld met hotspotlagen: vijf wolven op krukjes, sokkel met spot en sok nr. 6, bordjes, De Jager van achteren | openingsbeeld 0:10 + speelbord |
| 7 | *Radio-inzetje* met Wiebe in papa's zetel (portret, hergebruik) | — |

### Close-ups en minipuzzelschermen (6)
P3 symbolenslot (met handgreep) · familiefoto · P5 kaart (strip met drie paden + stippellijn van het sluippad) · P8 deur met twee knoppen · P9 touwtjesdoolhof · P10 beschuldiging (4 portretten: Roodkapje, Ursula, Das, muis; Ursula en Das hergebruikt van de tv).

### UI
Startscherm met hulpniveau-keuze (pet / detectivehoed) · detectiveboekje (doelen, hints, klopsignaal, foto, sokkenteller, stickers, ook *Sok nr. 6*) · inventaris · **huilknop** (maantje naast het boekje) · foto van Grootmoeder als hoekkader · spoorkaartje · tekening "Papa de held" (close-up) · drempelkeuze sok / deur (twee plaatjes) · voorwerpvakje van Roodkapje (één vak) · keuze 💬 / 😱 BOE in P10 · bonus: knoppen *Sluip binnen* / *Klaar* en drie plaatjesdoelen · pauzemenu · instellingen · ouderpagina.

### Voorwerpiconen (14)
briefje · afstandsbediening · tekening · **Ridder-radio** · mandje (leeg / met koekjes en want / met bloemen) · ovenwant · koekjes · kaart · foto · plank · sleutel · sok · emmer · bakplaat (alleen in het decor).

### Personages en animaties

| Personage | Animaties | # |
|---|---|---|
| **Walter** | 1 lopen (3 richtingen + spiegelen) · 2 idle · 3 praten · 4 oppakken laag · 5 oppakken hoog · 6 geven · 7 gebruiken (ook: radio aan het oor) · 8 bekijken · 9 au-poten · 10 kloppen · 11 emmer op hoofd · 12 knielen (ridderslag) · 13 twee stappen het pad in en terug · 14 cape-pose (tekening bekijken) · 15 graven (P1) · 16 in de zetel ploffen (opening) · 17 wijzen / detectivepose (ontmaskering) · **18 V1 struikelen** · **19 V2 plat op de snuit** (variant: duik in de breimand, vervangt de oude aparte duik) · **20 V3 plons** · **21 V4 bonk en loensen** · **22 huilen** · *overlays:* meel-wit, stuifmeel, natte pantoffels, ovenwant in zak, kokshoedje, sokkencape, **sokjes rond het hoofd**, **stofwolkje**, **pantoffel met hap** | 22 + 9 overlays |
| **Roodkapje** | idle, praten, schrijven, pad blokkeren, sprint, springen (stapstenen), kietelen met bloem (eend) · *vermomd:* idle in bed (schrijvend handje), praten, pruik-af-sprong (de eerste helft is ook de BOE-schrik), **bril en potlood** (ze duwt, vist), **deken trekken en kussen ploffen** · *ontmaskerd:* praten, schrijven klein, **emmer op en tegen de kast stappen** | 15 |
| **Wanda** | breien (ook: hand uitsteken voor het scheetkussen), praten, kloppen op Walters hoofd, tegenhouden aan de deur | 4 |
| **Wiebe** | ridder-idle (mandje / vergiet), praten (ook: meehuilen), ridderslag, tv kijken, koekje pikken, radioportret, **giechelen achter de zetel** | 7 |
| **Bert** | knagen (ook: pantoffel), praten, planken duwen, proeven | 4 |
| **Grootmoeder** | uit de kast stappen (spionnenpose, zonnebril), praten (ook: stempelen), koekje eten, sok aanreiken (onder het bed vandaan), sokkencape breien | 5 |
| **Ursula + Das** (op tv) | praten + knipoog (ook: opzij kijken en wachten) / praten met zakdoek (de zakdoek valt over hem heen) | 3 |
| **De Jager** | silhouet snuiven, niezen + hoed vliegt (ook: in het museum, van achteren), wegstappen (ook: de hoed achterna in het museum) | 3 |
| **Bijfiguren** | vis (oordelen, sok spugen, **lachen in bubbels**), vogel (boos), krekel, uil (sok gooien), kikker (plons), eend (slapen, niezen + wegvliegen), slak (traag/snel) | 11 |
| **Museumwolf** (bonus; één rig, vijf kleur- en propvarianten) | **giechelen / proesten**, **meehuilen** (grommen, krant lezen, breien en horloge kijken zijn de bestaande loops van het museumbeeld) | 2 |
| | **Overlay voor andere personages:** emmer op het hoofd (Bert, vis, Roodkapje) | + 1 overlay |
| | **Totaal** | **± 76 + 10 overlays** (ronde 3: 65 + 6) |

Grootste risico blijft het aantal animaties van Walter (22, netto +4: vijf nieuw, de aparte duik achter de breimand vervalt). Overlays (meel, stuifmeel, natte pantoffels, want in zak, kokshoedje, cape, sokjes, stofwolk, pantoffel met hap, emmer op andermans hoofd) zijn bewust losse sprites bovenop de bestaande animaties. De emmer in de inventaris hergebruikt "emmer op hoofd". Per scope-laag: *moet* = Walter V1–V4, sokjes, stofwolk, vis lacht, Wiebe giechelt, emmer-overlay; *zou* = huilen, Roodkapje vermomd (2), pantoffel met hap; *mag* = museumwolf (2), Roodkapje met emmer (1).

---

## Ingesproken regels

Schatting per personage, één taalversie, inclusief hints en verkeerde-voorwerp-reacties. **De tellingen zijn netto**: alle vervallen regels (tsjoeng- en bijna-zinnen, de tweede vragenronde, het oude slot, het telefoongesprek) zijn al afgetrokken.

| Personage | Regels | Waarvan |
|---|---|---|
| Walter | ± 323 | ~81 bekijk-zinnen, ~60 eigen verkeerd-voorwerp-reacties (+ emmer bij Bert, vis), ~15 standaardzinnen, ~56 hints (16 doelen × 3 + toestandsvarianten), ~68 verhaal en dialoog, ~14 P5-tochtjes en gekke extra's, ~4 drempel-waarschuwing, ~25 vallen en foutzinnen (3 zetelscores van de grond, ± 8 valgeluiden, 4 lade-zinnen, oven, 2 plonszinnen, klopje, stapstenen), ~4 chaos (huilen, radio, BOE, pantoffel), 1 in de bonus (*"Snif. Peperkoek?"*) |
| Roodkapje (incl. oma-stem) | ± 100 | vragenspel (één ronde, "Tien! Record."), weigering, lenen, Roodkapje-moment (11, met de eend), P10-antwoorden, vermomming ("Welk mandje?"), BOE (5), radio (2), oma-stem bij huilknop en radio (3), ontmaskering, oudertoets, slot, emmer (4) |
| Grootmoeder | ± 32 | kast (5 mopperzinnen), luisteremmer (4), radio en emmer-bonk (2), oudertoets, slot, sok 5 (normaal + gedempt) |
| Wanda | ± 21 | opening (telegram, 3), scheetkussen en huilknop (2), doorvragen (= hint 1), deur per hulpniveau |
| Bert | ± 26 | incl. *te kort / te lang* (3), pantoffel, emmer, huilknop |
| Wiebe | ± 26 | P2 met de radio, scheetkussen, radiozinnen (8), slot via de radio (2) |
| Ursula + Das | ± 7 | incl. *"...Ik wacht wel."* |
| De Jager | ± 3 | slot + niesvarianten (zijn museumzinnen staan in de rij hieronder) |
| Dieren (uil, kikker, eend, slak, vogel) | ± 8 | eend: snurken, kwak, niezen; kan door een andere stem ingesproken worden |
| Museumwolven + De Jager in het museum | ± 9 | één wolvenstem: 5 grommen, *"Nog drie uur negenenvijftig"*, koortje; De Jager: *"Hm?"*, *"Snif. ...Ik dacht even dat ik wolf rook."*, *"Het tocht hier."* |
| **Totaal** | **± 555** | ± 30 min ruwe audio (± 3,5 s per regel; valgeluiden en grommen zijn korter). Per laag: ronde 3 ± 485 · *moet* + 34 · *zou* + 23 · *mag* + 13 |

**Studio:** Walter 2,25 dagen, Roodkapje 2 halve dagen + één korte extra sessie (kindstem), de rest samen 1,75 dag. **± 5 opnamedagen per taalversie** (ronde 3: 4,5). Een Nederlandse versie is een aparte opname met hetzelfde script op ± 30 woorden na (zie [seriebijbel](seriebijbel.md#taalkeuze)).

Eerste schrapknop voor VO: bekijk-grappen naar 3 per scène (−30 regels). Daarna de *mag*- en *zou*-laag (−36).

### Spreeksnelheid

**Beslissing:** alle stemmen worden **op natuurlijk verteltempo** opgenomen (regie: rustig, duidelijk, voor kinderen van 8). De instelling *spreeksnelheid* verandert **nooit de opname zelf**: geen time-stretch en geen pitch-shift, want een kinderstem (Roodkapje) en komische timing verdragen dat slecht. De instelling regelt alleen de **pauze tussen twee zinnen**, en die pauze geldt overal: tussen twee zinnen binnen één regel én tussen twee sprekers.

| Stand | Pauze tussen twee zinnen | Ondertitel |
|---|---|---|
| Langzaam | ± 0,9 s | blijft na de zin nog even staan |
| Normaal (standaard) | ± 0,4 s | — |
| Vlot | ± 0,15 s | springt meteen naar de volgende zin |

- **Pipeline:** één audiobestand per zin, met het script-ID als naam. Een regel van twee zinnen wordt dus als twee bestanden opgenomen (of geknipt). Het dialoogsysteem plakt de pauzes ertussen; de mond-animatie volgt het bestand. Filmpjes blijven per zin wegklikbaar.
- **Kosten:** geen extra studiodagen; wel ± 10 % meer knipwerk.
- **Speelduur:** een mediane speelbeurt telt ± 130 zinsovergangen (± 40 in de filmpjes, ± 90 in dialogen op het kritieke pad; losse bekijk-zinnen hebben er geen). *Langzaam* voegt dus ± 130 × 0,5 s ≈ **+1:05** toe, *vlot* haalt er ± 130 × 0,25 s ≈ **−0:30** af. De speelduurtoets meet op *normaal*; *langzaam* wordt in de greybox apart gemeten.

---

## Speelduurtoets

Gemiddeld kind van 8, eerste keer, klikt rond en probeert een paar keer fout. Tijden per onderdeel; filmpjes zijn al inbegrepen.

| Scène | Onderdelen | Doel | Marge (rondklikker) |
|---|---|---|---|
| **1 Hol** | opening 0:08 · nieuws op de achtergrond (loopt parallel met P1, 0:00 extra) · val na het nieuws 0:04 · Wanda 0:12 · P1 0:30 · P2 incl. ridderslag en radio 0:20 · P3 1:25 · P4 0:30 · rondklikken en chaos 0:26 · vertrek 0:05 | **3:40** | +1:15 |
| **2 Kruispunt** | P5 incl. kaart en één fout tochtje 1:00 · mist, plank, sok 0:10 · vragenspel (één ronde, waarom-teller) + weigering 0:23 · bloemen + mandje lenen 0:20 · vergissing 0:20 · Roodkapje-moment incl. eend 0:45 · rondklikken en chaos 0:17 | **3:15** | +0:50 |
| **3 Beek** | twijfel 0:10 · Bert 0:15 · plank geven 0:05 · planken leggen incl. één plons 0:45 · vis, stapstenen en rondklikken 0:15 | **1:30** | +0:35 |
| **4 Huisje** | aankomst 0:10 · P8 (één fout + juist) 0:35 · terugklopje 0:10 · rozen 0:15 · doolhof 0:25 · emmergrap 0:05 · rondklikken en chaos 0:15 | **1:55** | +0:35 |
| **5 Finale** | binnen + uithoren 0:15 · P10 details 1:00 · beschuldiging (vier plausibele portretten) 0:20 · ontmaskering 0:25 · sleutel 0:15 · kast + oudertoets 0:30 · koekjes (+ sok 5 van oma) 0:10 · slot 0:35 · kast-grappen, BOE en sok 0:05 | **3:35** | +1:05 |
| **Totaal** | | **± 13:55** | **tot ± 18:15** |
| *Bonus* | *museum: openingsbeeld 0:10 + speelbord 0:50–1:20* | *buiten de speelduur* | |

**Waar de tijd vandaan komt** (t.o.v. ronde 3, 14:30): opening en Wanda parallel en in telegramstijl −0:21, ridderslag in één zin −0:05, P3 −0:05 (de foutzin noemt de foute plek), P4 in één beweging −0:10, vragenspel één ronde −0:07, P10 kortere "klopt"-zinnen −0:05, slot −0:10 (samen −1:03); erbij: vallen, plonsen en chaos in het rondklikken van scène 1–4 +0:28. Netto −0:35, en die marge is bewust voor P10 + beschuldiging (het grootste risico) en voor chaosklikkers als Mats.

**Spreiding:** een snelle speler (Meesterdetective, weinig rondklikken) doet ± 10:30, een rondklikker ± 18:15. Sokken, gekke extra's, chaos (huilknop, emmer, radio, BOE), de drempel-waarschuwing en de bonus zitten in de marge en nooit op het kritieke pad.

**Valideren (vóór de art start):**
1. **Papieren prototype** (week 2–3): alle puzzels op papier, een spelleider leest de zinnen voor, 6 kinderen van 8–9 jaar (minstens twee "chaoskinderen" zoals Mats). Stopwatch per doel; P10 en de beschuldiging apart.
2. **Greybox** (week 6): alles speelbaar met placeholder-art en tijdelijke stemmen. De flag-timestamps meten de tijd per doel en het aantal hint-kliks; in testbuilds telt een teller elke val, huil en chaosklik.
3. **Criteria:** mediaan ≤ 14:30, 80 % van de kinderen ≤ 18 min, eerste klik ≤ 0:10, vertrek uit het hol ≤ 3:45 (mediaan), geen enkel doel met een mediaan boven 2 min, P10 + beschuldiging samen ≤ 2:30. Wie daarboven gaat, schrapt volgens de lijst hieronder.

### Schraplijst

In deze volgorde, tot de mediaan binnen de 14:30 valt. Samen ± 2:05. De punten "vragenspel één ronde" en "ridderslag één zin" uit ronde 3 zijn al verwerkt.

| # | Wat | Scène | Wint | Wat we verliezen |
|---|---|---|---|---|
| 1 | Bekijk-grappen naar 3 per scène | alle | −0:20 | −30 regels VO |
| 2 | P3: de eerste schijf (opa/maan) staat al juist en gloeit als voorbeeld | 1 | −0:30 | een deel van de denkpiek van scène 1 |
| 3 | P7: drie planken in plaats van vier (geen te korte) | 3 | −0:15 | Berts protestgeknaag |
| 4 | P10: mandje-detail weg (drie vragen + puntje; minimum blijft 2) | 5 | −0:10 | de callback "heel veel mandjes" |
| 5 | P9: doolhof met twee touwtjes (vogelhuisje weg; de huilknop bij het huisje houdt dan alleen de oma-stem) | 4 | −0:10 | de vogelgrap |
| 6 | Roodkapje-moment: eend-denkstapje weg (de eend vliegt weg op de eerste vraag) | 2 | −0:10 | het slimme moment van Roodkapje |
| 7 | **Roodkapje-moment** helemaal weg; de sprint (0:05) komt terug in het vergissingsfilmpje | 2 | −0:30 | Lottes wens "Roodkapje spelen" (schuift naar sprookje 2) |

### Scope-lagen

Alles wat ronde 4 toevoegt, zit in een laag. Schrappen gebeurt van onder naar boven en breekt nooit het ontwerp: aan de lagen *zou* en *mag* hangt geen enkele puzzelflag.

| Laag | Wat | Kost | Valt het weg, dan... |
|---|---|---|---|
| **Moet** | sneller begin (nieuws op de achtergrond, Wanda in telegramstijl, P2 in één zin, P4 in één beweging) · slapstick V1–V4 met sokjes, stofwolk en zetelscore van de grond · fout = grap met informatie (P3, P4, P7, P8) · vragenspel één ronde met waarom-teller · korter slot · Ridder-radio (incl. slot-inzetje) · één scheetkussen (of zetelveer) · emmer → Bert en vis · de PO-punten uit ronde 3 | Walter +4, vis lacht, Wiebe giechelt, 3 overlays; VO + 34 | — (dit is de kern van ronde 4) |
| **Zou** | huilknop · BOE · vermomming die uit elkaar valt · luisteremmer · Bert eet de pantoffel · val op de stapstenen | Walter +1 (huilen), Roodkapje +2, 1 overlay; VO + 23 | de grappen vallen weg, de puzzels blijven gelijk |
| **Mag** | speelbare bonus in het museum · emmer → Roodkapje · *"...Ik wacht wel."* van Ursula | museumwolf +2, Roodkapje +1; VO + 13; UI: 3 plaatjesdoelen | de bonus wordt weer het filmpje van 0:15 met sok nr. 6 in beeld |

**Volgorde van de scope-schrappen (kosten, geen tijd):** laag *mag* (eerst emmer → Roodkapje, dan Ursula, dan de bonus) → laag *zou* (stapstenen, pantoffel, vermomming, luisteremmer, BOE, huilknop) → sokkenteller met scène-indicatie (alleen nog "3/5"; de drempel-waarschuwing gebruikt dan de Meesterdetective-zin) → spoorkaartje → sokkencape (alleen de sticker blijft) → museumbeeld na de aftiteling → radio-inzetje (Wiebe wordt alleen een stem).

**Wat nooit geschrapt wordt:** P10 met de foto, de HELP-sjaal, de oudertoets-regels (P6, kast, toestemming), Wiebes tekening, Wiebe in het slot (minstens als stem), De Jager aan het raam.

---

## Filmpjesbudget

Doel: **hoogstens 3 minuten** aan filmpjes. Alles in-engine en per zin wegklikbaar, behalve de eerste 5 seconden van het wauw-moment (de beloning).

| Filmpje | Duur |
|---|---|
| Opening (zetelplof + scheetkussen) | 0:08 |
| Val na het nieuws | 0:04 |
| Wanda (telegramstijl) | 0:12 |
| De vergissing | 0:20 |
| Ontmaskering | 0:25 |
| Kast open (wauw) + oudertoets + sorry | 0:30 |
| Slot (De Jager, radio, partners) | 0:35 |
| **Totaal filmpjes** | **± 2:15** (ronde 1: 3:25, ronde 2: 2:55, ronde 3: 2:45) |
| *Nieuws op de achtergrond* (besturing aan, telt als speeltijd) | *± 0:15* |
| *Korte momenten in het spel* (ridderslag, twijfel aan de beek, terugklopje, koekjes aan oma): de besturing blijft actief | *± 0:35* |
| *Roodkapje-moment* (speelbaar, telt als speeltijd) | *± 0:45* |
| *Sokkencape* (alleen bij 5 sokken) | *+ 0:08* |
| *Bonus: Griezelmuseum* (openingsbeeld 0:10 + speelbaar; buiten de speelduur) | *1:00–1:30* |

De huilknop staat uit tijdens alle filmpjes.

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

**Team:** 1 game designer/scenarist, 1 developer, 1 achtergrondartist, 1 personage-animator, **1 personage-ontwerper (freelance, week 3–6)** voor de model sheets van de vaste cast en de museumwolf (eindverantwoordelijk: de personage-animator), **1 UI-ontwerper (freelance)**, **1 QA-tester (deeltijds, voltijds tijdens polish)**, freelance audio (VO-regie, SFX) en componist.

| Fase | Duur |
|---|---|
| Engine-spike en open beslispunten (zie *Technische uitgangspunten*) | week 1–2 |
| Papieren prototype + greybox (alle puzzels speelbaar, placeholder-art) | 6 weken |
| **Personage-ontwerp**: model sheets (Walter met de vier valposes, Roodkapje vermomd en ontmaskerd, Wanda, Wiebe, Bert, Grootmoeder, De Jager als silhouet, museumwolf) | week 3–6, parallel |
| Engine-tooling (dialoog, flags, hints, boekje, hulpniveaus, eenmalige chaosreacties) | 8 weken, parallel |
| **UI-ontwerp**: boekje, inventaris, huilknop, hulpniveau-keuze, drempelkeuze, BOE-keuze, bonusdoelen, menu's, instellingen, ouderpagina; eerst als wireframe in de greybox, daarna in de eindstijl | ± 10 weken verspreid, vanaf week 3, parallel |
| Art + animatie | 13–15 weken (ronde 3: 12–14; + 11 animaties en 4 overlays) |
| VO, muziek en SFX | 4 weken, parallel met art |
| **QA**: testplan uit de softlock-tabel, het flagmodel, de verkeerde-voorwerp-tabel en de `CHAOS_*`-lijst (elke chaosreactie vóór en na de puzzel op die plek); testmatrix 2 hulpniveaus × muis/tablet × 3 spreeksnelheden × saveplaatsen; elke build een volledige speelbeurt + sokkenroute + "chaosroute" (alles aanklikken, met elke emmer en radio) | deeltijds vanaf de greybox (week 6), voltijds in de polishfase |
| Polish, speeltests met kinderen, bugfix | 6 weken |
| **Sprookje 1** | **± 7 maanden** (personage-ontwerp, UI en QA lopen parallel; de extra art-week valt binnen de polishbuffer) |
| Volgende sprookjes (tooling, valsysteem en vaste cast herbruikbaar) | ± 4 maanden per stuk |

**Grootste risico's:** animatiecount van Walter (22), VO-telling (twee taalversies verdubbelen de studiotijd), speelduur van P10, de testmatrix (hulpniveaus, toestellen, instellingen) en de chaosreacties (veel kleine combinaties). Elk risico heeft een schrapknop hierboven: voor Walter en de chaos zijn dat de scope-lagen *mag* en *zou*, voor de testmatrix de sokkenteller met scène-indicatie.

---

## Systeemschermen en ouderpagina (kort)

**Hoofdmenu:** Verder spelen · Nieuw verhaal · Instellingen · Voor ouders. Grote plaatjes, alles ingesproken.

**Hulpniveau:** bij een nieuw verhaal (pet of detectivehoed); wisselbaar in het pauzemenu.

**Opslaan:** **automatisch** na elke opgeloste puzzel en bij elke scènewissel (de flags zijn de save). Hervatten zet je terug op de laatste plek, met een korte zin van Walter: *"Waar was ik? Oh ja."* Drie saveplaatsen (voor broers en zussen), elk met een tekening als naam. Er is per saveplaats maar één save, dus het ontwerp zorgt dat geen enkele autosave ongemerkt iets optioneels onbereikbaar maakt: sok 1 komt automatisch, op de drempel van oma's kamer waarschuwt Walter één keer voor ontbrekende sokken (de keuze wordt pas daarna opgeslagen), en sok 5 is gegarandeerd vóór het slot. De bonus na de aftiteling bewaart alleen de sticker *Sok nr. 6*.

**Pauzemenu:** verder · boekje · hulpniveau · instellingen · naar het hoofdmenu.

**Instellingen:** volume (muziek, stemmen, effecten apart) · spreeksnelheid (langzaam / normaal / vlot: pauzes tussen zinnen, zie *Spreeksnelheid*) · ondertitelgrootte (3 standen) · minder beweging · spoorkaartje aan/uit · linkshandige inventaris (tablet).

**Voor ouders** (achter een eenvoudig ouderslot: hou twee knoppen 3 s ingedrukt):
- Geen advertenties, geen in-app aankopen, geen account, geen internet nodig, geen gegevens verzameld. Speeltest-metingen bestaan alleen in testversies.
- Wat er in het verhaal gebeurt, in drie zinnen, en welke waarden erin zitten (niet meegaan met vreemden, geen cadeaus van vreemden aannemen, vreemden niet vertellen waar je naartoe gaat, eerlijk zijn, niemand opsluiten, een grote mens halen als je bang bent). In het spel komen ze uit grappige dialoog en uit wat de personages zelf ontdekken; hier staan ze voluit. Zie de [seriebijbel](seriebijbel.md#oudertoets-en-waarden).
- Humor: slapstick zonder pijn (Walter valt over zijn eigen pantoffels en staat meteen recht), één scheetkussengrap van het welpje, niemand wordt gepest of uitgelachen.
- Speelduur (± 15 min, plus een korte bonus na de aftiteling), hulpniveaus uitgelegd, toegankelijkheidsopties.
- Credits.
