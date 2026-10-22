---
tags: [Info-1, Funktionen, vertraege, abstraktion]
vorlesung: 00-Einführung
folien: 21
---

# Verträge und Vertragsbedingungen

Mit der Funktion $P(n,r)$ aus dem [[Parkplatz-Puzzle]] hat man **abstrahiert** und sich damit vom tatsächlichen Parkplatz entfernt, bis man in der Realität geltende Einschränkungen aus den Augen verloren hat.

$P(n,r)$ erfüllt seine Aufgabe nur, **sofern man sich bei der Anwendung einschränkt**:

> [!note] Vertragsbedingungen
> $$r \text{ gerade} \quad\text{und}\quad 2n \le r \le 4n$$

Die Funktion kommt also **quasi mit Vertragsbedingungen**. Hält man sich als Aufrufer daran, garantiert die Funktion ein sinnvolles Ergebnis.

> [!tip] Zusatz: Woher kommen die Bedingungen?
> - **$r$ gerade:** Jedes Fahrzeug hat 2 oder 4 Räder, also ist $r$ immer gerade. Außerdem ist $P = \tfrac{1}{2}(r - 2n)$ nur dann ganzzahlig, wenn $r$ gerade ist.
> - **$2n \le r$:** Mindestens 2 Räder pro Fahrzeug (nur Motorräder). Sonst wäre $P < 0$.
> - **$r \le 4n$:** Höchstens 4 Räder pro Fahrzeug (nur PKWs). Sonst wäre $P > n$, also $M < 0$.
>
> Die drei Bedingungen sind **notwendig und hinreichend**: Gelten sie, ist $P$ ganzzahlig mit $0 \le P \le n$, also ein sinnvolles Ergebnis. Gilt eine nicht, kann es keinen passenden Parkplatz geben.
>
> Die Gegenbeispiele aus [[Parkplatz-Puzzle]] verletzen genau je eine Bedingung:
>
> | Aufruf | verletzt |
> |---|---|
> | $P(3,9)$ | $r$ gerade ($9$ ist ungerade) |
> | $P(5,2)$ | $2n \le r$ ($10 \le 2$ gilt nicht) |
> | $P(2,10)$ | $r \le 4n$ ($10 \le 8$ gilt nicht) |

## Siehe auch

- [[00 - Einführung]]
- [[Programmieren mit Funktionen]]
