---
tags: [Info-1, scheme, kommentare]
vorlesung: 01-Scheme
folien: 19-20
---

# Scheme: Kommentare

Der Code von `parking-lot-cars` ([[Parkplatz-Puzzle in Scheme]]) lässt, etwa für ein Teammitglied, **Fragen offen**:

- Was genau ist `n`?
- Was genau bezeichnet der Parameter `r`?
- Wie ist das Ergebnis der Funktion zu interpretieren?

**Kommentare** annotieren Programme, um solche Fragen zu klären.

> [!note] Kommentar (Folie 19)
> In Scheme leitet ein **Semikolon** `;` einen Kommentar ein. Er reicht bis zum Zeilenende und wird vom System bei der Auswertung **vollkommen ignoriert**.

> [!warning] Regel der Folie
> Funktionsdefinitionen sollte eine **ein- bis zweizeilige Kurzbeschreibung** als Kommentar vorangestellt werden.

> [!tip] Zusatz: Beispiel
> ```scheme
> ; Anzahl der PKWs auf einem Parkplatz mit n Fahrzeugen und r Rädern
> (define parking-lot-cars
>   (lambda (n r)
>     (/ (- r (* 2 n)) 2)))
> ```
> Die Beschreibung ist mein Beispiel, auf der Folie steht sie nicht.

## Zwei Zitate (Folie 20)

- **Harold Abelson und Gerald Sussman** (*Structure and Interpretation of Computer Programs*): Programme müssen vor allem für Menschen zum Lesen geschrieben werden, und nur nebenbei für Maschinen zum Ausführen.
- **Tom van Vleck** sagt, echte Programmierer kommentierten ihren Code nicht: Was schwer zu schreiben war, solle auch schwer zu verstehen sein.

> [!tip] Zusatz: Einordnung
> Das zweite Zitat ist ironisch gemeint und steht als Gegenpol zum ersten. Das ist meine Deutung, die Folie sagt es nicht.

## Siehe auch

- [[Konstruktionsanleitung für Funktionen]]: die Kurzbeschreibung ist dort Schritt 1
- [[Signaturen]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
