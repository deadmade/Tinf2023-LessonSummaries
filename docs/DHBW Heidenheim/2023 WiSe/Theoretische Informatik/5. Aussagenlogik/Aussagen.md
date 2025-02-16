# Aussage
#Definition 
Eine **Aussage** ist einsprachlich sinnvoller Satz mit der Eigenschaft **wahr** oder **falsch** zu sein (aber nicht beides gleichzeitig).

Wir schreiben $1$ für wahr und $0$ für falsch.

# Atomare Formel
#Definition 
Eine **atomare Formel** ist eine Aussage die nicht in weiteren Aussagen zersetzt werden kann.

# Junktoren
#Definition 
Ein **Junktor** ist ein Logischer Operator zwischen zwei Aussagen, also ein logischer Operator.

Es seien $A$ und $B$ Aussagen:
- **Konjunktion**: $A \land B$ ist genau dann wahr, wenn $A$ und $B$ wahr sind.
- **Disjunktion**: $A \lor B$ ist genau dann wahr, wenn $A$ oder $B$ wahr ist.
- **Negation**: $\lnot A$ ist genau dann wahr, wenn $A$ falsch ist.
- **Implikation**: $A \rightarrow B$ ist genau dann wahr, wenn $A$ falsch ist oder $A$ und $B$ wahr sind.
- **Äquivalenz**:  $A \leftrightarrow B$ ist genau dann wahr, wenn $A \rightarrow B$ und $B \rightarrow A$.

# Literale
#Definition 
**Literale** sind atomare Formeln und Negationen dieser.

# Formeln
#Definition 
Innerhalb der Aussagenlogik definieren wir **Formeln** wie folgt:
- Alle Atomare Formeln sind Formeln.
- Ist $A$ eine Formel, so ist auch $\lnot A$ eine Formel.
- Sind $A, B$ Formeln, so sind auch $(A \land B), (A \lor B), (A \rightarrow B), (A \leftrightarrow B)$ Formeln.