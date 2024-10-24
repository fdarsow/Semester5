
| Inhaltsverzeichnis                            |
| --------------------------------------------- |
| [Definition](#definition)                     |
| [Angabe einer Sprache](#angabe-einer-sprache) |
| [Chomsky Hierarchie](#chomsky-hierarchie)     |
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

- **Aufzählend:** $\{ a, ab, aba \}$  (geht nur bei endlichen Mengen)
- **Beschreibend:** $\{ \varepsilon, aa, aaaa, aaaaaa, \ldots \}$  (nicht eindeutig)
- **Beschreibend:** $\{ w \in A^* \mid \text{enthält geradzahlig viele } a \}$  (deutsch ist zu wenig klar)
- **Beschreibend:** $\{ w \in A^* \mid w.\text{startsWith("Hello")} \}$  (OK, durch Javascript-Semantik)
- **Spezifikation**  Wie lege ich mit endlich vielen Zeichen einer Sprache mit unendlich vielen Worten fest?
### Spezifikation

>[!error] Probleme bei der Spezifikation von Sprachen
> - Es gibt nicht für jede Sprache eine Spezifikation. (Mächtigkeit der Mengen)
>> <li  style="list-style-type: '-> ';">Die Klasse der Sprachen, die mit einer bestimmten Spezifikationsmethode angegeben werden kann, hängt von der Wahl dieser Methode ab.</li>
> - einige Spezifikationsmethoden sind schwächer als andere
> 	- haben dann andere Vorteile
> 		-  zusätzliche Ausdrucksmächtigkeit
> 		- sind schneller zu parsen
> - Mit genügend komplexen Ansätzen ergibt sich immer wieder dieselbe Klasse von Sprachen (Church-Turing These).



### Techniken zur Spezifikation einer Sprache:
1. Grammatiken
2. Maschinen
3. Reguläre Ausdrücke
4. Rekursive Funktionen
5. Jede Programmiersprache
6. Viele weitere

---

## Chomsky Hierarchie

Eine beliebte Einteilung in einfachere Klassen orientiert sich an der Spezifikationstechnik der Grammatiken und geht auf Noam Chomsky zurück:

| **Typ**                 | **Grammatiken**                                                       | Angabe                                                        | **Maschinen**                                                                                                                          |
| ----------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 3 (regulär)             | (links / rechts) regulär<br><br>(links / rechts) linear <br> <br>     | reguläre Menge,  <br>regulärer Ausdruck                       | Endlicher Automat <br> <br> **Deterministischer Endlicher Automat (DEA)** <br> **Nichtdeterministischer Endlicher Automat (NEA)**      |
| 2 (kontextfrei)         | kontextfreie Grammatik <br> <br>                                      | Chomsky Normalform, Greibach Normalform, reduzierte Grammatik | Kellerautomat <br> <br> akzeptierender Kellerautomat <br> kellerakzeptierender Kellerautomat <br> zustandsakzeptierender Kellerautomat |
| 1 (kontextsensitiv)     | kontextsensitive Grammatik                                            |                                                               | **Linear beschränkter Automat (LBA)** <br> Eingabe-beschränkter Automat                                                                |
| 0 (rekursiv aufzählbar) | allgemeine Grammatik, <br><br>normale Grammatik, separierte Grammatik |                                                               | **Turing Maschine (TM)** <br> **Random Access Maschine (RAM)**                                                                         |

