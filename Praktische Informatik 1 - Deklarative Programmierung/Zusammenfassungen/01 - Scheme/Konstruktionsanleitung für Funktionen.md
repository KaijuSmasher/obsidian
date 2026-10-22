---
tags: [Info-1, scheme, konstruktionsanleitung, klausur]
vorlesung: 01-Scheme
folien: 24
---

# Scheme: Konstruktionsanleitung für Funktionen

> [!note] Folie 24
> Zusammen ergeben die Elemente von Scheme eine erste **Konstruktionsanleitung für eine Funktion $f$**.

```scheme
; …                                  ; ① Kurzbeschreibung (Kommentar)
(: f (… -> …))                       ; ② Funktionssignatur
(check-expect (f …) …)               ; ③ Testfälle für f
  ⋮
(check-within (f …) …)
(define f                            ; ④ Definition von f
  (lambda (p₁ p₂ …)
    …))                              ; ⑤ Funktionsrumpf programmieren
```

| Schritt | Inhalt | Notiz |
|---|---|---|
| ① | Kurzbeschreibung (Kommentar) | [[Kommentare]] |
| ② | Funktionssignatur | [[Signaturen]] |
| ③ | Testfälle für $f$ | [[Testfälle]] |
| ④ | Definition von $f$ | [[Namen und Bindungen]], [[Lambda-Abstraktion]] |
| ⑤ | Funktionsrumpf programmieren | |

Im Laufe des Semesters wird diese Konstruktionsanleitung **systematisch verfeinert**.

> [!tip] Zusatz: Alles zusammen am Beispiel
> ```scheme
> ; Anzahl der PKWs auf einem Parkplatz mit n Fahrzeugen und r Rädern
> (: parking-lot-cars (natural natural -> natural))
> (check-expect (parking-lot-cars 6 16) 2)
> (check-expect (parking-lot-cars 2 4) 0)
> (check-expect (parking-lot-cars 2 8) 2)
> (define parking-lot-cars
>   (lambda (n r)
>     (/ (- r (* 2 n)) 2)))
> ```
> Das ist [[Parkplatz-Puzzle in Scheme]] nach der Anleitung. Das Beispiel ist mein Zusammenbau, die Folie zeigt nur das leere Schema.

## Siehe auch

- [[Programmieren mit Funktionen]]: die Grundidee "Funktion konstruieren, dann anwenden"
- [[01 - Scheme]]
