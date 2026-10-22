---
tags: [Info-1, scheme, literale]
vorlesung: 01-Scheme
folien: 7
---

# Scheme: Literale

**Literale** stehen für einen konstanten Wert (auch: **Konstante**) und sind **nicht weiter reduzierbar**.

| Literal | Bedeutung |
|---|---|
| `#t` `#f` | *true*, *false*, Wahrheitswerte |
| `"Zelda"` `"x"` `""` | Zeichenketten (auch: *Strings*) |
| `0` `1904` `-42` `007` | exakte Zahlen |
| `0.42` `3.1415` `-273.15` | exakte Zahlen |
| `1/2` `3/4` `-1/10` | exakte Zahlen |
| `#i1.4142` `#i-1.0` | inexakte Zahlen |
| (Bild) | Bilder |

> [!tip] Zusatz: Auffälliges
> - `007` ist einfach die Zahl $7$.
> - Brüche wie `1/2` sind eigene Literale und bleiben exakt.
> - Dezimalzahlen wie `0.42` sind in dieser Lehrsprache **exakt** (Folie), anders als in vielen Programmiersprachen. Inexakt wird nur, was mit `#i` beginnt. Mehr dazu in [[Exakte und inexakte Zahlen]].

## Siehe auch

- [[Exakte und inexakte Zahlen]]
- [[Ausdrücke und Auswertung]]
- [[Signaturen]]: Signaturen wie `natural`, `string`, `image` passen zu diesen Literalen
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
