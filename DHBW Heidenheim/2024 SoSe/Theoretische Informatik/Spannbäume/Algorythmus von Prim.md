Der **Algorithmus von Prim** ist ein [[Gierige Algorithmen]], der darauf abzielt, den minimalen Spannbaum eines Graphen zu finden, indem er immer die Kante mit dem kleinsten Gewicht auswählt, die zu einem neuen Knoten führt. 

- Der Algorithmus startet an einem beliebigen Knoten und fügt sukzessive die kleinste Kante hinzu, die zu einem noch nicht besuchten Knoten führt.
- Dies wird so lange wiederholt, bis alle Knoten besucht wurden und der MST gebildet ist.

![[Pasted image 20240828082046.png]]

## Eigenschaften des Algorithmus:

- **Effizient**: Die Effizienz hängt von der effizienten Verwaltung der möglichen Kanten ab (z.B. durch Verwendung eines binären Min-Heaps).
- **Laufzeit**: Die Laufzeit beträgt `(Kanten + Knoten) * log(Knoten)`, was in der Praxis effizient ist für große Graphen.

### Anwendungsgebiete

- **Netzwerkdesign**: Aufbau von Netzwerken ohne Schleifen.
- **Transportplanung**: Effiziente Verbindungen wie Pipeline-Netzwerke oder Bewässerungssysteme.
- **Labyrinth-Erstellung**: Minimaler Spannbaum hilft bei der Konstruktion endlicher Labyrinthe.
- **Routenoptimierung**: Basis für Lösungen des "Travelling Salesman Problems".

## Ablauf
![[Pasted image 20240828082132.png]]
