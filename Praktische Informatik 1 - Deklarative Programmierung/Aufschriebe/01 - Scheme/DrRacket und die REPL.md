---
tags: [Info-1, scheme, drracket, werkzeuge]
vorlesung: 01-Scheme
folien: 2-3, 6, 12
---

# DrRacket und die REPL

In der Vorlesung wird die Programmiersprache **Scheme** eingesetzt. Die Programmierumgebung dafür ist **DrRacket** (Version 9.3), frei verfügbar für macOS, Linux und Windows. Download: http://tiny.cc/Racket

## Einrichtung (Folie 2)

1. Help → *Deutsche Benutzeroberfläche für Racket*
2. Racket neu starten
3. Sprache → *Sprache auswählen…* → **SdP! - Anfänger** → OK
4. Sprache → *Teachpack hinzufügen* → `image.rkt` → OK

> [!tip] Zusatz: Wozu das Teachpack?
> Mit `image.rkt` gibt es **Bilder** als Werte (Literal-Typ "Bilder", siehe [[Literale]]). Das ist meine Deutung, die Folie nennt den Zweck nicht. Die Sprache heißt in der Statuszeile auf Folie 3 *Schreibe Dein Programm! - Anfänger*.

## Die zwei Fenster (Folie 3)

| Fenster | Lage | Zweck |
|---|---|---|
| **Definitionsfenster** | oben | das Programm (Definitionen und Ausdrücke) |
| **Interaktionsfenster** | unten | die REPL, Eingabeprompt `>` |

In der Werkzeugleiste stehen außerdem *Syntaxprüfung*, *Stepper*, *Start* und *Stop*.

> [!tip] Zusatz: Stepper
> Der Stepper zeigt vermutlich die Auswertung Schritt für Schritt, also genau die Reduktionsketten ⇝ aus [[Zusammengesetzte Ausdrücke]]. Die Folie nennt ihn nur in der Werkzeugleiste.

## Interaktionsfenster ≡ REPL (Folie 6)

> [!note] REPL
> Das Interaktionsfenster realisiert einen interaktiven **read-eval-print loop**:
> 1. **read:** liest einen Ausdruck,
> 2. **eval:** wertet ihn mittels ⇝ aus ([[Ausdrücke und Auswertung]]),
> 3. **print:** gibt den resultierenden Wert aus.

## Komplexere Programme im Definitionsfenster (Folie 12)

Sobald Programme komplexer werden und mehrere Bindungen mit `define` enthalten ([[Namen und Bindungen]]), gehören sie ins **Definitionsfenster**:

1. Programm im Definitionsfenster konstruieren.
2. Ausführen: Racket → Start, oder der Button *Start*, oder ⌘R (gleichwertig).
3. Die Werte der reduzierten Ausdrücke erscheinen in der REPL.

Alle gebundenen Namen sind danach auch in der REPL verfügbar. Gespeichert wird mit Datei → *Definitionen speichern* (⌘S) in einer Racket-Datei (Endung `.rkt`).

> [!tip] Zusatz: Windows und Linux
> ⌘ ist die Mac-Taste. Auf Windows und Linux ist das Kürzel üblicherweise mit Strg statt ⌘ belegt (also Strg+R, Strg+S).

## Siehe auch

- [[Ausdrücke und Auswertung]]
- [[Namen und Bindungen]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
