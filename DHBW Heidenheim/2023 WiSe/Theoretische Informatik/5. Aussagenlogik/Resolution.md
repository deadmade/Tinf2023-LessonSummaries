Die Resolution ist eine korrekte Methode zur [syntaktischen Folgerung](Folgerungsbeziehungen.md#Syntaktische%20Folgerung). Sie ist nicht vollständig im strengen Sinne. Sie ist jedoch vollständig genug, um Widersprüche herleiten zu können (refutation completeness).

Die [Erfüllbarkeit](Erfüllbarkeit.md#Erfüllbarkeit) oder Gültigkeit einer [Formel](Aussagen.md#Formeln) zu beweisen ist ein häufiges Problem. Mit Hilfe der Wahrheitstafel ist dies möglich, aber aufwändig. Eine Methode, die oft ein schnelleres Ergebnis liefert, ist die Resolution.

Die Resolution wird für drei Aufgaben eingesetzt:
- Beweis der **Erfüllbarkeit** aussagenlogischer Formeln
- Beweis der **Herleitbarkeit** aussagenlogischer Formeln
- Beweis von **Tautologien**

# Resolvente

Es seien $K_1$ und $K_2$ Klauseln einer [aussagenlogischen Formel](Aussagen.md#Formeln), die in [KNF](Normalformen.md#Konjunktive%20Normalform%20(KNF)) liegt, mit $K_1 \neq K_2$. Gibt es ein [Literal](Aussagen.md#Literale) $L$, welches in $K_1$ positiv und in $K_2$ negativ vorkommt, dann nennt man $$R = (K_1 \backslash \{L\}) \cup (K_2 \backslash \{\lnot L\})$$**Resolvente** von $K_1$ und $K_2$. Insbesondere gibt es keine Resolvente, falls kein solches Literal existiert.

>[!warning] Achtung
>Es darf immer nur genau **ein** Literal resolviert werden!
>---
>Die Resolvente ist nicht äquivalent zu den Ausgangsklauseln. Die Bedeutung der Resolvente liegt vielmehr darin, dass die Ausgangsklauseln nur dann beide gleichzeitig erfüllbar sind, wenn auch die Resolvente erfüllbar ist. Insbesondere gilt $$(K_{1}\land K_{2})\rightarrow R$$ weil $R$ eine notwendige Bedingung für $K_1$ und $K_2$ ist.


# Erfüllbarkeit aussagenlogischer Formeln

Für die Klauselmenge $F$ einer [Formel](Aussagen.md#Formeln) werden alle möglichen Resolventen ermittelt. Ist die leere Klausel in der Klauselmenge enthalten, ist die [Formel](Aussagen.md#Formeln) [unerfüllbar](Erfüllbarkeit.md#Erfüllbarkeit), ansonsten [erfüllbar](Erfüllbarkeit.md#Erfüllbarkeit).


>[!example] Beispiel Resolution
>- $F = (A \lor B) \land (\lnot A \lor C) \land (B \lor \lnot C) \land \lnot B$
>- $K_F = \{ \{ A, B \}, \{ \lnot A, C \}, \{ B, \lnot C \}, \{ \lnot B \} \}$
>- $K_F = \{ K_1, K_2, K_3, K_4 \}$
>---
>- $K_5 = (K_1 \backslash \{ B \}) \cup (K_4 \backslash \{ \lnot B \}) = \{ A \}$
>- $K_6 = (K_2 \backslash \{ C \}) \cup (K_3 \backslash \{ \lnot C \}) = \{ \lnot A \land B \}$
>- $K_7 = (K_5 \backslash \{ A \}) \cup (K_6 \backslash \{ \lnot A \}) = \{ B \}$
>- $K_8 = (K_7 \backslash \{ B \}) \cup (K_4 \backslash \{ \lnot B \}) = \{ \}$
>---
>Da die leere Klausel in der Klauselmenge enthalten, ist die Formel unerfüllbar.

# Beweis von Tautologien

Wenn eine Formelmenge $F$ eine Tautologie darstellt, kann dies bewiesen werden, indem mit Hilfe der Resolution gezeigt wird, dass $\lnot F$ unerfüllbar ist.

# Herleitbarkeit aussagenlogischer Formeln

Um zu zeigen, dass eine Formel $G$ aus einer Formel $F$ hergeleitet werden kann, muss mit Hilfe der Resolution gezeigt werden, dass $F \land \lnot G$ unerfüllbar ist.