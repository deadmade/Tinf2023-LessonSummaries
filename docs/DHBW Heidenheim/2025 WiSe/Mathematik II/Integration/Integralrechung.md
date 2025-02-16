## 📘 Grundlagen der Integralrechnung
Die Integralrechnung ist ein Teilgebiet der Analysis, das sich mit der Berechnung von Flächeninhalten, Volumina und anderen Größen befasst. Sie ergänzt die Differentialrechnung und basiert auf der Idee der **Aufleitung** (Integration).

### 🧩 Zusammenhang zwischen Ableitung und Aufleitung
- Die Ableitung gibt die Steigung einer Funktion an.
- Die Aufleitung ist der umgekehrte Prozess: Sie bestimmt die Funktion, deren Ableitung gegeben ist.

**Beispiel**  
Sei $f(x) = 2x$.  
Die Stammfunktion $F(x)$ ist eine Funktion, deren Ableitung $f(x)$ ergibt. Hier gilt:  
$$F(x) = x^2 + C$$  
wobei $C$ eine Konstante ist.

---

## 🎯 Unbestimmtes Integral
Das **unbestimmte Integral** repräsentiert die Familie aller Stammfunktionen. Es wird geschrieben als:  
$$\int f(x) \, dx$$  

### 🔑 Wichtige Regeln
1. **Potenzregel**  
   $$\int x^n \, dx = \frac{x^{n+1}}{n+1} + C, \quad \text{für } n \neq -1$$

2. **Summenregel**  
   $$\int \big(f(x) + g(x)\big) \, dx = \int f(x) \, dx + \int g(x) \, dx$$

3. **Konstante vorziehen**  
   $$\int c \cdot f(x) \, dx = c \cdot \int f(x) \, dx$$

---

## 🧮 Beispiele: Unbestimmtes Integral
> [!example]+ Beispiel 1: Potenzregel  
> $$\int x^3 \, dx = \frac{x^{3+1}}{3+1} + C = \frac{x^4}{4} + C$$

> [!example]+ Beispiel 2: Konstante vorziehen  
> $$\int 3x^2 \, dx = 3 \cdot \int x^2 \, dx = 3 \cdot \frac{x^{2+1}}{2+1} + C = x^3 + C$$

---

## 📏 Bestimmtes Integral
Das **bestimmte Integral** berechnet den exakten Flächeninhalt unter einer Kurve zwischen zwei Grenzen $a$ und $b$. Es wird geschrieben als:  
$$\int_a^b f(x) \, dx$$  

### 🚦 Berechnung
1. Berechne die Stammfunktion $F(x)$.
2. Setze die Grenzen $a$ (untere Grenze) und $b$ (obere Grenze) ein:
   $$\int_a^b f(x) \, dx = F(b) - F(a)$$

---

## 🧮 Beispiele: Bestimmtes Integral
> [!example]+ Beispiel 1: Fläche unter $f(x) = x^2$ von $x = 1$ bis $x = 3$  
> $$\int_1^3 x^2 \, dx = \left[ \frac{x^3}{3} \right]_1^3 = \frac{3^3}{3} - \frac{1^3}{3} = 9 - \frac{1}{3} = \frac{26}{3}$$

---

## 🛠️ Nützliche Tricks und Regeln
### 📌 Produktregel (Integration durch Substitution)
Falls $f(x)$ in der Form $g(h(x)) \cdot h'(x)$ vorliegt:
$$\int g(h(x)) \cdot h'(x) \, dx = \int g(u) \, du$$

**Beispiel**  
$$\int 2x \cdot (x^2 + 1)^3 \, dx$$  
Substitution: $u = x^2 + 1$, dann $du = 2x \, dx$.  
$$\int (x^2 + 1)^3 \cdot 2x \, dx = \int u^3 \, du = \frac{u^4}{4} + C = \frac{(x^2 + 1)^4}{4} + C$$



