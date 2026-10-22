---
tags: [Info-1, scheme, auswertung]
vorlesung: 01-Scheme
folien: 5
---

# Scheme: Ausdrücke und Auswertung

`(+ 40 2)` und `(odd? 42)` sind Beispiele für **Ausdrücke**, die bei **Auswertung** einen **Wert** liefern. Notation für die Auswertung: $\leadsto$

```scheme
(+ 40 2)   ⇝ 42
(odd? 42)  ⇝ #f
```

> [!note] Auswertung (Folie 5)
> $\leadsto$: Durch **Auswertung** (auch: **Reduktion** oder **Evaluation**) führt Scheme Programme aus.

> [!tip] Zusatz: Begriffe
> - **Ausdruck:** das, was man hinschreibt, z. B. `(+ 40 2)`.
> - **Wert:** das Ergebnis der Auswertung, z. B. `42`. Ein Wert lässt sich nicht weiter reduzieren.
> - `#t` und `#f` sind die Wahrheitswerte ([[Literale]]). `(odd? 42)` ist falsch, weil $42$ gerade ist.

## Siehe auch

- [[Zusammengesetzte Ausdrücke]]: Auswertung in mehreren Schritten
- [[DrRacket und die REPL]]: wo man Ausdrücke auswerten lässt
- [[Präfixnotation]]
- [[01 - Scheme]]
