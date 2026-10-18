# Fairly Odd Tales: productie (sprookje 1, Roodkapje)

Hoort bij het hoofdontwerp in [`README.md`](../README.md). Alle tijden en tellingen gaan over *De Zaak van de Rode Zakdoek* in de **kaartspelversie van ronde 6**. De point-&-click-versie van ronde 5 staat in [`archief/productie-point-and-click-ronde-5.md`](archief/productie-point-and-click-ronde-5.md); sommige onderdelen hieronder (spreeksnelheid, wauw-moment, muziek) komen daar bijna ongewijzigd uit.

**Uitgangspunt:** het speelbord is één herbruikbaar scherm (Walter links, tegenstanders rechts, kaarten onderaan) op een achtergrond per scène. Alle filmpjes zijn **in-engine scènes** met dezelfde sprites, per zin wegklikbaar.

---

## Technische uitgangspunten

| Onderwerp | Aanbevolen keuze | Waarom |
|---|---|---|
| **Platform** | **Tablet** (iPad, Android-tablet) **en pc/Mac**, tegelijk uitgebracht | Kaarten slepen of tik-tik werkt op beide. |
| **Stores** | App Store, Google Play, Steam, en **gratis in de browser** (web-export van Godot) | Gratis voor iedereen betekent ook: zonder tablet of store-account, op een schoolcomputer. Eén build-pipeline. |
| **Minimale hardware** | iPad 9e generatie (2021) of nieuwer · Android 10+ met 3 GB RAM · Windows 10 / macOS 12 | 2D, weinig tegelijk in beeld. |
| **Beeld** | 1920 × 1080 (16:9) met een **veilige zone voor 4:3** (iPad). De hand van 4 kaarten, de knop *Klaar* en de plannetjes staan altijd in de 4:3-zone. | |
| **Engine** | **Godot 4** (2D) | Geen licentiekosten, sterke 2D. Kaartspel-logica is maatwerk, maar eenvoudig: data-gedreven kaarten en tegenstanders. |
| **Data** | **Kaarten, tegenstanders, zakschatten en boskaarten als datatabellen** (bv. JSON of Godot-resources), met één effect-taal (💬 x, 🛋️ x, 😆 x, 🦋 x, 💪 x, trek x, ☕ x, 💛 x, 💨, 💧). Geen kaart heeft eigen code, behalve de zeven verhaalkaarten (afstandsbediening, *Mandje lenen*, klopjes, *"Grootmoeder, wat heb jij...!"*, *"Jij bent...!"*, *BOE!*, *Luisteremmer*). | Balanceren zonder developer; de **balanssimulator** leest dezelfde tabellen. |
| **Animatie** | Personages als **cut-out/skeletanimatie**; tegenstanders met **4 standen** (idle, aanval, geraakt, plat + wit vlaggetje) | Kaartillustraties worden zoveel mogelijk **uit de rig van Walter** gerenderd (zelfde poses als zijn animaties). |
| **Opslag** | Lokaal, automatisch na elke plek op de boskaart en na elke beurt. Het **stickerboek** is een apart bestand per saveplaats (blijft over speelbeurten heen). Geen account. | Een kind kan op elk moment stoppen. |
| **Grootte** | ≤ 1 GB per aflevering, beide taalversies inbegrepen | |
| **Verdienmodel** | **Geen. Het spel is gratis, voor iedereen.** Geen advertenties, geen in-app aankopen, geen kaartpakjes, geen donatieknoppen in het spel, geen account. Nieuwe afleveringen zijn gratis updates. | Een kaartspel voor kinderen mag nooit naar kaartpakjes-te-koop ruiken. Dit staat ook op de ouderpagina. |
| **Privacy** | Geen analytics in de uitgebrachte versie; speeltest-metingen alleen in testbuilds | |

**Wie beslist:** er is geen product owner meer. **Het kinderpanel is baas** (zie [README](../README.md#wie-beslist-het-kinderpanel)): alles wat over spelplezier gaat, beslissen de kinderen. Het team beslist alleen technische punten, en legt die keuzes uit aan het panel.

**Open technische beslispunten** (team, einde week 2): engine definitief na een spike van 2 weken (één gevecht speelbaar met data-gedreven kaarten); één app waarin afleveringen bijkomen (ligt voor de hand nu alles gratis is) of losse apps; kindercategorie in de App Store. Open vragen voor de kinderen: zie [ronde 6](ronde-6/game-design.md#6-openstaande-vragen-voor-het-kinderpanel).

---

## Art- en audiorichting

**Beeld**
- **Stijl:** handgeschilderd 2D met platte, ronde vormen, warm en prentenboekachtig. Personages met grote silhouetten, leesbaar op een tablet van 8 inch.
- **Speelbord:** de achtergrond van de scène, licht vervaagd. Walter links op de voorgrond, tegenstanders rechts. Boven elke tegenstander de **Nee-meter** (een balk met een groot getal) en het **plannetje** (icoon + getal in een denkwolkje).
- **Kaarten:** een vaste kaartvorm met **vier randvormen** per familie (rond wolkje, kussenrand, sokjesrand, sterretjes), zodat de familie ook zonder kleur herkenbaar is. Het getal staat altijd op dezelfde plek, groot.
- **Boskaart:** een geschilderde kaart per scène, met de plekken als grote ronde stempels. Walter wandelt er als klein figuurtje met pantoffels over.
- **Palet:** zoals in ronde 5. **Rood blijft gereserveerd voor bewijsstukken** en heeft altijd een eigen vorm.
- **Slapstick:** tekenfilmstijl (*Looney Tunes*, *Asterix*): snelle, ronde valpartijen en meppen met squash & stretch, overdreven tekenfilmpijn die meteen over is. Overlays: **bult** (groeit en ploept terug), **sterretjes én sokjes**, **pannenkoek** (plat, lospellen), **geblakerd** (zwart met knipperende oogjes), **pantoffelafdruk** op een wang, **modder**, **kletsnat**. Zie de humorlijn in de [README](../README.md#de-humorlijn).

**Muziek per scène:** zoals in ronde 5 (hol: sloffend walsje · kruispunt: mysterieus, opent naar licht · Roodkapje-thema · beek: werfritme van Bert · huisje: op de tippen van je tenen · finale: spionnenthema · museum: gegromd wolvenkoortje). **Nieuw:** elk gevecht heeft een **gevechtslaag** bovenop het scènethema (een extra ritme dat erbij komt als de kaarten uitgedeeld worden en wegvalt bij het witte vlaggetje), en Ekster Ellie heeft een kort kermisdeuntje.

**Belangrijke SFX:** kaart trekken (papiertje), kaart spelen per familie (💬 *bla-bla-blub*, 🛋️ *poef*, 🧦 *PETS*, ⭐ *ting*), tekenfilmgeluiden (*BONK*, *TOING*, *PLETS*, *ZWIEP*, *KLETS*, bult-*plop*, harkgetril, bananenschil-*zoeff*), plat gaan per tegenstander (eigen geluid), opladen (inademen, rammelen), thee schenken (☕), Nee-meter zakt (*tok* per stap), slotje open (*klik*), overtuigd (*zucht + akkoord*), moed zakt (een kort tekenfilm-*au* of *oef*), plus de verhaal-SFX uit ronde 5 (klopjes, kastgemopper, *HATSJOE*, plons, krekel).

---

## Assetlijst

### Achtergronden (5 + 3)

| # | Achtergrond | Als |
|---|---|---|
| 1 | Wolvenhol | speelbord (tutorials) + filmpjes |
| 2 | Kruispunt in de mist | speelbord, met mist-overlay (dunner na *Borden in de mist*) |
| 3 | De Beek | speelbord; tweede uitsnede voor *Ondertussen* |
| 4 | Voor het huisje | speelbord + deur-close-up (klopsignaal) |
| 5 | Oma's kamer | speelbord finale (alle vermommingsdetails als tikbare lagen) + filmpjes |
| 6 | Boskaarten (3 geschilderde kaarten: scène 2, 3, 4) | elk met 3 handgemaakte paden als lagen |
| 7 | Glimmerkraam van Ekster Ellie | één kraam, drie varianten (mos, vlot, tuinbank) |
| 8 | Griezelmuseum (bonus) | zoals ronde 5 |

### Close-ups (4)
Familiefoto + symbolenslot (❓ lade) · kaart met drie paden (❓ borden) · touwtjesdoolhof (❓ touwtjes) · beschuldiging (4 portretten). Hergebruikt uit ronde 5.

### Kaartillustraties

| Groep | Aantal | Opmerking |
|---|---|---|
| Kaartenpool (💬 🛋️ 🧦) | 24 | ± 15 gerenderd uit Walters rig (poses), ± 9 handgetekend |
| Vriendkaarten | 6 | Wanda, Wiebe, Roodkapje, Bert, vis, kat: portret in hun eigen pose |
| Verhaalkaarten | 9 | afstandsbediening, *Mandje lenen*, Klopje, BONK, *"Grootmoeder, wat heb jij...!"*, *"Jij bent...!"*, *BOE!*, *Luisteremmer*, 💧 natte pantoffel |
| Mini-stapels | 5 | Roodkapje (*Waarom?*, *Bloem kietelen*), museum (*Kietelveer*, *Harige kietelveer*, *Hoed weg*) |
| **Totaal** | **44** | plus een ⭐-variant (alleen een randje en ander getal, geen nieuwe tekening) |

### Zakschat-iconen (14) en UI
Zakschatten: zie README. **UI:** speelbord-HUD (moed, thee, trek- en aflegstapel, *Klaar*), plannetje-iconen (😤 🙉 🔥 💭 ❓ 🍄 👢 🦷 💦 👀 🌹 🦔 🕵️ 😴 🧶), effect-iconen (😆 🦋 💪 💨 💧 🔒), voorspelling (spookbalk op Nee-meter en moed), kaartbeloning (1 uit 3 + overslaan), zetelkeuze, glimmerkraam, boskaart-HUD, stickerboek, hulpniveau-keuze, Speurtocht-menu met hoedjes, pauzemenu, instellingen, ouderpagina.

### Personages en animaties

| Personage | Animaties | # |
|---|---|---|
| **Walter** | idle · grote mond/kaart spelen · kussen pakken/gooien · pantoffelmep · geraakt (bult) · pannenkoek (moed op, lospellen) · bukken · juichen · **V1 struikelen** · **V2 buikschuiver** · **V3 plons** · **Bijna!** · huilen · emmer op hoofd · detectivepose · in de zetel ploffen (opening) · wandelen (boskaart, klein) | 15 |
| **Roodkapje** | idle, praten, schrijven, waarom-salvo, *Genoteerd* (🙉), sprint · *Ondertussen:* vragen, kietelen · *vermomd:* idle, praten, vermomming valt per detail (4 kleine), pruik-af-sprong, BOE-schrik | 14 |
| **Wiebe** | ridder-idle, praten, helm op (🙉), ridderslag, radioportret | 5 |
| **Wanda** | breien, praten, klopt op de tafel | 3 |
| **Bert** | idle, dam bouwen (🛡️), knagen (kaart pakken), staartklets, plat onder zijn planken | 5 |
| **Grootmoeder** | uit de kast stappen, praten, koekje eten | 3 |
| **Ekster Ellie** | idle, praten, iets meenemen | 3 |
| **Ursula + Das, De Jager, museumwolf** | zoals ronde 5 | 7 |
| **Tegenstanders** (10; de vogelfamilie hergebruikt de boze vogel) | 4 standen elk; mist, kikkers en paddenstoelen zijn eenvoudige loops (3 standen) | ± 37 |
| **Tutorial-oven** | 3 standen (gloeien, *ssss*, uit) | 3 |
| | **Totaal** | **± 95** (ronde 5: 74 + 10 overlays) |

**Grootste kost zit in de tegenstanders.** Ze zijn wel eenvoudiger dan point-&-click-animaties (geen wandelen, geen oppakken, geen richtingen). Schrapknop: zie *Scope-lagen*.

---

## Ingesproken regels

| Personage | Regels | Waarvan |
|---|---|---|
| Walter | ± 190 | 38 kaartgrappen · ± 20 zetelscores (boskaart, vallen) · ± 40 reacties in gevechten (eerste ontmoeting, overtuigd, *"Klopt."*, de vragen van de finale) · ± 67 verhaal (filmpjes, ❓-momenten) · ± 25 tutorial en uitleg |
| Wiebe | ± 45 | tutorial, radio-tips (één per tegenstander × 2 niveaus), slot |
| Roodkapje (incl. oma-stem) | ± 75 | groot gevecht, *Ondertussen*, voordeur, finale (antwoorden, BOE), ontmaskering, slot |
| Tegenstanders | ± 80 | per tegenstander: eerste ontmoeting, 1–2 aanvalskreten, plat gaan |
| Grootmoeder | ± 25 | kast, luisteremmer, oudertoets, koekjes en geheimen, slot |
| Bert | ± 15 | groot gevecht, brug, pantoffel |
| Ekster Ellie | ± 20 | begroeting per kraam, kopen, kaart meenemen |
| Wanda | ± 15 | opening, lade, *Telegram*, hint |
| Ursula + Das, De Jager, dieren, museum | ± 25 | zoals ronde 5 |
| **Totaal** | **± 480** | ± 28 min ruwe audio. Ronde 5: ± 566 (de bekijk-grappen en hints vallen weg, de kaartgrappen en tegenstanders komen erbij). |

**Studio:** ± 4,5 opnamedagen per taalversie.

### Spreeksnelheid

Ongewijzigd ten opzichte van ronde 5: alle stemmen op natuurlijk verteltempo; de instelling (langzaam / normaal / vlot) regelt alleen de **pauze tussen twee zinnen**, nooit de opname zelf. Eén audiobestand per zin.

---

## Speelduurtoets

Gemiddeld kind van 8, eerste keer, Speurneus.

| Scène | Onderdelen | Doel |
|---|---|---|
| **1 Hol** | opening + nieuws 0:20 · Wanda 0:15 · tutorial Wiebe 1:00 · tutorial oven 1:00 · eerste kaartkeuze 0:15 · ❓ lade 0:55 · vertrek 0:10 | **4:00** |
| **2 Kruispunt** | 3 gevechten × 1:15 · ❓ borden 1:00 · 1 andere plek (🛋️ / ✨ / ❓) 0:30 · beloningen en boskaart 0:45 · 👑 Roodkapje 2:30 · vergissing 0:20 · *Ondertussen* 0:45 | **8:00** (± 0:30 marge) |
| **3 Beek** | twijfel + zetel 0:30 · 2 gevechten × 1:15 · 1 andere plek 0:30 · beloningen en boskaart 0:30 · 👑 Bert 2:15 · ❓ brug 0:30 | **6:30** (± 0:15) |
| **4 Huisje** | 2 gevechten × 1:15 · ❓ touwtjes 0:30 · ❓ brievenbus of 🛋️ 0:20 · beloningen en boskaart 0:30 · 👑 voordeur 1:00 · binnenstappen 0:10 | **5:30** (± 0:30) |
| **5 Finale** | leunstoel 0:20 · intro 0:15 · 👑 "Grootmoeder" 2:30 · beschuldiging 0:20 · ontmaskering 0:25 · kast + koekjes 0:40 · slot 0:40 · eindscherm 0:20 | **6:00** (± 0:30) |
| **Totaal** | | **± 30:00** (snelle speler ± 22 min, wie elke taaie doet ± 36 min) |
| *Bonus* | museum | *± 1:30* |
| *Speurtocht* | zonder filmpjes en vaste ❓, ± 12 gevechten + 4 groot | *± 20 min* |

**Criteria (greybox, week 8):** mediaan verhaal ≤ 32 min · 80 % van de kinderen ≤ 40 min · eerste kaart gespeeld ≤ 0:45 · tutorial 1 + 2 samen ≤ 2:30 · geen gewoon gevecht met een mediaan boven 2:00 · geen groot gevecht boven 3:30 · elke scène ≤ 9 min (een goed stoppunt).

### Balanstoets

Een kaartspel staat of valt met de getallen. Daarom een **balanssimulator** (script, week 3–6) die de datatabellen leest en per gevecht 10 000 keer speelt met vier eenvoudige "kindstrategieën":

| Strategie | Speelt | Staat voor |
|---|---|---|
| **Gulzig** | altijd de kaart met het grootste 💬-getal | een 7-jarige die "aanvalt" |
| **Bang** | eerst kussens tot het plannetje gedekt is, daarna praten | een voorzichtig kind |
| **Plannetjes-lezer** | kussens alleen als er gemopperd wordt, anders praten | het gedrag dat we willen aanleren |
| **Willekeurig** | een willekeurige speelbare kaart | ondergrens |

**Doelen:** met de startstapel wint de *plannetjes-lezer* elk gewoon gevecht van scène 2 op Speurneus met ≥ 20 💛 over; *gulzig* wint het nog altijd in ≥ 90 % (een 7-jarige mag niet vastlopen); *willekeurig* verliest hoogstens 1 op 5 gevechten over een heel verhaal op Speurneus. Op Meesterdetective moet *gulzig* in ± 1 op 3 grote gevechten minstens één keer "moed op" halen, en de *plannetjes-lezer* nooit. Elk gevecht duurt 2–5 beurten.

Daarna **speeltests** met kinderen (zie *Team en planning*), met in testbuilds een log van elke beurt: welke kaarten in de hand, welke gespeeld, hoeveel tijd per beurt. Een beurt met een mediaan boven 30 s is een signaal dat de keuze te moeilijk is.

### Schraplijst (speelduur)

| # | Wat | Wint | Wat we verliezen |
|---|---|---|---|
| 1 | Eén gewoon gevecht minder op de boskaart van scène 2 | −1:15 | een stap op de kaart |
| 2 | ❓ lade: eerste schijf staat al juist | −0:25 | een deel van de kijkpuzzel |
| 3 | Boskaart van scène 4 naar 3 stappen | −1:15 | een gevecht |
| 4 | *Ondertussen* weg (sprint in het filmpje) | −0:45 | Roodkapje spelen |
| 5 | Scène 3 en 4 samen op één boskaart | −2:30 | een groot moment wordt een ❓ (Bert of de voordeur) |

---

## Scope-lagen

| Laag | Wat | Valt het weg, dan... |
|---|---|---|
| **Moet** | speelbord, kaarten en effecten · voorspelling · boskaart met 6 soorten plekken · 10 tegenstanders + 4 grote · 24 kaarten + 6 vrienden · 10 zakschatten · Speurneus/Meesterdetective · alle filmpjes van het verhaal · stickerboek · ❓ lade, borden, brug, touwtjes · klopsignaal · finale met slotjes | — (dit is het spel) |
| **Zou** | Speurtocht met hoedjes · *Ondertussen* · Ekster Ellie (anders: een glimmerkraam zonder personage) · 4 extra zakschatten (thermos, leesbril, wol, cape) · BOE en luisteremmer · 3 handgemaakte paden per boskaart (anders 1) | het verhaal blijft compleet, minder herspeelbaar |
| **Mag** | bonus museum (anders een filmpje van 0:15) · De Gelaarsde Kat (anders een gewone taaie) · Vogelfamilie · snelle-animatie-instelling | minder grappen |

**Volgorde van schrappen bij een animatietekort:** taaien worden kleurvarianten van gewone tegenstanders → mist, kikkers en paddenstoelen krijgen 2 standen → museum wordt een filmpje → *Ondertussen* weg.

**Wat nooit geschrapt wordt:** de voorspelling, de plannetjes met exact getal, Speurneus zonder verliesmoment, de finale met de foto, de oudertoets-momenten (weigeren, lenen, de kast, toestemming), Wiebe in het slot, De Jager aan het raam.

---

## Filmpjesbudget

| Filmpje | Duur |
|---|---|
| Opening (zetelplof, nieuws, buikschuiver) | 0:20 |
| Wanda (telegramstijl) | 0:15 |
| De vergissing | 0:20 |
| Twijfel aan de beek | 0:15 |
| Ontmaskering | 0:25 |
| Kast open (wauw) + oudertoets | 0:25 |
| Slot | 0:40 |
| **Totaal** | **± 2:40** van ± 30 min |

Alles in-engine en per zin wegklikbaar, behalve de eerste 5 seconden van het wauw-moment. In de Speurtocht worden alle filmpjes overgeslagen.

## Wauw-moment

Ongewijzigd ten opzichte van ronde 5: de ontmaskering plus de kast die opengaat (shotlist in het [archief](archief/productie-point-and-click-ronde-5.md#wauw-moment)). Het enige verschil: het moment start niet na het kiezen van een portret in een keuzescherm, maar na het spelen van de kaart **"Jij bent...!"** op het portret van Roodkapje. **Tweede, kleiner wauw:** de mist die optrekt na *Borden in de mist*.

---

## Team en planning

**Team:** 1 game designer/scenarist, **1 game designer balans (deeltijds, vanaf week 2)**, **2 developers** (gameplay + UI/tooling), 1 achtergrondartist, 1 personage-animator, 1 kaartillustrator (freelance, week 6–20), 1 personage-ontwerper (freelance, week 3–6), 1 UI-ontwerper (freelance), 1 QA-tester, freelance audio en componist.

| Fase | Duur |
|---|---|
| Engine-spike (één gevecht met data-gedreven kaarten) en open beslispunten | week 1–2 |
| **Papieren prototype** (kaarten op papier, spelleider als tegenstander, 8 kinderen van 7–10) | week 1–3 |
| **Balanssimulator** + eerste getallen | week 3–6 |
| **Greybox** (alle gevechten, boskaarten, ❓-momenten speelbaar met placeholders) | week 3–8 |
| **Beslismoment greybox** (kinderpanel, einde week 8): de kinderen spelen de greybox en kiezen wat blijft uit de lagen *zou* en *mag*; het team legt de gemeten speelduur en balans ernaast | — |
| Personage-ontwerp (vaste cast + 10 tegenstanders + Ellie) | week 3–7 |
| UI-ontwerp (speelbord, kaart, boskaart, stickerboek): eerst wireframes in de greybox | week 3–14 |
| Art + animatie + kaartillustraties | 14–16 weken |
| VO, muziek en SFX | 4 weken, parallel met art |
| **Speeltests met kinderen** om de 3 weken vanaf week 8 (telkens 6 kinderen, minstens twee van 7 jaar) | doorlopend |
| QA (elke kaart × elke tegenstander-regel, saves midden in een gevecht, stickerboek over speelbeurten) | deeltijds vanaf week 8, voltijds in de polish |
| Polish, balans, bugfix | 6 weken |
| **Sprookje 1** | **± 8 maanden** (ronde 5: 7,5) |
| Volgende sprookjes (speelbord, effect-taal, simulator en vaste cast herbruikbaar) | ± 4 maanden per stuk |

**Grootste risico's:** de balans voor een brede leeftijd (7 vs. 10 jaar) → simulator + Speurneus/Meesterdetective + hoedjes; het aantal tegenstander-animaties → 4 standen, kleurvarianten als schrapknop; begrip van plannetjes bij 7-jarigen → papieren prototype in week 1–3, vóór er iets getekend wordt.

---

## Systeemschermen en ouderpagina (kort)

**Hoofdmenu:** Verder spelen · Nieuw verhaal · Speurtocht (na het eerste uitspelen) · Stickerboek · Instellingen · Voor ouders. Grote plaatjes, alles ingesproken.

**Opslaan:** automatisch na elke beurt en elke plek op de boskaart. Hervatten zet je terug midden in het gevecht: *"Waar was ik? Oh ja. Mijn beurt."* Drie saveplaatsen, elk met een eigen stickerboek.

**Instellingen:** volume (muziek, stemmen, effecten apart) · spreeksnelheid · ondertitelgrootte · minder beweging · snelle animaties · voorspelling aan/uit (standaard aan) · linkshandige kaarten (tablet).

**Voor ouders** (achter een ouderslot):
- **Gratis, voor iedereen.** Geen advertenties, geen in-app aankopen, **geen kaartpakjes te koop**, geen account, geen internet nodig, geen gegevens verzameld.
- Gemaakt samen met een **kinderpanel**: kinderen van 7 tot 10 beslissen mee wat er in het spel komt.
- *"Er wordt gevochten zoals in Looney Tunes of Asterix: met kussens, pantoffels, bananenschillen en een grote mond. Bulten ploppen terug, niemand raakt echt gewond, kinderen worden nooit gemept, en wie verliest, wordt een vriend. Er zitten geen vuile woorden in; wie vloekt, doet het als Kapitein Haddock."*
- Wat er in het verhaal gebeurt, in drie zinnen, en de waarden (zie de [seriebijbel](seriebijbel.md#oudertoets-en-waarden)).
- Moeilijkheid: Speurneus (je kan niet vastlopen, je speelt een gevecht gewoon opnieuw) en Meesterdetective. Wat rekenen betreft: alleen optellen en aftrekken tot 30, en het spel toont altijd de uitkomst vooraf.
- Speelduur: ± 30 minuten voor het verhaal, in vijf stukjes van 4 tot 8 minuten; daarna de herspeelbare Speurtocht van ± 20 minuten.
- Credits.
