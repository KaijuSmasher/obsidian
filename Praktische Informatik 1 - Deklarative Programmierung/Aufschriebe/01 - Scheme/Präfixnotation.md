---
tags: [Info-1, scheme, praefixnotation]
vorlesung: 01-Scheme
folien: 4
---

# Scheme: Präfixnotation

> [!note] Funktionsanwendung (Folie 4)
> Die Anwendung von Funktionen wird in Scheme **ausschließlich in Präfixnotation** durchgeführt. **Allgemein:** Anwendung einer Funktion $f$ auf $n$ Argumente via `(f argument₁ argument₂ … argumentₙ)`.

| Mathematik | Scheme |
|---|---|
| $44 - 2$ | `(- 44 2)` |
| $f(x,y)$ | `(f x y)` |
| $\sqrt{81}$ | `(sqrt 81)` |
| $\lfloor x \rfloor$ | `(floor x)` |
| $9^2$ | `(expt 9 2)` |
| $3!$ | `(! 3)` |

Die Funktion steht **immer vorne**, dann folgen die Argumente, alles in Klammern. Das gilt auch für Operatoren wie $-$.

> [!tip] Zusatz: Was die Klammern leisten
> Jede Klammer ist genau eine Funktionsanwendung. Dadurch ist die Reihenfolge der Auswertung immer eindeutig, und man braucht keine Regeln wie "Punkt-vor-Strich" ([[Zusammengesetzte Ausdrücke]]).
>
> Zur letzten Zeile der Tabelle: Die Folie schreibt `(! 3)`. In Standard-Racket gibt es meines Wissens keine eingebaute Funktion `!` (die Bibliothek `math/number-theory` hat `factorial`). Ob die Lehrsprache `!` bereitstellt, habe ich nicht geprüft.

## Siehe auch

- [[Programmieren mit Funktionen]]: derselbe Gedanke in der Einführung
- [[Ausdrücke und Auswertung]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
