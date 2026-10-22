---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 31-33
---

# Äquivalenz von Ausdrücken prüfen

**Frage:** Wann repräsentieren zwei Ausdrücke $A$ und $B$ dieselbe Boolesche Funktion?

**Gleichbedeutend:** Ist $A \leftrightarrow B$ eine [[Boolesche Ausdrücke und Tautologie|Tautologie]]?

Zwei Ausdrücke sind **äquivalent**, wenn ihre Auswertung für **alle** Variablenbelegungen identisch ist.

## Zwei Methoden

1. **Funktionstabellen:** beide Ausdrücke für alle Belegungen auswerten und vergleichen. Mechanisch, aber bei vielen Variablen lang ($2^n$ Zeilen).
2. **Algebraische Umformung:** einen Ausdruck mit den Gesetzen ([[Rechenregeln der Schaltalgebra]]) in den anderen umformen.

## Beispiel

$$f_1(a, b) = (a \land b) \lor (\overline{a} \land \overline{b}) \qquad f_2(a, b) = (a \lor \overline{b}) \land (\overline{a} \lor b)$$

Ist $f_1 = f_2$?

### Umformung (Folie 33)

$$
\begin{aligned}
(a \land b) \lor (\overline{a} \land \overline{b}) &= [(a \land b) \lor \overline{a}] \land [(a \land b) \lor \overline{b}] && \text{(Distributivgesetz)} \\
&= [(a \lor \overline{a}) \land (b \lor \overline{a})] \land [(a \lor \overline{b}) \land (b \lor \overline{b})] && \text{(Distributivgesetz)} \\
&= [1 \land (b \lor \overline{a})] \land [(a \lor \overline{b}) \land 1] && \text{(inverses Element)} \\
&= (b \lor \overline{a}) \land (a \lor \overline{b}) && \text{(neutrales Element)} \\
&= (\overline{a} \lor b) \land (a \lor \overline{b}) && \text{(Kommutativgesetz)}
\end{aligned}
$$

Das ist bis auf die Reihenfolge der Faktoren genau $f_2$. Also sind $f_1$ und $f_2$ **äquivalent**.

### Probe mit Wahrheitstabelle

| $a$ | $b$ | $f_1$ | $f_2$ |
|---|---|---|---|
| 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 |

Beide sind $1$, wenn $a = b$. Beide Ausdrücke beschreiben also die **Äquivalenz** $a \leftrightarrow b$ aus [[Zweistellige Boolesche Funktionen]].

> [!tip] Zusatz
> - Beim Umformen immer erst überlegen, **welches Gesetz** den nächsten Schritt erlaubt, und es hinschreiben (wie auf der Folie). Das ist in der Klausur wahrscheinlich Teil der Bewertung.
> - Hier wird das Distributivgesetz in der "ungewohnten" Form $a \lor (b \land c) = (a \lor b) \land (a \lor c)$ verwendet. Dafür ist man schnell blind, wenn man nur normales Ausmultiplizieren kennt.
> - Wenn du nach einer Umformung nicht weiterkommst: Wahrheitstabelle. Sie ist langsam, aber garantiert.
