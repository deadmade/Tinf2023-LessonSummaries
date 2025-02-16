Die **Huffman-Codierung** ist ein verlustfreies Komprimierungsverfahren, das von David A. Huffman entwickelt wurde. Sie wird verwendet, um die Anzahl der Bits zu minimieren, die zur Darstellung von Zeichen oder Symbolen benötigt werden, basierend auf ihrer **Häufigkeit** in einem Datensatz. Das Verfahren nutzt **binäre Bäume** zur Codierung und ist besonders effizient, wenn einige Zeichen deutlich häufiger vorkommen als andere.

---

## Schritte der Huffman-Codierung

1. **Häufigkeitsanalyse**: 
   - Ermitteln der Häufigkeit jedes Zeichens in den Daten.

2. **Sortierung der Zeichen**:
   - Die Zeichen werden nach ihrer Häufigkeit sortiert (häufigste Zeichen mit niedrigerer Priorität).

3. **Baumkonstruktion**:
   - Jedes Zeichen wird als Blatt in einem Binärbaum dargestellt.
   - Die zwei am seltensten vorkommenden Zeichen werden zu einem neuen Knoten zusammengefasst, dessen Häufigkeit der Summe der beiden entspricht.
   - Wiederholen des Vorgangs, bis nur noch ein Baum existiert.

4. **Zuordnung von Binärcodes**:
   - Jede Kante im Baum wird entweder mit `0` oder `1` markiert.
   - Um ein Zeichen zu codieren, folgt man vom Wurzelknoten des Baumes bis zum Blattknoten des Zeichens und liest die entsprechenden `0`- und `1`-Folgen ab.
   - Häufig vorkommende Zeichen erhalten kürzere Codes, seltene Zeichen längere.

---

## Beispiel

Angenommen, wir haben die Zeichenfolge **"ABRACADABRA"** mit folgenden Häufigkeiten:

| Zeichen | Häufigkeit |
|---------|------------|
| A       | 5          |
| B       | 2          |
| R       | 2          |
| C       | 1          |
| D       | 1          |

Auf Basis dieser Häufigkeiten wird der Huffman-Baum erstellt und folgende Codes zugeordnet:

- A: `0`
- B: `101`
- R: `100`
- C: `1110`
- D: `1111`

Die Zeichenfolge **"ABRACADABRA"** wird somit zu:
```
0 101 100 0 1110 0 1111 0 101 100 0
```


---

## Vorteile

- **Effiziente Komprimierung**: Optimal für die verlustfreie Komprimierung von Daten.
- **Verlustfrei**: Keine Informationen gehen bei der Komprimierung verloren.


