---
tags: [Info-1, Funktionen, leibniz, klausur]
vorlesung: 00-Einführung
folien: 26-27
---

# Programmieren "ohne Leibniz"

Man **kann** ohne das [[Leibniz-Prinzip]] programmieren. Vielleicht erstaunlich: Die weitaus meisten Programmiersprachen sichern den Entwicklern das Prinzip **nicht** zu.

> [!warning] Was verloren geht (Folie 26)
> Die Vorhersagbarkeit des Verhaltens einer Funktion allein mittels ihres Arguments:
> $$x = y \;\;\text{und}\;\; f(x) = z \;\;\not\Rightarrow\;\; f(y) = z$$

## Konsequenzen (Folie 27)

Viele intuitive Annahmen gelten bei der Programmkonstruktion im Allgemeinen **nicht mehr**. Beispiel:

$$f(x) + f(x) \ne 2 \times f(x)$$

Das Verhalten von $f$ kann von einer **unübersichtlichen Vielzahl impliziter Parameter** abhängen:

- vorhergegangene Anwendungen weiterer Funktionen (inkl. $f$ selbst)
- Systemzustand
- Zeit
- Eingaben des Users
- Mondphase, ...

> [!tip] Zusatz: Beispiel
> Eine Funktion $f$, die bei jedem Aufruf einen internen Zähler erhöht und den neuen Stand zurückgibt, liefert beim ersten Aufruf $1$, beim zweiten $2$. Dann ist $f(x) + f(x) = 1 + 2 = 3$, aber $2 \times f(x) = 2 \times 1 = 2$. Das Argument $x$ hat sich nicht geändert, das Ergebnis schon.
>
> Das ist genau die Formel von Folie 26: Es gilt $x = y$ (dasselbe Argument) und $f(x) = 1$, aber $f(y) = 2$. Damit ist es ein **Gegenbeispiel** zum Leibniz-Prinzip. Ein Zähler als Beispiel steht nicht auf der Folie.

## Siehe auch

- [[Programmierfehler Bugs]]
- [[Funktionen und Parallelität]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Einführung/01 - Einführung]]
