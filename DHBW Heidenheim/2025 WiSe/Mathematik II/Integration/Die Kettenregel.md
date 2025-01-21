Die **Kettenregel** ist eine Methode zur Differentiation von zusammengesetzten Funktionen. Sie ermöglicht es, die Ableitung einer Funktion zu berechnen, die aus der Verkettung von zwei (oder mehr) Funktionen besteht.

---

## 📘 Grundidee

Wenn eine Funktion \( f(x) \) als Verkettung von zwei Funktionen geschrieben werden kann, z. B.:

$$
f(x) = g(h(x))
$$

dann lautet die Ableitung von \( f(x) \):

$$
f'(x) = g'(h(x)) \cdot h'(x)
$$

Die Kettenregel besagt also, dass man:
1. Zuerst die äußere Funktion \( g \) ableitet und
2. die innere Funktion \( h(x) \) unverändert einsetzt, dann
3. die innere Funktion \( h(x) \) ableitet.

---

## 🚦 Vorgehen bei der Anwendung der Kettenregel

1. **Zerlege die Funktion**: Identifiziere die äußere und die innere Funktion.
2. **Berechne die Ableitung der äußeren Funktion**: Leite die äußere Funktion \( g(u) \) ab, wobei \( u = h(x) \).
3. **Berechne die Ableitung der inneren Funktion**: Leite \( h(x) \) ab.
4. **Multipliziere die Ableitungen**: Kombiniere die Ergebnisse.

---

## 🧮 Beispiele

> [!example]+ Beispiel 1: Quadratische Verkettung  
> Gegeben: \( f(x) = (x^2 + 3)^5 \)  
> 
> 1. **Äußere Funktion**: \( g(u) = u^5 \), innere Funktion: \( h(x) = x^2 + 3 \)  
> 2. **Ableitung der äußeren Funktion**: \( g'(u) = 5u^4 \)  
> 3. **Ableitung der inneren Funktion**: \( h'(x) = 2x \)  
> 4. **Kombination**:  
>    $$
>    f'(x) = g'(h(x)) \cdot h'(x) = 5(x^2 + 3)^4 \cdot 2x
>    $$
> 5. **Vereinfachung**:  
>    $$
>    f'(x) = 10x (x^2 + 3)^4
>    $$

> [!example]+ Beispiel 2: Trigonometrische Verkettung  
> Gegeben: \( f(x) = \sin(3x) \)  
> 
> 1. **Äußere Funktion**: \( g(u) = \sin(u) \), innere Funktion: \( h(x) = 3x \)  
> 2. **Ableitung der äußeren Funktion**: \( g'(u) = \cos(u) \)  
> 3. **Ableitung der inneren Funktion**: \( h'(x) = 3 \)  
> 4. **Kombination**:  
>    $$
>    f'(x) = g'(h(x)) \cdot h'(x) = \cos(3x) \cdot 3
>    $$
> 5. **Vereinfachung**:  
>    $$
>    f'(x) = 3 \cos(3x)
>    $$

> [!example]+ Beispiel 3: Natürlicher Logarithmus  
> Gegeben: \( f(x) = \ln(x^2 + 1) \)  
> 
> 1. **Äußere Funktion**: \( g(u) = \ln(u) \), innere Funktion: \( h(x) = x^2 + 1 \)  
> 2. **Ableitung der äußeren Funktion**: \( g'(u) = \frac{1}{u} \)  
> 3. **Ableitung der inneren Funktion**: \( h'(x) = 2x \)  
> 4. **Kombination**:  
>    $$
>    f'(x) = g'(h(x)) \cdot h'(x) = \frac{1}{x^2 + 1} \cdot 2x
>    $$
> 5. **Vereinfachung**:  
>    $$
>    f'(x) = \frac{2x}{x^2 + 1}
>    $$

---

## 💡 Tipps zur Kettenregel

1. **Identifiziere klar die äußere und innere Funktion.**  
   Beispiel: Bei \( (x^3 + 2)^4 \) ist die äußere Funktion \( g(u) = u^4 \) und die innere \( h(x) = x^3 + 2 \).

2. **Prüfe deine Ableitung durch Rückrechnung.**  
   Leite die Lösung zurück, um sicherzustellen, dass sie die ursprüngliche Funktion ergibt.

3. **Arbeite Schritt für Schritt.**  
   Bei komplexen Verkettungen (mehr als zwei Ebenen) leite von außen nach innen ab.

