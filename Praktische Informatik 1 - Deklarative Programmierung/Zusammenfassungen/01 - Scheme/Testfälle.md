---
tags: [Info-1, scheme, testfaelle, klausur]
vorlesung: 01-Scheme
folien: 23
---

# Scheme: Testfälle

**Testfälle** dokumentieren das erwartete Ergebnis eines Ausdrucks nach Auswertung:

> [!note] check-expect (Folie 23)
> `(check-expect e₁ e₂)` ; ergibt $e_1$ den erwarteten Wert $e_2$?

`(check-expect …)` ist eine **Spezialform** ([[Spezialformen]]) mit folgendem Effekt:

1. Werte den Ausdruck $e_1$ aus,
2. teste, ob der erhaltene Wert unserer Erwartung (= Wert des Ausdrucks $e_2$) entspricht,
3. protokolliere positive und negative Testergebnisse.

> [!warning] Regel der Folie
> Stelle Funktionsdefinitionen direkt **mehrere Testfälle** für *interessante* Argumente (z. B. **Randfälle**) voran.

> [!tip] Zusatz: Beispiele
> ```scheme
> (check-expect (parking-lot-cars 6 16) 2)   ; Beispiel von Folie 18
> (check-expect (parking-lot-cars 2 4) 0)    ; Randfall r = 2n: nur Motorräder
> (check-expect (parking-lot-cars 2 8) 2)    ; Randfall r = 4n: nur PKWs
> ```
> Die Randfälle entsprechen genau den Grenzen der Vertragsbedingung $2n \le r \le 4n$ ([[Verträge und Vertragsbedingungen]]). Die Beispiele sind meine, nicht von der Folie.
>
> Auf Folie 24 steht auch `check-within`, ohne Erklärung. Soweit ich weiß, nimmt es eine zusätzliche Toleranz, z. B. `(check-within e₁ e₂ 0.001)`, und ist für inexakte Zahlen gedacht ([[Exakte und inexakte Zahlen]]).

## Siehe auch

- [[Konstruktionsanleitung für Funktionen]]: Testfälle sind dort Schritt 3
- [[Signaturen]]
- [[Parkplatz-Puzzle in Scheme]]
- [[01 - Scheme]]
