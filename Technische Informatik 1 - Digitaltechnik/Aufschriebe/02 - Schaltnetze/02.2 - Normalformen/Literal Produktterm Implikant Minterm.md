---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen]
vorlesung: 02-Boolesche-Algebra
folien: 36-38
---

# Literal, Produktterm, Implikant, Minterm

Eine Boolesche Funktion ([[Boolesche Funktionen]]) kann durch viele verschiedene Ausdrücke beschrieben werden. **Normalformen** sind eine besonders einfache, standardisierte Gleichungsform. Dafür braucht man ein paar Begriffe.

## Literal

Ein **Literal** $L_i$ ist eine Schaltvariable oder ihre Negation:

$$L_i \in \{x_i, \overline{x_i}\}$$

## Produktterm

Ein **Produktterm** $K(x_1, \dots, x_m)$ ist eine **Konjunktion** von Literalen (oder die Konstante $0$ oder $1$):

$$K = \bigwedge_{i=1}^{m} L_i = L_1 \land \dots \land L_m$$

Beispiele: $a \land a \land b$, $\overline{x_i} \land x_i$.

Mehrfach vorkommende gleiche Literale kann man nach dem Idempotenzgesetz streichen ($a \land a = a$, siehe [[Rechenregeln der Schaltalgebra]]).

> [!tip] Schreibweise
> Auf den Folien wird das $\land$ oft weggelassen: $a\,b\,\overline{c}$ bedeutet $a \land b \land \overline{c}$ (wie das Malzeichen beim normalen Rechnen).

## Implikant

Ein Produktterm $K(x_1, \dots, x_n)$ heißt **Implikant** einer Funktion $y(x_1, \dots, x_n)$, wenn $K \to y$ gilt.

Das heißt: Für jede Belegung $B \in \{0,1\}^n$ gilt: **Wenn** $K(B) = 1$, **dann** ist auch $y(B) = 1$.

> [!tip] Zusatz: Anschaulich
> Ein Implikant ist ein Produktterm, der "nur dort $1$ ist, wo $y$ auch $1$ ist". Er darf also nie eine Stelle abdecken, an der $y = 0$ ist. Er muss aber nicht *alle* Einsen von $y$ abdecken.

## Minterm

Ein Implikant von $y(x_1, \dots, x_n)$ heißt **Minterm**, wenn ein Literal **jeder** Variablen $x_i$ **genau einmal** vorkommt.

| Beispiel für $y(x_1, \dots, x_4)$ | Minterm? | Grund |
|---|---|---|
| $x_1 \land x_2 \land x_3 \land x_4$ | ja | alle 4 Variablen genau einmal |
| $x_1 \land \overline{x_2} \land x_3 \land x_4$ | ja | alle 4 Variablen genau einmal |
| $x_1 \land x_2$ | nein | nicht alle Variablen |
| $x_1 \land \overline{x_2} \land x_3 \land x_3 \land x_4$ | nein | $x_3$ doppelt |

> [!tip] Zusatz: Was die Tabelle (noch) nicht prüft
> Die Folie prüft nur die **Form**. Damit ein solcher Term wirklich ein Minterm *von $y$* ist, muss er zusätzlich ein Implikant von $y$ sein, also in seiner einzigen Zeile der Funktionstabelle den Wert $y = 1$ haben.
>
> Ein Term mit allen Variablen ist in **genau einer** Zeile der Tabelle wahr. Deshalb gibt es bei $n$ Variablen genau $2^n$ mögliche Minterme (siehe [[Disjunktive Normalform DNF]]).

> [!tip] Zusatz: Kürzere Implikanten
> Ein Term wie $x_1 \land x_2$ kann durchaus ein Implikant sein (wenn $y$ überall $1$ ist, wo $x_1 \land x_2$ wahr ist), er ist nur kein Minterm. Solche kürzeren Implikanten dürften bei der Minimierung (Kapitel 2.3) wichtig werden.

## Siehe auch

- [[Implikat und Maxterm]]: die duale Version für ODER-Terme
- [[Disjunktive Normalform DNF]]
