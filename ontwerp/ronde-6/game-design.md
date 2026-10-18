# Ronde 6: game design (pivot naar een kaartspel)

**Opdracht.** De gameplay krijgt een heel andere vorm: een kaartspel in de stijl van *Slay the Spire*, met de moeilijkheid afgestemd op kinderen van **7 tot 10 jaar**. Het verhaal blijft gelijkaardig. Dit document legt uit wat er verandert, wat blijft en waarom, en hoe elke oude puzzel in het kaartspel terechtkomt. Het hoofdontwerp staat in [`README.md`](../../README.md); het point-&-click-ontwerp van ronde 5 is bewaard in [`ontwerp/archief/`](../archief/).

---

## 1. Wat we van *Slay the Spire* overnemen, en wat niet

| *Slay the Spire* | Overnemen? | Bij ons |
|---|---|---|
| Kaart met splitsende paden en soorten plekken | **ja** | De boskaart, 4–5 stappen per scène, hoogstens 2 keuzes per splitsing |
| Gevechten met kaarten, energie en block | **ja, als gesprekken** | Overtuigen met 💬, kussens 🛋️, thee ☕. Niemand vecht. |
| Intents (je ziet wat de vijand gaat doen) | **ja, en het is de kern** | Plannetjes met exact getal, voorgelezen. Dit is wat het spel denkbaar maakt voor een 7-jarige: je ziet het probleem, je kiest een antwoord. |
| Kaart kiezen na een gevecht (1 uit 3 of overslaan) | **ja** | Plus glimmers als je overslaat, zodat overslaan geen "niets" is |
| Relics | **ja** | Zakschatten: dingen uit het verhaal (ovenwant, radio, emmer) |
| Rustplaatsen (rusten of upgraden) | **ja** | De zetel, met zetelscore |
| Winkel, kaarten verwijderen | **ja** | Ekster Ellie |
| Elites | **ja, altijd optioneel** | Taaien, altijd met een pad eromheen |
| Permadeath | **nee in het verhaal**, ja in de Speurtocht | Speurneus: hetzelfde gesprek opnieuw. Meesterdetective: begin van de scène. |
| 50+ statuseffecten, gif, multiplicatoren, percentages | **nee** | Drie effecten (😆 🦋 💪), alleen plus en min |
| 5 kaarten, 80 HP, tientallen schade | **nee** | 4 kaarten, 30 moed, getallen ≤ 30 |
| Willekeurige events met verborgen gevolgen | **nee** | ❓-momenten tonen wat elke keuze geeft |
| Lange runs (± 1 uur) | **nee** | Verhaal ± 30 min in vijf stukjes, Speurtocht ± 20 min |

## 2. Waarom dit werkt voor 7–10 jaar

- **Zichtbare plannetjes maken strategie concreet.** "De uil gaat HOE-HOE doen, 7" → "ik speel kussens". Dat is één stap denken, en die stap is telkens anders. Oudere kinderen (9–10) gaan vanzelf twee stappen vooruit denken (sparen, combineren), jongere kinderen spelen de beurt voor zich.
- **Stapelbouwen is verzamelen.** Kinderen van deze leeftijd verzamelen al (stickers, Pokémon-kaarten). Een vriend die een kaart wordt, voelt als een beloning met een verhaal.
- **Herspeelbaar zonder nieuw verhaal.** Het point-&-click-spel was na 15 minuten op. De Speurtocht geeft weken speelplezier met dezelfde art.
- **Leesdrempel blijft laag.** Iconen met getallen, alles ingesproken, geen tekst die je moet lezen om te kunnen spelen.

### Wat we bewust beschermen

| Risico van het genre | Maatregel |
|---|---|
| Rekenen (schade min block, verschillende multiplicatoren) | **Voorspelling** bij het vasthouden van een kaart; alleen plus en min; kaarten die tellen, tonen hun eindgetal |
| Te veel keuzes in één beurt | 4 kaarten, 3 thee, hoogstens 3 tegenstanders |
| Frustratie bij verliezen na 20 minuten | Speurneus: het gesprek opnieuw, meteen. Wiebes tekening als eenmalig vangnet. Nooit een "game over"-scherm. |
| Te veel regels | Eén nieuwe regel per scène, elk aan één tegenstander gekoppeld en door Wiebe voorgedaan |
| Een te dikke stapel zonder het te merken | Overslaan levert glimmers op; Ellie neemt kaarten mee; Wanda zegt het één keer |
| Geweld als kern van het genre | Gesprekken in plaats van gevechten; mopperen in plaats van schade; overtuigd in plaats van verslagen; de "vijand" wordt een vriendkaart |

## 3. Van puzzel naar kaartspel

Elke puzzel uit ronde 5 komt ergens terecht. De kijk- en denkpuzzels die goed werkten (lade, borden, brug, klopsignaal, foto) blijven bijna gelijk als ❓-moment of als speciale regel van een groot gesprek.

| Ronde 5 | Ronde 6 | Wat blijft | Wat verandert |
|---|---|---|---|
| P1 Iets in mijn rug | Opening | afstandsbediening + sok 1 uit de zetel | geen bekijk-tutorial meer nodig |
| P2 Ridder Wiebe | **Tutorial 1** (praten) | ridderslag, tekening, Ridder-radio | Wiebe is de eerste tegenstander; je kan niet verliezen |
| P3 Symbolenslot | ❓ **De lade** | familiefoto, pootjes, Wanda telt | overgeslagen in de Speurtocht |
| P4 Hete koekjes | **Tutorial 2** (kussens) | ovenwant, koekjes in het mandje | de oven is een tegenstander die "ssss" doet |
| P5 Borden in de mist | ❓ **Borden in de mist** | de kaart als strip, de bewijsstukken bij fouten, de mist die optrekt | fouten kosten niets; levert de losse plank op |
| P6 Roodkapje en haar vragen | 👑 **Roodkapje** | waarom-teller, *Bijna!*, weigeren, lenen, de vergissing | haar vragen zijn een plannetje met drie kleine keren; *Mandje lenen* is een kaart |
| Ondertussen | **Ondertussen** | de slapende eend, vragen werken niet | Roodkapje heeft een eigen mini-stapel |
| P7 Brug van Bert | 👑 **Bert** + ❓ **brug** | plank als ruilmiddel, plons, te kort/te lang | Bert knaagt kaarten; de plank maakt het gesprek korter |
| P8 Klopsignaal | 👑 **De voordeur** (kaartpuzzel) | ● ● ⬤, de nep-oma verspreekt zich, het terugklopje | je speelt *Klopje*, *Klopje*, *BONK* als kaarten |
| P9 Welk touwtje? | ❓ **Welk touwtje?** | het doolhof, de emmer, de vogel | elk touwtje geeft iets anders; ovenwant beschermt |
| P10 Grootmoeder, wat heb jij...! | 👑 **Finale met slotjes** | de foto, alle details, de rode-kap-vraag na twee vragen, BOE, luisteremmer, de beschuldiging met vier portretten | elk gevonden verschil opent een slotje op de Nee-meter |
| P11 Grootmoeder bevrijden | ❓ **De kast** | sleutel in het mandje, wauw-moment, oudertoets | koekjes zijn nu een keuze onderweg (geven = Nee −5, bewaren = spionnengeheim) |
| Bonus museum | Bonus museum | kietelen, harige veer, sok nr. 6, zonder Walter | een mini-stapel van 3 kaarten |

## 4. Wat er wegvalt

- **Rondklikken en bekijk-grappen** (± 90 Walter-zinnen). Een deel komt terug als grap op een kaart of als zetelscore op een 🛋️.
- **Hints op drie niveaus** en het boekje als takenlijst: er is geen "waar moet ik naartoe?" meer. In de plaats: Wiebe-tips en een glanzende kaart.
- **Softlock-preventie, flagtabellen, verkeerde-voorwerp-reacties:** elke plek op de kaart is een afgesloten moment, dus vastlopen kan niet meer.
- **Het spoorkaartje:** de boskaart toont zelf waar Walter is.
- **De drempel-waarschuwing voor sokken:** sokken blijven in het stickerboek over speelbeurten heen.

## 5. Wat nieuw is (en waarom)

| Nieuw | Waarom |
|---|---|
| **Tegenstanders op de bospaden** (mist, paddenstoelen, uil, kikkers, reiger, vis, egel, rozen, vogels) | Een kaartspel heeft gewone gevechten nodig tussen de verhaalmomenten. Ze komen allemaal uit de decors en bekijk-grappen van ronde 5 (de uil in de holle boom, de oordelende vis, de rozen "met het humeur van een egel"). |
| **De Gelaarsde Kat** als taaie | Callback naar *"Kat met laarzen. Nee dank je."* uit ronde 5, en een knipoog naar een ander sprookje (publiek domein). |
| **Ekster Ellie** | Een winkel moet een reden hebben in de wereld: een ekster verzamelt wat glimt. Glimmers zijn logisch voor een kind. |
| **Speurtocht met detectivehoedjes** | Herspeelbaarheid voor 9–10-jarigen; de verhaalmodus blijft vriendelijk voor 7-jarigen. |
| **Vriendkaarten** | De pitch van de reeks (*elke slechterik heeft een alibi*) zit nu in de mechaniek: wie je overtuigt, helpt je. |

## 6. Openstaande vragen voor het kinderpanel

Er is geen product owner meer en het spel is gratis, dus de prijsvraag vervalt. De kinderen beslissen.

1. **Speelduur:** is ± 30 minuten voor het verhaal oké, of moet het (zoals in ronde 5) ± 15 minuten blijven? Een korter verhaal kan: scène 3 en 4 samenvoegen tot één boskaart (± 8 min winst), of één gewoon gesprek per scène minder (± 4 min).
2. **Losse aflevering of één spel:** een kaartspel leeft van één groeiende kaartenpool. Willen we per aflevering een losse stapel (zoals nu), of een gedeelde stapel die over de reeks groeit? Dat raakt de seriebijbel-regel "geen state over afleveringen heen".
3. **Speurtocht vanaf het begin?** Nu komt ze pas vrij na het verhaal. Oudere kinderen willen misschien meteen.

### Uitslag (beoordelingen ronde 6)

| Vraag | Lotte (9) | Mats (8) | Noor (7) | Beslissing |
|---|---|---|---|---|
| 1. Speelduur | 30 min houden, niet korter | 30 min oké, filmpjes niet langer | 30 min oké, in stukjes, en het spel onthoudt waar je stopte | **± 30 minuten blijft.** Opslaan na elke beurt en stoppunt na elke scène blijven; de filmpjes worden niet langer dan ± 2:40. |
| 2. Kaarten mee naar het volgende sprookje | alleen de vriendkaarten | ja, de hele stapel | ja, de vriendkaarten (Wiebe!) | **Oplossing voor iedereen:** alle **vriendkaarten** gaan mee (daar zijn ze het alle drie over eens), plus **één lievelingskaart** naar keuze (Mats neemt *Plons* mee, en het blijft één kaart, zodat het niet te makkelijk wordt, zoals Lotte vroeg). De rest begint opnieuw. |
| 3. Speurtocht | pas na het verhaal (anders is de verrassing van oma kapot) | meteen | pas na het verhaal (eerst weten hoe het afloopt) | **Pas na het verhaal** (2 tegen 1). Voor Mats en Lowie: de filmpjes blijven per zin wegklikbaar, dus het verhaal kan vlot. |

**Meteen rechtgezet** (Noor zag het, en het ging tegen onze eigen regel *"mopperen is nooit pijn, niemand wordt uitgelachen"*): de egel prikt niet meer maar heeft *kriebelstekels* (hij rolt zich op, Walters moed zakt er niet van); de vis lacht **mee met** Walter na een plons, en Walter lacht zelf ook; de rozenstruik prikt niet maar blijft *haken* aan Walters cardigan.

De andere wensen van de kinderen (o.a. Wiebe met een eigen mini-stapel, minder gewone gesprekken en meer ❓-puzzels, één *Struikel!* in de startstapel, minder effecticonen, een waarschuwing voor het HOE-HOE van de uil) zijn de opdracht voor ronde 7.

## 7. Validatie

- **Papieren prototype (week 1–3):** kaarten op papier, een spelleider als tegenstander. Testen met **minstens 8 kinderen**: twee van 7, drie van 8–9 (waaronder Lotte en Mats), drie van 10. Meten: begrijpt een 7-jarige na tutorial 2 zonder hulp wat een plannetje is? Kiest een 9-jarige soms bewust om een kaart over te slaan?
- **Balanssimulator (week 3–6):** een script dat duizenden gesprekken speelt met eenvoudige strategieën ("altijd de duurste kaart", "altijd kussens als er gemopperd wordt"), om Nee-meters en plannetjes af te stellen. Zie [productie](../productie.md#balanstoets).
- **Doelen:** Speurneus: ≥ 95 % van de kinderen speelt het verhaal uit; Meesterdetective: ≥ 70 %; gemiddeld hoogstens één keer "moed op" per verhaal op Speurneus.
