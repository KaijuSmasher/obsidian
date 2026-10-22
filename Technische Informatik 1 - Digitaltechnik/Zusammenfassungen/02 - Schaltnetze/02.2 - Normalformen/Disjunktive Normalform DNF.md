---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 39-41
---

# Disjunktive Normalform (DNF)

Standarddarstellungen Boolescher Funktionen im Operatorensystem $(\land, \lor, \overline{\phantom{x}})$ sind die **disjunktive Normalform (DNF)** und die [[Konjunktive Normalform KNF|konjunktive Normalform (KNF)]].

> [!note] Definition
> Ein Boolescher Ausdruck heißt **DNF** der Funktion $y$, wenn er aus einer **disjunktiven Verknüpfung von Mintermen** $K_i$ besteht:
> $$y = K_0 \lor K_1 \lor \dots \lor K_k, \qquad k \le 2^n - 1$$
> Es darf **keine zwei** Konjunktionen $K_i, K_j$ mit $i \ne j$ geben, die zueinander äquivalent sind.

**Kurz:** ODER von Mintermen, jeder Minterm höchstens einmal.

Bei $n$ Schaltvariablen gibt es $2^n$ verschiedene Minterme. **Jeder Minterm hat nur bei einer Kombination der Wertetabelle den Wert 1**, bei allen anderen den Wert 0 ([[Literal Produktterm Implikant Minterm]]).

> [!tip] Zusatz: Warum ist die DNF eindeutig?
> Eine DNF ist nichts anderes als die Auswahl, **welche** der $2^n$ Minterme dabei sind (nämlich genau die Zeilen mit $y = 1$). Es gibt also $2^{2^n}$ mögliche DNFs, genau so viele wie Funktionen ([[Boolesche Funktionen]]). Jede Funktion hat damit **genau eine** DNF (bis auf die Reihenfolge).

## Beispiele (Folie 40)

**In DNF:**

$$f(a,b,c) = a\,b\,c \lor a\,\overline{b}\,c \lor \overline{a}\,\overline{b}\,c$$

Alle drei Terme enthalten $a$, $b$, $c$ genau einmal, und kein Term kommt doppelt vor.

**Nicht in DNF:**

$$f(a,b,c) = a\,b\,c \lor a\,\overline{b} \lor c\,a\,b \lor a\,(b\,c \lor \overline{b}\,\overline{c})$$

| Term | Problem |
|---|---|
| $a\,\overline{b}$ | enthält nicht alle Variablen |
| $a\,b\,c$ und $c\,a\,b$ | sind äquivalent (nur andere Reihenfolge) |
| $a\,(b\,c \lor \overline{b}\,\overline{c})$ | keine reine Konjunktion |

## Aufgabe (Folie 41)

Ist $f(a,b,c) = a\,\overline{b}\,c \lor a\,a\,\overline{b}\,c \lor \overline{b}\,c$ in DNF? Welche Produktterme sind Minterme?

**Antwort der Folie: Nein**, denn

- $\overline{b}\,c$ enthält nicht alle Variablen, ist also kein Minterm,
- $a\,\overline{b}\,c$ und $a\,a\,\overline{b}\,c$ sind äquivalent,
- $a\,a\,\overline{b}\,c$ ist kein Minterm ($a$ doppelt).

Der einzige Minterm ist also $a\,\overline{b}\,c$.

> [!question]- Selbst probieren: Wie sieht die DNF dieser Funktion aus?
> Überlege zuerst selbst: Für welche Belegungen von $a, b, c$ ist $f = 1$? Dann schreibe die passende DNF auf. Hinweis: Vereinfache erst mit Idempotenz und Absorption.
>
> **Lösung:** Mit Idempotenz ist $a\,a\,\overline{b}\,c = a\,\overline{b}\,c$. Mit Absorption ist $a\,\overline{b}\,c \lor \overline{b}\,c = \overline{b}\,c$. Also ist $f = \overline{b}\,c$, das ist $1$ für $b = 0$ und $c = 1$, egal wie $a$ ist. Die fehlende Variable ergänzt man mit $a \lor \overline{a} = 1$:
> $$f = \overline{b}\,c\,(a \lor \overline{a}) = a\,\overline{b}\,c \lor \overline{a}\,\overline{b}\,c$$
> Das ist die DNF (zwei Minterme).

> [!warning] Checkliste: Ist ein Ausdruck eine DNF?
> 1. Ist es ein ODER von Termen, und ist jeder Term eine reine UND-Verknüpfung von Literalen (keine verschachtelten Klammern)?
> 2. Kommt in jedem Term **jede** Variable **genau einmal** vor (negiert oder nicht)?
> 3. Kommt kein Term (auch nicht in anderer Reihenfolge) doppelt vor?

## Siehe auch

- [[DNF und KNF aus der Funktionstabelle]]
- [[Konjunktive Normalform KNF]]
