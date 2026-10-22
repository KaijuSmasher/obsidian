---
tags: [Info-1, scheme, lambda, auswertung, klausur]
vorlesung: 01-Scheme
folien: 17
---

# Scheme: Funktionsanwendung (Applikation)

> [!note] Applikation (Folie 17)
> Die **Anwendung** (auch: **Applikation**) einer Lambda-Abstraktion führt zur **Ersetzung** aller Vorkommen der Parameter $p_i$ im Rumpf $e$ durch die angegebenen **Argumente**.
> Die Anwendung von $f$ auf $x$ wird wie gewohnt mittels **Juxtaposition** notiert: `(f x)`.

Beispiel der Folie (Funktion `(lambda (days) …)`, Argument `365`):

```scheme
((lambda (days) (* days (* 135 minutes-in-a-day))) 365)
① ⇝ (* 365 (* 135 minutes-in-a-day))   ; days durch 365 ersetzt
② ⇝ (* 365 (* 135 1440))
③ ⇝ (* 365 194400)
④ ⇝ 70956000
```

> [!tip] Zusatz: Die Schritte im Einzelnen
> - **Schritt ①** ist die Ersetzung des Parameters `days` durch das Argument `365`.
> - **Schritt ②** ersetzt den Namen `minutes-in-a-day` durch seinen Wert $1440$ ([[Namen und Bindungen]]).
> - **Schritte ③ und ④** sind normale Reduktionen von innen nach außen ([[Zusammengesetzte Ausdrücke]]): $135 \cdot 1440 = 194400$ und $365 \cdot 194400 = 70\,956\,000$.
>
> Dieses "Parameter durch Argument ersetzen" nennt man oft **Substitutionsmodell**. Der Begriff steht nicht auf der Folie.

## Siehe auch

- [[Lambda-Abstraktion]]
- [[Zusammengesetzte Ausdrücke]]
- [[Parkplatz-Puzzle in Scheme]]: noch ein Beispiel für Funktionsanwendung
- [[01 - Scheme]]
