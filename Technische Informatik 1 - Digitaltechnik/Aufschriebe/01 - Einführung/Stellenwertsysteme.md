---
tags: [TI-1, Digitaltechnik, zahlensysteme]
vorlesung: 01-Einführung
folien: 32-34
---

# Stellenwertsysteme

Neben dem Ziffernwert zählt auch die **Position** der Ziffer.

## Dezimalsystem

Ziffern $\{0, 1, \dots, 9\}$. Für Ziffern $a_{n-1}, \dots, a_1, a_0$ gilt

$$z = \sum_{i=0}^{n-1} a_i \cdot 10^i$$

Beispiel: $3908 = 3 \cdot 10^3 + 9 \cdot 10^2 + 0 \cdot 10^1 + 8 \cdot 10^0$

## Beliebige Basis $b \in \mathbb{N}$

$$z = a_{n-1} \cdot b^{n-1} + \dots + a_1 \cdot b^1 + a_0 \cdot b^0 = \sum_{i=0}^{n-1} a_i \cdot b^i$$

Man nennt das **$b$-adische Zahlensysteme**. Schreibweise: $(a_{n-1} \dots a_1 a_0)_b$

> [!note] Eindeutigkeit
> Gilt zusätzlich $0 \le a_i < b$ für $i = 0, \dots, n-1$, ist die Darstellung **eindeutig**: Zwei Zahlen sind genau dann gleich, wenn ihre Ziffernfolgen übereinstimmen.

## Relevante Systeme in der Informatik

| System | Basis $b$ | Ziffern | Beispiele |
|---|---|---|---|
| Binär (Dual) | 2 | 0, 1 | 1101, 10111101 |
| Oktal | 8 | 0–7 | 702, 4711 |
| Hexadezimal | 16 | 0–9, A–F ($A = 10, \dots, F = 15$) | 7A, AFFE |

## Siehe auch

- [[Zahlensysteme umrechnen]]
- [[Codierung Grundbegriffe]]
