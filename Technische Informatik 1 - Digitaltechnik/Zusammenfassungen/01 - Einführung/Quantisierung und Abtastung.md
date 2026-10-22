---
tags: [TI-1, Digitaltechnik, signale]
vorlesung: 01-Einführung
folien: 22-23
---

# Quantisierung und Abtastung

Umwandlung eines analogen in ein digitales Signal ([[Analog vs digital]]) braucht zwei Schritte.

| Schritt | Was passiert | Folge |
|---|---|---|
| **Quantisierung** (Wertdiskretisierung) | Jedem Wertintervall wird ein digitaler Wert zugeordnet (typischerweise linear oder logarithmisch). Nah beieinander liegende analoge Werte werden auf den gleichen digitalen Wert abgebildet ("kodiert"). | Quantisierungsfehler, maximal so groß wie ein Intervall. |
| **Abtastung / Sampling** (Zeitdiskretisierung) | Signalwerte werden zu diskreten, meist äquidistanten Zeitpunkten registriert. | Aus dem kontinuierlichen Signal wird eine Folge von Werten. |

## Abtastrate und Abtastfrequenz

Bei äquidistanter Abtastung heißt die Zeitspanne $t$ **Abtastrate** (Sample Rate), ihr Kehrwert **Abtastfrequenz**:

$$f_s = \frac{1}{t}$$

> [!tip] Zusatz
> - **Nyquist-Shannon-Abtasttheorem**: Ein Signal ist aus seinen Abtastwerten nur rekonstruierbar, wenn $f_s > 2 \cdot f_{max}$. Sonst entsteht **Aliasing**.
> - Wird gerundet, ist der Quantisierungsfehler höchstens ein *halbes* Intervall.

## Siehe auch

- [[Binärcodierung und Signalpegel]]
