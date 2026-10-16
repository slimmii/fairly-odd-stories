# Beoordeling product owner – ronde 2

**Score: 8/10**

Dit ontwerp kan naar het team voor papieren prototype en greybox. De tien punten uit ronde 1 zijn echt opgelost, niet alleen afgevinkt. De herschrijving heeft wel een paar nieuwe kiertjes opgeleverd: een ontwerpfout bij de sokken, één gemengd signaal bij "vreemden" en wat tegenstrijdigheden tussen de documenten. Alles is klein en lokaal op te lossen. Los de punten 1 tot 4 op vóór de greybox; de rest mag tijdens de greybox.

## Verbeterd t.o.v. ronde 1

- **Productie:** er is nu een assetlijst, een VO-telling (± 470 regels, ± 4,5 studiodagen), een planning en een filmpjesbudget (2:55, alles in-engine). Mijn grootste kostenvraag heeft nu een antwoord.
- **Speelduur:** er is een tijd per onderdeel, een marge per scène, meetbare criteria en een schraplijst met de volgorde en wat elke schrap kost. Ik heb het nagerekend: 14:30 en 18:15 kloppen.
- **P10 is visueel waterdicht:** het rode puntje met kwastje, het handje met potlood en de schoentjes aan de voeten. De afleiders leren het kind dat niet elk detail bewijs is.
- **Oudertoets:** Walter weigert expliciet, het bloemenidee komt van Roodkapje zelf en een volwassene zegt de regel over opsluiten. Partners worden ze alleen met toestemming.
- Het wauw-moment is geregisseerd met een shotlist en een thema dat drie keer vooraf geplant wordt. De seriebijbel lost de tegenspraak tussen premisse en cliffhanger op. Taalkeuze, art- en audiorichting, systeemschermen en toegankelijkheid zijn compleet.

## Actiepunten (geprioriteerd)

1. **Sokken kunnen definitief gemist worden.** In oma's kamer kan je niet meer weg (*"Ik ga niet weg zonder antwoorden"*), dus sok 2 tot 4 zijn dan onbereikbaar. Sok 5 kan je missen als je de koekjes geeft vóór je onder het bed kijkt, want het slot start meteen. De autosave overschrijft de enige save. Het geheimpje is voor verzamelaars, en precies die groep straffen we hiermee. *Oplossing:* laat Walter aan oma's voordeur zeggen dat hij nog een sok "voelt", en geef sok 5 automatisch vóór het slot (of laat oma hem aanreiken).
2. **Gemengd signaal over cadeaus van vreemden.** Roodkapje weigert koekjes van een vreemde wolf (*"Mama zegt: nooit"*), maar neemt wel zijn mandje aan. Een ouder ziet dat meteen. *Oplossing:* maak er expliciet lenen van (*"Ik leen het. Ik schrijf het op. Je krijgt het terug."*). In P11 komt dat netjes terug.
3. **"Blijf op het pad" tegenover het sluippad.** Op de kaart van P5 loopt het bloemenpad alleen naar het bloemenveld. Toch komt Roodkapje via een "sluippad" bij de beek uit. Een kind dat net de kaart heeft leren lezen, ziet dat als een fout, en de waarde uit P6 verliest zijn kracht. *Oplossing:* teken het sluippad op de kaart als een stippellijn van de bloemen naar de beek.
4. **Tegenstrijdigheden door de herschrijving:**
   - Volgens de README staan er bij de start twee doelen, maar `INTRO_DONE` zet er drie (ook WIEBE). Dat botst ook met de regel "doelen pas na ontdekking".
   - De wijzigingslog zegt "geen openingsfilmpje", maar productie.md budgetteert een openingsfilmpje van 0:25.
   - De animaties voor Walter tellen op tot 15, niet 16. Graven (P1), in de zetel ploffen, de detectivepose en natte pantoffels ontbreken.
   - De eend in het Roodkapje-moment heeft geen inhoud.

   *Waarom:* het team bouwt wat er staat. Maak één document leidend.
5. **Spreeksnelheid technisch vastleggen.** "Langzaam / normaal / vlot" bij volledig ingesproken audio betekent ofwel time-stretching (wat een kinderstem slecht verdraagt), ofwel langere pauzes tussen de zinnen. *Waarom:* dit beslist mee over de opnamekosten en de audiopipeline.
6. **Platform en engine ontbreken.** Er staat "muis en tablet" en "8 inch", maar niet welke stores, welke minimale hardware, welke engine of welke opslag. Ook het verdienmodel van een episodische reeks zonder in-app aankopen ontbreekt: losse apps of een bundel? *Waarom:* zonder die keuzes kan de developer de tooling (8 weken) niet plannen.
7. **Scope groeit in de breedte.** Er zijn nu twee hulpniveaus met tien gedragsverschillen, plus de sokkenteller met scène-indicatie, het spoorkaartje, het Roodkapje-moment, het museum, de telefoon, drie saveslots en een linkshandige inventaris. Elk onderdeel is goed, maar samen vormen ze een testmatrix. Er staat ook geen QA en geen UI- of personage-ontwerper in het team. *Actie:* voeg QA en UI toe aan de planning, of schuif "juiste voorwerp wiebelt" en de sokkenteller met scène-indicatie naar de scope-schrappen.
8. **De speelduurschatting is optimistisch.** Er zit 0:10 tot 0:20 rondklikken in per scène, terwijl er elk minstens vier bekijk-grappen van ± 3,5 s zijn plus wandeltijd. Ook 1:05 voor zeven details in P10 is krap. Daarnaast is ± 4:15 van de 14:30 passief (filmpjes, in-game momenten, Roodkapje-moment). De validatie is goed opgezet, maar verwacht dat schrap 1 tot 3 nodig zijn.
9. **De sokkencape in de reeks.** Volgens de seriebijbel draagt Walter de cape "eventueel" vanaf sprookje 2. Dat betekent state die over afleveringen heen gaat, en een overlay in elk filmpje van elk vervolg. *Beslis nu:* geen cape in vervolgafleveringen, of de cape alleen als ontgrendelbaar kostuum.
10. **Tonaliteit van de kast** (laag). *"Mmmf!"* en HELP doen samen aan een gekneveld oma denken. Laat oma verstaanbaar mopperen, zodat duidelijk is dat ze boos is en niet bang. In P10 zitten ook kleine twijfels: de sloffen zijn een afleider die eigenlijk een aanwijzing is (*"waarom draagt ze ze niet?"*), en oma *"zwijgt als een kussen"* vlak na een hele preek.
