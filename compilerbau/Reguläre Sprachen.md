## Typ 3 Grammatik-Definition

Eine Grammatik heißt

1. **linkslinear (leftlinear)**, wenn $R \subseteq N \times [T \cup (N \cdot T)]$
   bzw. jede Regel eine der folgenden zwei Formen hat:
   $$ A \to x \quad\quad A \to By $$

2. **rechtslinear (rightlinear)**, wenn $R \subseteq N \times [T \cup (T \cdot N)]$,
   bzw. jede Regel eine der folgenden zwei Formen hat:
   $$ A \to x \quad\quad A \to yB $$

3. **linksregulär (leftregular)**, wenn $R \subseteq N \times [T \cup (N \cdot T) \cup \{ \varepsilon \}]$,
   bzw.  jede Regel eine der folgenden drei Formen hat:
   $$ A \to x \quad\quad A \to By \quad\quad A \to \varepsilon $$

4. **rechtsregulär (rightregular)**, wenn $R \subseteq N \times [T \cup (T \cdot N) \cup \{ \varepsilon \}]$,
   bzw. jede Regel eine der folgenden drei Formen hat:
   $$ A \to x \quad\quad A \to yB \quad\quad A \to \varepsilon $$

## Typ 3 Grammatiktheorem

>Für eine Sprache $\mathcal{L} \subseteq A^*$ sind die folgenden Aussagen äquivalent:
>
>1. $\mathcal{L} \setminus \{ \varepsilon \}$ wird durch eine **linkslineare Grammatik** beschrieben.
>2. $\mathcal{L} \setminus \{ \varepsilon \}$ wird durch eine **rechtslineare Grammatik** beschrieben.
>3. $\mathcal{L}$ wird durch eine **linksreguläre Grammatik** beschrieben.
>4. $\mathcal{L}$ wird durch eine **rechtsreguläre Grammatik** beschrieben.

## Definition: Reguläre Sprache

>Eine *Sprache*, für die eine der oben angeführten äquivalenten Aussagen gilt, heißt **reguläre Sprache (regular language)** oder **Typ 3 Sprache**.

## Pumping Lemma

Sei $\mathcal{L}$ eine Typ 3 Sprache über einem Alphabet $A$.

Dann existiert eine Zahl $n \in \mathbb{N}$ mit der folgenden Eigenschaft:
- Zu jedem Wort $q$ der Sprache, 
- das mindestens die Länge $n$ hat ($|q| \geq n$, )
- existiert eine Zerlegung $q = uvw$ mit $u, v, w \in A^*$, 
- mit nicht leerem $v$ und $|uv| \leq n$, 
- ==> so dass für jedes $i \in \mathbb{N}$ alle Wörter der Form $uv^iw$[^1] wieder in der Sprache $\mathcal{L}$ liegen. 


> **Formal:**
>$$ \exists n \in \mathbb{N} \colon \forall q \in \mathcal{L}, |q| \geq n \colon \exists u, v, w \in A^*, v \neq \varepsilon, |uv| \leq n \colon \forall i \in \mathbb{N} \colon uv^iw \in \mathcal{L} $$

**Anschaulich:**
Jedes hinreichend lange Wort hat relativ weit am Anfang einen Bestandteil, den wir beliebig oft vervielfachen können, ohne dadurch die Sprache zu verlassen.

**Anwendung:** Zeigen, dass eine bestimmte Sprache nicht regulär ist.


[^1]: Mit der Notation $v^i$ ist die $i$-fache Konkatenation von $v$ gemeint: $v^1 = v$, $v^2 = vv$, $v^3 = vvv$ usw.
## Abschlusstheorem

> Die Klasse der Typ 3 Sprachen ist **abgeschlossen** unter **Vereinigung, Durchschnitt, Konkatenation, Sternbildung, Komplement und Spiegelung**.

Das heißt genauer:

Sind $\mathcal{L}_1$ und $\mathcal{L}_2$ reguläre Sprachen. Dann sind auch die folgenden Sprachen wieder reguläre Sprachen:

1. die Vereinigung $\mathcal{L}_1 \cup \mathcal{L}_2$,
2. der Durchschnitt $\mathcal{L}_1 \cap \mathcal{L}_2$,
3. die Konkatenationssprache $\mathcal{L}_1 \cdot \mathcal{L}_2 = \{ r_1 r_2 \mid r_1 \in \mathcal{L}_1 \wedge r_2 \in \mathcal{L}_2 \}$, die aus der Konkatenation eines Wortes aus $\mathcal{L}_1$ und eines Wortes aus $\mathcal{L}_2$ besteht.

Ist $\mathcal{L}$ eine reguläre Sprache, dann sind auch die folgenden Sprachen wieder reguläre Sprachen:

1. die Kleene-Stern-Sprache $\mathcal{L}^* = \{ \varepsilon \} \cup \mathcal{L} \cup \mathcal{L} \cdot \mathcal{L} \cup \ldots$, die aus der Konkatenation einer beliebigen Anzahl* von Worten aus $\mathcal{L}$ besteht.
2. das Komplement $\mathbb{C} \mathcal{L}$ der Sprache, also die Menge ihrer "Nicht-Wörter" und
3. die Menge aller gespiegelten Wörter aus $\mathcal{L}$.
