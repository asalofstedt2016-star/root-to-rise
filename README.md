# root-to-rise

## Redigera textinnehåll

Varje sektion på hemsidan har en egen fil i mappen `content/`. Du kan ändra rubriker, brödtexter och listpunkter genom att redigera dessa filer direkt i GitHub – ingen kodkunskap behövs.

### Vilken fil styr vad?

| Fil | Sektion på sidan |
|-----|-----------------|
| `content/hero.md` | Startsidans citat och namnrad |
| `content/om-asa.md` | "Om Åsa" |
| `content/om-kursen.md` | "Om kursen" |
| `content/kursinnehall.md` | "Vad ingår i kursen" (sex moduler) |
| `content/him.md` | "HIM-processen" |
| `content/erbjuder.md` | "Vad jag erbjuder" |
| `content/testimonials.md` | Deltagarröster |
| `content/kontakt.md` | Kontaktsektionen |

### Hur ändrar du texten?

1. Öppna rätt fil i `content/`, t.ex. `content/om-asa.md`.
2. Ändra texten efter kolonet eller citattecknet – se exemplet nedan.
3. Spara och pusha (eller godkänn ändringen i GitHub). Sidan uppdateras automatiskt.

#### Exempel – ändra biografitexten om Åsa

Öppna `content/om-asa.md`. Filen ser ut ungefär så här:

```
---
overline: "Om Åsa"
heading: "<em>Bakom Root to Rise</em>"
body: |
  Jag är Åsa - vägledare och djupt övertygad om naturens läkande kraft...
---
```

Byt ut texten efter `body: |` mot din nya text. Håll in den med minst två mellanslag i början av varje rad, precis som i originalet.

#### Exempel – lägga till en ny kursmodul

Öppna `content/kursinnehall.md` och lägg till ett nytt block i listan `items`:

```
  - number: "07"
    title: "Din nya modul"
    body: "Kort beskrivning av modulen."
```

Se till att indenteringen (mellanrummen i början av raderna) stämmer med de övriga punkterna.

### Viktiga regler

- **Ta inte bort `---` raderna** längst upp och längst ned i filen.
- **Ta inte bort kolon eller citattecken** efter nyckelorden (`overline:`, `heading:` osv.).
- **Håll indenteringen konsekvent** för listpunkter – varje `-` ska ha exakt två mellanslags indrag, och fältnamn under en punkt (som `title:` och `body:`) ska ha fyra mellanslag.
- Fält som `heading:` i Om Åsa och Om kursen innehåller `<em>...</em>` för kursiv stil – ta inte bort dessa taggar om du vill behålla kursiveringen.
- Om en fil inte kan läsas in visas automatiskt den ursprungliga texten – sidan "går inte sönder" av en felaktig redigering.

---

## Lägga till ett nytt event

1. Skapa en ny fil i mappen `events/`, t.ex. `events/mitt-event.md`, med följande innehåll:

```
---
title: "Namn på eventet"
date: "2026-08-20"
time: "18:00"
location: "Zoom"
price: "Gratis"
signup_url: "mailto:din@email.se?subject=Anmälan"
description: "Kort beskrivning av eventet."
---
```

2. Öppna `events/index.json` och lägg till filnamnet i listan:

```json
{ "events": ["webinar-juni.md", "mitt-event.md"] }
```

3. Spara och pusha. Eventet visas automatiskt på hemsidan så länge datumet inte har passerat.

> **Tips:** Ta bort ett event från listan i `index.json` för att dölja det, eller låt det vara kvar — det försvinner automatiskt när datumet passerat.

