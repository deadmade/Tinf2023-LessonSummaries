> [!info] Hintergrund  
> Differentialgleichungen sind in Naturwissenschaft und Technik allgegenwärtig, aber analytisch oft schwierig zu lösen. Nur in wenigen Spezialfällen sind geschlossene Lösungen möglich.

## Freier Fall: Einführungsbeispiel
Ein Körper fällt im luftleeren Raum, beeinflusst nur durch die Schwerkraft:  
- **Koordinatensystem**: Positive Richtung nach oben.  
- **Beschleunigung**: $$a = -g$$ (Schwerkraft entgegen positiver Richtung).

Differentialgleichung:
$$
s''(t) = -g
$$

### Lösungsprozess:
1. Integration ergibt:  
   $$v(t) = -g \cdot t + c_1$$  
2. Zweite Integration ergibt:  
   $$s(t) = -\frac{1}{2} g \cdot t^2 + c_1 \cdot t + c_2$$

Die Anfangsbedingungen \( s(0) = s_0 \) und \( v(0) = v_0 \) bestimmen die Konstanten:  
$$
s(t) = -\frac{1}{2} g \cdot t^2 + v_0 \cdot t + s_0
$$

> [!example] Wichtiger Punkt  
> Partikuläre Lösungen berücksichtigen spezifische Anfangsbedingungen, im Gegensatz zur allgemeinen Lösung.

---

## 1.1 Mathematische Formulierung

> [!important] Definition: Gewöhnliche Differentialgleichung (DGl)
> Eine DGl ist eine Gleichung, die Ableitungen einer Funktion $$y = y(x)$$ enthält.  
> - **Implizit**:  
>   $$
>   F(x, y, y', \dots, y^{(n)}) = 0
>   $$  
> - **Explizit**:  
>   $$
>   y^{(n)} = f(x, y, y', \dots, y^{(n-1)})
>   $$

> [!example]- Beispiele:
> 1. $y' = 2x$ (explizit, 1. Ordnung).  
> 2. $x^2 y'' - y' + y = 0$ (implizit, 2. Ordnung).  
> 3. $s''(t) = -g$ (explizit, 2. Ordnung).  

---

## 1.2 Lösungen einer Differentialgleichung

> [!important] Definition: Lösung einer DGl
> Eine Funktion $y = y(x)$, die die DGl erfüllt, heißt Lösung.  
> - **Allgemeine Lösung**: Enthält \( n \) Integrationskonstanten.  
> - **Partikuläre Lösung**: Spezifisch durch zusätzliche Bedingungen festgelegt.

> [!example]- Beispiel:
> Die allgemeine Lösung von $y' = 2x$ lautet:
> $$
> y = x^2 + c \quad (c \in \mathbb{R})
> $$

---

## 1.3 Anfangs- und Randwertprobleme

### Anfangswertproblem (AWP)
Gesucht ist die Lösung, die durch den Punkt $(x_0, y(x_0))$ und die Ableitungen bis zur $(n-1)$-ten Ordnung geht.

### Randwertproblem (RWP)
Hier werden \( n \) Funktionswerte an \( n \) verschiedenen Stellen vorgegeben.

---

## 1.4 Trennung der Variablen

> [!important] Lösungsmethode
> Für DGl der Form $y' = f(x) \cdot g(y)$:
> 1. Trennung der Variablen.  
> 2. Integration beider Seiten.  
> 3. Auflösen nach \(y\).

> [!example]- Beispiel:
> $$
> y' = y \quad \Rightarrow \quad \frac{1}{y} \, dy = dx \quad \Rightarrow \quad \ln|y| = x + c \quad \Rightarrow \quad y = C \cdot e^x
> $$

---

## 1.5 Integration durch Substitution

### Lösungsmethode
Für spezielle Typen wie:
1. $y' = f(ax + by + c)$.  
2. $\frac{y'}{y} = f(x)$.  

Durch Substitution wird die DGl vereinfacht.

### Beispiel:
$$
y' = 1 + 2x \quad \Rightarrow \quad u = 1 + 2x, \, du = 2dx \quad \Rightarrow \quad \text{Integration und Rücksubstitution.}
$$

