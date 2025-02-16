![[Pasted image 20240827184256.png]]

## Bäume in Graphen

**Bäume** sind eine spezielle Art von Graphen, die zyklenfrei sind und eine hierarchische Struktur aufweisen. Jeder Knoten hat genau einen Vorgänger, außer der Wurzelknoten, der keinen Vorgänger hat. Zwischen der Wurzel und jedem Knoten gibt es genau einen Pfad.

### Wichtige Begriffe

- **Wurzelknoten**: Der oberste Knoten eines Baumes.
- **Elternknoten**: Ein Knoten, der Nachfolgerknoten (Kinderknoten) hat.
- **Kindknoten**: Knoten, die von einem Elternknoten abstammen.
- **Blattknoten**: Knoten ohne Nachfolger.
- **Innere Knoten**: Knoten, die sowohl Vorgänger als auch Nachfolger haben.
- **Teilbaum**: Ein Teil des gesamten Baumes, der selbst wieder ein Baum ist.

### Binäre Suchbäume (BST)
![[Pasted image 20240827184936.png]]
Ein **binärer Suchbaum** ist ein binärer Baum, in dem für jeden Knoten gilt:

- Die Werte der linken Nachfahren sind kleiner oder gleich dem Wert des Knotens.
- Die Werte der rechten Nachfahren sind größer oder gleich dem Wert des Knotens.

**Vorteile**:

- **Suchen**: O(log N) im besten Fall
- **Einfügen**: O(log N) im besten Fall
- **Löschen**: O(log N) im besten Fall

### Traversierung von Binären Bäumen

Es gibt verschiedene Traversierungsmethoden:

- **Inorder (L-W-R)**: Besucht zuerst den linken Teilbaum, dann den Knoten, und zuletzt den rechten Teilbaum.
- **Preorder (W-L-R)**: Besucht zuerst den Knoten, dann den linken und den rechten Teilbaum.
- **Postorder (L-R-W)**: Besucht zuerst den linken, dann den rechten Teilbaum und zuletzt den Knoten.
- **Level-order**: Besucht alle Knoten auf einer Ebene, bevor zur nächsten Ebene übergegangen wird.

### Einfügen in Binären Suchbäumen

Das Einfügen eines Wertes erfolgt an der Stelle, die den Regeln des binären Suchbaums entspricht, d.h., im linken Teilbaum, wenn der Wert kleiner ist, und im rechten Teilbaum, wenn der Wert größer ist.

### Löschen aus Binären Suchbäumen

Beim Löschen eines Knotens unterscheidet man drei Fälle:

- Der Knoten hat keine Kinder: Einfach löschen.
- Der Knoten hat ein Kind: Löschen und das Kind an die Stelle des Knotens setzen.
- Der Knoten hat zwei Kinder: Ersetzen durch den Nachfolgerknoten (der kleinste Knoten im rechten Teilbaum).