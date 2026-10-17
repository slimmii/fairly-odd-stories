# Beoordeling product owner – ronde 3

**Score: 9/10**

Dit ontwerp is klaar voor het ontwikkelteam. Alle tien punten uit ronde 2 zijn inhoudelijk opgelost. Ik heb de cijfers opnieuw nagerekend: de scènetijden geven samen 14:30 (marge tot 18:15), de filmpjes 2:45, de schraplijst 2:25, Walters VO komt uit op ± 296 regels en de animaties op 65 + 6 overlays. Het flagmodel, de softlock-tabel en de documenten zeggen nu hetzelfde. Wat hieronder overblijft, zijn kleine dingen. Die mogen tijdens het papieren prototype en de greybox opgelost worden.

## Opgelost

1. **Sokken:** er is een waarschuwing op de drempel met een keuze tussen sok en deur. Sok 5 is gegarandeerd via oma. De autosave slaat de keuze pas op nadat het kind gekozen heeft, en `SOCK_WARNED` wordt niet te vroeg opgeslagen. Dit is waterdicht.
2. **Lenen:** Roodkapje leent het mandje en schrijft dat op. In P11 geeft ze het terug en streept ze het door. Dat klopt met het inventarisoverzicht en met `BASKET`.
3. **Sluippad:** het staat als stippellijn op de kaart, zonder herkenningspunt. Daardoor kan het geen antwoord zijn bij P5. Het sluit aan op de stapstenen van scène 3 en op het Roodkapje-moment.
4. **Tegenstrijdigheden:** bij de start staan er twee doelen (`WIEBE_ASKED`). De opening is overal een in-engine scène van 0:25. Walter heeft 18 animaties + 6 overlays, en de eend speelt nu een echte rol.
5. **Spreeksnelheid:** de stemmen worden op natuurlijk tempo opgenomen, met instelbare pauzes en zonder time-stretch. Er is één bestand per zin. Dat is een duidelijke beslissing voor de pipeline.
6. **Techniek en verdienmodel:** platformen, stores, minimale hardware, 4:3-safe zone, Godot 4 met een spike en een terugvaloptie, opslag en premium zonder IAP liggen vast. De open beslispunten hebben een eigenaar en een deadline.
7. **Team:** UI en QA zijn toegevoegd, met een testmatrix en een eerste scope-schrap voor de matrix.
9. **Cape:** er gaat geen state over afleveringen heen. Dat maakt losse titels mogelijk.
10. **Kast:** oma moppert verstaanbaar en is boos, niet bang. De sloffen en "zwijgt als een kussen" zijn rechtgezet.

De oudertoets is zelfs beter geworden: de opsluitregel komt nu uit Roodkapjes eigen boekje en wordt niet meer als preek gebracht. Hij blijft wel expliciet.

## Resterende punten (klein)

1. **Speelduur blijft het grootste risico** (mijn punt 8 uit ronde 2 is niet gewijzigd). De beschuldiging heeft nu vier plausibele portretten met grappen die het bewijs nakijken, maar het budget is maar 0:20. P10 krijgt nog steeds 1:05. Daar komen de eend (+0:05) en de drempel bij. Meet P10 + beschuldiging apart in het papieren prototype.
2. **Formulering "geen sok is definitief te missen"** (README, seriebijbel). Wie op de drempel bewust voor de deur kiest, verliest sok 2–4 wél. Schrijf: "nooit ongemerkt te missen".
3. **VO-tabel:** bij Wanda staat "telefoon", maar in het script belt alleen Wiebe. Schrap die vermelding of schrijf de regel. Vermeld ook of de "± 4 vervallen regels" in het slot al van de ± 485 zijn afgetrokken.
4. **Spreeksnelheid:** "Vlot: volgende zin start zonder wachten" botst met de pauze van 0,15 s. Leg ook vast of de pauze alleen tussen zinnen binnen één regel valt of ook tussen sprekers. Dat bepaalt of "+0:30 bij langzaam" klopt (mijn schatting ligt eerder rond +0:45 à 1:00).
5. **Sok 5 onder het bed vóór de kast open is:** oma reageert dan, maar ze zit nog in de kast. Leg vast dat die regel uit de kast komt (gedempte variant).
6. **Emmer-touwtje na de derde keer:** wat gebeurt er als het kind daarna opnieuw trekt (er staat geen emmer meer op het dak)? Er is één reactie nodig.
7. **Koekjes → Roodkapje:** het staartje *"...Wat voor koekjes?"* verzwakt het signaal "geen cadeaus van vreemden". Laat het weg, of laat haar meteen afsluiten met *"Genoteerd: niet aannemen."*
8. **Personage-ontwerp** (model sheets voor de vaste cast) staat nog bij niemand in het team. Wijs het toe aan de animator of de achtergrondartist, of huur een freelancer in voor week 3–6.

Geen van deze punten blokkeert de start van de spike of het papieren prototype.
