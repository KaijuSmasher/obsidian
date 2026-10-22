---
tags: [Info-1, scheme, lambda, abstraktion, klausur]
vorlesung: 01-Scheme
folien: 14-16
---

# Scheme: Lambda-Abstraktion

## Ausdrücke mit "Löchern" (Folie 14)

Ein Ausdruck mit einem **"Loch"** ⬚: Setzt man einen Wert ein, erhält man einen auswertbaren Ausdruck.

```scheme
(* ⬚ (* 135 minutes-in-a-day))
```

Scheme markiert solche Löcher mit **lambda**:

```scheme
(lambda (⬚)   (* ⬚   (* 135 minutes-in-a-day)))
(lambda (days) (* days (* 135 minutes-in-a-day)))
```

## Definition (Folie 15)

> [!note] Lambda-Abstraktion
> Eine **Lambda-Abstraktion** (auch: **Funktion**) erlaubt die Formulierung eines Ausdrucks $e$, in dem mittels **Parametern** $p_i$ von konkreten Werten **abstrahiert** wird:
> `(lambda (p₁ p₂ …) e)`
> Dabei ist $e$ der **Rumpf**. Er enthält Vorkommen von $p_1, p_2, \dots$

`(lambda …)` ist eine **Spezialform** ([[Spezialformen]]). Der **Wert** der Lambda-Abstraktion ist `#<function>`. Darauf kommt die Vorlesung später zurück.

> [!tip] Zusatz: Anschaulich
> `lambda` sagt: "Hier fehlt ein Wert, nimm ihn als Parameter." Eine Lambda-Abstraktion ist eine Funktion ohne Namen. Mit `define` ([[Namen und Bindungen]]) gibt man ihr einen, z. B. `parking-lot-cars` in [[Parkplatz-Puzzle in Scheme]].

## Warum $\lambda$? (Folie 16)

Die Folie zitiert Henk Barendregt (*The Impact of Lambda Calculus in Logic and Computer Science*, 1997). In Whiteheads und Russells *Principia Mathematica* schrieb man die Funktion $f$ mit $f(y) = 2y + 1$ als $2\hat{y} + 1$. Alonzo Church wollte ursprünglich $\hat{y}.2y+1$ schreiben. Der Setzer konnte das Dach aber nicht über das $y$ setzen und stellte es davor, es entstand $\wedge y.2y+1$. Ein weiterer Setzer machte daraus $\lambda y.2y+1$.

## Siehe auch

- [[Funktionsanwendung Applikation]]: was passiert, wenn man eine Lambda-Abstraktion anwendet
- [[Spezialformen]]
- [[Programmieren mit Funktionen]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
