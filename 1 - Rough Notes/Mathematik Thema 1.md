# Logik

## Was ist ein Axiom?

Ein Axiom ist eine Aussage, der durch die Festlegung des Wahrheitswertes 1, also wahr, zugewiesen wurde.

## Grundlegende logische Operatoren

Eine Aussage ist eine Äußerung, der eindeutig ein Wahrheitswert wahr (w) oder falsch (f) zugeordnet ist. Aus Aussagen X und Y können wir durch das Anwenden logischer Operatoren neue Aussagen bilden:

- *Negation* -> Invertiert die Wahrheitswerte
$$\begin{array}{c | c}
X & \neg X \\
\hline
0 & 1 \\
1 & 0 \\ 
\end{array}$$
- *Konjunktion* -> Ist dann wahr, wenn beide Aussagen wahr sind
$$\begin{array}{c | c | c}
X & Y & X \land Y \\
\hline
0 & 0 & 0 \\
0 & 1 & 0 \\
1 & 0 & 0 \\
1 & 1 & 1 \\
\end{array}$$
- *Disjunktion* -> Ist dann wahr, wenn mindestens eine der beiden Aussagen wahr ist
$$\begin{array}{c | c | c}
X & Y & X \lor Y \\
\hline
0 & 0 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1 \\
1 & 1 & 1 \\
\end{array}$$
- *Äquivalenz* -> Ist dann wahr, wenn beide Wahrheitswerte gleich sind
$$\begin{array}{c | c | c}
X & Y & X \Leftrightarrow Y \\
\hline
0 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 0 \\
1 & 1 & 1 \\
\end{array}$$
- *Implikation* -> Wenn X, dann Y 
$$\begin{array}{c | c | c}
X & Y & X \Rightarrow Y \\
\hline
0 & 0 & 1 \\
0 & 1 & 1 \\
1 & 0 & 0 \\
1 & 1 & 1 \\
\end{array}$$
$$\begin{array}{c | c | c | c}
Symbol & Bedeutung & Bezeichnung & Alternative \ Beschreibung \\
\hline
\neg X & nicht \ X & Negation & \\
X \land Y & X \ und \ Y & Konjunktion & \\
X \lor Y & X \ oder \ Y & Disjunktion & \\
X \Rightarrow Y & aus \ X \ folgt \ Y & Implikation & (\neg X) \lor Y \\
X \Leftrightarrow Y & genau \ dann \ X, \ wenn \ Y & Äquivalenz & (X \Rightarrow Y) \land (Y \Rightarrow X) 
\end{array}$$


## Aussageformen mit Quantoren

Eine Aussageform ist eine Äußerung, die eine oder mehrere Variablen enthält und zu einer Aussage (d.h. wahr oder falsch) wird, wenn man zulässige Werte für diese Variablen einsetzt.

$$\begin{array}{l l}
\forall \ : & \text{"für alle"} \\
\exists \ : & \text{"es existiert ein"} \\
\exists! \ : & \text{"es existiert genau ein"} \\
\nexists \ : & \text{"es existiert kein"} \\
\end{array}$$

Ist P eine Aussageform, die von einer Variablen $x$ abhängt, so bedeutet:
$$\begin{array}{l l}
\forall x \ : P(x) \ : & \text{"für alle x gilt P(x)"}\\
\exists x \ : P(x) \ : & \text{"es gibt ein x, so dass P(x) gilt"} \\
\end{array}$$
Mit Hilfe der Quantoren haben wir aus den Aussageformen neue Aussagen gebildet.

## Richtiges Verneinen einer Aussage

$$\neg(\forall x : P(x)) \Leftrightarrow \exists x : (\neg P(x))$$
Die Verneinung der Aussage "für alle x gilt die Aussage P(x)" ist gleichbedeutend mit "es gibt ein x, für das die Aussage P(x) nicht gilt."