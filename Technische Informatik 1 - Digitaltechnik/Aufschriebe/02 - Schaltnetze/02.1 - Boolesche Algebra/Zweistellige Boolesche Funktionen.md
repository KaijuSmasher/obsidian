---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 24-25
---

# Zweistellige Boolesche Funktionen

Es gibt $2^{2^2} = 16$ zweistellige Funktionen ([[Boolesche Funktionen]]).

## Weitere bekannte Funktionen (Folie 24)

| $x$ | $y$ | Implikation $x \to y$ | Äquivalenz $x \leftrightarrow y$ | NAND | Inverse Implikation $x \leftarrow y$ | Antivalenz (XOR) | NOR |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 1 | 1 | 1 | 1 | 0 | 1 |
| 0 | 1 | 1 | 0 | 1 | 0 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 | 1 | 0 | 0 |

- **NAND** $= \overline{x \land y}$ ("nicht und"), **NOR** $= \overline{x \lor y}$ ("nicht oder").
- Die **Antivalenz** (XOR, auf den Folien $\not\leftrightarrow$) ist $1$, wenn die Eingänge **verschieden** sind.
- Die **Äquivalenz** ist $1$, wenn die Eingänge **gleich** sind. Sie ist die Negation von XOR.
- Die **Implikation** $x \to y$ ist nur falsch, wenn $x = 1$ und $y = 0$ ("aus Wahrem folgt Falsches" ist falsch).

> [!tip] Zusatz: Wichtige Darstellungen
> - $x \oplus y = (x \land \overline{y}) \lor (\overline{x} \land y)$
> - $x \leftrightarrow y = (x \land y) \lor (\overline{x} \land \overline{y})$
> - $x \to y = \overline{x} \lor y$

## Alle 16 Funktionen (Folie 25)

Die Spalte steht für die Ausgabe zu den Eingaben $(x_1, x_0) = 00, 01, 10, 11$. **Der Index $i$ von $f_i$ ist genau diese Ausgabe als Binärzahl gelesen.** Beispiel: $f_6$ hat die Ausgabe $0110$, und $0110_2 = 6$.

| Funktion | Ausgabe | verbal | symbolisch | Bezeichnung |
|---|---|---|---|---|
| $f_0$ | 0000 | konstant 0 | $0$ | Kontradiktion |
| $f_1$ | 0001 | $x_1$ und $x_0$ | $x_1 \land x_0$ | Konjunktion |
| $f_2$ | 0010 | nicht $x_0$, aber $x_1$ | $x_1 \land \overline{x_0}$ | Inhibition |
| $f_3$ | 0011 | identisch $x_1$ | $x_1$ | Identität |
| $f_4$ | 0100 | nicht $x_1$, aber $x_0$ | $\overline{x_1} \land x_0$ | Inhibition |
| $f_5$ | 0101 | identisch $x_0$ | $x_0$ | Identität |
| $f_6$ | 0110 | $x_1$ ungleich $x_0$ | $x_1 \oplus x_0$ | Antivalenz (XOR) |
| $f_7$ | 0111 | $x_1$ oder $x_0$ | $x_1 \lor x_0$ | Disjunktion |
| $f_8$ | 1000 | nicht ($x_1$ oder $x_0$) | $\overline{x_1 \lor x_0}$ | NOR |
| $f_9$ | 1001 | $x_1$ gleich $x_0$ | $x_1 \leftrightarrow x_0$ | Äquivalenz |
| $f_{10}$ | 1010 | nicht $x_0$ | $\overline{x_0}$ | Negation |
| $f_{11}$ | 1011 | wenn $x_0$, dann $x_1$ | $x_0 \to x_1$ | Implikation |
| $f_{12}$ | 1100 | nicht $x_1$ | $\overline{x_1}$ | Negation |
| $f_{13}$ | 1101 | wenn $x_1$, dann $x_0$ | $x_1 \to x_0$ | Implikation |
| $f_{14}$ | 1110 | nicht ($x_1$ und $x_0$) | $\overline{x_1 \land x_0}$ | NAND |
| $f_{15}$ | 1111 | konstant 1 | $1$ | Tautologie |

> [!tip] Zusatz
> - Echte "zweistellige" Funktionen sind nur die, die von **beiden** Eingängen abhängen. Konstanten ($f_0$, $f_{15}$), Identitäten ($f_3$, $f_5$) und Negationen ($f_{10}$, $f_{12}$) hängen höchstens von einem Eingang ab.
> - Paare gegenüber: $f_i$ und $f_{15-i}$ sind Negationen voneinander (zum Beispiel AND $f_1$ und NAND $f_{14}$, OR $f_7$ und NOR $f_8$, XOR $f_6$ und Äquivalenz $f_9$).

## Siehe auch

- [[Vollständige Operatorensysteme]]: warum NAND und NOR so wichtig sind
