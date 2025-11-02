# Mengen

## Definitionsversuch (Georg Cantor)

Eine **Menge ist eine Zusammenfassung von bestimmten, wohlunterschiedenen Objekten** unserer Anschauung oder unseres Denkens **zu einem Ganzen**. Die in einer Menge zusammengefaßten Objekte nennen wir die **Elemente der Menge**.

## Notation

Mengen können durch **unterschiedliche Notationen** angegeben werden:

- Auflisten der Elemente: $\{1, 2, 3, 4, 0\}$
- Vorschreiben einer Eigenschaft: $\{x | x$ ist eine natürliche Zahl kleiner als $6\}$
- Sei M eine Menge:
	- $x \in M$ heißt "x ist Element von M"
	- $x \notin M$ heißt "x ist nicht Element von M"
- $\{\}$ und $\emptyset$ bezeichnen die leere Menge, d.h. die Menge, die kein Element enthält

---

## Inklusionsrelationen 

Inklusionsrelationen beschreiben, wie die **Elemente zweier Mengen zueinander in Beziehung stehen**, wie z.B. die Teilmengen oder Gleichheitsbeziehung.

- $M \subseteq N :\iff (x\in M \Rightarrow x \in N)$ "M ist eine *Teilmenge* von N"
- $M = N :\iff (M \subseteq N \land N \subseteq M) \iff (x \in M \Leftrightarrow x \in N)$ 
- $M \neq N :\iff \neg(M = N) \iff ((\exists x \in M : x \notin N) \lor (\exists x \in N : x \notin M))$
- $M \subsetneqq N :\iff (M \subseteq N \land M \neq N)$ "M ist eine *echte Teilmenge* von N"

## Teilmenge vs echte Teilmenge

- Teilmenge:
	- Eine Menge $A$ ist eine Teilmenge von Menge $B$, wenn **alle Elemente von $A$ auch in $B$ sind**.
	- Eine Menge **kann eine Teilmenge von sich selbst sein**.
	- $A \subseteq B$
- Echte Teilmenge:
	- Eine Menge $A$ ist eine echte Teilmenge von Menge $B$, **wenn $A$ eine Teilmenge von $B$ ist und die beiden Mengen *nicht* identisch sind**. Das bedeutet, es muss **mindestens ein Element in $B$ geben, das nicht in $A$ ist**.
	- Eine echte Teilmenge hat also **immer weniger Elemente als die ursprüngliche Menge** (oder zumindest ein Element weniger), außer wenn die Mengen gleich sind.
	- $A \subsetneqq B$

Zusammenfassend:
Der *Hauptunterschied* zwischen einer Teilmenge und einer echten Teilmenge liegt in den **zusätzlichen Elementen der übergeordneten Menge**. Während eine Teilmenge lediglich erfordert, dass alle ihre Elemente in der übergeordneten Menge vorhanden sind, verlangt eine echte Teilmenge, dass die übergeordnete Menge mindestens ein Element enhält, das nicht in der Untermenge vorhanden ist.

## Beispiele

- $\{1, 2, 5, 3, 4, 0\} = \{x | x$ ist eine natürliche Zahl kleiner als $6\}$
- $\{1, 3\} \subsetneqq \{1, 2, 3\}$ -> *echte Teilmenge*
- $\{1, 3\} = \{1, 2\} = \{2, 1\}$
- $1 \notin \{2, 3\}, 2 \in \{2, 3\}$

---

## Zahlenbereiche

Zahlenbereiche sind **Mengen von Zahlen, die gemeinsame Eigenschaften** haben und durch **bestimmte Regeln definiert** sind. Diese Mengen ermöglichen es, mathematische Operationen innerhalb bestimmter Grenzen durchzuführen und enthalten je nach Bereich *unterschiedliche Zahlentypen*.

- $\mathbb{N} = \{0, 1, 2, 3, 4, ...\}$  die Menge der *natürlichen* Zahlen
- $\mathbb{Z} = \{..., -3, -2, -1, 0, 1, 2, 3, ...\}$ die Menge der *ganzen* Zahlen
- $\mathbb{Q} = \{ \dfrac{p}{q} \ | \ p, q \in \mathbb{Z}, \ q \neq 0\}$ die Menge der *rationalen* Zahlen
- $\mathbb{R},$ die Menge der *reellen* Zahlen, d.h. der Dezimalbrüche 

Beachten:
$$\mathbb{N} \subsetneqq \mathbb{Z} \subsetneqq \mathbb{Q} \subsetneqq \mathbb{R}$$

---

## Operationen von Mengen

Mengenoperationen sind **Abbildungen, die einer oder mehreren Mengen eindeutig eine Menge zuordnen**. Einstellige Operationen werden auch unäre und zweistellige auch binäre Operationen genannt.

- $M \cap N := \{x \ | \ x \in M \land x \in N \}$ *Durchschnitt* von M und N -> (M *und* N)
- $M \cup N := \{x \ | \ x \in M \lor x \in N \}$ *Vereinigung* von M und N -> (M *oder* N)
- $M \setminus N := \{x \ | \ x \in M \land x \notin N\}$ *Differenz* von M und N -> (M *ohne* N)
- $M \times N := \{(x, y) \ | \ x \in M \land y \in N\}$ *kartesisches Produkt* von M und N -> $(x, y), (u, v) \in M \times N$ 
$$(x, y) = (u, v) \iff (x = u \land y = v)$$
Beispiel:
$M = \{1, 2\}$ und $N = \{e, \pi, i\}$ 
$$M \times N = \{(1,e),(1,\pi),(1,i),(2,e),(2,\pi),(2,i)\}$$
- $M \cap N = \emptyset$ *Disjunkte Menge* von M und N
- $P = M \uplus N :\iff (P = M \cup N \land M \cap N = \emptyset)$ *Diskunkte Vereinigung* von M und N
![[Operationen von Mengen Abbildung.png]]
- $\cap_{i \in I} \ M_i := \{x \ | \ x \in M_i \ \forall i \in I\}$ *Durchschnitt aller* $M_i$
- $\cup_{i \in I} \ M_i := \{x \ | \ \exists i \in I : x \in M_i\}$ *Vereinigung aller* $M_i$
- $P = \uplus_{i \in I} \ M_i :\iff (P = \cup_{i \in I} \ M_i \ \land \ M_i \cap M_j = \emptyset \ \forall \ i,j \in I$ mit $i \neq j)$
Wir nennen die $(M_i)_{i \in I}$ dann auch eine *disjunkte Zerlegung* von P, und wir sagen, die $M_i$ sind *paarweise disjunkt*

## Rechengesetze für Mengenoperationen

Es seien $M, N, P$ Mengen
- *Assoziativgesetze*
	- $(M \cup N) \cup P = M \cup (N \cup P)$
	- $(M \cap N) \cap P = M \cap (N \cap P)$
- *Kommutativgesetze*
	- $M \cup N = N \cup M$
	- $M \cap N = N \cap M$
- *Distributivgesetze*
	- $M \cap (N \cup P) = (M \cap N) \cup (M \cap P)$
	- $M \cup (N \cap p) = (M \cup N) \cap (M \cup P)$
- *Identitätsgesetze*
	- $M \cup \emptyset = M$
	- $M \subseteq N \implies M \cap N = M$
- *Komplementgesetze*
	- $M \subseteq N \implies M \cup (N \setminus M) = N$
	- $M \subseteq N \implies M \cap (N \setminus M) = \emptyset$

---

## Paradoxon von Russel

**Man muss bei der Definition von Mengen mittels Eigenschaften vorsichtig sein!**
Betrachte die "Menge"
$$M = \{X \ | \ X \ ist \ Menge \ \land \ X \notin X\}$$
aller Mengen, die sich nicht selbst als Element ernthalten!
Angenommen, $M$ wäre eine Menge. Dann sind zwei Fälle zu unterscheiden.
1. Fall: $M \notin M$: Dann ist $M$ eine Menge, die sich nicht selbst als Element enthält.
	Mithin gilt $M \in M$ aufgrund der Definition von $M$. Dies ist ein Widerspruch.
2. Fall: $M \in M$: Dann ist $M$ eine Menge, die sich selbst als Element enthält.
	Mithin gilt $M \notin M$ aufgrund der Definition von $M$. Dies ist ebenfalls ein Widerspruch.

Also kann keiner der beiden Fälle auftreten, und wir haben insgesamt einen Widerspruch hergeleitet.
**Fazit:** M ist keine Menge! Auch die *Menge aller Mengen* gibt es *nicht*!