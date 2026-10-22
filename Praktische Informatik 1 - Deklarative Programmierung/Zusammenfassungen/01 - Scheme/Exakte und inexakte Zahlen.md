---
tags: [Info-1, scheme, zahlen, klausur]
vorlesung: 01-Scheme
folien: 10
---

# Scheme: Arithmetik mit exakten vs. inexakten Zahlen

| 1. Exakte Zahlen | 2. Inexakte Zahlen |
|---|---|
| `(+ 0.1 0.2)` | `(+ #i0.1 #i0.2)` |
| ⇝ `0.3` | ⇝ `#i0.30000000000000004` |

> [!warning] Achtung (Folie 10)
> Schemes interne Darstellung von inexakten Zahlen `#i…` ist **kompakt**, die Arithmetik ist **sehr effizient**, kann aber zu **Ungenauigkeiten** führen.
>
> Insbesondere können **Tests auf Gleichheit** unerwartet ausfallen:
> `(= (+ #i0.1 #i0.2) 0.3)` ⇝ `#f`

> [!tip] Zusatz: Woher kommt die Ungenauigkeit?
> Inexakte Zahlen sind meist Gleitkommazahlen im Binärsystem. Der Wert $0.1$ lässt sich dort nicht exakt darstellen (ähnlich wie $\tfrac{1}{3}$ im Dezimalsystem), deshalb bleibt bei $0.1 + 0.2$ ein winziger Rest. Der Grund steht nicht auf der Folie.
>
> Praktische Folge: Inexakte Ergebnisse vergleicht man mit einer Toleranz, siehe `check-within` in [[Testfälle]].

## Siehe auch

- [[Literale]]
- [[Testfälle]]
- [[01 - Scheme]]
