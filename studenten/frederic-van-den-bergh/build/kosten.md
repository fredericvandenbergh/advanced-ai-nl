# Kosten per run

Datum: 14 oktober 2026. Koers: 1 dollar = 0,90 euro (aanname).

## Hoe gemeten

- Niet met `/context` en `/cost`: `/context` startte de cursusskill `context` in plaats van de meting.
- In plaats daarvan: `claude -p --model haiku --output-format json`, twee runs vanuit een neutrale map.
  - Basisrun: alleen "ok". Dat geeft de context.
  - Jouw run: `build/prompt.md` + T01 ("Mistlicht vooraan links werkt niet").
- Tokens uit de API: input = nieuwe tokens + cache schrijven + cache lezen.
- Het model dat `haiku` opleverde was `claude-haiku-5-5`, niet Haiku 4.5 uit de tabel van de README.
- **Eén run per meting.** Het denkwerk schommelt per run.

## Meting

| Model | Context | Totaal input | Jouw deel input | Jouw deel output | Kost per run | Per maand, jouw volume | 10× | 1.000× |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Haiku (prijs Haiku 4.5: 1 / 5 dollar per miljoen) | ± 27.300 | 29.202 | 1.885 | 460 (waarvan 353 denkwerk) | ± 0,0042 dollar, ± 0,0038 euro | 20 runs: ± 0,08 dollar, ± 0,08 euro | 200 runs: ± 0,84 dollar, ± 0,76 euro | 20.000 runs: ± 84 dollar, ± 76 euro |

## Gecorrigeerd in week 5

De tabel hierboven rekende met de prijs van Haiku 4.5 (1 / 5 dollar per miljoen). Het model was `claude-haiku-5-5`, dus de prijs is die van Haiku 5.5: 0,10 dollar per miljoen input, 0,50 dollar per miljoen output (tabel van 21 oktober 2026, geldt tot 100.000 tokens per vraag; deze run zit daar ruim onder).

- Output: 460 × 0,50 ÷ 1.000.000 = 0,00023 dollar
- Input, jouw deel: 1.885 tokens. Cache lezen kost 0,01 per miljoen, cache schrijven 0,125 tot 0,20, een nieuwe token 0,10. Zonder de uitsplitsing per soort reken ik met de hoogste prijs (0,10): 1.885 × 0,10 ÷ 1.000.000 = 0,00019 dollar. Dat is een bovengrens.
- Kost per run: 0,00023 + 0,00019 = **± 0,00042 dollar, ± 0,00038 euro** (bovengrens)
- Per maand, 20 runs: **± 0,0084 dollar, ± 0,0076 euro**
- Per jaar, 240 runs: **± 0,10 dollar, ± 0,09 euro**

Oude regel (Haiku 4.5, 0,0042 dollar per run, 0,91 euro per jaar): gecorrigeerd in week 5. Die getallen gelden niet meer.

Effect op de waarde: de tool kost bijna niets. Het netto blijft ± 1.400 euro per jaar (1.400 − 0,09). Het kantelpunt van het nakijken verandert niet.

## Volume

- Echte plek: het transportbedrijf van mijn vader (± 30 medewerkers).
- 4 à 5 meldingen per week, dus ± 20 per maand (4,33 weken per maand) en ± 240 per jaar.
- Bron: schatting van mezelf. Nog na te vragen bij mijn vader of de wagenparkbeheerder.
- De tool zou op 3 computers en 2 gsm's komen. Dat verandert het aantal runs niet, het zijn dezelfde meldingen.

## Ander model, zelfde volume (20 runs per maand)

Aanname: hetzelfde aantal tokens (1.885 input, 460 output). Een ander model denkt anders, dus dit is bij benadering.

| Model | Prijs per miljoen (input / output) | Kost per run | Per maand |
|---|---|---:|---:|
| Haiku 4.5 | 1 / 5 | 0,0042 dollar | 0,08 dollar |
| Sonnet 5.5 | 2 / 10 | 0,0084 dollar | 0,17 dollar |
| Opus 5.5 | 4 / 20 | 0,0167 dollar | 0,33 dollar |
| Fable 5.1 | 10 / 50 | 0,0419 dollar | 0,84 dollar |

Bij dit volume doet de prijs er niet toe. De bedragen zijn kleiner dan een euro per maand, ook bij het duurste model.

Rekenwerk:
- Context: 2 + 13.263 + 14.052 = 27.317 (basisrun)
- Totaal input jouw run: 2 + 12.488 + 16.712 = 29.202
- Jouw deel input: 29.202 − 27.317 = 1.885
- Input: 1.885 × 1 ÷ 1.000.000 = 0,001885 dollar
- Output: 460 × 5 ÷ 1.000.000 = 0,00230 dollar

## Open punten

- De prijs van Haiku 5.5 is nu gebruikt uit de tabel van de README (21 oktober 2026). Open: de uitsplitsing van de 1.885 input-tokens per soort (nieuw, cache schrijven, cache lezen) om de bovengrens exact te maken. Die staat in de JSON-output van `claude -p --output-format json` (velden `cache_creation_input_tokens` en `cache_read_input_tokens`).
- De kost die de tool zelf rapporteerde (0,0028 dollar voor de basisrun) is gebaseerd op de Opus-prijs. Die cijfers gebruik ik niet.
- Meerdere runs draaien en het gemiddelde nemen.
- Het volume (4 à 5 meldingen per week) is mijn eigen schatting, nog na te vragen bij mijn vader. De uurkost van 100 euro heeft hij bevestigd.

## Waarde: hoeveel tijd wint de tool?

Alle tijden zijn realistische schattingen van mezelf (Frédéric), geen metingen. Het nakijken stond eerst op 3 min en is aangepast naar 1 min (reden: mijn vader zegt dat hij door 40 jaar ervaring binnen 1 minuut ziet of iets ernstig is; zijn eigen inschatting, niet gemeten).

| Schakel | Waarde | Bron |
|---|---|---|
| Met de hand | chauffeur geeft melding door 2 min + vader denkt na en beslist 5 min = **7 min** | mijn schatting |
| Met de tool | chauffeur 2 min + tool openen en draaien 0,5 min + vader kijkt na en beslist 1 min = **3,5 min** | mijn schatting |
| Winst per melding | **3,5 min** (alleen bij mijn vader; de 2 min van de chauffeur blijven gelijk) | |
| Volume | 4 à 5 per week · 20 per maand · 240 per jaar | mijn schatting, nog na te vragen |
| Uren gewonnen | 15,75 min per week · 70 min per maand · **14 u per jaar** | |
| Uurkost | **100 euro** | bevestigd door mijn vader (zaakvoerder): wat een uur van hem het bedrijf kost |
| Waarde | 14 × 100 = **1.400 euro per jaar** | |
| Kost van de tool | 240 × 0,0042 dollar = ± 1 dollar = ~~± 0,91 euro per jaar~~ (gecorrigeerd in week 5, zie hierboven): **± 0,09 euro per jaar** | gemeten, prijs Haiku 5.5 uit de tabel van 21 oktober 2026 |
| Netto | **± 1.400 euro per jaar** (was ± 1.399, gecorrigeerd in week 5) | |

## Mijn zwakste cijfer: het nakijken van 1 minuut

Winst per melding = 5 min − 0,5 min (tool) − nakijktijd.

| Nakijken | Winst per melding | Uren per jaar | Netto per jaar |
|---|---:|---:|---:|
| 1 min | 3,5 min | 14 u | ± 1.399 euro |
| 2 min | 2,5 min | 10 u | ± 999 euro |
| 3 min | 1,5 min | 6 u | ± 599 euro |
| 4 min | 0,5 min | 2 u | ± 199 euro |
| 4,5 min | 0 min | 0 u | − 0,91 euro |
| 5 min | −0,5 min | −2 u | ± − 201 euro |

Het kantelpunt is 4,5 min nakijken. Daarboven kost de tool tijd. In mijn testset zat de tool niet altijd juist (zie `test-set.md`), dus 1 minuut nakijken is de schakel die ik het minst vertrouw.
