---
tags: [TI-1, Digitaltechnik, codierung]
vorlesung: 01-Einführung
folien: 28-30
---

# Codierung Grundbegriffe

## Codierungstheorie

- **Zeichenvorrat**: endliche Menge unterscheidbarer Dinge.
- **Zeichen**: Element eines Zeichenvorrats.
- **Alphabet**: Zeichenvorrat mit *linearer Ordnung*.
- **Code**: Vorschrift für eine *eindeutige Zuordnung* der Zeichen eines Zeichenvorrats zu denen eines anderen.
- Beispiel: binärer Zeichenvorrat $\{0, 1\}$ mit den Binärzeichen 0 und 1 ([[Binärcodierung und Signalpegel]]).

## Bit, Wort, Byte

- **Bit** (Binary Digit): kleinste Informationseinheit, zwei Zustände ("0" und "1").
- **Binärwort / Maschinenwort**: endliche geordnete Folge von Binärzeichen.
- **Wortlänge** $n$: Anzahl der Binärzeichen eines Binärworts, angegeben in bit.
- **Byte**: Wortlänge $n = 8$ bit.

## ASCII

- **A**merican **S**tandard **C**ode for **I**nformation **I**nterchange.
- 7-Bit-Code: ordnet jedem 7-stelligen Binärwort eindeutig ein druckbares Zeichen oder Sonderzeichen zu.
- Tabelle: Zeilen = obere 3 Bit, Spalten = untere 4 Bit.

> [!tip] Zusatz
> ASCII kennt nur 128 Zeichen, also keine Umlaute. Dafür gibt es erweiterte Codes (ISO-8859-x) und heute meist **Unicode/UTF-8**. UTF-8 ist zu ASCII abwärtskompatibel.

## Siehe auch

- [[Einheiten der Digitaltechnik]]
- [[Stellenwertsysteme]]
