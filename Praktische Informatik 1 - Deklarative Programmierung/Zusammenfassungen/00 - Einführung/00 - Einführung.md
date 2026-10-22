---
tags: [Info-1, Funktionen, scheme, leibniz, index]
vorlesung: 00-Einführung
folien: 17-29
---

# Info-1 00 Funktionen und Leibniz (Folien 17–29)

Teil der Einführung zu *Informatik 1* (Prof. Dr. Torsten Grust, WS 26/27). Folie 17 ist nur eine Titelfolie ohne Inhalt. Der rote Faden: **Funktionen** als Grundbaustein, ihr **verlässliches Verhalten** (Leibniz-Prinzip) und was passiert, wenn dieses Verhalten fehlt.

## Funktionen modellieren

- [[Parkplatz-Puzzle]]
- [[Verträge und Vertragsbedingungen]]

## Funktionen in Programmen

- [[Programmieren mit Funktionen]]

## Verlässliches Verhalten

- [[Leibniz-Prinzip]]
- [[Programmieren ohne Leibniz]]
- [[Programmierfehler Bugs]]
- [[Funktionen und Parallelität]]

> [!warning] Klausurrelevant (mein Vorschlag, die Folien sagen dazu nichts)
> Vermutlich wichtig: das **Leibniz-Prinzip** in Formelform sauber aufschreiben können ([[Leibniz-Prinzip]]) und erklären, **was ohne es verloren geht** ([[Programmieren ohne Leibniz]]). Die Parkplatz-Herleitung ([[Parkplatz-Puzzle]]) ist ein gutes Beispiel für Rechnen mit Gleichungssystemen und für die Frage, **wann** eine Funktion wirklich sinnvolle Ergebnisse liefert ([[Verträge und Vertragsbedingungen]]).

## Zusammenfassung der Folien

- Ein Puzzle (Fahrzeuge und Räder auf einem Parkplatz) beschreibt gleich eine **ganze Familie** von Aufgaben und führt auf Funktionen $P(n,r)$ und $M(n,r)$.
- Die Lösungsfunktion $P(n,r) = \tfrac{1}{2}(r - 2n)$ liefert für manche Eingaben **Unsinn**. Sie hat **Vertragsbedingungen**: $r$ gerade und $2n \le r \le 4n$.
- Funktionen sind zentrale Bausteine der Mathematik. In Scheme bauen wir **ganze Programme aus Funktionsanwendungen** $(f\ x_1\ x_2\ \dots\ x_n)$.
- **Leibniz-Prinzip:** Gleiche Argumente führen immer zum gleichen Ergebnis. Die meisten Programmiersprachen **garantieren das nicht**.
- Ohne Leibniz gilt z. B. $f(x) + f(x) \ne 2 \times f(x)$, und das Verhalten hängt von vielen impliziten Parametern ab.
- Mit Leibniz kann man unabhängige Funktionsaufrufe **parallel** auf mehreren CPU-Kernen berechnen.
