Die Prädikatenlogik ist eine Erweiterung der Aussagenlogik. Im Unterschied zur Aussagenlogik macht diese aber von [[Quantoren]] gebrauch.

# Prädikat
#Definition 
Als **Prädikat** bezeichnet man den Teil einer [atomaren Formel](Aussagen.md#Atomare%20Formel), der wahrheitsfunktional ist. Ein Prädikat hat dabei beliebig viele Argumentstellen.

Spezifischer: Ein Prädikat ist eine Abbildung $p:\{ 0, 1 \}^n \to \{ 0, 1 \}$ für ein beliebiges $n \in \mathbb{N}_0$.

# Prädikatenlogik erster Stufe

Die Prädikatenlogik erster Stufe lässt sich mittels der [Zermello-Fraenkel -Mengenlehre](https://de.wikipedia.org/wiki/Zermelo-Fraenkel-Mengenlehre) formulieren. Die axiomatischen Definition dessen ist für uns zunächst überflüssig und wird hier nicht behandelt.

Wir beschreiben hier die verwendete Sprache auf rein syntaktische Weise, das heißt, wir legen die betrachteten Zeichenketten, die wir Ausdrücke der Sprache nennen wollen, ohne Bezug auf ihre Bedeutung fest.

## Symbole

Eine Sprache erster Stufe wird aus folgenden **Symbolen** aufgebaut
- logische Symbole:
	- [[Quantoren]]: $\forall$, $\exists$
	- [Junktoren](Aussagen.md#Junktoren): $\land$, $\lor$, $\lnot$, $\rightarrow$, $\leftrightarrow$
	- technische Zeichen: $(,)$, $\equiv$
- Variablensymbole: $v_{0}, v_{1}, v_{2}, ...$
- eine (möglicherweise leere) Menge $\mathcal {C}$ von Konstantensymbolen
- eine (möglicherweise leere) Menge $\mathcal {F}$ von Funktionssymbolen
- eine (möglicherweise leere) Menge $\mathcal {R}$ von Relationssymbolen

Unterschiedliche Sprachen unterscheiden sich in den Symbolen $\mathcal {C}$, $\mathcal {F}$ und $\mathcal {R}$, die man üblicherweise als Symbolmenge $S$ zusammenfasst. Diese Menge nennt sich die **Signatur** der Sprache.

## Terme

Die nach folgenden Regeln aufgebaute Zeichenketten heißen **Terme**:
- Ist $v$ ein Variablensymbol, so ist $v$ ein Term
- Ist $c$ ein Konstantensymbol, so ist $c$ ein Term
- Ist $f$ ein $n$-stelliges Funktionssymbol und $t_{1}, t_{2}, ..., t_n$ Terme, so ist $ft_1t_2...t_n$ ein Term

## Formeln

Wir erklären nun durch Bildungsgesetze, welche Zeichenketten wir als **Formeln** der Sprache ansehen wollen (vergleich: [Aussagenlogik](Aussagen.md#Formeln)).
### Atomare Formeln
- Sind $t_1$ und $t_2$ Terme, so ist $t_{1}\equiv t_2$ eine Formel
- Ist $R$ ein $n$-stelliges Relationssymbol und $t_{1}, t_{2}, ..., t_n$ Terme, so ist $Rt_1t_2...t_n$ eine Formel
### Zusammengesetzte Formeln
- Ist $\varphi$ eine Formel, so ist $\lnot \varphi$ eine Formel
- Sind $\varphi$ und $\psi$ Formeln und $K$ eine Konjunktion, so ist $\varphi K \psi$ eine Formel
- Ist $\varphi$ eine Formel, $Q$ ein Quantor und $x$ eine Variable, so ist $Qx\varphi$ eine Formel

Damit sind alle Formeln unserer Sprache festgelegt.