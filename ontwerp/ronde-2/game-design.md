# Ronde 2: game design en productie

*Doel: PO en Lotte allebei 8+. Kern: sneller zelf spelen, minder handholding, een P10 die visueel klopt, een geregisseerd wauw-moment en een productieplan waar je echt mee kan plannen.*

---

## 1. Productie-overzicht *(klaar voor de README)*

**Filmpjes:** alle filmpjes zijn **in-engine scènes** (zelfde sprites, scriptcamera, geen aparte cinematics).

### Decors (5 + 1 optioneel)
| # | Decor | Varianten |
|---|---|---|
| 1 | Wolvenhol (woonkamer + open keuken, 1 scherm breed + lichte scroll) | tv: uit / nieuws / tekenfilm |
| 2 | Kruispunt | mist (3 lagen, per pad weg te halen) / helder |
| 3 | Beek | brug: 0–3 planken (losse plank-sprites) |
| 4 | Huisje buiten | deur dicht / open, emmer, vogel |
| 5 | Kamer van Grootmoeder | kast dicht / open, sjaal 0–4 |
| (6) | *Griezelmuseum: één stilstaand beeld na de aftiteling* | — |

### Close-ups en minipuzzelschermen (6)
P3 symbolenslot · familiefoto · P5 wegwijzer + kaart · P8 deur met twee knoppen · P9 touwtjesdoolhof · P10 beschuldiging (4 portretten). Plus de UI: detectiveboekje, foto van Grootmoeder als hoekkader, inventaris, hulpniveau-keuze.

### Personages en animaties
| Personage | Animaties | # |
|---|---|---|
| **Walter** | lopen (3 richtingen + spiegelen), idle, praten, oppakken laag/hoog, geven, gebruiken, bekijken, au-poten, kloppen, emmer op hoofd, cape-pose (tekening) | 14 |
| **Roodkapje** | idle, praten, schrijven, meelopen, pad blokkeren, sprint · *vermomd:* idle in bed, praten, handje-uit-mouw, pruik-af-sprong | 10 |
| **Wanda** | breien, praten, opstaan, tegenhouden aan de deur | 4 |
| **Wiebe** | ridder-idle, praten, geven, tv kijken, koekje eten | 5 |
| **Bert** | knagen, praten, plank duwen, proeven | 4 |
| **Grootmoeder** | uit de kast stappen, praten, koekje eten | 3 |
| **Ursula + Das** (op tv) | praten, knipoog / praten | 3 |
| **Bijfiguren** | vis (knipperen), vogel (boos), krekel, De Jager (silhouet + niesen, optioneel) | 5 |
| | **Totaal** | **± 48** |

### Ingesproken regels (schatting)
| Personage | Regels | Waarvan |
|---|---|---|
| Walter | ± 300 | ~90 bekijk-zinnen, ~60 verkeerd-voorwerp, ~45 hints (15 doelen × 3), verhaal |
| Roodkapje (incl. oma-stem) | ± 90 | vragenspel, P10-antwoorden, ontmaskering |
| Wanda | ± 30 | incl. "je bent iets vergeten"-varianten |
| Grootmoeder | ± 20 | |
| Bert / Wiebe | ± 25 / ± 20 | |
| Ursula + Das | ± 12 | |
| **Totaal** | **± 500** | ± 35 min ruwe audio |

**Studio:** Walter 2 dagen, Roodkapje 1 dag (kindstem: korte sessies!), rest samen 1–1,5 dag. **± 5 opnamedagen** per taalversie. Twee castings (Vlaams + Nederlands) = de VO verdubbelt; beslis dit vóór het script vastligt.

### Realistische inschatting (klein team)
Team: 1 game designer/scenarist, 1 developer, 1 achtergrondartist, 1 personage-animator, freelance audio en muziek.
| Fase | Duur |
|---|---|
| Papieren prototype + greybox (alle puzzels speelbaar, placeholder-art) | 6 weken |
| Engine-tooling (dialoog, flags, hints, boekje) | parallel, 8 weken |
| Art + animatie | 12–14 weken |
| VO, muziek en SFX | 4 weken (parallel met art) |
| Polish, speeltests met kinderen, bugfix | 6 weken |
| **Sprookje 1** | **± 7 maanden** |
| Volgende sprookjes (tooling herbruikbaar) | ± 4 maanden per stuk |

Grootste risico's: animatiecount van Walter en de VO-telling. Eerste schrapknop: bekijk-grappen naar 3 per scène (−30 regels).

---

## 2. Speelduur-toets

Gemiddeld 8-jarig kind, eerste keer, klikt rond en probeert een paar keer fout.

| Scène | Huidig ontwerp | Realistisch | Na ronde 2 | Marge |
|---|---|---|---|---|
| 1 Hol | 5:00 | **8:00** (filmpjes 1:20, P3 alleen al 2:30, rondklikken 1:30) | **4:30** | +1:00 |
| 2 Kruispunt | 3:00 | **4:30** (P5 gokken 2:00, vragenspel 1:30) | **3:00** | +0:45 |
| 3 Beek | 1:30 | **2:00** | **1:30** | +0:30 |
| 4 Huisje | 2:00 | **3:00** | **2:00** | +0:30 |
| 5 Finale | 3:30 | **6:30** (6 details × ingesproken antwoord) | **4:00** | +1:00 |
| **Totaal** | 15:00 | **± 24 min** | **± 15 min** | **tot ± 19 min** |

Spreiding: een snelle speler doet 11–12 min, een rondklikker 17–19 min. De optionele extra's (sokken, museum) zitten in die marge en nooit op het kritieke pad.

### Wat wordt korter (vast)
- **Scène 1:** P1 en P2 worden samengevoegd (zie §3). Openingsfilmpje en nieuws worden samen 0:30. Wanda's uitleg 0:15. P3: twee schijven moeten draaien, de eerste (opa/maan) staat al juist en gloeit meteen op als voorbeeld.
- **Scène 2:** vragenspel van 5 naar **3** antwoordopties. P5: de Molen-pijl staat al juist (de mist is daar al weg, en dat toont hoe het werkt).
- **Scène 5:** het antwoord van de "grootmoeder" is telkens ≤ 1 zin. Ontmaskering van 0:35 naar 0:25, slot van 0:45 naar 0:30.

### Schrap-lijst als de speeltest uitloopt (in volgorde)
| Scène | 1e schrap | 2e schrap | 3e schrap |
|---|---|---|---|
| 1 | Wiebe eet een koekje | P4 wordt 1 klik (want hangt al op de oven) | P3 met 2 schijven i.p.v. 3 |
| 2 | Antwoordoptie 3 | Wegwijzer met 2 pijlen | Race-icoontje |
| 3 | Twijfel-moment wordt 1 zin | Plankpuzzel 3 planken i.p.v. 4 (geen te korte) | — |
| 4 | Vogelhuisje-touwtje | Bekijk-grap rieten dak | Doolhof wordt "kies 1 van 2" |
| 5 | Das-grap op oma's tv | Mandje-vraag in P10 | Museum-uitleg wordt 1 zin |

Meten tijdens de speeltest: tijd per doel uit de flag-timestamps (zie §6) en aantal hint-kliks per doel.

---

## 3. Sneller beginnen, minder handholding

**Regel: binnen 10 seconden heeft het kind de besturing, binnen 60 seconden een eerste puzzel opgelost.**

### Nieuwe opening (0:30 in totaal, daarna meteen spelen)
1. *(0:20, in-engine)* De tv staat al aan. Walter ploft neer, thee in de hand, en het nieuws is al bezig: Ursula + Das in **3 regels** (wolf verdwenen, rode zakdoek, niezen). Weerbericht-grap blijft.
2. *(0:10)* Walter laat de thee vallen, Wanda kijkt op. **Besturing aan.**

### Wanda: kort en speels (0:15)
> **Wanda:** "Walter. Grootmoeder. Geheime spionne. Diep in het bos."
> **Walter:** "Een spion? Met een rollator?"
> **Wanda** *(gooit hem het briefje toe)*: "Kaart. Mandje. Koekjes. Hup!"

Drie plaatjes ploppen in het boekje. Wie wil, vraagt door ("Welke kaart?"). Hoe het verloopt, beslist de speler.

### P1+P2 samengevoegd: "De ridder en de afstandsbediening"
Wiebe zit met het mandje op zijn hoofd: *"Ik wil tekenfilms! Maar de afstandsbediening is weg."* De zetel heeft een zichtbare bobbel. Klik je op de zetel, dan zegt Walter *"Hier zit iets in mijn rug"* en verschijnt **één keer** het oog-icoon (bekijken leren blijft). Bekijken → graven → afstandsbediening + sok. Geven aan Wiebe → mandje + tekening. **Eén puzzel, één filmpje minder, en het mandje is meteen een doel.**

### Hulpniveau: "Speurneus" en "Meesterdetective"
Walter vraagt het bij de start, met twee grote plaatjes (vergrootglas vs. detectivehoed): *"Ben jij een speurneus of een meesterdetective?"* Je kan het altijd wisselen in het pauzemenu. Standaard staat het op Speurneus.

| Hulp | Speurneus | Meesterdetective |
|---|---|---|
| Wiebelend inventaris-icoon | ja | **nee** |
| Boekje wiebelt na stilstand | na 60 s | **nooit** |
| Plank bij de wegwijzer | glinstert na P5 | **zelf vinden** (geen glinster) |
| Wanda bij de deur | noemt wat ontbreekt | *"Je bent iets vergeten, Walter."* (boekje toont het) |
| Hints in het boekje | 3 niveaus | 3 niveaus, maar niveau 3 pas na 2 min |
| Highlight (spatie / vergrootglas) | altijd | altijd *(toegankelijkheid, niet uitzetten)* |
| Feedback per schijf/pijl/plank | ja | ja *(eerlijkheid, niet uitzetten)* |
| Einde | — | **Detectivehoed-badge** als je geen niveau 3-hint gebruikte |

**Plank:** wordt nergens meer automatisch opgepakt. Bij de beek op Speurneus: *"Had ik niet ergens een stuk hout gezien?"*

**Ovenwant (Lotte vergeet hem):** Walter stopt hem zichtbaar in zijn cardiganzak en de duim hangt eruit (overlay-sprite). Die zie je dus de hele tijd.

**Lottes extra's, goedkoop:** **5 sokken** als optioneel geheim (zetel, wegwijzer, dam, brievenbus, onder oma's bed; teller in het boekje, en wie ze alle vijf heeft, ziet een extra beeld na de aftiteling). Dat beslist meteen de sokvraag van de PO: **de sok zit in de scope, als verzamelobject.** Het museumbeeld na de aftiteling toont saaie wolven die "grrr" doen en de Jager van achteren. Gekke dingen: ovenwant → Walter zelf ("Kokswolf!"), koekje → vis ("Hij oordeelt nog altijd").

---

## 4. P10 visueel waterdicht

**Ontwerpregel:** elke aanwijzing is **vanaf binnenkomst in beeld**, zonder camerabeweging en met hoog contrast. Walter benoemt alleen wat het kind zelf kan zien. Hover-namen verklappen niets ("Voeten", niet "Rode schoentjes van Roodkapje").

**Kostuum aangepast:** Roodkapje heeft haar kap **gefrommeld onder de nachtmuts** gestoken, en het **rode puntje met kwastje** (de vorm uit het toegankelijkheidsdeel) hangt eruit. Het deken is te kort: haar **voeten steken onderaan uit het bed**, met de rode schoentjes mét strikje *aan*. Uit de te lange mouw piept af en toe een **piepklein handje** met haar potlood (ze kan het schrijven niet laten).

| Detail (bekijken) | Wat je in beeld ziet | Op de foto | Vraag die vrijkomt | Antwoord "grootmoeder" |
|---|---|---|---|---|
| **Bril** | dikke glazen, ogen 2× vergroot | geen bril | *"Wat heb jij grote ogen!"* | "Om jou beter te zien! ...Wazig." |
| **Handje** | piepklein handje met potlood uit een slappe mouw | grote handen, breinaalden | *"Wat heb jij kleine handjes!"* | "Om kleine koekjes vast te houden!" |
| **Voeten** | kleine voetjes onder het deken, **rode schoentjes aan** | grote voeten in sloffen | *"Wat heb jij kleine voetjes!"* | "Om... sneller te breien?" |
| **Mandje** | Walters mandje, bloemen erin | — (Walter herkent het) | *"Wat heb jij een bekend mandje!"* | "Er zijn heel veel mandjes." |
| Grijze krullen (pruik) | grijze krullen | grijze krullen | — | *"Klopt met de foto... denk ik."* |
| Sloffen naast het bed | oma's sloffen, leeg | sloffen | — | *"Oma's sloffen. Kloppen. Maar waarom draagt ze ze niet?"* (extra hint naar de voeten) |
| Breiwerk | breinaalden | breinaalden | — | *"Klopt met de foto."* |
| **Rood puntje** | rood puntje met kwastje onder de muts | geen kap | *"Wat heb jij een RODE KAP!"* | *(start de beschuldiging)* |

- Vragen 1–4 mogen in elke volgorde. De kap-vraag komt pas na **≥ 2 gestelde** vragen. Bekijk je het puntje eerder: *"Rood. Met een kwastje. Waar heb ik dat gezien?"*
- Pruik + sloffen zijn de afleiders (= "niet elk detail is bewijs").
- Met **Hint 2** licht het hoekkader van de foto op ter hoogte van ogen/handen/voeten.

---

## 5. Het wauw-moment: ontmaskering + kast

**Muzikale opbouw:** het **spionnenthema** (contrabas, bongo's, gestopte trompet) wordt al vroeg geplant: twee maten in Wanda's "geheime spionne" en één basnoot onder het terugklopje (P8). Pas bij de kast speelt het volledig.

| Tijd | Camera | Animatie | Audio |
|---|---|---|---|
| 0:00 | Portret Roodkapje gekozen → terug naar de kamer, **snelle push-in** op het bed | Walter wijst, staat in een detectivepose | Muziek valt stil. Eén klok-*tok* |
| 0:02 | Close-up Walter | *"Jij bent... ROODKAPJE!"* | Komisch "dun-dun-DUN" |
| 0:04 | Uitzoomen | Roodkapje **springt rechtop op het bed**, trekt muts + pruik in één ruk af, de kap **ploept open** (squash & stretch), het notitieboekje fladdert | *Poef* + papiergeritsel |
| 0:06 | Totaalbeeld | *"Oké! Ik ben het!"* | Speels pizzicato-thema van Roodkapje |
| 0:07–0:25 | Shot/tegenshot | Ingekorte dialoog (sleutel = "Wat is een sleutel eigenlijk?") | Kast: BONK, *"Mmmf!"* |
| — | *speler zoekt de sleutel (P11)* | | |
| K+0:00 | Sleutel in het slot → **camera schuift traag naar de kast**, licht wordt iets gedimd behalve een warme spot op de kast | De HELP-sjaal wordt met een *sssslurp* de kast in gezogen | Stilte, 1 s |
| K+0:02 | Statisch | Slot draait: *klik... klik... KLIK* (3 tikken, ritme van het klopsignaal ⬤ ● ●) | Basnoot onder elke klik |
| K+0:04 | **Kleine camera-schok** | Deuren zwaaien open, een wolk **breiwol** (geen rook) dwarrelt eruit | **Spionnenthema volledig** |
| K+0:05 | Lage hoek, heldenshot | Grootmoeder stapt eruit in spionnenpose, zonnebril op (!), de sjaal **ontrolt zich over de breedte van het scherm**: H-E-L-P | Trompetstoot |
| K+0:08 | Muziek stopt abrupt | Ze zet de zonnebril af: *"Een kwartier. Ik zit al een KWARTIER in een kast."* | Krekel tjirpt (callback) |

- **Trailershot:** K+0:05 (sjaal over het hele scherm).
- Geen flitsen, en de camera-schok staat uit als "minder beweging" aan staat.
- Duur samen: ± 0:35, alles wegklikbaar behalve K+0:00–0:05 (5 s, dat is de beloning).

---

## 6. Flagmodel (volledig herzien)

**Fouten in ronde 1:** (1) `HAS_MITT` werd nergens gezet. (2) `Q_ASKED` telde op bij het *bekijken*, niet bij het *stellen*. (3) De touwtjes werkten ook vóór het klopsignaal, waardoor Walter zonder uitnodiging binnen kon. (4) Mandje-eigendom na P6 en P11 stond nergens. (5) De plank was een neveneffect, nu is het een eigen actie.

```
# Algemeen
HELP_LEVEL = SPEURNEUS | MEESTER      SOCKS (0–5)      MASTER_BADGE (geen hint-3 gebruikt)
elke flag krijgt een timestamp → speelduurmeting per doel

# Scène 1
NEWS_SEEN (start)  → TALKED_WANDA → HAS_NOTE, GOALS{MAP,BASKET,COOKIES}
LOOKED_SOFA → HAS_REMOTE, SOCKS+1
REMOTE_GIVEN_WIEBE (vereist HAS_REMOTE) → HAS_BASKET, HAS_DRAWING
DRAWER_DISCS (0–3, opa staat al juist) → DRAWER_OPEN → HAS_MAP, HAS_PHOTO
MITT_TAKEN (haakje) → HAS_MITT          ← ontbrak
COOKIES_TAKEN (vereist HAS_MITT) → COOKIES = 3
WIEBE_ATE_COOKIE → COOKIES −1 (max 1×, COOKIES ≥ 1)
CAN_LEAVE_DEN = TALKED_WANDA & HAS_BASKET & HAS_MAP & HAS_COOKIES
  (HAS_DRAWING bewust niet vereist: komt altijd samen met HAS_BASKET;
   HAS_MITT niet vereist: COOKIES_TAKEN kan niet zonder)

# Scène 2
ARROW_MILL (start=juist) / ARROW_FIELD / ARROW_GRANNY → SIGNPOST_SOLVED → MIST_GONE, RK_FOLLOWING
PLANK_TAKEN → HAS_PLANK                 ← eigen actie, niet automatisch
RK_Q (0–3) ; RK_FLOWER_OPTION
BASKET_GIVEN_RK (vereist RK_FOLLOWING) → HAS_BASKET=false, RK_GONE, PATH_GRANNY_OPEN

# Scène 3
PLANK_GIVEN_BERT (vereist HAS_PLANK) → HAS_PLANK=false
PLANKS_PLACED (0–3) → BRIDGE_FIXED

# Scène 4
KNOCK_SOLVED → CLOSET_KNOCKED_BACK, INVITED
ROSES_OPEN (vereist HAS_MITT)
ROPE_CORRECT (vereist ROSES_OPEN & INVITED) → DOOR_OPEN   ← gat gedicht
  vóór INVITED: "Ik ga niet zomaar binnen. Ik ben een beleefde wolf."

# Scène 5
SEEN_{GLASSES,HAND,FEET,BASKET,TASSEL}  (bekijken)
ASKED_{GLASSES,HAND,FEET,BASKET}        (vraag gesteld) → Q_ASKED = som
Q_CAP_UNLOCKED = SEEN_TASSEL & Q_ASKED ≥ 2
ASKED_CAP → ACCUSE_OPEN → UNMASKED
KEY_FOUND (vereist UNMASKED) → HAS_KEY, HAS_BASKET=true
CLOSET_OPEN (vereist HAS_KEY) → HAS_KEY=false
COOKIES_GIVEN_GRANNY (vereist CLOSET_OPEN & COOKIES ≥ 1) → FINALE
CLOSET_LOOKS (0–4, HELP-sjaal; reset visueel bij CLOSET_OPEN)
```

**Boekje-doelen (= hintbronnen):** MAP, BASKET, COOKIES, LEAVE, SIGNPOST, PLANK, RK_BUSY, BRIDGE, KNOCK, ROPE, COMPARE, ACCUSE, KEY, CLOSET, COOKIES_GRANNY (**15 doelen**, × 3 hints = de 45 hintregels uit §1).

**Nieuwe softlock-regels:** plank vergeten (Meesterdetective) → het kruispunt blijft bereikbaar en de plank blijft liggen. Mandje terug in P11 = de nieuwe `HAS_BASKET` (de mandje-reacties na de finale kloppen dan weer).
