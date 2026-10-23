---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra]
vorlesung: 02-Boolesche-Algebra
folien: 12-14
---

# Schaltalgebra

Die **Schaltalgebra** ist eine spezielle Boolesche Algebra ([[Boolesche Algebra Definition und Axiome]]) mit nur zwei Werten.

| Boolesche Algebra | Schaltalgebra |
|---|---|
| $V$ | $\{0, 1\}$ |
| $\oplus$ | $\lor$ (ODER) |
| $\otimes$ | $\land$ (UND) |
| $n$ (Nullelement) | $0$ |
| $e$ (Einselement) | $1$ |
| $\overline{a}$ | $\overline{a}$ (NICHT) |

**Schreibweisen:** $a + b$ für $a \lor b$, $a \,\&\, b$ für $a \land b$, $\overline{a}$ für $\lnot a$.

Die Werte $0$ und $1$ entsprechen den Spannungspegeln Low/High aus [[Binärcodierung und Signalpegel]].

## Funktionstabellen

| $x$ | $y$ | $x \land y$ (AND, Konjunktion) | $x \lor y$ (OR, Disjunktion) |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 |

| $x$ | $\overline{x}$ (NOT, Negation) |
|---|---|
| 0 | 1 |
| 1 | 0 |

> [!tip] Merkhilfe
> - UND ist nur $1$, wenn **beide** Eingänge $1$ sind (wie zwei Schalter in Reihe).
> - ODER ist $1$, sobald **mindestens ein** Eingang $1$ ist (wie zwei Schalter parallel).

## Huntingtonsche Axiome in der Schaltalgebra

| Axiom       | Gesetz                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------------- |
| Kommutativ  | $a \lor b = b \lor a$ (K1)<br>$a \land b = b \land a$ (K2)                                                          |
| Distributiv | $a \land (b \lor c) = (a \land b) \lor (a \land c)$ (D1)<br>$a \lor (b \land c) = (a \lor b) \land (a \lor c)$ (D2) |
| Neutral     | $a \lor 0 = a$ (N1)<br>$a \land 1 = a$ (N2)                                                                         |
| Komplement  | $a \land \overline{a} = 0$ (C1)<br>$a \lor \overline{a} = 1$ (C2)                                                   |

## Siehe auch

- [[Rechenregeln der Schaltalgebra]]: weitere Gesetze, die aus den Axiomen folgen
- [[Boolesche Ausdrücke und Tautologie]]
