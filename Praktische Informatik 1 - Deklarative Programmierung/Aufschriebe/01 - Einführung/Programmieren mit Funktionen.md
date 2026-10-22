---
tags: [Info-1, Funktionen, scheme]
vorlesung: 00-Einführung
folien: 22-23
---

# Programmieren mit Funktionen

Funktionen gehören zu den zentralen Bausteinen der Mathematik:

$$f(x_1, x_2, \dots, x_n)$$

**In Scheme** übernimmt man diese Idee und nutzt Funktionen als Bausteine, aus denen man **ganze Programme** konstruiert:

```scheme
(f x₁ x₂ ... xₙ)
```

## Die Grundidee (Folie 23)

Diese einfache Idee begleitet durch das **gesamte Semester**:

1. **Konstruiere** (oder nutze die eingebaute) Funktion $f$.
2. **Wende** $f$ auf die benötigte Anzahl von Argumenten **an**.

Beispiele der Folie:

```scheme
(+ 40 2)
(odd? 42)
```

> [!tip] Zusatz: Schreibweise
> In Scheme steht die Funktion **immer vorne**, dann folgen die Argumente, alles in Klammern (Präfixnotation). Auch $+$ ist eine Funktion mit zwei Argumenten: $(+\ 40\ 2)$ entspricht $40 + 2 = 42$. Das Ergebnis von $(\text{odd?}\ 42)$ ist falsch, weil $42$ gerade ist. Die Folie nennt die Ergebnisse nicht.

## Siehe auch

- [[Leibniz-Prinzip]]: warum man sich auf Funktionen verlassen kann
- [[Parkplatz-Puzzle]]: ein Beispiel für eine mathematische Funktion
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Einführung/01 - Einführung]]
