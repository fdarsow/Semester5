> [!info] Formale Sprache
> Eine Formale Sprache $L$ ist eine Menge von Wörtern über einem Alphabet $X$. $(L\subseteq X^*)$
> ###### Typ 0
> Alle Sprachen, für die es eine Grammatik gibt
> ###### Typ 1
> Alle Regeln haben die Form 
> ###### Typ 2, Kontextfrei
> - $h_1 H h_2 \to (x \cup H)*$ h_1 und h_2 sind der Kontext
> ###### Typ 3, Regulär
> - Rechte Seite hat max. 1 Hilfssymbol
> - egal, ob Automat deterministisch ist, oder nicht





>[!info] Grammatik
>Eine Grammatik $G =[X,H,R,s]$ besteht aus 
>- Menge von Terminalsybolen $X$
>- Menve von Hilfssymbolen $H$, wobei $X\cap H = \emptyset$
>- Produktionsregeln $R\subseteq ((X \cup H)* + \setminus X^*) \times (X\cup H)*$
>- einem Startsymbol $s \in H$
>
>Rechte Seite beliebig, linke Seite hat min. 1 Hilfssymbol.

>[!info] Wortproblem
> Sprache L, OWrt w
> $w \overset{?}{\in}  L$



>[!Anmerkung] 
>- Interessante Sprachen sind unendlich groß
>- das Ableiten ist für uns nicht interressant
>- 

###### Wortproblem hat linear viel speicher
aPa -> abba
`aababbbaa`
```Text
aababbbaa
 |
 Start -> geht nicht

aababbaa
   | Start. Erkennen, das ist die rechte seite ->
aabaPaaa 
```

###### Kellerautomat
- DEA
- mit Stack

