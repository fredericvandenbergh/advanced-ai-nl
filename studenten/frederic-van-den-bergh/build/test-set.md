# Testset

Set v2: T01–T30, 27 oktober

Elke rij is een echt bericht (zonder namen of nummerplaten) met het juiste antwoord, dat jij als baas hebt bepaald.
Run 1 en Run 2 vul je pas in nadat de tool met de huidige prompt.md heeft gedraaid.

| ID | Input | Juiste soort | Juiste dringendheid | Waarom | Run 1 | Run 2 |
|---|---|---|---|---|---|---|
| T01 | Mistlicht vooraan links werkt niet | verlichting | kan wachten | Niet dringend, het mistlicht moet gewoon nagekeken worden. | verlichting / snel nakijken (voertuig: niet vermeld) | verlichting / snel nakijken (voertuig: niet vermeld) |
| T02 | Spatlap rechts achter is kapot | carrosserie | kan wachten | De spatlap heeft geen invloed op het rijden van de vrachtwagen. | carrosserie / kan wachten (voertuig: niet vermeld) | carrosserie / kan wachten (voertuig: niet vermeld) |
| T03 | Ik zit met een versleten band op mijn remorque kant chauffeur 3de as. nummerplaat: Q-XXX-000 | banden | snel nakijken | Versleten band: niet acuut gevaarlijk, maar hij moet nagekeken worden. Er staat geen tijdstip in het bericht, de tool mag er geen verzinnen. | banden / direct terugkeren naar depot (voertuig: remorque, kant chauffeur, 3de as, nummerplaat Q-XXX-000) | banden / snel nakijken (voertuig: remorque, kant chauffeur, 3de as, Q-XXX-000) |
| T04 | Bache remorque is kapot | carrosserie | snel nakijken | De bache moet werken. Het probleem moet 's avonds in de garage nagekeken worden. Daarna wordt de bache hersteld of de remorque vervangen. | carrosserie / snel nakijken (voertuig: remorque) | onzeker / onzeker (voertuig: remorque) |
| T05 | Ik hoor lucht blazen onder de vrachtwagen | onzeker | snel nakijken | Je kan nog rijden, dus snel nakijken. Lucht blazen kan het remsysteem of iets anders zijn, dus de soort is onzeker. (Na Run 1 twee keer aangepast: dringendheid eerst onzeker, dan snel nakijken; soort eerst remmen, dan onzeker.) | onzeker / direct terugkeren naar depot (voertuig: niet vermeld) | onzeker / onzeker (voertuig: niet vermeld) |
| T06 | la benne paut pas monter | ander | direct terugkeren naar depot | Dringend: de remorque moet direct vervangen worden. | ander / direct terugkeren naar depot (voertuig: niet vermeld) | onzeker / onzeker (voertuig: niet vermeld) |
| T07 | Rempedaal zakt door tot op de vloer en de vrachtwagen stopt amper, sta aan de kant | remmen | direct stilleggen | Remmen die falen zijn de gevaarlijkste fout. De wagen mag niet meer rijden, ook niet traag naar het depot. De baas moet meteen ingrijpen en een takeldienst sturen. | remmen / direct stilleggen (voertuig: niet vermeld) | remmen / direct stilleggen (voertuig: niet vermeld) |
| T08 | Achterlicht links stuk | verlichting | snel nakijken | Heel kort bericht. Een achterlicht is verplicht en andere weggebruikers zien de wagen anders niet, dus niet "kan wachten". Het is geen stilleggen. Voertuig niet vermeld. | verlichting / snel nakijken (voertuig: niet vermeld) | verlichting / snel nakijken (voertuig: niet vermeld) |
| T09 | Allo, mon pneu avant gauche van de camion verliest lucht, heb al 2x moeten oppompen vandaag | banden | direct terugkeren naar depot | Frans/Nederlands door elkaar. Een band die tijdens het rijden lucht verliest, geeft kans op een klapband. Zelfde regel als het voorbeeld met de remorque 22. Voertuig: vrachtwagen (camion), links voor. | banden / direct terugkeren naar depot (voertuig: camion, voorband links) | banden / direct terugkeren naar depot (voertuig: camion) |
| T10 | Er is iets met de wagen, hij trilt raar | onzeker | onzeker | Te weinig info. Het kan de banden, de wielophanging of iets anders zijn, en je weet niet of het gevaarlijk is. De tool moet hier "onzeker" zeggen en niet gokken. Voertuig niet vermeld. | onzeker / onzeker (voertuig: niet vermeld) | onzeker / direct terugkeren naar depot (voertuig: niet vermeld) |

## Set v2: nieuwe inputs T11 tot T30

Antwoorden vooraf ingevuld, vóór de run. T11 tot T20: meegemaakt door mij. T21 tot T30: van mijn vader.

| ID | Input | Bron | Juiste soort | Juiste dringendheid | Waarom | Run 1 |
|---|---|---|---|---|---|---|
| T11 | Motorlampje brandt oranje, wagen rijdt normaal | meegemaakt door mij | motor | snel nakijken | Oranje lampje en de wagen rijdt normaal. Niet acuut, maar het moet nagekeken worden. | motor / snel nakijken (voertuig: niet vermeld) |
| T12 | Olielampje rood en de motor tikt | meegemaakt door mij | motor | direct stilleggen | Rood oliedruklampje: de motor kan stuk gaan. Niet meer verder rijden. | motor / direct stilleggen (voertuig: niet vermeld) |
| T13 | Temperatuur van de motor in het rood, er komt stoom onder de motorkap uit | meegemaakt door mij | motor | direct stilleggen | Oververhitting. Verder rijden kan de motor vernielen. | motor / direct stilleggen (voertuig: niet vermeld) |
| T14 | Ruitenwisser links is kapot en het regent | meegemaakt door mij | ander | snel nakijken | Slecht zicht, maar hij kan nog rijden. Zichtproblemen vallen onder "ander". | ander / snel nakijken (voertuig: niet vermeld) |
| T15 | Ruitenwisserspuit is leeg of werkt niet | meegemaakt door mij | ander | kan wachten | Het zicht is niet in gevaar. | ander / kan wachten (voertuig: niet vermeld) |
| T16 | Airco werkt niet meer | meegemaakt door mij | ander | kan wachten | Comfort, geen veiligheid. | ander / kan wachten (voertuig: niet vermeld) |
| T17 | Laadlift achteraan lekt olie maar werkt nog | meegemaakt door mij | ander | snel nakijken | Het blijft werken, maar het lek moet hersteld worden. | ander / direct terugkeren naar depot (voertuig: niet vermeld) |
| T18 | Wagen start moeilijk in de ochtend | meegemaakt door mij | ander | snel nakijken | Waarschijnlijk de batterij. Nu rijdt hij nog, maar hij kan binnenkort niet meer starten. | motor / snel nakijken (voertuig: niet vermeld) |
| T19 | Koppeling slipt als ik bergop rijd met volle lading | meegemaakt door mij | ander | snel nakijken | Hij rijdt nog, maar de koppeling is aan het slijten. | ander / direct terugkeren naar depot (voertuig: niet vermeld) |
| T20 | Knipperlicht achteraan rechts doet niets meer | meegemaakt door mij | verlichting | snel nakijken | Een knipperlicht is verplicht. Niet gevaarlijk genoeg om terug te keren. | verlichting / snel nakijken (voertuig: niet vermeld) |
| T21 | Stuur trekt naar links als ik rem | van mijn vader | remmen | direct terugkeren naar depot | De remmen werken, maar ongelijk. Dat geeft gevaar bij een noodstop. | remmen / direct stilleggen (voertuig: niet vermeld) |
| T22 | Spiegel rechts hangt los, glas is gebarsten | van mijn vader | carrosserie | snel nakijken | Het lijkt carrosserie, maar de spiegel is wettelijk verplicht. Daarom niet "kan wachten". | carrosserie / snel nakijken (voertuig: niet vermeld) |
| T23 | Remlichten werken niet, zegt een collega | van mijn vader | verlichting | direct terugkeren naar depot | Een remlicht dat uitvalt is gevaarlijker dan een gewoon achterlicht (T08). Het bericht komt van een tweede persoon; de tool behandelt dat als betrouwbaar, want controleren kost niets en het risico is groot. | remmen / direct stilleggen (voertuig: niet vermeld) |
| T24 | Les freins font un bruit métallique quand je freine | van mijn vader | remmen | direct terugkeren naar depot | Frans. Metaal op metaal betekent dat de remblokken op zijn. | remmen / direct stilleggen (voertuig: niet vermeld) |
| T25 | Le clignotant arrière droit ne marche plus | van mijn vader | verlichting | snel nakijken | Frans. Zelfde regel als T20. | verlichting / snel nakijken (voertuig: niet vermeld) |
| T26 | AdBlue-lampje brandt, nog 500 km te gaan | van mijn vader | ander | kan wachten | Nog 500 km marge. Bijvullen kan bij de volgende stop. | ander / snel nakijken (voertuig: niet vermeld) |
| T27 | Er hangt iets los onder de wagen | van mijn vader | onzeker | onzeker | Kan de uitlaat, een beschermplaat of iets anders zijn. Niet duidelijk hoe gevaarlijk. | onzeker / onzeker (voertuig: niet vermeld) |
| T28 | Er stinkt iets raar in de cabine | van mijn vader | onzeker | onzeker | Te weinig info. Kan de motor, de remmen of iets anders zijn. | onzeker / onzeker (voertuig: niet vermeld) |
| T29 | Ik hoor een tik als ik wegrijd | van mijn vader | onzeker | onzeker | Geen plaats, geen onderdeel, niet duidelijk of het gevaarlijk is. | onzeker / onzeker (voertuig: niet vermeld) |
| T30 | Er is iets met de remorque, bel me terug | van mijn vader | onzeker | onzeker | Alleen het voertuig staat erin, geen probleem. De tool mag hier niet gokken. | onzeker / onzeker (voertuig: remorque) |

## Set v2: run 1 op T01 tot T10

Met de huidige `prompt.md`, één run, nieuw gesprek per input.

- T01: verlichting / snel nakijken (fout, juist: kan wachten)
- T02: carrosserie / kan wachten (juist)
- T03: banden / onzeker (fout, juist: snel nakijken)
- T04: carrosserie / snel nakijken (juist)
- T05: onzeker / snel nakijken (juist)
- T06: ander / snel nakijken (fout, juist: direct terugkeren naar depot)
- T07: remmen / direct stilleggen (juist)
- T08: verlichting / snel nakijken (juist)
- T09: banden / direct terugkeren naar depot (juist)
- T10: onzeker / onzeker (juist)

**Score T01 tot T10: 7 op 10 (set v2, 1 run).**
**Score totaal set v2: 20 op 30 (set v2, 1 run).** Dat is T01 tot T10 (7 op 10) plus T11 tot T30 (13 op 20).

## Succespercentage

- Run 1 (T05, T06, T07, T09, T10): **4 op 5 juist (n = 5, 1 run)**. Fout: T05 (v1).
- Run 1 (T01, T02, T03, T04, T08, met v2): **3 op 5 juist (n = 5, 1 run)**. Fouten: T01, T03.
- Run 2 (alle tien, met v2): **5 op 10 juist (n = 10, 1 run)**. Fouten: T01, T04, T05, T06, T10.
- **Samen: 12 op 20 juist (n = 10, 2 runs).**
- Foutklassen over beide runs: F1 = 4, F5 = 1, F6 = 3 (8 fouten van 20 antwoorden).
- Run 1 samen (alle tien): **7 op 10 juist (n = 10, 1 run)**. Let op: de eerste vijf draaiden met v1, de tweede vijf met v2.

## Foutklassen

| ID | Run | Klasse | Wat er gebeurde |
|---|---|---|---|
| T05 | Run 1 (v1) | F5 | Model twijfelde bij de soort (onzeker), maar koos toch direct terugkeren naar depot |
| T01 | Run 1 (v2) | F1 | Model koos snel nakijken, juist is kan wachten |
| T03 | Run 1 (v2) | F1 | Model koos direct terugkeren naar depot, juist is snel nakijken |
| T01 | Run 2 (v2) | F1 | Model koos opnieuw snel nakijken, juist is kan wachten |
| T04 | Run 2 (v2) | F6 | Run 1 juist (carrosserie / snel nakijken), Run 2 onzeker / onzeker |
| T05 | Run 2 (v2) | F1 | Model koos onzeker / onzeker, juist is onzeker / snel nakijken |
| T06 | Run 2 (v2) | F6 | Run 1 juist (ander / direct terugkeren), Run 2 onzeker / onzeker (Run 1 met v1) |
| T10 | Run 2 (v2) | F6 | Run 1 juist (onzeker / onzeker), Run 2 onzeker / direct terugkeren naar depot (Run 1 met v1) |

## Open punten
- Zichtproblemen (ruitenwisser, ruitenwisserspuit) vallen onder soort "ander". Ruitenwisser kapot: snel nakijken. Ruitenwisserspuit kapot: kan wachten. Beslissen: nieuwe soort "zicht" of "ander" houden.
- T05: besloten op "onzeker" (na de definitie van direct terugkeren: de wagen kan nog rijden, en dat staat niet in het bericht).
- Nog geen testrij voor het onderscheid ruitenwisser (snel nakijken) en ruitenwisserspuit (kan wachten). Eventueel T11 en T12 toevoegen.
