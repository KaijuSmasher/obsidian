---
tags: [TI-1, Digitaltechnik, boolesche-algebra]
vorlesung: 02-Boolesche-Algebra
folien: 5-7
---

# Boolesche Algebra: Definition und Axiome

Entwickelt von dem Mathematiker **George Boole** (1815–1864) als *Algebra der Logik*. Sie eignet sich hervorragend, um Eigenschaften und Verhalten logischer Funktionen zu untersuchen.

## Definition 2.1

Eine **Boolesche Algebra** ist eine Menge $V = \{a, b, c, \dots\}$ mit zwei zweistelligen Operationen $\oplus$ und $\otimes$, die folgende Bedingungen erfüllen.

**H0 Abgeschlossenheit:** Für alle $a, b \in V$ gilt $a \otimes b \in V$ und $a \oplus b \in V$. Die Operationen führen also nicht aus der Menge heraus.

Dazu kommen die vier **Huntingtonschen Axiome**:

| Axiom | Name                   | Gesetz                                                                                                                                   |
| ----- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| H1    | Kommutativgesetze      | $a \otimes b = b \otimes a$ (K1) <br>$a \oplus b = b \oplus a$ (K2)                                                                      |
| H2    | Distributivgesetze     | $a \otimes (b \oplus c) = (a \otimes b) \oplus (a \otimes c)$ (D1) <br>$a \oplus (b \otimes c) = (a \oplus b) \otimes (a \oplus c)$ (D2) |
| H3    | Neutrale Elemente      | Es gibt $e, n \in V$ mit <br>$a \otimes e = a$ ($e$ = **Einselement**) (N1)<br>$a \oplus n = a$ ($n$ = **Nullelement**) (N2)             |
| H4    | Komplementäre Elemente | Zu jedem $a$ gibt es ein $\overline{a}$ mit <br>$a \otimes \overline{a} = n$ (C1) <br>$a \oplus \overline{a} = e$ (C2)                   |

> [!tip] Zusatz: Was ist hier anders als beim normalen Rechnen?
> Das zweite Distributivgesetz $a \oplus (b \otimes c) = (a \oplus b) \otimes (a \oplus c)$ gilt bei normalen Zahlen **nicht** ($\otimes$ = Mal, $\oplus$ = Plus). In der Booleschen Algebra sind beide Operationen gleichberechtigt, die Axiome sind *symmetrisch* aufgebaut. Das ist der Kern der **Dualität**: Vertauscht man $\oplus \leftrightarrow \otimes$ und $n \leftrightarrow e$, geht jedes gültige Gesetz wieder in ein gültiges über.

> [!warning] Achtung bei den Nummern
> Die Nummerierung (N1, N2, D1, D2 ...) ist auf den Folien nicht ganz einheitlich (zum Beispiel ist N1 auf Folie 7 etwas anderes als auf Folie 14). Merk dir die **Gesetze selbst**, nicht die Nummern.

## Siehe auch

- [[Mengenalgebra als Beispiel]]: eine konkrete Boolesche Algebra
- [[Schaltalgebra]]: die Boolesche Algebra mit $V = \{0, 1\}$
