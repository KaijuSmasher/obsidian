---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen]
vorlesung: 02-Boolesche-Algebra
folien: 47
---

# Unvollständig definierte Funktionen

Nicht immer sind Schaltfunktionen **vollständig ausdekodiert**: Es gibt Fälle, in denen nicht für jede Kombination der Eingangsvariablen ein Ausgangswert definiert ist.

Ist der Wert der Ausgangsvariablen **egal** (kann $0$ oder $1$ sein), spricht man von einem **Don't-care-Term**, geschrieben $*$.

## Beispiel (Folie 47)

| Nr. | $x_3$ | $x_2$ | $x_1$ | $f$ |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 2 | 0 | 1 | 0 | 1 |
| 3 | 0 | 1 | 1 | 0 |
| 4 | 1 | 0 | 0 | 1 |
| 5 | 1 | 0 | 1 | $*$ |
| 6 | 1 | 1 | 0 | $*$ |
| 7 | 1 | 1 | 1 | $*$ |

Die Zeilen 0–4 stimmen mit der Paritätsfunktion aus [[Boolesche Funktionen]] überein, in den Zeilen 5–7 ist der Wert frei.

> [!tip] Zusatz: Wozu braucht man das?
> - Typisches Beispiel: Ein Eingang ist ein **BCD-Code** (Dezimalziffer in 4 Bit). Die Belegungen $1010$ bis $1111$ (10 bis 15) kommen nie vor, der Ausgang dafür ist egal.
> - Man darf jedes $*$ **frei als $0$ oder $1$ wählen**, und zwar so, dass der Ausdruck möglichst einfach wird. Das ist ein wichtiges Werkzeug bei der **Minimierung** (nächstes Kapitel 2.3), weil DNF und KNF allein ja nicht minimal sind ([[02.2 - Normalformen]]).
> - Beim Aufstellen einer DNF/KNF nach [[DNF und KNF aus der Funktionstabelle]] sind $*$-Zeilen nicht automatisch $1$ oder $0$, sondern du entscheidest je nach Vereinfachung.
