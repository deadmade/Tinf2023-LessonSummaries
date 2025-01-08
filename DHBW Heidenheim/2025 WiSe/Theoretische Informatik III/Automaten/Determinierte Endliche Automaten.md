
Das ein Automat den Zustand wechselt

Muss ein bestimmter Trigger ausgelöst werden

Ein Determinierter Automat, hat immer einen eindeutigen Zustand

Beispiel Schranke

## Transduktor
![[Pasted image 20250107153458.png]]
Regeln: 
- Beziehungen müssen immer eine Eingabe haben, Ausgabe sind optional
- Der Anfangszustand muss mit -> Markiert werden
- Anfang oder Ende muss nochmal umkreist werden

## Definitionen

| Symbohl       | Beschreibung                               |
| ------------- | ------------------------------------------ |
| Q             | Menge aller Zustände                       |
| $\varepsilon$ | Eingabealphabet                            |
| $\gamma$      | Übergan Funktion<br>$Q x \varepsilon -> Q$ |
| F             | Menge der finalen Zustände<br>$F \leq Q$   |
| $q_0$         | Startzustand                               |

## Biespiel
$L_Biergarten = {Bier, Brot, Brezel, Butter}$
$\sum Biergarten = {B,I,E,R,O,T,Z, L,U}$
![[Pasted image 20250107174021.png]]