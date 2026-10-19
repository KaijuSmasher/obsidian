---
tags: [TI-1, Digitaltechnik, hardware]
vorlesung: 01-Einführung
folien: 38-40
---

# Hardware ist anders

## Grobes Verständnis

Hardware besteht aus **Funktionseinheiten** und **Signalen**.

- Signale sind Träger von Information und übertragen Werte zwischen Funktionseinheiten (über elektrische Leitungen).
- Funktionseinheiten verknüpfen Eingangssignale und erzeugen daraus Werte für die Ausgangssignale.
- Beispiel: f1 erzeugt aus s1, s2, s3 das Signal tmp. f2 erzeugt aus tmp und s4 das Signal s5.

## Drei Besonderheiten gegenüber Software

1. **Hardware ist parallel.**
   `y = a & b;` ist in Software ein Befehl, der irgendwann nacheinander abgearbeitet wird. In Hardware existiert das UND-Gatter dauerhaft und arbeitet gleichzeitig mit allen anderen Gattern.
2. **Hardware ist nicht ideal.**
   Ein Inverter (`y = not a`) soll idealerweise abrupt umschalten. Die reale Kennlinie ist ein stetiger Übergang (Folie: Schaltschwelle bei etwa 0,6 V bei 1,2 V Versorgung). Dazwischen ist das Verhalten undefiniert, vergleiche den verbotenen Bereich in [[Binärcodierung und Signalpegel]].
3. **Hardware ist in jeglicher Hinsicht endlich.**
   - Register: endliche Wortbreiten, also nur begrenzt viele darstellbare Werte.
   - Busse: endliche Breite, begrenzte Bandbreite und Übertragungsgeschwindigkeit.
   - Speicher: endliche Kapazität, begrenzte Zugriffsgeschwindigkeit.
   - Prozessoren: begrenzte Ausführungszeit.

> [!tip] Zusatz
> Die Endlichkeit hat direkte Folgen für die Programmierung, zum Beispiel **Überlauf**: Ein `uint8_t` in C++ kann nur 0–255 darstellen, und $255 + 1$ ergibt wieder 0. Zur Wortlänge siehe [[Codierung Grundbegriffe]].

## Siehe auch

- [[Abstraktionsebenen im Hardware-Entwurf]]
