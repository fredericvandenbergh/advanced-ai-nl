# Week 5: 20 nieuwe inputs

## Mijn foutmarge

Mijn claim was dat de lucht-blazen-regel de score verbetert. Ik trek die claim in. Zonder de regel haalde de prompt 4 tot 5 op 10, met de regel 5 tot 6 op 10, telkens over 3 runs met dezelfde 10 meldingen. De bereiken overlappen op 5, dus het verschil valt binnen de foutmarge en is niet aangetoond.

## Model en effort

Ik gokte dat Opus (setup C) het best zou scoren, en dat klopte: Opus 7 op 10, Sonnet (A) 6 op 10, Haiku (B) 5 op 10. Het verschil tussen C en A is één input, binnen de foutmarge (1 run per setup). De kosten per jaar zijn ± €1,29 (A), ± €0,13 (B) en ± €3,20 (C). Ik zet setup A in productie: Opus kost ± €1,90 per jaar meer voor een score die ik niet van Sonnet kan onderscheiden.

## Mijn value chain, met de foutmarge erin

Met de hand kost een melding 7 minuten (2 voor de chauffeur, 5 voor mijn vader). Met de tool is dat 3,5 minuten (2 voor de chauffeur, 0,5 voor de tool, 1 om na te kijken). Een fout kost mijn vader 2 minuten herstel: 1,0 minuut per melding bij een score van 5 op 10, 0,8 bij 6 op 10. Een melding kost dan 4,5 of 4,3 minuten, een winst van 2,5 tot 2,7 minuten. Bij 240 meldingen per jaar en € 150 per uur is dat 10 tot 10,8 uur, ± € 1.500 tot € 1.620 per jaar. De foutmarge verschuift dat met ± € 120.

Mijn zwakste cijfer zijn de 5 minuten van mijn vader: een schatting, geen meting. Bij 3 minuten is de winst bij een score van 5 op 10 nog maar 0,5 minuut per melding (± € 300 per jaar), een groter effect dan de foutmarge. Het kantelpunt ligt bij ± 3,5 minuten nakijken.

## Mijn dashboard

https://fredericvandenbergh.github.io/advanced-ai-nl/studenten/frederic-van-den-bergh/build/dashboard.html

## Mijn AI-ismen

"Ik wil AI kunnen gebruiken om bepaalde processen in zowel mijn leven als in het bedrijf van mijn vader te vergemakkelijken." (week 1)
Herschrijving: Ik wil Claude gebruiken om chauffeursmeldingen sneller te verwerken, want één melding kost nu ± 7 minuten.

"Het geheel klopte meestal wel, maar niet altijd volgens de lesinhoud." (week 1)
Herschrijving: Claude zette een synoniem dat juist was, maar niet in de vocabulairelijst stond.

"Een taalmodel kan bij een bepaalde input iets bepalen en iets uithalen." (week 2)
Herschrijving: Het taalmodel haalt uit een chauffeursbericht het voertuig, de soort probleem en de dringendheid.

"Het is ook een moeilijke situatie in het echte leven, en een computer kan daar nog niet echt een antwoord op weten." (week 3)
Herschrijving: Bij T05 (lucht blazen) gaf de tool in twee runs twee verschillende antwoorden.

"De F6-fouten vind ik het vervelendst, want daar is de tool niet eens consequent met zichzelf." (week 4)
Herschrijving: Bij 3 van de 8 fouten (T04, T06 en T10) gaf de tool in run 2 een ander antwoord.

## Mijn testset groeit

Voor set v2 voegde ik 20 inputs toe aan mijn oorspronkelijke 10: 10 gewone meldingen, 6 randgevallen (zoals een melding in het Frans en een knipperlicht) en 4 onzekere inputs.

Bij T23 verwachtte ik voor een remlicht "verlichting" en "direct terugkeren naar depot", maar de tool gaf "remmen" en "direct stilleggen". Mijn prompt schrijft bij remproblemen het strengste niveau voor, en hetzelfde zie ik bij T17, T21 en T24. Antwoordsleutel en prompt botsen dus; welke fout is, zoek ik nog uit.

Score op set v2: 20 op 30 (1 run), 7 op 10 bij T01 tot T10 en 13 op 20 bij T11 tot T30.
