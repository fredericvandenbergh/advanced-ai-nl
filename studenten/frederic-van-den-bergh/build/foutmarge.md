# Foutmarge — prompt v1 tegen v2

Gedraaid met de foutmargetest van week 5. Dezelfde tien inputs uit `test-set.md`, drie runs per versie, dus 60 runs in totaal.

## Opzet

- **Model:** `claude-haiku-5-5` (dezelfde als de testset, in `kosten.md` ook zo gemeten).
- **Versies:** v1 = `prompt.md` van commit `a82b937` (week 3, zonder de uitzonderingsregel over lucht blazen). v2 = de huidige `prompt.md` (commit `77dc371`).
- **Aanroep:** `claude -p --model claude-haiku-5-5 --tools "" --no-session-persistence`, elke run een aparte sessie, input via stdin. Geen tools, geen vorige berichten. Gedraaid vanuit een lege, neutrale map (niet vanuit `studenten/`), zodat de `CLAUDE.md` van deze map niet werd ingeladen.
- **Prompt:** de volledige `prompt.md`, met de bouwsteen-markers `[1]`, `[3]` enzovoort zoals ze in het bestand staan. Alleen de regel `[6] <plak hier één bericht>` is vervangen door de input.
- **Score:** een input telt als juist als **soort probleem én dringendheid** allebei gelijk zijn aan het verwachte antwoord uit `test-set.md`. Voertuig telt niet mee: de testset heeft daarvoor geen verwacht antwoord. Het model kreeg de verwachte antwoorden nooit te zien. De testset is niet aangepast.
- **Kosten van deze 60 runs:** ± 0,075 dollar (uit de JSON-output van `claude -p`).

## Score per run

Score = aantal juiste inputs op 10.

| Versie | Run 1 | Run 2 | Run 3 | Laagste | Hoogste |
|---|---|---|---|---|---|
| Vorige versie (v1, commit a82b937) | 4/10 | 4/10 | 5/10 | **4/10** | **5/10** |
| Laatste versie (v2, huidige prompt.md) | 6/10 | 6/10 | 5/10 | **5/10** | **6/10** |

## Per input

Een ✓ is juist. Bij een fout staat het antwoord van het model (soort / dringendheid).

| ID | Input | Verwacht (soort / dringendheid) | v1 r1 | v1 r2 | v1 r3 | v2 r1 | v2 r2 | v2 r3 |
|---|---|---|---|---|---|---|---|---|
| T01 | Mistlicht vooraan links werkt niet | verlichting / kan wachten | ✗ verlichting / snel nakijken | ✗ verlichting / snel nakijken | ✗ verlichting / snel nakijken | ✗ verlichting / snel nakijken | ✗ verlichting / snel nakijken | ✗ verlichting / snel nakijken |
| T02 | Spatlap rechts achter is kapot | carrosserie / kan wachten | ✓ | ✗ carrosserie / snel nakijken | ✓ | ✓ | ✓ | ✗ carrosserie / snel nakijken |
| T03 | Ik zit met een versleten band op mijn remorque kant chauffeur 3de as. nummerplaat: Q-XXX-000 | banden / snel nakijken | ✗ banden / onzeker | ✗ banden / onzeker | ✗ banden / direct terugkeren naar depot | ✗ banden / onzeker | ✗ banden / direct terugkeren naar depot | ✗ banden / onzeker |
| T04 | Bache remorque is kapot | carrosserie / snel nakijken | ✗ ander / onzeker | ✗ carrosserie / onzeker | ✗ carrosserie / onzeker | ✗ carrosserie / onzeker | ✗ ander / onzeker | ✗ carrosserie / onzeker |
| T05 | Ik hoor lucht blazen onder de vrachtwagen | onzeker / snel nakijken | ✗ onzeker / direct stilleggen | ✗ onzeker / direct stilleggen | ✗ onzeker / direct stilleggen | ✓ | ✓ | ✓ |
| T06 | la benne paut pas monter | ander / direct terugkeren naar depot | ✗ ander / snel nakijken | ✗ onzeker / snel nakijken | ✗ ander / snel nakijken | ✗ ander / snel nakijken | ✗ ander / snel nakijken | ✗ ander / snel nakijken |
| T07 | Rempedaal zakt door tot op de vloer en de vrachtwagen stopt amper, sta aan de kant | remmen / direct stilleggen | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| T08 | Achterlicht links stuk | verlichting / snel nakijken | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| T09 | Allo, mon pneu avant gauche van de camion verliest lucht, heb al 2x moeten oppompen vandaag | banden / direct terugkeren naar depot | ✗ banden / onzeker | ✓ | ✓ | ✓ | ✓ | ✓ |
| T10 | Er is iets met de wagen, hij trilt raar | onzeker / onzeker | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

## Lezen

- v1 haalt 4 tot 5 op 10, v2 5 tot 6 op 10. De bereiken overlappen op 5 juist.
- Met drie runs per versie is dit een zwakke meting. Een verschil van één input kan ruis zijn. Het verschil tussen de versies is hier niet betrouwbaar aan te tonen.
- Wat wel opvalt, per input: T01, T03, T04 en T06 zijn in alle zes runs fout, in beide versies. T01 krijgt steeds snel nakijken waar kan wachten juist is. T03 krijgt in geen enkele run snel nakijken.
- T05 is in v2 bij alle drie de runs juist (onzeker / snel nakijken). In v1 was het bij alle drie fout (direct stilleggen). Dat is het enige input waar de wijziging duidelijk in één richting werkt.
- T09 is in v2 bij alle drie de runs juist; in v1 één van de drie runs fout.
- Let op: het verwachte antwoord van T05 is op 10 en 11 oktober twee keer aangepast, na het zien van de output (zie `log.md`). De score van T05 is daarom minder hard als bewijs.

## Ruwe antwoorden

Voor controle: de volledige tekst van elk antwoord zoals het model die gaf.

<details><summary>v1 T01 run 1: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: Het mistlicht vooraan links werkt niet, wat het zicht en de zichtbaarheid van de wagen verkleint, maar de chauffeur meldt geen acuut gevaar.
```

</details>

<details><summary>v1 T01 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het mistlicht vooraan links niet werkt, een verlichtingsstoring die snel nagekeken moet worden maar geen direct gevaar oplevert.
```

</details>

<details><summary>v1 T01 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het mistlicht vooraan links niet werkt, er wordt geen voertuig genoemd en geen direct gevaar gemeld.
```

</details>

<details><summary>v1 T02 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: kan wachten
Reden: De chauffeur meldt alleen dat de spatlap rechts achter kapot is, zonder dat er gevaar of een direct rijprobleem wordt genoemd.
```

</details>

<details><summary>v1 T02 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: snel nakijken
Reden: Een kapotte spatlap is carrosserieschade, en een losse spatlap kan op de weg terechtkomen, dus snel nakijken is veiliger dan wachten.
```

</details>

<details><summary>v1 T02 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: kan wachten
Reden: De chauffeur meldt alleen een kapotte spatlap rechts achter, zonder vermelding van gevaarlijke gevolgen of van een probleem met remmen, banden of andere veiligheidsonderdelen.
```

</details>

<details><summary>v1 T03 run 1: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000 (3de as, chauffeurskant)
Soort probleem: banden
Dringendheid: onzeker
Reden: De chauffeur meldt een versleten band, maar beschrijft de ernst niet, dus de baas moet de band zelf beoordelen.
```

</details>

<details><summary>v1 T03 run 2: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000
Soort probleem: banden
Dringendheid: onzeker
Reden: De chauffeur meldt een versleten band aan de chauffeurskant van de 3de as, maar hij geeft niet aan hoe ernstig de slijtage is of of hij nog veilig kan rijden.
```

</details>

<details><summary>v1 T03 run 3: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt een versleten band aan de kant van de chauffeur op de derde as van de remorque; een band is een veiligheidsonderdeel en de mate van slijtage staat niet vermeld, dus kies ik het strengste niveau.
```

</details>

<details><summary>v1 T04 run 1: fout</summary>

```
Voertuig: remorque
Soort probleem: ander
Dringendheid: onzeker
Reden: De chauffeur meldt dat de bache van de remorque kapot is, maar zegt niet of de remorque nog rijdt of hoe ernstig de schade is.
```

</details>

<details><summary>v1 T04 run 2: fout</summary>

```
Voertuig: Bache remorque
Soort probleem: carrosserie
Dringendheid: onzeker
Reden: De chauffeur meldt dat de bâche van de remorque kapot is, maar zegt niet hoe ernstig de schade is of of hij nog kan rijden.
```

</details>

<details><summary>v1 T04 run 3: fout</summary>

```
Voertuig: remorque
Soort probleem: carrosserie
Dringendheid: onzeker
Reden: De chauffeur meldt dat de bâche van de remorque kapot is, maar niet of die los hangt, of de lading open ligt of of er direct gevaar is.
```

</details>

<details><summary>v1 T05 run 1: fout</summary>

```
Voertuig: vrachtwagen

Soort probleem: onzeker

Dringendheid: direct stilleggen

Reden: De chauffeur hoort lucht blazen onder de vrachtwagen, maar het bericht zegt niet waar het lek zit of welk systeem het betreft, en een luchtlek kan remlucht zijn, dus is het strengste niveau gekozen.
```

</details>

<details><summary>v1 T05 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: direct stilleggen
Reden: De chauffeur hoort lucht ontsnappen onder de vrachtwagen, wat op een lek in het luchtsysteem kan wijzen, maar de bron en de ernst zijn uit het bericht niet op te maken.
```

</details>

<details><summary>v1 T05 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: direct stilleggen
Reden: Het geluid van lucht die onder de vrachtwagen ontsnapt wijst op een lek in het luchtsysteem, mogelijk van de remmen of een band, en het bericht zegt niet waar of hoe ernstig het is, dus het wordt als veiligheidsrisico op het strengste niveau gemeld.
```

</details>

<details><summary>v1 T06 run 1: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: ander
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat de kipbak niet omhoog gaat, dus hij kan niet lossen, maar er staat niets over lekkage of gevaar tijdens het rijden.
```

</details>

<details><summary>v1 T06 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat de benne niet omhoog kan, maar de oorzaak en eventuele lekkage of andere veiligheidsrisico's worden niet genoemd.
```

</details>

<details><summary>v1 T06 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: ander
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat de kipbak niet omhoog gaat, zonder gevaar of lek te noemen, dus het is een storing die snel nagekeken moet worden.
```

</details>

<details><summary>v1 T07 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: De chauffeur meldt dat het rempedaal tot op de vloer zakt en de vrachtwagen nauwelijks remt, wat een acuut remprobleem is dat verder rijden onveilig maakt.
```

</details>

<details><summary>v1 T07 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: Het rempedaal zakt tot op de vloer en de vrachtwagen remt nauwelijks, een direct veiligheidsrisico waardoor de wagen getakeld moet worden.
```

</details>

<details><summary>v1 T07 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: Het rempedaal zakt door tot op de vloer en de vrachtwagen stopt nauwelijks, en de chauffeur staat aan de kant, dus de wagen kan niet veilig verder en moet getakeld worden.
```

</details>

<details><summary>v1 T08 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt alleen dat het linker achterlicht stuk is, zonder voertuig of direct gevaar te noemen, dus het moet snel nagekeken worden.
```

</details>

<details><summary>v1 T08 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: Het achterlicht links is stuk, wat de zichtbaarheid van de wagen verkleint, maar de chauffeur meldt geen direct gevaar of rijonmogelijkheid.
```

</details>

<details><summary>v1 T08 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: Het achterlicht links is stuk, maar de melding noemt geen onrijdbaarheid of ander direct gevaar.
```

</details>

<details><summary>v1 T09 run 1: fout</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: onzeker
Reden: De voorband links vooraan verliest steeds lucht en is vandaag al twee keer bijgepompt, maar het bericht zegt niet of de wagen nog veilig kan rijden, dus de urgentie is niet vast te stellen.
```

</details>

<details><summary>v1 T09 run 2: juist</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt dat de voorband links steeds lucht verliest en vandaag al twee keer moest worden opgepompen, een veiligheidsrisico terwijl hij nog rijdt.
```

</details>

<details><summary>v1 T09 run 3: juist</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur moet de voorlinkerband vandaag al twee keer bijpompen, wat op lekkage wijst en een veiligheidsrisico is, maar de wagen rijdt nog dus terugkeren naar het depot is voldoende.
```

</details>

<details><summary>v1 T10 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: De chauffeur meldt alleen dat de wagen raar trilt, zonder voertuig of oorzaak, dus het type probleem en de urgentie zijn niet te bepalen.
```

</details>

<details><summary>v1 T10 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: Het bericht noemt geen voertuig en zegt alleen dat de wagen raar trilt, zonder de oorzaak of de ernst, dus de baas moet zelf navragen.
```

</details>

<details><summary>v1 T10 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: De chauffeur meldt dat de wagen raar trilt, maar noemt geen voertuig en niet waar de trilling vandaan komt, dus de oorzaak en het risico zijn niet vast te stellen.
```

</details>

<details><summary>v2 T01 run 1: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het mistlicht vooraan links niet werkt, zonder voertuig te noemen en zonder te zeggen dat de wagen niet meer kan rijden.
```

</details>

<details><summary>v2 T01 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het mistlicht vooraan links niet werkt, een verlichtingsstoring die snel nagekeken moet worden, maar er is geen direct gevaar of uitvalverschijnsel gemeld.
```

</details>

<details><summary>v2 T01 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het mistlicht vooraan links niet werkt, maar hij zegt niet dat de wagen niet meer kan rijden en noemt geen ander probleem.
```

</details>

<details><summary>v2 T02 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: kan wachten
Reden: De chauffeur meldt alleen een kapotte spatlap rechts achter, zonder veiligheidsrisico of verlies van functie.
```

</details>

<details><summary>v2 T02 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: kan wachten
Reden: De chauffeur meldt alleen dat de spatlap rechts achter kapot is, zonder dat er sprake is van remmen, banden of een ander veiligheidsrisico.
```

</details>

<details><summary>v2 T02 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: carrosserie
Dringendheid: snel nakijken
Reden: De chauffeur meldt een kapotte spatlap rechts achter zonder dat er gevaar of verlies van rijvermogen wordt genoemd, maar een losse spatlap kan onderdelen op de weg verspreiden, dus laat hem snel nakijken.
```

</details>

<details><summary>v2 T03 run 1: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000 (3de as, kant chauffeur)
Soort probleem: banden
Dringendheid: onzeker
Reden: De chauffeur meldt een versleten band zonder te zeggen hoe ernstig de slijtage is of of er lucht verloren gaat, dus de urgentie valt niet vast te stellen.
```

</details>

<details><summary>v2 T03 run 2: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt een versleten band aan de bestuurderskant van de 3de as, maar niet of de band lucht verliest of of de wagen nog kan rijden, dus kies ik voor het strengste niveau bij een veiligheidsprobleem dat niet duidelijk is.
```

</details>

<details><summary>v2 T03 run 3: fout</summary>

```
Voertuig: remorque, nummerplaat Q-XXX-000
Soort probleem: banden
Dringendheid: onzeker
Reden: De chauffeur meldt een versleten band op de remorque, maar zegt niet hoe ernstig het is of of hij nog veilig kan rijden, dus de baas moet dit zelf beoordelen.
```

</details>

<details><summary>v2 T04 run 1: fout</summary>

```
Voertuig: remorque
Soort probleem: carrosserie
Dringendheid: onzeker
Reden: Het bericht zegt alleen dat de bache van de remorque kapot is, zonder te vermelden hoe ernstig het is of of de chauffeur nog kan rijden.
```

</details>

<details><summary>v2 T04 run 2: fout</summary>

```
Voertuig: remorque
Soort probleem: ander
Dringendheid: onzeker
Reden: De chauffeur meldt dat de bâche van de remorque kapot is, maar het bericht zegt niet of de bâche losraakt of gevaar oplevert en of de wagen nog veilig kan rijden, dus de urgentie valt niet vast te stellen.
```

</details>

<details><summary>v2 T04 run 3: fout</summary>

```
Voertuig: remorque
Soort probleem: carrosserie
Dringendheid: onzeker
Reden: De chauffeur meldt dat de bâche van de remorque kapot is, maar hij zegt niet of de lading open ligt of of hij nog kan rijden.
```

</details>

<details><summary>v2 T05 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: snel nakijken
Reden: De chauffeur hoort alleen lucht blazen onder de wagen, maar meldt geen drukverlies en zegt niet dat hij niet meer kan rijden, en uit het bericht blijkt niet of het om remmen, banden of iets anders gaat.
```

</details>

<details><summary>v2 T05 run 2: juist</summary>

```
Voertuig: vrachtwagen
Soort probleem: onzeker
Dringendheid: snel nakijken
Reden: De chauffeur hoort lucht blazen onder de vrachtwagen maar meldt geen drukverlies en geen onvermogen om te rijden, dus de wagen kan nog rijden en snel nakijken volstaat.
```

</details>

<details><summary>v2 T05 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: snel nakijken
Reden: De chauffeur hoort lucht blazen onder de vrachtwagen, maar meldt geen drukverlies en zegt niet dat hij niet meer kan rijden, dus hij kan nog rijden en moet snel nagekeken worden.
```

</details>

<details><summary>v2 T06 run 1: fout</summary>

```
Voertuig: benne
Soort probleem: ander
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat de benne niet omhoog gaat, dus hij kan niet lossen, maar hij noemt geen gevaar, lekkage of stilstand van de wagen.
```

</details>

<details><summary>v2 T06 run 2: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: ander
Dringendheid: snel nakijken
Reden: De chauffeur meldt alleen dat de benne niet omhoog gaat, zonder rijonveiligheid, lekkage of stilstand van de wagen te vermelden.
```

</details>

<details><summary>v2 T06 run 3: fout</summary>

```
Voertuig: niet vermeld
Soort probleem: ander
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat de benne niet omhoog kan, wat het lossen belemmert, maar er wordt geen gevaar, lekkage of verlies van druk genoemd.
```

</details>

<details><summary>v2 T07 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: Het rempedaal zakt door tot op de vloer en de vrachtwagen stopt nauwelijks, wat een direct veiligheidsrisico is en het verder rijden onmogelijk maakt.
```

</details>

<details><summary>v2 T07 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: Het rempedaal zakt door tot op de vloer en de vrachtwagen remt nauwelijks, en de chauffeur staat aan de kant, dus de wagen kan niet veilig verder en moet getakeld worden.
```

</details>

<details><summary>v2 T07 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: remmen
Dringendheid: direct stilleggen
Reden: Het rempedaal zakt tot op de vloer en de vrachtwagen remt nauwelijks, dus de wagen is niet veilig meer te rijden en moet getakeld worden.
```

</details>

<details><summary>v2 T08 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt alleen dat het achterlicht links stuk is, zonder verlies van remmen, banden of druk en zonder dat hij niet meer kan rijden.
```

</details>

<details><summary>v2 T08 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt dat het linker achterlicht stuk is, wat snel nagekeken moet worden omdat andere weggebruikers het niet goed zien, maar het bericht zegt niet dat de wagen moet stoppen.
```

</details>

<details><summary>v2 T08 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: verlichting
Dringendheid: snel nakijken
Reden: De chauffeur meldt alleen dat het linker achterlicht stuk is, zonder dat de wagen niet meer kan rijden, maar het licht is nodig om door andere weggebruikers gezien te worden.
```

</details>

<details><summary>v2 T09 run 1: juist</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt dat een band vooraan links steeds lucht verliest en dat hij die vandaag al twee keer heeft moeten oppompen, maar hij zegt niet dat hij niet meer kan rijden.
```

</details>

<details><summary>v2 T09 run 2: juist</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt dat de voorband links lucht verliest en dat hij die vandaag al twee keer heeft moeten oppompen, dus een veiligheidsrisico, maar hij zegt niet dat hij niet meer kan rijden.
```

</details>

<details><summary>v2 T09 run 3: juist</summary>

```
Voertuig: camion
Soort probleem: banden
Dringendheid: direct terugkeren naar depot
Reden: De chauffeur meldt dat de band voorlinks lucht verliest en dat hij die vandaag al twee keer heeft moeten oppompen, maar hij rijdt nog, dus de wagen moet direct naar het depot.
```

</details>

<details><summary>v2 T10 run 1: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: De chauffeur meldt dat de wagen raar trilt, maar zegt niet welk voertuig het is of waar de trilling vandaan komt, en trillingen kunnen op veiligheidsproblemen met banden, remmen of motor wijzen.
```

</details>

<details><summary>v2 T10 run 2: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: De chauffeur meldt dat de wagen raar trilt, maar noemt geen voertuig, onderdeel of ernst, dus de baas moet dit zelf navragen.
```

</details>

<details><summary>v2 T10 run 3: juist</summary>

```
Voertuig: niet vermeld
Soort probleem: onzeker
Dringendheid: onzeker
Reden: De chauffeur meldt alleen dat de wagen raar trilt, zonder voertuig of onderdeel, dus de oorzaak en het risico zijn niet vast te stellen.
```

</details>

