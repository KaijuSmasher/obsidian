---
tags: [TI-1, Digitaltechnik, boolesche-algebra, schaltalgebra, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 28-30
---

# Vollständige Operatorensysteme

> [!note] Definition
> Ein System von Operatoren, mit dem sich **alle** Booleschen Funktionen darstellen lassen, heißt **vollständiges Operatorensystem**.

Die Operatoren $(\land, \lor, \overline{\phantom{x}})$ bilden ein vollständiges Operatorensystem.

Beispiel: $a \leftrightarrow  b$ liefert dasselbe wie $(a \land \overline{b}) \lor (\overline{a} \land b)$, lässt sich also durch $\land$, $\lor$ und Negation ersetzen.

## Tabelle (Folie 29)

| Operatorensystem | Negation $\overline{a}$ | Konjunktion $a \land b$ | Disjunktion $a \lor b$ |
|---|---|---|---|
| $(\land, \lor, \overline{\phantom{x}})$ | $\overline{a}$ | $a \land b$ | $a \lor b$ |
| $(\land, \overline{\phantom{x}})$ | $\overline{a}$ | $a \land b$ | $\overline{\overline{a} \land \overline{b}}$ |
| $(\lor, \overline{\phantom{x}})$ | $\overline{a}$ | $\overline{\overline{a} \lor \overline{b}}$ | $a \lor b$ |
| **NAND** | $a \,\overline{\land}\, a$ | $(a \,\overline{\land}\, b) \,\overline{\land}\, (a \,\overline{\land}\, b)$ | $(a \,\overline{\land}\, a) \,\overline{\land}\, (b \,\overline{\land}\, b)$ |
| **NOR** | $a \,\overline{\lor}\, a$ | $(a \,\overline{\lor}\, a) \,\overline{\lor}\, (b \,\overline{\lor}\, b)$ | $(a \,\overline{\lor}\, b) \,\overline{\lor}\, (a \,\overline{\lor}\, b)$ |
| $(\land, \not\leftrightarrow)$ | $a \not\leftrightarrow 1$ | $a \land b$ | $a \not\leftrightarrow b \not\leftrightarrow (a \land b)$ |

Die ersten beiden Zeilen mit Negation folgen direkt aus [[Rechenregeln der Schaltalgebra]] (De Morgan).

## Nachweis: NAND ist vollständig

**Ansatz:** Die Elementaroperatoren $\land, \lor, \overline{\phantom{x}}$ auf NAND zurückführen. Schreibe $x \,\overline{\land}\, y$ für $\overline{x \land y}$.

**NOT:**

$$\overline{x} = \overline{x \land x} = x \,\overline{\land}\, x$$

**AND:** Das äußere NOT durch ein NAND ersetzen.

$$x \land y = \overline{\overline{x \land y}} = \overline{(x \,\overline{\land}\, y) \land (x \,\overline{\land}\, y)} = (x \,\overline{\land}\, y) \,\overline{\land}\, (x \,\overline{\land}\, y)$$

**OR:** Mit De Morgan, dann die beiden inneren NOTs durch NANDs ersetzen.

$$x \lor y = \overline{\overline{x \lor y}} = \overline{\overline{x} \land \overline{y}} = \overline{(x \,\overline{\land}\, x) \land (y \,\overline{\land}\, y)} = (x \,\overline{\land}\, x) \,\overline{\land}\, (y \,\overline{\land}\, y)$$

Weil NOT, AND und OR mit NAND darstellbar sind und $(\land, \lor, \overline{\phantom{x}})$ vollständig ist, ist auch NAND **allein** vollständig. Für NOR geht es analog.

> [!tip] Zusatz: Warum ist das wichtig?
> - In der Praxis lässt sich jede Schaltung aus **nur einem Gattertyp** (NAND oder NOR) bauen. Das ist in CMOS-Technik besonders günstig, weil NAND und NOR direkt mit wenigen Transistoren realisierbar sind.
> - Nicht jedes System ist vollständig: Zum Beispiel reichen $\land$ und $\lor$ **allein nicht**, weil man damit keine Negation bauen kann (jede damit gebaute Funktion liefert bei Eingang $0\ldots0$ eine $0$ und bei $1\ldots1$ eine $1$).

> [!warning] Übungstipp
> Typische Aufgabe: "Stelle $a \lor b$ nur mit NAND dar." Vorgehen: erst die Formel in AND/NOT umschreiben (De Morgan), dann jedes NOT und AND durch NAND ersetzen. Prüfe das Ergebnis immer mit einer Wahrheitstabelle.

## Siehe auch

- [[Zweistellige Boolesche Funktionen]]
- [[Hardware ist anders]]: Gatter als reale Bauelemente
