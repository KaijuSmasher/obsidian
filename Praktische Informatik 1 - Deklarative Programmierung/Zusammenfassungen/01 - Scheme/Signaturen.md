---
tags: [Info-1, scheme, signaturen, klausur]
vorlesung: 01-Scheme
folien: 21-22
---

# Scheme: Signaturen

## Signatur eines Namens (Folie 21)

> [!note] Signatur
> Eine **Signatur** prüft, ob ein Name $id$ an einen Wert einer angegebenen **Sorte** $sig$ gebunden wird:
> `(: id sig)`

`(: …)` ist eine **Spezialform** mit Effekt: **Signaturüberprüfung** ([[Spezialformen]]).

Racket kennt eine Reihe eingebauter Signaturen:

| Signatur $sig$ | akzeptierte Werte |
|---|---|
| `natural` | $\mathbb{N}_0$ (natürliche Zahlen mit $0$) |
| `integer` | $\mathbb{Z}$ (ganze Zahlen) |
| `rational` | $\mathbb{Q}$ (rationale Zahlen, Brüche) |
| `real` | $\mathbb{R}$ (reelle Zahlen) |
| `number` | $\mathbb{C}$ (komplexe Zahlen, umfasst $\mathbb{N}_0, \mathbb{Z}, \mathbb{Q}, \mathbb{R}$) |
| `boolean` | `#t`, `#f` (Wahrheitswerte, Booleans) |
| `string` | Zeichenketten |
| `image` | Bilder |

> [!tip] Zusatz: Reihenfolge der Zahlsorten
> Die Zahlsorten sind ineinander enthalten: $\mathbb{N}_0 \subset \mathbb{Z} \subset \mathbb{Q} \subset \mathbb{R} \subset \mathbb{C}$. Ein Wert, der zu `natural` passt, passt also auch zu `integer`, `rational`, `real` und `number`.

## Signaturen für Funktionen (Folie 22)

**Funktionssignaturen** der Form `(… -> …)` legen Signaturen sowohl für die Parameter $p_1, p_2, \dots, p_n$ als auch für den **Resultatwert** einer Funktion fest:

```scheme
(sig₁ sig₂ … sigₙ -> sig-result)
```

Signaturen werden **bei jeder Anwendung** der zugehörigen Funktion erneut überprüft:

- Passt das $i$-te Argument zur Signatur $sig_i$ und
- passt das Resultat der Funktion zu $sig\text{-}result$?

> [!warning] Achtung (Folie 22)
> Signaturverletzungen werden von DrRacket **protokolliert**, aber das Programm wird **weiter ausgeführt**.

> [!tip] Zusatz: Beispiel
> ```scheme
> (: parking-lot-cars (natural natural -> natural))
> ```
> Das ist mein Beispiel für [[Parkplatz-Puzzle in Scheme]]. Es prüft, dass beide Argumente und das Ergebnis natürliche Zahlen sind. Die Vertragsbedingung $r \le 4n$ ([[Verträge und Vertragsbedingungen]]) erfasst es nicht.

## Siehe auch

- [[Konstruktionsanleitung für Funktionen]]: die Signatur ist dort Schritt 2
- [[Literale]]
- [[Testfälle]]
- [[01 - Scheme]]
