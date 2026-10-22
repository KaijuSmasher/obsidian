---
tags: [Info-1, scheme, spezialform, klausur]
vorlesung: 01-Scheme
folien: 11, 15, 21, 23
---

# Spezialformen

Mehrere Bausteine dieser Vorlesung werden auf den Folien ausdrücklich **Spezialform** genannt. Dieser Überblick sammelt sie.

| Spezialform | Folie | Wert oder Effekt |
|---|---|---|
| `(define id e)` | 11 | **Effekt:** bindet den Namen $id$ an den Wert von $e$ ([[Namen und Bindungen]]) |
| `(lambda (p₁ p₂ …) e)` | 15 | **Wert:** `#<function>` ([[Lambda-Abstraktion]]) |
| `(: id sig)` | 21 | **Effekt:** Signaturüberprüfung ([[Signaturen]]) |
| `(check-expect e₁ e₂)` | 23 | **Effekt:** testet, ob $e_1$ den erwarteten Wert $e_2$ ergibt ([[Testfälle]]) |

> [!tip] Zusatz: Was "speziell" daran ist
> Bei einer normalen Funktionsanwendung werden zuerst alle Argumente ausgewertet ([[Zusammengesetzte Ausdrücke]]). Das passt für Spezialformen nicht immer:
> - Bei `(define x (+ 1 2))` darf `x` nicht ausgewertet werden, der Name ist ja noch gar nicht gebunden.
> - Bei `lambda` soll der Rumpf nicht ausgewertet werden, sondern erst bei der Anwendung ([[Funktionsanwendung Applikation]]).
>
> Das ist meine Erklärung, die Folien sagen nur, dass es Spezialformen sind.

## Siehe auch

- [[Namen und Bindungen]]
- [[Lambda-Abstraktion]]
- [[Signaturen]]
- [[Testfälle]]
- [[Praktische Informatik 1 - Deklarative Programmierung/Aufschriebe/01 - Scheme/01 - Scheme]]
