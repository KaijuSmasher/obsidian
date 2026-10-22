---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 15-17
---

# Rechenregeln der Schaltalgebra

Aus den vier Axiomen ([[Schaltalgebra]]) lassen sich weitere Sätze **ableiten**.

| Name | UND-Form | ODER-Form |
|---|---|---|
| Assoziativ | $(a \land b) \land c = a \land (b \land c)$ (A1) | $(a \lor b) \lor c = a \lor (b \lor c)$ (A2) |
| Idempotenz | $a \land a = a$ (ID1) | $a \lor a = a$ (ID2) |
| Absorption | $a \land (a \lor b) = a$ (AS1) | $a \lor (a \land b) = a$ (AS2) |
| De Morgan | $\overline{a \land b} = \overline{a} \lor \overline{b}$ (DM1) | $\overline{a \lor b} = \overline{a} \land \overline{b}$ (DM2) |

> [!tip] Zusatz: Merkregeln
> - **Idempotenz:** Wiederholen ändert nichts. "a oder a" ist einfach a.
> - **Absorption:** Der längere Term wird "aufgesaugt". $a \lor (a \land b)$: Wenn $a$ wahr ist, ist alles wahr. Wenn $a$ falsch ist, ist auch $a \land b$ falsch. Also hängt das Ergebnis nur von $a$ ab.
> - **De Morgan:** Negation "zieht" in die Klammer, dabei wird aus UND ein ODER und umgekehrt (*Balken brechen, Zeichen wechseln*). Das ist in der Schaltungstechnik extrem wichtig, weil damit zum Beispiel ein NAND zu einem ODER mit negierten Eingängen wird.
> - Alle Gesetze kommen **paarweise** vor (UND ↔ ODER, 0 ↔ 1). Das ist die Dualität.

## Beweis Absorptionsgesetz AS2

Zu zeigen: $a \lor (a \land b) = a$

$$
\begin{aligned}
a \lor (a \land b) &= (a \land 1) \lor (a \land b) && \text{(neutrales Element: } a = a \land 1) \\
&= a \land (1 \lor b) && \text{(Distributivgesetz)} \\
&= a \land (b \lor 1) && \text{(Kommutativgesetz)} \\
&= a \land 1 && (b \lor 1 = 1) \\
&= a && \text{(neutrales Element)}
\end{aligned}
$$

> [!tip] Zusatz: Warum gilt $b \lor 1 = 1$?
> Das nutzt die Folie einfach. Es lässt sich aus den Axiomen herleiten:
> $b \lor 1 = (b \lor 1) \land 1 = (b \lor 1) \land (b \lor \overline{b}) = b \lor (1 \land \overline{b}) = b \lor \overline{b} = 1$
> (neutrales Element, Komplement, Distributivgesetz, neutrales Element, Komplement).

## Beweis De Morgan: $\overline{a \land b} = \overline{a} \lor \overline{b}$

**Idee:** Das Komplement eines Elements $x$ ist eindeutig. Wenn man zeigt, dass $\overline{a} \lor \overline{b}$ beide Komplementgesetze für $x = a \land b$ erfüllt, dann *ist* es das Komplement $\overline{x}$.

Zu zeigen sind $x \lor \overline{x} = 1$ und $x \land \overline{x} = 0$ mit $x = a \land b$ und $\overline{x} = \overline{a} \lor \overline{b}$.

**Teil 1:** $x \lor \overline{x} = 1$

$$
\begin{aligned}
(a \land b) \lor \overline{x} &= (a \lor \overline{x}) \land (b \lor \overline{x}) \\
&= (a \lor \overline{a} \lor \overline{b}) \land (b \lor \overline{a} \lor \overline{b}) \\
&= (1 \lor \overline{b}) \land (1 \lor \overline{a}) = 1 \land 1 = 1
\end{aligned}
$$

**Teil 2:** $x \land \overline{x} = 0$

$$
\begin{aligned}
x \land (\overline{a} \lor \overline{b}) &= (x \land \overline{a}) \lor (x \land \overline{b}) \\
&= (a \land b \land \overline{a}) \lor (a \land b \land \overline{b}) \\
&= (0 \land b) \lor (a \land 0) = 0 \lor 0 = 0
\end{aligned}
$$

> [!warning] Probe mit Wahrheitstabelle
> Ob ein Gesetz stimmt, kannst du immer mit einer Wahrheitstabelle überprüfen (4 Zeilen bei 2 Variablen). Für DM1:
>
> | $a$ | $b$ | $\overline{a \land b}$ | $\overline{a} \lor \overline{b}$ |
> |---|---|---|---|
> | 0 | 0 | 1 | 1 |
> | 0 | 1 | 1 | 1 |
> | 1 | 0 | 1 | 1 |
> | 1 | 1 | 0 | 0 |

## Siehe auch

- [[Äquivalenz von Ausdrücken prüfen]]: Umformen mit diesen Gesetzen
- [[Vollständige Operatorensysteme]]: De Morgan wird dort gebraucht
