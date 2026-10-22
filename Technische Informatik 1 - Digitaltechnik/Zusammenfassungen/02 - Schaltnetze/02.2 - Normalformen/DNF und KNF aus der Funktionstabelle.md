---
tags: [TI-1, Digitaltechnik, schaltnetze, normalformen, klausur]
vorlesung: 02-Boolesche-Algebra
folien: 44-46
---

# DNF und KNF aus der Funktionstabelle

> [!warning] Klausur
> Das ist die zentrale Rechenaufgabe zu diesem Kapitel.

## Rezept

**DNF (Zeilen mit $y = 1$):**

1. Nimm jede Zeile mit Funktionswert **1**.
2. Verknüpfe in dieser Zeile **alle** Eingangsvariablen mit $\land$. Variablen mit Wert **0** werden **negiert**.
3. Verknüpfe alle so entstandenen Minterme mit $\lor$.

**KNF (Zeilen mit $y = 0$):**

1. Nimm jede Zeile mit Funktionswert **0**.
2. Verknüpfe in dieser Zeile **alle** Eingangsvariablen mit $\lor$. Variablen mit Wert **1** werden **negiert**.
3. Verknüpfe alle so entstandenen Maxterme mit $\land$.

> [!tip] Merkhilfe
> - **DNF:** Eins-Zeilen, UND-Terme, **0 wird negiert**.
> - **KNF:** Null-Zeilen, ODER-Terme, **1 wird negiert**.
>
> Der Maxterm sieht aus wie der Minterm mit vertauschten Operatoren und umgekehrten Negationen.

## Beispiel (Folie 44)

Die Zeilennummer ist die Binärzahl $c\,b\,a$ (mit $a$ als niederwertigem Bit, siehe [[Zahlensysteme umrechnen]]).

| Nr. | $c$ | $b$ | $a$ | $y$ | Minterm | Maxterm |
|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | **1** | $\overline{a} \land \overline{b} \land \overline{c}$ | |
| 1 | 0 | 0 | 1 | **0** | | $\overline{a} \lor b \lor c$ |
| 2 | 0 | 1 | 0 | **0** | | $a \lor \overline{b} \lor c$ |
| 3 | 0 | 1 | 1 | **1** | $a \land b \land \overline{c}$ | |
| 4 | 1 | 0 | 0 | **1** | $\overline{a} \land \overline{b} \land c$ | |
| 5 | 1 | 0 | 1 | **0** | | $\overline{a} \lor b \lor \overline{c}$ |
| 6 | 1 | 1 | 0 | **0** | | $a \lor \overline{b} \lor \overline{c}$ |
| 7 | 1 | 1 | 1 | **1** | $a \land b \land c$ | |

**DNF:**

$$y = (\overline{a}\,\overline{b}\,\overline{c}) \lor (a\,b\,\overline{c}) \lor (\overline{a}\,\overline{b}\,c) \lor (a\,b\,c)$$

**KNF:**

$$y = (\overline{a} \lor b \lor c) \land (a \lor \overline{b} \lor c) \land (\overline{a} \lor b \lor \overline{c}) \land (a \lor \overline{b} \lor \overline{c})$$

> [!tip] Zusatz: Selbstkontrolle
> - Probe: Setze eine Zeile in beide Formeln ein. Zeile 3 ($a = b = 1$, $c = 0$): In der DNF ist der Term $a\,b\,\overline{c} = 1$, also $y = 1$ ✓. In der KNF ist jeder Maxterm $1$ (jeder enthält ein wahres Literal), also $y = 1$ ✓.
> - Anzahl: Die DNF hat so viele Terme wie Einsen in der Tabelle, die KNF so viele wie Nullen. Zusammen sind es immer $2^n$. Eine Funktion mit wenigen Einsen hat also eine kurze DNF, eine mit wenigen Nullen eine kurze KNF.
> - Zeile 4 ist ein guter Fehlerkandidat: $c = 1$, $b = 0$, $a = 0$ ergibt $\overline{a}\,\overline{b}\,c$. Nur $c$ bleibt unnegiert, weil nur $c$ den Wert $1$ hat.

## Deutung (Folie 45)

- Jeder **Minterm** der DNF entspricht einer Zeile mit $y = 1$.
- Jeder **Maxterm** der KNF entspricht einer Zeile mit $y = 0$.

**Herkunft der Bezeichnungen:**

- Eine Funktion aus genau **einem Minterm** ist nur für eine Belegung $1$. Abgesehen von der Nullfunktion hat sie also die **minimale** Anzahl an Einsen. Daher "Min"-Term.
- Eine Funktion aus genau **einem Maxterm** ist nur für eine Belegung $0$. Abgesehen von der Einsfunktion hat sie die **maximale** Anzahl an Einsen. Daher "Max"-Term.

## Siehe auch

- [[Disjunktive Normalform DNF]]
- [[Konjunktive Normalform KNF]]
- [[Äquivalenz von Ausdrücken prüfen]]: DNF und KNF derselben Funktion sind äquivalent
