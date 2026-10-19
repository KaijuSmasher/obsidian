---
tags: [TI-1, Digitaltechnik, codierung]
vorlesung: 01-Einführung
folien: 25-27
---

# Binärcodierung und Signalpegel

Einfachste Codierung digitaler Signalwerte: **Binär-Codierung** mit zwei logischen Werten.

| Wert | Logik | Schalter | Zustand |
|---|---|---|---|
| $0$ | falsch ("false") | offen | sperrend, aus |
| $1$ | wahr ("true") | geschlossen | leitend, ein |

Mathematische Grundlage ist die **Boolesche Algebra** (auch Schaltalgebra), kommt später in der Vorlesung.

## Positive und negative Logik

| | 0 | 1 |
|---|---|---|
| **Positive Logik** | Low (L), niedriger Spannungspegel | High (H), hoher Spannungspegel |
| **Negative Logik** | High (H) | Low (L) |

Welche Logik gilt, hängt von der verwendeten Technologie ab (TTL, 5V-CMOS, 3,3V-CMOS). Zwischen Low und High liegt ein **verbotener Bereich**, in dem der Wert nicht definiert ist.

> [!tip] Zusatz: Störabstand (Noise Margin)
> Bei TTL gilt am Eingang Low $\le 0{,}8\,\text{V}$ und High $\ge 2{,}0\,\text{V}$, am Ausgang Low $\le 0{,}4\,\text{V}$ und High $\ge 2{,}4\,\text{V}$. Der Ausgang liefert also strengere Pegel, als der Eingang verlangt. Der Unterschied (hier $0{,}4\,\text{V}$) ist der **Störabstand** und der Grund, warum Digitaltechnik robust ist.

## Vorteil digitaler Übertragung

- Analog: Störung **verzieht** das Signal direkt.
- Digital: Störung beeinflusst das Signal **nur in extremen Fällen**, nämlich wenn der Pegel im jeweils anderen Bereich landet.

## Siehe auch

- [[Codierung Grundbegriffe]]
- [[Hardware ist anders]]
