---
tags: [TI-1, Digitaltechnik, einheiten, klausur]
vorlesung: 01-Einführung
folien: 31
---

# Einheiten der Digitaltechnik

Vielfache von Bits und Bytes ([[Codierung Grundbegriffe]]) sind Zweierpotenzen:

| Präfix | Wert | Bytes |
|---|---|---|
| 1 K (Kilo) | $2^{10}$ | 1.024 |
| 1 M (Mega) | $2^{20}$ | 1.048.576 |
| 1 G (Giga) | $2^{30}$ | 1.073.741.824 |
| 1 T (Tera) | $2^{40}$ | 1.099.511.627.776 |

Außerdem: $1\,\text{Byte} = 8\,\text{Bit}$.

## Dezimal im Alltag

Im Alltag gilt $1\,\text{Kilo} = 10^3$, $1\,\text{Mega} = 10^6$ usw. Der "Rundungsfehler" wächst mit der Größe:

| Einheit | Dezimal | Binär | Abweichung |
|---|---|---|---|
| Kilobyte (kB) | $10^3$ Byte | $2^{10}$ Byte | 2,4 % |
| Megabyte (MB) | $10^6$ Byte | $2^{20}$ Byte | 4,9 % |
| Gigabyte (GB) | $10^9$ Byte | $2^{30}$ Byte | 7,4 % |
| Terabyte (TB) | $10^{12}$ Byte | $2^{40}$ Byte | 10,0 % |
| Petabyte (PB) | $10^{15}$ Byte | $2^{50}$ Byte | 12,6 % |
| Exabyte (EB) | $10^{18}$ Byte | $2^{60}$ Byte | 15,3 % |
| Zettabyte (ZB) | $10^{21}$ Byte | $2^{70}$ Byte | 18,1 % |

> [!tip] Zusatz
> Dafür gibt es die IEC-Präfixe **KiB, MiB, GiB, TiB** (Basis 2), während kB, MB, GB (Basis 10) bedeuten. Deshalb zeigt eine "1-TB"-Festplatte im Betriebssystem oft nur etwa 931 GiB an.

> [!warning] Klausur
> Zweierpotenzen bis $2^{10}$ auswendig können, siehe [[Zahlensysteme umrechnen]].
