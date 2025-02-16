In der Aussagenlogik haben wir bereits einige [[Normalformen]] kennen gelernt.

# Pränexform

Eine [Formel](Aussagen.md#Formeln) heißt **pränex**, fall alle Quantoren außerhalb bzw. vor der eigentlichen Formel stehen.

>[!tip] Bemerkung
>Zu jeder Formel existiert eine äquivalente Pränexform.

> [!example] Beispiel
> Wir bringen eine Formel in Pränexform:
> $\lnot (\exists Xp(X, Y) \lor \forall Zq(Z)) \land \exists Wp(W)$
> $\lnot \exists Xp(X, Y) \land \lnot \forall Zq(Z) \land \exists Wp(W)$
> $\forall X \lnot p(X, Y) \land \exists Z \lnot q(Z) \land \exists Wp(W)$
> $\forall X \exists Z \exists W(\lnot p(X, Y) \land \lnot q(Z) \land p(W))$

# Substitution

Wir erinnern uns: Für Prädikatenlogische Formeln $F$ und $G$ gilt die Äquivalenz
$$(\forall XF \land G) \equiv \forall X(F \land G)$$
nur dann, wenn $X$ nicht als freie Variable in $G$ vorkommt. Also wäre es nicht möglich, in anderen Fällen eine Formel in Pränexform zu überführen!

Also wenden wir die **Substitution** an. Hierbei ersetzen wir eine Variable durch eine Konstante, eine Variable oder eine Funktion ersetzen.

>[!example] Beispiel
>Äquivalent zum obigen Beispiel:
>$\lnot (\exists Xp(X, Y) \lor \forall Zq(X, Z)) \land \exists Wp(W)$
>Diese Formel kann nicht in Pränexform überführt werden. Wir substituieren:
>$F[X/U]$ mit $F = \forall Z q(X, Z)$
>Wir erhalten:
>$\lnot (\exists Xp(X, Y) \lor \forall Zq(U, Z)) \land \exists Wp(W)$

# Bereinigte Form

Eine [Formel](Prädikatenlogik.md#Formel) heißt **bereinigt**, falls keine Variablen vorkommen, die sowohl [gebunden](Gebundenheit%20von%20Variablen.md) als auch [ungebunden](Gebundenheit%20von%20Variablen.md) sind. Dies kann mit Substitution erreicht werden, wie im oberen Beispiel.

# Skolemform

Eine [Formel](Prädikatenlogik.md#Formel) heißt **skolemisiert** oder in **Skolemform**, falls sie in Pränexform ist und keine [Existenzquantoren](Quantoren.md) in der Formel vorkommen. Überflüssige Existenzquantoren können mithilfe von Substitution entfernt werden.

>[!example] Einfaches Beispiel
>Gegeben sei die folgende Formel:
>$$\forall X \exists Y \forall Z p(X, Y, Z)$$
>Diese Formel ist nicht skolemisiert, weil es den Existenzquantor $\exists Y$ gibt. Wir können diesen aber durch ein Funktionssymbol $f$ ersetzen:
>$$\forall X \forall Z p(X, f(X), Z)$$
>Hierbei ist $f$ von $X$ abhängig, weil $\exists Y$ ebenfalls von $X$ abhängig ist. Allerdings ist $\exists Y$ nicht von $Z$ abhängig, also ist $f$ auch nicht von $Z$ abhängig.
>---
>Falls ein Existenzquantor von keinem Allquantor abhängig ist, so können wir die Variable durch eine Konstante ersetzen:
>$$\exists X \forall Y \exists Z p(X, Y, Z)$$
>Und wir substituieren:
>$$\forall Y \exists Z p(a, Y, Z)$$

# Hornklausel

Eine KNF heißt **Horn-Form**, falls jede Klausel der KNF höchstens ein nicht-negiertes Literal enthält und alle Variablen von einem Allquantor gebunden sind. Die Klauseln dieser KNF heißen **Hornklauseln**.

>[!example] Beispiel
>Die Formel
>$$\forall X \forall Y \forall Z ((p(X) \lor \lnot q(Y) \lor \lnot r(Z)))$$
>ist in Horn-Form.