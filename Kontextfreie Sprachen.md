# Kontextfreie Grammatiken

>[!info] Definition
> Eine Grammatik ${\cal G} = ({\cal N}, {\cal T}, \mbox{S}, R)$ heißt **kontextfrei (context free)**, wenn jede Regel links genau ein Nichtterminal hat.

Das bedeutet $R \subseteq N \times [(N \cup T)^*]$.

Die Regeln haben also alle die folgende Form mit $\mbox{N} \in {\cal N}$ und ${\cal X} \in ({\cal N} \cup {\cal T})^*$:
$$\mbox{N} \to {\cal X}$$

## Typ 2 Normalformen

Eine Grammatik heißt
1. **in** $\text{Chomsky}$ **Normalform**, wenn jede Regel links genau ein Nichtterminal hat und rechts entweder genau ein Terminal oder genau zwei Nichtterminale.
   Also wenn $R \subseteq N \times [T \cup (N \cdot N)]$.

Wenn die Regeln eine der folgenden zwei Formen haben: 
$$A \to x \quad\quad A \to BC$$

2. **in** $\text{Greifenbach}$ **Normalform**, wenn jede Regel links genau ein Nichtterminal hat und rechts stets mit einem Terminal beginnt, dem 0 oder mehr Nichtterminale folgen.

Also wenn $R \subseteq N \times [T \cdot N^*]$.

Wenn jede Regel eine der folgenden Formen hat:
$$A \to x \quad\quad A \to xB \quad\quad A \to xBC \quad\quad A \to xBCD \ldots$$

## Typ 2 Grammatiktheorem

Für eine Sprache ${\cal L} \subseteq A^*$ sind die folgenden Aussagen äquivalent:
1. ${\cal L}$ wird durch eine **kontextfreie Grammatik** beschrieben.
2. ${\cal L} \setminus \{ \varepsilon \}$ wird durch eine Grammatik in {\sc Chomsky} **Normalform** beschrieben.
3. ${\cal L} \setminus \{ \varepsilon \}$ wird durch eine Grammatik in {\sc Greibach} **Normalform** beschrieben.
4. ${\cal L}$ wird durch eine **reduzierte Grammatik** beschrieben.

Eine *Sprache* ${\cal L}$, die durch eine kontextfreie Grammatik beschrieben werden kann, heißt eine **kontextfreie Sprache (contextfree language)** oder **Typ 2 Sprache**.

## Typ 2 Pumping Lemma

Sei ${\cal L}$ eine Typ 2 Sprache über einem Alphabet $A$.

Dann existiert eine Zahl $n \in \mathbb{N}$ mit der folgenden Eigenschaft: Zu jedem Wort $q$ der Sprache, das mindestens die Länge $n$ hat, $|q| \geq n$, existiert eine Zerlegung $q = uvwxy$ mit $v$ und $x$ nicht gleichzeitig das leere Wort und $|vwx| \leq n$, so dass für jedes $i \in \mathbb{N}$ alle Wörter der Form $uv^iwx^iy$ wieder in der Sprache ${\cal L}$ liegen.

**Formal:**
$$  
\exists n \in \mathbb{N} \colon \forall q \in {\cal L}, |q| \geq n \colon
\exists u,v,w,x,y \in A^*, v \neq \varepsilon \wedge x \neq \varepsilon, |vwx| \leq n \colon 
\forall i \in \mathbb{N} \colon
uv^iwx^iy \in {\cal L}
$$

## Typ 2 Abschlusssatz

Die Klasse der Typ 2 Sprachen ist **abgeschlossen** unter **Vereinigung, Konkatenation** und **Sternbildung**.

Das heißt:

Sind ${\cal L}_1$ und ${\cal L}_2$ kontextfreie Sprachen, dann sind auch die folgenden Sprachen wieder reguläre Sprachen:
1. die Vereinigung ${\cal L}_1 \cup {\cal L}_2$.
2. die Konkatenationssprache $\{ r_1 r_2 \mid r_1 \in {\cal L}_1 \land r_2 \in {\cal L}_2 \}$, die aus der Konkatenation eines Wortes aus ${\cal L}_1$ und eines Wortes aus ${\cal L}_2$ besteht.

Ist ${\cal L}$ eine kontextfreie Sprache, dann ist auch die {\sc Kleene}--Stern--Sprache ${\cal L}^*$ eine kontextfreie Sprache.

## Definition: Ableitungsbaum

Der **Ableitungsbaum (derivation tree)** eines Wortes $w \in T^*$ bezüglich einer kontextfreien Grammatik ist ein geordneter, knotenattributierter Baum mit Attributmenge $N \cup T$, der den folgenden drei Bedingungen genügt:

1. Die **Wurzel** des Baumes trägt als Attribut das Startsymbol der Grammatik.
2. Sei $p$ ein **Knoten, der keine Wurzel** ist und sei $(n_1, n_2, \ldots , n_r)$ die geordnete Folge der Nachfolgerknoten von $p$. Dann gilt:

Wenn der Knoten $p$ das Attribut $P$ trägt und die Nachfolgerknoten $n_i$ die Attribute tragen $N_i$, dann ist
$$P \to N_1 N_2 \cdots N_r$$
eine Regel der Grammatik.

3. Die **Blätter** tragen als Attribute terminale Symbole, die im Sinne der Ordnung des Baumes gelesen das Wort $w$ ergeben.

## Theorem vom Ableitungsbaum

Sei ${\cal G}$ eine kontextfreie Grammatik. Dann gilt:

Zu einem Wort $w \in T^*$ aus terminalen Symbolen gibt es genau dann einen Ableitungsbaum bezüglich der Grammatik ${\cal G}$, wenn $w$ ein Wort der Sprache ist. 

Zu jedem Ableitungsbaum eines Wortes $w$ gibt es genau eine Linksableitung und genau eine Rechtsableitung für $w$, deren Wörter aus terminalen und nichtterminalen Symbolen den Attributen von Knotenfronten entsprechen, die sich im Baum von der Wurzel zu den Blättern ausbreiten. 

Zu jeder Linksableitung gibt es genau einen entsprechenden Ableitungsbaum.

Zu jeder Rechtsableitung gibt es genau einen entsprechenden Ableitungsbaum.

## Definition: Eindeutigkeit 

Eine kontextfreie Grammatik heißt **eindeutig (unambiguous)**, wenn es zu jedem Wort der Sprache genau einen Ableitungsbaum gibt.

Eine kontextfreie Grammatik heißt **mehrdeutig (ambiguous)**, wenn sie nicht eindeutig ist. Das bedeutet, dass es zu mindestens einem Wort der Sprache mehr als einen Ableitungsbaum gibt.

> Zu einer eindeutigen Sprache gibt es *immer* mehrdeutige Grammatiken.
>
> Eine Sprache ist mehrdeutig, wenn *jede* ihrer Grammatiken mehrdeutig ist.
>
> Eine Sprache ist eindeutig, wenn es für sie *mindestens* eine eindeutige Grammatik gibt.

## Beispiel: Ableitungsbaum und Eindeutigkeit

Gegeben sei die Grammatik 
$$S \to SS \mid a \mid b$$
mit den Terminalen $a$ und $b$ und dem Nichtterminal $S$, das zugleich Startsymbol ist.

$aab$ ist ein Wort der durch diese Grammatik erzeugten Sprache. 

Zu $aab$ gibt es genau die folgenden zwei Ableitungsbäume:
```plaintext
            S                 S
           / \               / \
          S   S             S   S
         / \   \           /   / \
        S   S   b         a   S   S
        |   |                 |   |
        a   a                 a   b

```

Zu jedem dieser Ableitungsbäume gehört jeweils genau eine Linksableitung und genau eine Rechtsableitung:

|                                    |                                            |
| ---------------------------------- | ------------------------------------------ |
| Linksableitung des linken Baumes   | $S \to SS \to SSS \to aSS \to aaS \to aab$ |
| Rechtsableitung des linken Baumes  | $S \to SS \to Sb \to SSb \to Sab \to aab$  |
| Linksableitung des rechten Baumes  | $S \to SS \to aS \to aSS \to aaS \to aab$  |
| Rechtsableitung des rechten Baumes | $S \to SS \to SSS \to SSb \to Sab \to aab$ |

Zu dieser Sprache gibt es auch eine eindeutige Grammatik: 
$$S \to aS \mid bS \mid a \mid b$$
Die Grammatik ist sogar rechtslinear. Somit ist diese Sprache auch regulär.

## Beispiel: Mehrdeutige Sprache

Die Sprache $\{ a^n b^m c^m \mid n, m \in \mathbb{N} \} \cup \{ a^m b^m c^n \mid n, m \in \mathbb{N} \}$ ist mehrdeutig.
