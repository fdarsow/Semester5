## Definition

**Alphabet:** Eine endliche, nichtleere Menge $A$, deren Elemente *Buchstaben (Zeichen)* heißen.

**Wort-Monoid:** Das Wort-Monoid $A^* := \{ a_1 \ldots a_n \mid a_j \in A \} \uplus \{ \varepsilon \}$ ist die Menge aller endlichen Worte über dem Alphabet $A$.

**Leeres Wort:** $\varepsilon$ bezeichnet das leere Wort.

**Länge:** Das Wort $a_1 \ldots a_n$ hat die Länge $n$, das Wort $\varepsilon$ hat die Länge $0$.

**Sprache:** Eine Sprache ${\cal L}$ über einem Alphabet $A$ ist eine Teilmenge ${\cal L} \subseteq A^*$.


>[!note] Bemerkung: Formale Sprachen als Monoid
>
>Ein Monoid ist eine algebraische Struktur, die aus einer Menge $M$ und einer binären Operation $\cdot$ besteht.
>
>In einem Monoid gelten zwei Eigenschaften:
>
>1. **Assoziativität:** 
 >  $$\forall x,y,z \in M: (x \cdot y) \cdot z = x \cdot (y \cdot z)$$
>
>2. **Neutrales Element:** 
 >  $$ \exists n \in M: \forall x \in M: n \cdot x = x \cdot n = x$$
>
>Eine formale Sprache über einem Alphabet $A$ ist ein Monoid, wobei:
>
>- $M = A^*$ die Menge aller Worte ist.
>- Die Operation $\cdot$ das Hintereinanderschreiben der Worte beschreibt:
  $$a_1a_2a_3 \cdot b_1b_2b_3b_4 = a_1a_2a_3b_1b_2b_3b_4$$
  $$a_1a_2a_3 \cdot \varepsilon = a_1a_2a_3$$
  $$  \varepsilon \cdot a_1a_2a_3 = a_1a_2a_3  $$
  $$  \varepsilon \cdot \varepsilon = \varepsilon  $$
  

---

## Angabe einer Sprache

**Aufzählend:** $\{ a, ab, aba \}$  (geht nur bei endlichen Mengen)

**Beschreibend:** $\{ \varepsilon, aa, aaaa, aaaaaa, \ldots \}$  (nicht eindeutig)

**Beschreibend:** $\{ w \in A^* \mid \text{enthält geradzahlig viele } a \}$  (deutsch ist zu wenig klar)

**Beschreibend:** $\{ w \in A^* \mid w.\text{startsWith("Hello")} \}$  (OK, durch Javascript-Semantik)

### Spezifikation

Wie kann ich mit *endlich* vielen Zeichen eine Sprache mit *unendlich* vielen Worten festlegen?

**Problem:** Es gibt nicht für jede Sprache eine Spezifikation. (Mächtigkeit der Mengen)

**Frage:** Für welche Klassen von Sprachen gibt es eine Spezifikation?

### Techniken zur Spezifikation einer Sprache:
1. Grammatiken
2. Maschinen
3. Reguläre Ausdrücke
4. Rekursive Funktionen
5. Jede Programmiersprache
6. Viele weitere

**Vermutung:** Die Klasse der Sprachen, die mit einer bestimmten Spezifikationsmethode angegeben werden kann, hängt von der Wahl dieser Methode ab.

**Antwort 1:** Ja.

**Beispiel:** Die Klasse der Sprachen, die mit regulären Ausdrücken festgelegt werden kann, ist kleiner als die Klasse der Sprachen, die mit kontextfreien Grammatiken festgelegt werden kann.

1. Wenn ${\cal L}$ durch einen regulären Ausdruck beschrieben wird, dann ist ${\cal L}$ kontextfrei.
2. $\{ a^n b^n \mid n \in \mathbb{N} \}$ ist kontextfrei, aber nicht regulär.

**Antwort 2:** Es gibt Spezifikationsmethoden, die schwächer sind als andere.

**Antwort 3:** Mit genügend komplexen Ansätzen ergibt sich immer wieder dieselbe Klasse von Sprachen (Church-Turing These).

**Antwort 4:** Schwächere Spezifikationsmethoden haben trotzdem ihre Berechtigung:
1. Sie besitzen zusätzliche Ausdrucksmächtigkeit.
2. Sie reichen für die jeweilige Anwendung aus.
3. Sie sind schneller zu parsen.

---

## Chomsky Hierarchie

Eine beliebte Einteilung in einfachere Klassen orientiert sich an der Spezifikationstechnik der Grammatiken:

| **Typ**                     | **Grammatiken**                    | **Maschinen**                          |
|-----------------------------|------------------------------------|---------------------------------------|
| 3 (regulär)                 | reguläre Grammatik                 | Endlicher Automat                      |
| 2 (kontextfrei)            | kontextfreie Grammatik             | Kellerautomat                          |
| 1 (kontextsensitiv)        | kontextsensitive Grammatik         | linear beschränkter Automat           |
| 0 (rekursiv aufzählbar)    | allgemeine Grammatik               | Turingmaschine                        |
