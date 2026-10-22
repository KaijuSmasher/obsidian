---
tags: [Info-1, Funktionen, leibniz, parallelitaet]
vorlesung: 00-Einführung
folien: 29
---

# Funktionen und moderne Rechner

Sei folgender Ausdruck Teil eines Programms:

```scheme
(f (g x) (h y))
```

- Laut [[Leibniz-Prinzip]] **beeinflussen sich die Berechnungen** von `(g x)` und `(h y)` **nicht gegenseitig**.
- Warum also nicht `(g x)` und `(h y)` **parallel** berechnen?

Die Folie zeigt dazu einen **Intel Core i7 (Nehalem), 4-core CPU (2008)**, auf dem die vier Kerne markiert sind.

> [!tip] Zusatz: Warum braucht man dafür Leibniz?
> Wenn `g` und `h` nur von ihren Argumenten abhängen, ist egal, welcher Aufruf zuerst fertig wird. Das Ergebnis von `(f (g x) (h y))` bleibt gleich.
>
> Ohne Leibniz ([[Programmieren ohne Leibniz]]) könnte `g` etwas verändern, das `h` liest (Systemzustand, vorherige Aufrufe). Dann hinge das Ergebnis von der Reihenfolge ab und paralleles Rechnen wäre unsicher. Das ist meine Folgerung aus Folie 27, die Folie 29 nennt es nicht.

## Siehe auch

- [[Programmieren mit Funktionen]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Einführung/01 - Einführung]]
