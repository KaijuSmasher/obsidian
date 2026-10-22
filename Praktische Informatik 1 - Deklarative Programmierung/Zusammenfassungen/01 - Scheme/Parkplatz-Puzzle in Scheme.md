---
tags: [Info-1, scheme, modellierung]
vorlesung: 01-Scheme
folien: 18
---

# Beispiel: Das Parkplatz-Puzzle in Scheme

Erinnerung an [[Parkplatz-Puzzle]]: Die Anzahl der PKWs $P(n,r)$ auf einem Parkplatz mit $n$ Fahrzeugen und $r$ Rädern ist

$$P(n,r) = \frac{r - 2 \times n}{2}$$

Eine mögliche Definition der Funktion $P$ in Scheme (Folie 18):

```scheme
(define parking-lot-cars
  (lambda (n r)
    (/ (- r (* 2 n))
       2)))
```

Anwendung in der REPL:

```scheme
(parking-lot-cars 6 16)   ; 6 Fahrzeuge mit 16 Rädern
⇝ 2                       ; 2 Autos + 4 Motorräder
```

> [!tip] Zusatz: Probe und Vertragsbedingungen
> - Probe: $P(6,16) = (16 - 12)/2 = 2$ PKWs, also $6 - 2 = 4$ Motorräder, und $2 \cdot 4 + 4 \cdot 2 = 16$ Räder ✓.
> - Die Funktion **prüft ihre Vertragsbedingungen nicht** ([[Verträge und Vertragsbedingungen]]). Die Gegenbeispiele liefern einfach Werte: `(parking-lot-cars 3 9)` ⇝ `3/2` (ein exakter Bruch, siehe [[Literale]]), `(parking-lot-cars 5 2)` ⇝ `-4`, `(parking-lot-cars 2 10)` ⇝ `3`.
> - Eine Signatur mit Resultat `natural` ([[Signaturen]]) würde `3/2` und `-4` melden, `3` aber nicht, denn $3$ ist eine natürliche Zahl. Die Bedingung $r \le 4n$ fängt sie also nicht.

## Siehe auch

- [[Parkplatz-Puzzle]]
- [[Verträge und Vertragsbedingungen]]
- [[Lambda-Abstraktion]]
- [[Funktionsanwendung Applikation]]
- [[01 - Scheme]]
