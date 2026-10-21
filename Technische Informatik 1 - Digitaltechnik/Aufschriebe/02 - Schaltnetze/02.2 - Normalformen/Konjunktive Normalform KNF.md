---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 43
---

# Konjunktive Normalform (KNF)

> [!note] Definition
> Ein Boolescher Ausdruck heißt **KNF** der Funktion $y(x_1, \dots, x_m)$, wenn er aus einer **konjunktiven Verknüpfung von Maxtermen** $D_i$ besteht ([[Implikat und Maxterm]]):
> $$y = D_0 \land D_1 \land \dots \land D_k, \qquad k \le 2^n - 1$$
> Es darf **keine zwei** Disjunktionen $D_i, D_j$ mit $i \ne j$ geben, die zueinander äquivalent sind.

**Kurz:** UND von Maxtermen, jeder Maxterm höchstens einmal.

> [!tip] Zusatz: Vergleich
> | | DNF | KNF |
> |---|---|---|
> | Aufbau | ODER von UND-Termen | UND von ODER-Termen |
> | Terme | Minterme | Maxterme |
> | Zeilen der Tabelle | mit $y = 1$ | mit $y = 0$ |

## Hinweis der Folie: Dualität

Jede Schaltfunktion ist **sowohl** in der DNF **als auch** in der KNF darstellbar. Beide Darstellungen sind äquivalent (**Dualitätsprinzip**).

## Siehe auch

- [[Disjunktive Normalform DNF]]
- [[DNF und KNF aus der Funktionstabelle]]: Beispiel mit beiden Normalformen
