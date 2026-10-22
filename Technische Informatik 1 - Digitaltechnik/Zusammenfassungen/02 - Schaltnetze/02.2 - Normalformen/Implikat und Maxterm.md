---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen]
vorlesung: 02-Boolesche-Algebra
folien: 42
---

# Implikat und Maxterm

Das ist die **duale** Version von [[Literal Produktterm Implikant Minterm]]: Statt UND-Terme gibt es ODER-Terme, statt der Einsen zählen die Nullen.

## Definition Implikat

Sei $D(x_1, \dots, x_m)$ eine **Disjunktion** von Literalen (oder die Konstante $0$ oder $1$):

$$D = \bigvee_{i=1}^{m} L_i = L_1 \lor \dots \lor L_m$$

$D$ heißt **Implikat** einer Funktion $y$, wenn $\overline{D} \to \overline{y}$ gilt.

Das heißt: Für jede Belegung $B \in \{0,1\}^n$ gilt: **Wenn** $D(B) = 0$, **dann** ist auch $y(B) = 0$.

> [!tip] Zusatz: Vergleich mit dem Implikanten
> | | Implikant (UND-Term $K$) | Implikat (ODER-Term $D$) |
> |---|---|---|
> | Bedingung | $K = 1 \Rightarrow y = 1$ | $D = 0 \Rightarrow y = 0$ |
> | Er darf nie ... | $1$ sein, wo $y = 0$ ist | $0$ sein, wo $y = 1$ ist |

## Maxterm

Ein Implikat einer Funktion $y(x_1, \dots, x_m)$ heißt **Maxterm**, wenn ein Literal **jeder** Variablen $x_i$ **genau einmal** im Implikaten vorkommt.

Beispiele für $y(x_1, x_2, x_3)$:

$$x_1 \lor x_2 \lor x_3 \qquad x_1 \lor \overline{x_2} \lor x_3$$

> [!tip] Zusatz: Jeder Maxterm ist in genau einer Zeile falsch
> Ein ODER-Term über alle Variablen ist nur für **eine** Belegung $0$ (alle Literale gleichzeitig $0$). Zum Beispiel ist $x_1 \lor \overline{x_2} \lor x_3$ nur $0$ bei $x_1 = 0$, $x_2 = 1$, $x_3 = 0$.
>
> Außerdem gilt: Der Maxterm einer Zeile ist die **Negation** des Minterms derselben Zeile. Nach De Morgan ([[Rechenregeln der Schaltalgebra]]): $\overline{a \land \overline{b} \land c} = \overline{a} \lor b \lor \overline{c}$.

## Siehe auch

- [[Konjunktive Normalform KNF]]
