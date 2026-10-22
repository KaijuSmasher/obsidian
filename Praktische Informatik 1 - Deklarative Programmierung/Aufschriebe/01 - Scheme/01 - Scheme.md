---
tags: [Info-1, scheme, index]
vorlesung: 01-Scheme
folien: 1-24
---

# Info-1 01 Scheme: Ausdrücke, Auswertung und Abstraktion (Folien 1–24)

Vorlesung *Informatik 1* (Prof. Dr. Torsten Grust, WS 26/27, Universität Tübingen). Folie 1 ist nur die Titelfolie. Davor: [[00 - Einführung]]. Die Folienzahlen in den Notizen sind die auf den Folien aufgedruckten Seitenzahlen.

Der rote Faden: Ausdrücke werden **ausgewertet** (⇝), Werte bekommen **Namen**, und mit **lambda** abstrahiert man von konkreten Werten. Am Ende steht eine erste **Konstruktionsanleitung** für Funktionen.

## Werkzeug

- [[DrRacket und die REPL]]

## Ausdrücke und Werte

- [[Präfixnotation]]
- [[Ausdrücke und Auswertung]]
- [[Zusammengesetzte Ausdrücke]]
- [[Literale]]
- [[Exakte und inexakte Zahlen]]

## Namen und Abstraktion

- [[Namen und Bindungen]]
- [[Spezialformen]]
- [[Lambda-Abstraktion]]
- [[Funktionsanwendung Applikation]]
- [[Parkplatz-Puzzle in Scheme]]

## Gute Programme

- [[Kommentare]]
- [[Signaturen]]
- [[Testfälle]]
- [[Konstruktionsanleitung für Funktionen]]

> [!warning] Klausurrelevant (mein Vorschlag, die Folien sagen dazu nichts)
> Vermutlich wichtig: Ausdrücke **Schritt für Schritt auswerten** können ([[Zusammengesetzte Ausdrücke]], [[Funktionsanwendung Applikation]]), die **Konstruktionsanleitung** anwenden ([[Konstruktionsanleitung für Funktionen]]) und den Unterschied **exakt vs. inexakt** erklären ([[Exakte und inexakte Zahlen]]).

## Zusammenfassung der Folien

- Scheme wird in **DrRacket** programmiert. Das **Definitionsfenster** (oben) enthält das Programm, das **Interaktionsfenster** (unten) ist eine **REPL** (read, eval, print).
- Funktionen werden **ausschließlich in Präfixnotation** angewendet: `(f argument₁ … argumentₙ)`.
- **Auswertung** ⇝ (auch Reduktion, Evaluation) liefert aus Ausdrücken Werte, bei zusammengesetzten Ausdrücken **von innen nach außen**. **Literale** sind nicht weiter reduzierbar.
- **Exakte** Zahlen rechnen genau, **inexakte** (`#i…`) sind effizient, aber ungenau: `(= (+ #i0.1 #i0.2) 0.3)` ergibt `#f`.
- `(define id e)` **bindet** einen Namen an einen Wert. `define` ist eine **Spezialform** und hat einen Effekt statt eines Werts.
- `(lambda (p₁ p₂ …) e)` ist eine **Lambda-Abstraktion** (Funktion). Bei der **Anwendung** werden die Parameter im Rumpf durch die Argumente ersetzt.
- **Kommentare** (`;`), **Signaturen** (`:`) und **Testfälle** (`check-expect`) machen Funktionen verständlich und überprüfbar.
- **Konstruktionsanleitung:** Kurzbeschreibung, Signatur, Testfälle, Definition, Rumpf programmieren. Sie wird im Semester verfeinert.
