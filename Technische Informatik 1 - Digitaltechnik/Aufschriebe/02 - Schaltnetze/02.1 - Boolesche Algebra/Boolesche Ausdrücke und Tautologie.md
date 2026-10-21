---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra]
vorlesung: 02-Boolesche-Algebra
folien: 18-20
---

# Boolesche Ausdrücke und Tautologie

## Boolescher Ausdruck

Ein **Boolescher Ausdruck** ist eine Zeichenfolge aus binären Variablen, den Operatoren $\land$ und $\lor$ (und Negation) sowie Klammern, die bestimmte **syntaktische Regeln** erfüllt. Das Syntaxdiagramm (Folie 18) sagt, dass ein Ausdruck ist:

1. die Konstante $0$, oder
2. die Konstante $1$, oder
3. eine binäre Variable, oder
4. eine Negation eines Booleschen Ausdrucks, oder
5. zwei Boolesche Ausdrücke, verbunden durch $\land$ oder $\lor$, oder
6. ein Boolescher Ausdruck in Klammern.

Der Aufbau ist also **rekursiv**.

| Syntaktisch korrekt | Nicht korrekt |
|---|---|
| $a \lor b$ | $a \lor \lor a$ (zwei Operatoren hintereinander) |
| $0$ | $1\ 0$ (zwei Konstanten ohne Operator) |
| $(a \land b) \lor c$ | $() \lor c$ (leere Klammer) |

## Wahrheitswerte und Belegung

- Die Konstanten heißen auch **Wahrheitswerte**: $0$ = falsch, $1$ = wahr.
- Ein Ausdruck mit Variablen hat zunächst **keinen** Wahrheitswert.
- Erst durch eine **Belegung** der Variablen mit Wahrheitswerten bekommt er einen.

## Evaluation

- **Evaluation** = Variablen belegen und den Ausdruck daraufhin auswerten.
- Das Ergebnis ist wahr oder falsch.
- Verschiedene Belegungen können zum selben Wahrheitswert führen.

## Tautologie

Ein Ausdruck, der für **alle** möglichen Variablenbelegungen wahr ist, heißt **Tautologie**.

Beispiel: $\overline{a} \lor a$ ist eine Tautologie (nach dem Komplementgesetz immer $1$).

> [!tip] Zusatz
> - Das Gegenstück ist die **Kontradiktion**: immer falsch, zum Beispiel $a \land \overline{a}$. Beide tauchen später als Funktionen $f_{15}$ (konstant 1) und $f_0$ (konstant 0) auf, siehe [[Zweistellige Boolesche Funktionen]].
> - Ein Ausdruck, der für mindestens eine Belegung wahr ist, heißt *erfüllbar*. Das Erfüllbarkeitsproblem (SAT) ist eines der berühmtesten Probleme der theoretischen Informatik.

## Siehe auch

- [[Boolesche Funktionen]]
- [[Äquivalenz von Ausdrücken prüfen]]: Tautologie als Werkzeug
