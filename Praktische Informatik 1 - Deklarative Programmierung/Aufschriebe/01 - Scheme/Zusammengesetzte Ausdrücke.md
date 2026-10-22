---
tags: [Info-1, scheme, auswertung, klausur]
vorlesung: 01-Scheme
folien: 8-9
---

# Scheme: Zusammengesetzte Ausdrücke

## Auswertung in Schritten (Folie 8)

Die Auswertung zusammengesetzter Ausdrücke vollzieht $\leadsto$ in **mehreren Schritten** (Step ①, ②, …), von **innen nach außen**. Sie stoppt, sobald keine weitere Reduktion mehr möglich ist.

```scheme
(+ (+ 20 20) (+ 1 1))
⇝ (+ 40 (+ 1 1))      ; Step 1: (+ 20 20) reduziert
⇝ (+ 40 2)            ; Step 2: (+ 1 1) reduziert
⇝ 42                  ; Step 3
```

Die Folie markiert, welcher Teilausdruck als Nächstes reduziert wird. Die beiden inneren Ausdrücke `(+ 20 20)` und `(+ 1 1)` sind unabhängig, deshalb wäre eine **parallele Reduktion OK**.

> [!tip] Zusatz: Warum von innen nach außen?
> Eine Funktion kann erst angewendet werden, wenn ihre Argumente Werte sind. Bei `(+ (+ 20 20) (+ 1 1))` müssen also erst die Summen berechnet werden.
>
> Dass parallele Reduktion erlaubt ist, ist genau die Situation aus der Einführung: `(g x)` und `(h y)` beeinflussen sich laut [[Leibniz-Prinzip]] nicht ([[Funktionen und Parallelität]]).

## Beispiel: $2 - 1 + 3$ (Folie 9)

Die Mathematik braucht neben "Punkt-vor-Strich" weitere Konventionen, die Zweideutigkeiten auflösen. Der Ausdruck $2 - 1 + 3$ lässt sich auf zwei Arten klammern:

| Variante | Klammerung | Wert |
|---|---|---|
| 1. rechts-tief | $2 - (1 + 3)$ | $-2$ |
| 2. links-tief | $(2 - 1) + 3$ | $4$ |

**Scheme ist explizit** und unterscheidet die Varianten 1. und 2.

> [!tip] Zusatz: Wie das in Scheme aussieht
> ```scheme
> (- 2 (+ 1 3))  ⇝ -2    ; Variante 1: erst 1+3, dann 2-4
> (+ (- 2 1) 3)  ⇝ 4     ; Variante 2: erst 2-1, dann 1+3
> ```
> In der Mathematik gilt die Konvention "von links nach rechts", also Variante 2 mit dem Ergebnis $4$. Die Scheme-Schreibweisen stehen nicht auf der Folie, sind aber direkte Übersetzungen der beiden Klammerungen.

## Siehe auch

- [[Ausdrücke und Auswertung]]
- [[Präfixnotation]]
- [[Funktionsanwendung Applikation]]: Auswertung mit Ersetzung
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
