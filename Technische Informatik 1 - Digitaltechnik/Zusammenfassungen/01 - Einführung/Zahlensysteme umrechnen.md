---
tags: [TI-1, Digitaltechnik, zahlensysteme, klausur]
vorlesung: 01-Einführung
folien: 35-37
---

# Zahlensysteme umrechnen

Grundlage: [[Stellenwertsysteme]].

> [!warning] Klausur
> Wird ohne Hilfsmittel geprüft. Zweierpotenzen bis $2^{10}$ auswendig können.

## Beliebige Basis → Dezimal

Ziffern mit Potenzen der Basis gewichten und aufsummieren.

- $(1101)_2 = 1 \cdot 2^3 + 1 \cdot 2^2 + 0 \cdot 2^1 + 1 \cdot 2^0 = 8 + 4 + 0 + 1 = (13)_{10}$
- $(702)_8 = 7 \cdot 8^2 + 0 \cdot 8^1 + 2 \cdot 8^0 = 448 + 0 + 2 = (450)_{10}$
- $(A4F)_{16} = 10 \cdot 16^2 + 4 \cdot 16^1 + 15 \cdot 16^0 = 2560 + 64 + 15 = (2639)_{10}$

## Dezimal → Binär (Divisionsrestverfahren)

1. Zahl ganzzahlig durch 2 teilen.
2. Den Rest notieren.
3. Wiederholen, bis die Zahl 0 ist.
4. Die Reste **in umgekehrter Reihenfolge** lesen (letzter Rest zuerst).

Beispiel $(13)_{10}$:

| Rechnung | Rest |
|---|---|
| $13 : 2 = 6$ | **1** |
| $6 : 2 = 3$ | **0** |
| $3 : 2 = 1$ | **1** |
| $1 : 2 = 0$ | **1** |

Von unten nach oben gelesen: $(13)_{10} = (1101)_2$

> [!tip] Zusatz
> - Das Verfahren funktioniert für jede Zielbasis $b$: einfach durch $b$ statt durch 2 teilen.
> - Zur Probe das Ergebnis zurück ins Dezimalsystem rechnen.

## Binär ↔ Oktal / Hexadezimal durch Gruppierung

Weil $8 = 2^3$ und $16 = 2^4$ Zweierpotenzen sind, kann man Binärzahlen einfach **gruppieren**:

- Beginne **rechts** (Exponent 0).
- Jeweils **3 Bit** ergeben eine Oktalziffer, jeweils **4 Bit** eine Hexadezimalziffer.
- Fehlende Stellen links mit 0 auffüllen.

Beispiele:

- $(101\,001\,001\,111)_2 = (5117)_8$
- $(1010\,0100\,1111)_2 = (A4F)_{16}$
- $(702)_8 = (111\,000\,010)_2$
- $(AFFE)_{16} = (1010\,1111\,1111\,1110)_2$

## Tabelle der Zweierpotenzen

| $n$ | $2^n$ |
|---|---|
| 0 | 1 |
| 1 | 2 |
| 2 | 4 |
| 3 | 8 |
| 4 | 16 |
| 5 | 32 |
| 6 | 64 |
| 7 | 128 |
| 8 | 256 |
| 9 | 512 |
| 10 | 1.024 |
| 16 | 65.536 |
| 32 | 4.294.967.296 |

> [!tip] Zusatz
> In Programmen schreibt man Hex- und Binärzahlen mit Präfix: `0x2639`, `0b1101` (C/C++).

## Siehe auch

- [[Einheiten der Digitaltechnik]]
