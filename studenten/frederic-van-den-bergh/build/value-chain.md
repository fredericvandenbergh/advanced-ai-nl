# Value chain, 21 oktober 2026

Taak: een melding van een chauffeur ordenen (soort en dringendheid). Netto per jaar voor het transportbedrijf van mijn vader.

| Schakel | Waarde | Bron |
|---|---|---|
| 1. Met de hand | 7 min per melding: chauffeur 2 min, vader 5 min | mijn schatting |
| 2. Met de tool | 3,5 min (chauffeur 2, tool 0,5, nakijken 1) + herstel | mijn schatting; tool gemeten |
| Herstel | fout-deel × 2 min per fout met de hand | fout-deel: score op mijn testset; 2 min: mijn schatting (vader denkt na en past de melding aan) |
| 3. Winst per melding | 7 − tool | |
| 4. Volume | 4 à 5 per week, 240 per jaar | bevestigd door mijn vader |
| 5. Uren per jaar | winst × 240 | |
| 6. Uurkost | **150 euro** = bruto uurloon 100 euro × 1,5 | uurloon van mijn vader (zaakvoerder, bestuurder), zoals hij het zelf zegt; factor 1,5 volgens de cursusregel |
| 7. Kost van de tool | ± €0,09 per jaar | gemeten, prijs Haiku 5.5 |
| 8. Netto per jaar | uren × 150 − kost van de tool | |

## Bereik (score v2: 5 tot 6 op 10)

| | Score 5/10 (50% fout) | Score 6/10 (40% fout) |
|---|---:|---:|
| Herstel per melding | 1,0 min | 0,8 min |
| Met de tool per melding | 4,5 min | 4,3 min |
| Winst per melding | 2,5 min | 2,7 min |
| Uren per jaar | 10 u | 10,8 u |
| Waarde per jaar | € 1.500 | € 1.620 |
| **Netto per jaar** | **± € 1.500** | **± € 1.620** |

Bereik: **± € 1.500 tot € 1.620 per jaar**.

## Zwakste cijfer

De 5 minuten die mijn vader met de hand besteedt (de vader-kant van de 7 minuten). Ik heb ze niet gemeten.

- Zijn het 3 minuten in plaats van 5, dan is de winst bij score 5/10 nog 0,5 minuut per melding: ± 2 uur, ± € 300 per jaar.
- Het kantelpunt: bij score 5/10 kost de tool tijd als het nakijken boven ± 3,5 minuut uitkomt (2 + 0,5 + nakijken + 1 herstel is dan meer dan 7 minuten). In week 4 was dat nog 4,5 minuut, zonder herstel.

De foutmarge verschuift het netto met ± € 120. Dat cijfer weegt dus veel minder zwaar dan de 5 minuten van mijn vader.

## Let op

- De score komt van mijn testset (tien moeilijke berichten, bewust gekozen). Het echte aandeel fouten kan lager of hoger zijn.
- Het herstel van 2 minuten gaat uit van één foute melding die je vader zelf moet herdoen. Het is een schatting.
