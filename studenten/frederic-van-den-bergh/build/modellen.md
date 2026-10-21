# Modeltest, 21 oktober 2026

## Mijn gok (vóór de runs ingevuld)

Welke setup scoort het best?

ik zou denken dat setup C het beste scoort. Namelijk is dit het meest geavanceerde model en ook het slimste model.

Welke is goed genoeg voor mijn echte plek?

door dat Opus zo duur zou ik gaan voor het model sonnet dit model is denk ik goed genoeg om de opdracht uit te voeren

## Setups

| Setup | Model | Effort | Score (n = 10, 1 run) | Binnen mijn foutmarge? | Output-tokens per run | Kost per run | Per jaar |
|---|---|---|---:|---|---:|---:|---:|
| A · standaard | Sonnet 5.5 | medium | 6/10 | ja (binnen 5–6) | 220 | $0,0059 (€0,0054) | $1,42 (€1,29) |
| B · omlaag | Haiku 5.5 | medium | 5/10 | ja (binnen 5–6) | 789 | $0,0006 (€0,0005) | $0,14 (€0,13) |
| C · omhoog | Opus 5.5 | medium | 7/10 | net boven 5–6, maar 1 punt verschil met A: binnen de foutmarge | 363 | $0,0147 (€0,0133) | $3,54 (€3,20) |

Foutmarge (uit `foutmarge.md`): v2 (laatste prompt) haalt 5 tot 6 op 10, over drie runs.

Opzet: de laatste prompt (v2), dezelfde tien inputs uit `test-set.md`, één run per setup, effort medium voor alle drie zodat alleen het model verschilt. Model gezet met `--model` en `--effort medium`. Kost per run = eigen input (± 1.865 tokens) × inprijs + output × uitprijs, met de tabel van 21 oktober 2026. Per jaar = kost per run × 240 runs (4 à 5 meldingen per week, uit je week 4-post). Wisselkoers voor de euro-bedragen: $1 ≈ €0,905, zoals in `kosten.md`.

## Uitkomst

- Hoogste score: C (Opus 5.5), 7 op 10. Laagste: B (Haiku 5.5), 5 op 10. A (Sonnet 5.5) scoort 6 op 10.
- Het verschil tussen C en A is één input. Dat ligt binnen de foutmarge, dus op score zijn A en C niet te onderscheiden.
- Fouten per setup: A: T01, T03, T04, T06. B: T01, T02, T03, T04, T06. C: T03, T04, T06.
- T03, T04 en T06 zijn bij alle drie de setups fout. Dat past bij de foutmarge-test, waar die drie ook steeds fout waren.
- Kosten per jaar: C ± €3,20, A ± €1,29, B ± €0,13. Het verschil tussen A en C is ± €1,90 per jaar.
- Nog niet gedaan: meer runs per setup. Eén run per setup is geen bewijs.
