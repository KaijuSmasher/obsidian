---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 21-23, 26-27
---

# Boolesche Funktionen (Schaltfunktionen)

## Definition

Gegeben ein Tupel binärer Variablen $(x_1, x_2, \dots, x_n)$. Eine **$n$-stellige Boolesche Funktion** ordnet jeder möglichen Belegung genau einen Wahrheitswert zu:

$$f: \{0,1\}^n \to \{0,1\}, \qquad y = f(x_1, x_2, \dots, x_n)$$

Beispiele:

- Negation: einstellig, $f: \{0,1\} \to \{0,1\}$.
- $\land$ und $\lor$: zweistellig, $f: \{0,1\} \times \{0,1\} \to \{0,1\}$.

## Wie viele gibt es?

| Frage | Antwort |
|---|---|
| Anzahl der Belegungen von $n$ Variablen | $2^n$ |
| Anzahl verschiedener $n$-stelliger Funktionen | $2^{2^n}$ |

> [!tip] Zusatz: Warum $2^{2^n}$?
> Die Wahrheitstabelle hat $2^n$ Zeilen. In jeder Zeile darf der Funktionswert $0$ oder $1$ sein, und die Zeilen sind unabhängig. Das sind $2 \cdot 2 \cdots 2 = 2^{(2^n)}$ Möglichkeiten.
>
> | $n$ | Zeilen $2^n$ | Funktionen $2^{2^n}$ |
> |---|---|---|
> | 1 | 2 | 4 |
> | 2 | 4 | 16 |
> | 3 | 8 | 256 |
> | 4 | 16 | 65.536 |
>
> Für $n = 2$ sind das genau die 16 Funktionen aus [[Zweistellige Boolesche Funktionen]].

## Darstellungsformen

1. **Funktionstabelle** (Wahrheitstabelle)
2. **Algebraischer Ausdruck** (symbolische Form)
3. **Binäres Entscheidungsdiagramm** (BDD)

Beispiel $f(a, b) = a \land b$: Tabelle mit den Zeilen $00 \to 0$, $01 \to 0$, $10 \to 0$, $11 \to 1$.

### Beispiel: dreistellige Paritätsfunktion

Die Funktion ist $1$, wenn eine **ungerade Anzahl** von Eingängen $1$ ist.

$$f = (\overline{x_3} \land \overline{x_2} \land x_1) \lor (\overline{x_3} \land x_2 \land \overline{x_1}) \lor (x_3 \land \overline{x_2} \land \overline{x_1}) \lor (x_3 \land x_2 \land x_1)$$

| Nr. | $x_3$ | $x_2$ | $x_1$ | $f$ |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 2 | 0 | 1 | 0 | 1 |
| 3 | 0 | 1 | 1 | 0 |
| 4 | 1 | 0 | 0 | 1 |
| 5 | 1 | 0 | 1 | 0 |
| 6 | 1 | 1 | 0 | 0 |
| 7 | 1 | 1 | 1 | 1 |

> [!tip] Zusatz
> - Die Nummer der Zeile ist die Binärzahl $x_3 x_2 x_1$ (siehe [[Zahlensysteme umrechnen]]).
> - Jeder der vier Summanden in der Formel gehört zu **einer** Zeile mit $f = 1$ (Zeilen 1, 2, 4, 7). Genau so liest man aus einer Tabelle einen Ausdruck ab: pro $1$-Zeile ein UND-Term, alle mit ODER verbunden.
> - Die Parität ist die dreifache Antivalenz $x_1 \oplus x_2 \oplus x_3$, siehe [[Zweistellige Boolesche Funktionen]].
> - Das **binäre Entscheidungsdiagramm** auf der Folie testet nacheinander $x_1$, $x_2$, $x_3$. Bei $0$ geht man links, bei $1$ rechts, am Ende steht der Funktionswert in einem Blatt ($0$ oder $1$).

## Von der symbolischen Form zur Tabelle

Durch **rekursive Auswertung** des Ausdrucks, von innen nach außen.

**Vorrang-Konvention:**

1. Negation vor Konjunktion
2. Konjunktion vor Disjunktion
3. Klammern legen eine andere Reihenfolge fest

Also: $\overline{a} \land b \lor c$ bedeutet $((\overline{a}) \land b) \lor c$. "UND bindet stärker als ODER", wie "Punkt vor Strich".

> [!warning] Übungstipp
> Bei der Auswertung hilft es, für jeden Teilausdruck eine eigene Spalte in der Wahrheitstabelle anzulegen. Zum Beispiel für $(a \land b) \lor (\overline{a} \land \overline{b})$ die Spalten $a \land b$, $\overline{a}$, $\overline{b}$, $\overline{a} \land \overline{b}$ und dann das Ergebnis.

## Siehe auch

- [[Boolesche Ausdrücke und Tautologie]]
- [[Vollständige Operatorensysteme]]
