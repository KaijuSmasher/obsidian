---
tags: [Info-1, Funktionen, modellierung]
vorlesung: 00-Einführung
folien: 18-20
---

# Parkplatz-Puzzle

> [!note] Aufgabe (Folie 18)
> Auf einem Parkplatz stehen PKWs und Motorräder (ohne Beiwagen). Zusammen seien es $n$ Fahrzeuge mit insgesamt $r$ Rädern. Bestimme die Anzahl $P$ der PKWs.

Das beschreibt gleich eine **ganze Menge von Puzzles**, eines für jede Wahl von $n$ und $r$. Deshalb hat man es mit **Funktionen** zu tun:

- $P(n,r)$: Anzahl der PKWs
- $M(n,r)$: Anzahl der Motorräder

## Herleitung (Folie 19)

PKWs steuern je 4 Räder bei, Motorräder je 2:

$$P + M = n \quad\Rightarrow\quad M = n - P$$

$$4P + 2M = r$$

Einsetzen von $M = n - P$:

$$4P + 2(n - P) = r \;\Rightarrow\; 4P + 2n - 2P = r \;\Rightarrow\; 2P = r - 2n$$

$$\boxed{P(n,r) = \tfrac{1}{2}\,(r - 2n)}$$

> [!tip] Zusatz: Motorräder und Probe
> Aus $M = n - P$ folgt $M(n,r) = n - \tfrac{1}{2}(r - 2n) = \tfrac{1}{2}(4n - r)$.
>
> Probe mit $n = 5$, $r = 14$: $P = 2$, $M = 3$, und $2 \cdot 4 + 3 \cdot 2 = 14$ ✓.

## Ist das Puzzle damit gelöst? (Folie 20)

Die Funktion "sieht gut aus", aber nicht jede Eingabe ergibt Sinn:

| Aufruf | Ergebnis | Problem (Folie) |
|---|---|---|
| $P(3,9)$ | $1{,}5$ | Halbe PKWs? |
| $P(5,2)$ | $-4$ | Noch 4 PKWs einparken, dann ist der Parkplatz leer... |
| $P(2,10)$ | $3$ | Subtil: mehr PKWs als Fahrzeuge |

Die Lösung dafür steht in [[Verträge und Vertragsbedingungen]].

## Siehe auch

- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Einführung/01 - Einführung]]
- [[Programmieren mit Funktionen]]
