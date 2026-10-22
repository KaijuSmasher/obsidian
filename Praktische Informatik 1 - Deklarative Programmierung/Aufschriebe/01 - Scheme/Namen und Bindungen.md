---
tags: [Info-1, scheme, define, namen]
vorlesung: 01-Scheme
folien: 11, 13
---

# Scheme: Namen und Bindungen

Ein Wert kann an einen **Namen** (auch: *Identifier*) gebunden werden:

> [!note] define (Folie 11)
> `(define id e)` mit $id$: Identifier und $e$: Ausdruck.

Solche **Bindungen** erlauben die konsistente Wiederverwendung und dienen der Selbstdokumentation von Programmen.

> [!warning] Spezialform
> `(define …)` ist eine sogenannte **Spezialform** ([[Spezialformen]]). Sie besitzt **keinen Wert, sondern einen Effekt**: Der Name $id$ wird an den Wert des Ausdrucks $e$ gebunden.

## Regeln für Namen (Folie 13)

Namen können in Scheme fast beliebig gewählt werden, solange

1. die Zeichen `( ) [ ] { } " , ' ` ; # | \` nicht vorkommen,
2. der Name nicht einem numerischen Literal gleicht ([[Literale]]),
3. kein Whitespace (Space, Tab, Return) enthalten ist, und
4. der Name nicht bereits an einen Wert gebunden ist.

Groß- und Kleinschreibung ist in Namen **nicht relevant**.

Beispiel: `euro->us$` ist ein gültiger Identifier. `Euro->US$` ist als Identifier **identisch**.

> [!tip] Zusatz: Was Bindungen bewirken
> Nach `(define id e)` steht `id` überall für den Wert von `e`. In [[Funktionsanwendung Applikation]] wird so `minutes-in-a-day` im Schritt ② durch `1440` ersetzt. Die Definition von `minutes-in-a-day` zeigt die Folie nicht, der Wert $1440$ ergibt sich aus der Reduktion dort.
>
> Gängige Namen enthalten Bindestriche, z. B. `parking-lot-cars` ([[Parkplatz-Puzzle in Scheme]]). Das geht, weil `-` laut Regel 1 nicht verboten ist.

## Siehe auch

- [[Spezialformen]]
- [[Lambda-Abstraktion]]: `define` gibt einer Funktion einen Namen
- [[DrRacket und die REPL]]: Bindungen im Definitionsfenster
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
