Die Methode der **Substitution** ist ein Werkzeug, um komplizierte Integrale zu vereinfachen. Dabei wird eine Funktion durch eine andere Variable ersetzt, um das Integral leichter lösen zu können.

---

## 📘 Grundidee

Die Substitution basiert auf der Kettenregel der Differentiation. Gegeben ist ein Integral der Form:

$$
\int f(g(x)) \cdot g'(x) \, dx
$$

Hier setzt man:

$$
u = g(x) \quad \text{und damit} \quad du = g'(x) \, dx
$$

Das Integral wird dann umgeschrieben zu:

$$
\int f(g(x)) \cdot g'(x) \, dx = \int f(u) \, du
$$

---

## 🚦 Vorgehen bei der Substitution

1. **Substitution wählen**: Finde \( u = g(x) \), um das Integral zu vereinfachen.
2. **Ableitung berechnen**: Differenziere \( u \) und ersetze \( dx \) durch \( du \).
3. **Integral umschreiben**: Ersetze alle \( x \)-Terme durch \( u \)-Terme.
4. **Integriere**: Löse das Integral in Bezug auf \( u \).
5. **Rücksubstitution**: Ersetze \( u \) wieder durch die ursprüngliche Funktion \( g(x) \).

---

## 🧮 Beispiele

> [!example]+ **Beispiel 1: Einfaches Integral**  
> Gegeben: $\int 2x \cdot (x^2 + 1)^3 \, dx$
> 1. **Substitution wählen**:  $u = x^2 + 1$ , also $$du = 2x \, dx $$.  
> 2. **Ersetze im Integral**:  
>    $$
>    \int 2x \cdot (x^2 + 1)^3 \, dx = \int u^3 \, du
>    $$
> 3. **Integriere**:  
>    $$
>    \int u^3 \, du = \frac{u^4}{4} + C
>    $$
> 4. **Rücksubstitution**:  
>    $$
>    \frac{u^4}{4} + C = \frac{(x^2 + 1)^4}{4} + C
>    $$

> [!example]+ **Beispiel 2: Trigonometrisches Integral**  
> Gegeben: \(\int \cos(3x) \, dx\)  
> 1. **Substitution wählen**: \( u = 3x \), also \( du = 3 \, dx \), \( dx = \frac{du}{3} \).  
> 2. **Ersetze im Integral**:  
>    $$
>    \int \cos(3x) \, dx = \int \cos(u) \cdot \frac{1}{3} \, du = \frac{1}{3} \int \cos(u) \, du
>    $$
> 3. **Integriere**:  
>    $$
>    \frac{1}{3} \int \cos(u) \, du = \frac{1}{3} \sin(u) + C
>    $$
> 4. **Rücksubstitution**:  
>    $$
>    \frac{1}{3} \sin(u) + C = \frac{1}{3} \sin(3x) + C
>    $$

> [!example]+ **Beispiel 3: Bestimmtes Integral**  
> Gegeben: \(\int_0^2 x \cdot (x^2 + 1)^2 \, dx\)  
> 1. **Substitution wählen**: \( u = x^2 + 1 \), also \( du = 2x \, dx \), \( x \, dx = \frac{du}{2} \).  
> 2. **Grenzen anpassen**:  
>    Für \( x = 0 \): \( u = 0^2 + 1 = 1 \).  
>    Für \( x = 2 \): \( u = 2^2 + 1 = 5 \).  
> 3. **Ersetze im Integral**:  
>    $$
>    \int_0^2 x \cdot (x^2 + 1)^2 \, dx = \int_1^5 u^2 \cdot \frac{1}{2} \, du = \frac{1}{2} \int_1^5 u^2 \, du
>    $$
> 4. **Integriere**:  
>    $$
>    \frac{1}{2} \int_1^5 u^2 \, du = \frac{1}{2} \cdot \left[ \frac{u^3}{3} \right]_1^5 = \frac{1}{2} \cdot \left( \frac{5^3}{3} - \frac{1^3}{3} \right)
>    $$
> 5. **Berechne das Ergebnis**:  
>    $$
>    \frac{1}{2} \cdot \frac{124}{3} = \frac{62}{3}
>    $$

---

## 💡 Tipps zur Substitution

1. **Wähle \( u \), sodass \( du \) im Integral vorhanden ist.**  
   Beispiel: Bei \( \int x \cdot (x^2 + 1)^n \, dx \) bietet sich \( u = x^2 + 1 \) an, da \( du = 2x \, dx \).

2. **Kontrolliere das Ergebnis durch Ableitung:**  
   Die Ableitung der Lösung sollte das ursprüngliche Integral ergeben.
