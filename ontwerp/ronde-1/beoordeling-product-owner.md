# Beoordeling product owner – ronde 1

**Score: 7/10**

Een sterk, goed doordacht spelontwerp. Puzzels, softlocks, hints en state zijn grondiger uitgewerkt dan ik in deze fase verwacht. Het is nog geen 8. Er ontbreken productiedocumenten die een klein team nodig heeft om te plannen, de speelduur is op papier krap berekend, en de finale bevat een paar logische kiertjes. Allemaal oplosbaar in één ronde.

## Sterke punten

- **Premisse en twist dragen het product.** Twee detectives die elkaar proberen uit te horen terwijl geen van beiden iets weet: dat is grappig, merkwaardig en meteen te pitchen. De omgekeerde "Grootmoeder, wat heb jij..."-scène is een echte vondst.
- **Kindveilig zonder slap te worden.** Wolven zijn veilig, niemand wordt vastgebonden, de dader is komisch. Er wordt iets afgesloten vóór de cliffhanger.
- **Eerlijke, gevarieerde puzzels:** symbolen, ruimtelijk inzicht, dialoog, patroon, vergelijken. Feedback per stap en lezen is nooit een voorwaarde.
- **Bouwbare systemen:** flagmodel, hints die uit de flags lezen, softlock-tabel en verplichte verkeerde-voorwerp-reacties. Daar kan een developer direct mee aan de slag.
- **Running gags en Walters boog** (zetelscore, tekening, "er zijn heel veel grootmoeders/mandjes") geven het geheel samenhang.

## Actiepunten naar 8+ (geprioriteerd)

1. **Productie-overzicht toevoegen.** Ik wil een assetlijst (5 decors, ± 9 personages, animaties per personage, close-ups P3/P5/P8/P9/P10), een schatting van het aantal ingesproken regels en de duur van de filmpjes in de engine. *Waarom:* "alles ingesproken" en negen personages is de grootste kostenpost. Zonder telling kan niemand zeggen of dit haalbaar is voor een klein team.
2. **Speelduur valideren met een papieren prototype.** In scène 5 gaat 1:35 naar filmpjes, dus blijft er ± 2 minuten over voor zes details, een beschuldiging en P11, terwijl elk antwoord ook ingesproken wordt. Scène 1 is net zo krap. *Waarom:* "max 15 min" is een harde productbelofte. Een achtjarige die zoekt en alles aanklikt, doet hier eerder 20–25 minuten over. Zet per scène een marge en geef aan wat je schrapt als het uitloopt (nu staat dat er alleen voor de filmpjes).
3. **De logica van P10 rechtzetten.** (a) Roodkapje draagt een pruik en een nachtmuts, geen kap, dus "wat heb jij een RODE KAP!" klopt niet met wat je ziet. Laat een punt van de kap onder de muts uitsteken, of pas de zin aan. (b) De mouwen hangen over haar handen, dus hoe ziet Walter "kleine handjes"? Laat lege, slappe mouwtoppen of piepkleine vingertjes zien. (c) De schoentjes staan *onder* het bed. Maak expliciet dat ze van haar zijn. *Waarom:* dit is de denkpiek. Een vergelijkingspuzzel moet visueel waterdicht zijn.
4. **Het "wauw"-moment benoemen en regisseren.** Het ontwerp heeft goede payoffs (de mist die optrekt, de HELP-sjaal, de ontmaskering), maar geen enkel moment is aangeduid als spektakel, ook niet voor de trailer. Kies er één (mijn voorstel: de ontmaskering plus de kast die opengaat) en beschrijf camera, muziek en animatie. *Waarom:* dat moment verkoopt de reeks.
5. **Een seriebijbel van een halve pagina.** De pitch zegt "de slechterik is de held", maar Walter speelt duidelijk door naar Hans en Grietje. Wie is daar de "slechterik-held"? Hoe komen Walter en Roodkapje terug? Wat is de boog over de hele reeks (De Jager, de vijf wolven)? *Waarom:* sprookje 1 moet een reeks lanceren, en de premisse en de cliffhanger spreken elkaar nu tegen.
6. **Oudertoets op "vreemden".** Een kind dat zegt "ik ga met je mee" tegen een vreemde wolf, en een wolf die haar met een mandje wegstuurt, ligt gevoelig. Laat Walter expliciet weigeren met een duidelijke zin ("Je gaat nooit mee met vreemden, ook niet met lieve wolven"). Ook "oma opsluiten in de kast" verdient een korte reactie van een volwassene. *Waarom:* ouders beslissen over de aankoop.
7. **Systeemschermen en ouderinfo:** hoofdmenu, autosave per scène, hervatten, volume en spreeksnelheid, ondertitelgrootte, ouderpagina (geen advertenties, geen aankopen, geen data). *Waarom:* het ontwerp is nu nog niet volledig. Dit wordt vaak vergeten en kost veel later alsnog.
8. **Taal en markt vastleggen.** Woorden als "zetel", "wou" en "maat" zijn Vlaams. Kies Vlaanderen, Nederland of beide (met twee castings?). Plan ook de lokalisatie, want de grappen zijn taalgebonden (bv. "ali-wat", "zwijgt als een kussen"). *Waarom:* dit bepaalt de VO-kosten en de scriptbudgetten.
9. **Art- en audiorichting in een paar regels:** stijlreferenties, palet (met de rood/groen-regel uit het toegankelijkheidsdeel), muziek per scène en de klop-SFX. *Waarom:* "stijl Return to Monkey Island" is geen briefing voor een artist.
10. **Kleine toegankelijkheidsaanvullingen:** de tempo van de stem instelbaar, geen flitsende effecten (de mist, de golven), een optie om het race-icoontje uit te zetten. *Waarom:* een race die je altijd "verliest" kan sommige kinderen stress geven.

## Scope- en consistentiezorgen

- **Scope:** elf puzzels met vier close-up-minigames, volledige VO, 3:25 aan filmpjes en minstens vier bekijk-grappen per scène, voor 15 minuten. Dat is ambitieus voor een klein team. Overweeg om filmpjes als geanimeerde scènes in de engine te maken in plaats van als echte cinematics.
- **De sok** is "optioneel" maar komt op vier plekken voor. Beslis: in de scope of eruit.
- **Puzzelregel "hoogstens twee stappen"** versus P11 (mandje, sleutel, kast en dan koekjes) en P7 (geven en dan leggen): technisch klopt het, maar het voelt langer. Bewaak dat in de speeltest.
- **Flags:** `HAS_MITT` wordt nergens gezet (de bron ontbreekt). `CAN_LEAVE_DEN` vereist het mandje, maar niet expliciet de tekening. Dat is goed, maar documenteer het als bewuste keuze.
- **Het race-icoontje** schuift op "bij een opgeloste puzzel", maar Roodkapje wint altijd. Zorg dat het niet als nederlaag aanvoelt.
