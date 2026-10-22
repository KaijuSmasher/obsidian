---
tags: [TI-1, Digitaltechnik, boolesche-algebra]
vorlesung: 02-Boolesche-Algebra
folien: 8-11
---

# Mengenalgebra als Beispiel

Die Axiome aus [[Boolesche Algebra Definition und Axiome]] gelten zum Beispiel für Mengen.

## Korrespondenztabelle

| Boolesche Algebra | Mengenalgebra | Bedeutung |
|---|---|---|
| $V$ | $\wp(T)$ | Potenzmenge einer Grundmenge $T$ |
| $\oplus$ | $\cup$ | Vereinigung |
| $\otimes$ | $\cap$ | Durchschnitt |
| $n$ (Nullelement) | $\emptyset$ | leere Menge |
| $e$ (Einselement) | $T$ | Grundmenge |
| $\overline{a}$ | $\overline{A}$ | Komplementärmenge $T \setminus A$ |

Veranschaulichung durch **Venn-Diagramme** für $A$, $\overline{A}$, $A \cup B$, $A \cap B$.

## Konkretes Beispiel

Grundmenge $T = \{x, y, z\}$. Dann ist die Potenzmenge

$$\wp(T) = \{\emptyset, \{x\}, \{y\}, \{z\}, \{x,y\}, \{x,z\}, \{y,z\}, T\}$$

Mit $A = \{x, y\}$ und $B = \{x, z\}$ gilt $A \cup B = \{x, y, z\}$ und $A \cap B = \{x\}$.

Weil $A \cup B \in \wp(T)$ und $A \cap B \in \wp(T)$ für alle $A, B \in \wp(T)$ gilt, ist die **Abgeschlossenheit** erfüllt.

## Axiome in der Mengenalgebra

| Axiom | Gesetz |
|---|---|
| Kommutativ | $A \cup B = B \cup A$, $A \cap B = B \cap A$ |
| Distributiv | $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$, $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ |
| Neutral | $A \cap T = A$, $A \cup \emptyset = A$ |
| Komplement | $A \cap \overline{A} = \emptyset$, $A \cup \overline{A} = T$ |

Die Folie 11 zeigt das Distributivgesetz $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$ grafisch mit Venn-Diagrammen: Beide Seiten ergeben dieselbe schraffierte Fläche.

> [!tip] Zusatz
> - Die Potenzmenge einer $k$-elementigen Menge hat $2^k$ Elemente. Hier $2^3 = 8$.
> - Die Mengenalgebra ist ein gutes Gedankenmodell: Wenn du bei einer Umformung unsicher bist, zeichne ein Venn-Diagramm. Später wird $\cup$ zu "oder" und $\cap$ zu "und", siehe [[Schaltalgebra]].
