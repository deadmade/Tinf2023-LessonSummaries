![](https://youtu.be/ZRPoEKHXTJg)

**MergeSort** ist ein effizienter, vergleichsbasierter Sortieralgorithmus, der nach dem Divide-and-Conquer-Prinzip arbeitet. Er ist besonders geeignet für die externe Sortierung großer Datenmengen und bekannt für seine Stabilität und Parallelisierbarkeit.

## Grundidee

1. **Teilen**: Der Eingangsstapel (die zu sortierende Liste) wird in zwei möglichst gleich große Teile geteilt.
2. **Rekursive Sortierung**: Jeder Teil wird einem Helfer gegeben, der das gleiche Verfahren rekursiv anwendet.
3. **Mischen**: Sobald die Helfer die sortierten Teillisten zurückgeben, werden diese im "Reißverschlussprinzip" (Merge) zu einer einzigen sortierten Gesamtliste zusammengefügt.

> [!info]- 📌 **Veranschaulichung**: 
> Man wartet, bis beide Hälften sortiert sind, und kombiniert sie dann, indem man die jeweils kleinste verbleibende Karte (Element) auswählt und zum Ergebnisstapel (sortierte Liste) hinzufügt.

![[Pasted image 20240828184427.png]]

## Eigenschaften von MergeSort

- **Divide & Conquer**: Der Algorithmus teilt das Problem in kleinere Unterprobleme, löst diese rekursiv und kombiniert die Lösungen.
- **Vergleichsbasiert**: Die Sortierung erfolgt durch Vergleiche der Elemente.
- **Zeitkomplexität**: O(n log(n)) im Worst-Case.
- **Speicherbedarf**: O(n) zusätzlich — MergeSort ist kein in-place Algorithmus, da er zusätzlichen Speicher benötigt, um die Teillisten zu speichern.
- **Stabil**: Die Reihenfolge gleichwertiger Elemente bleibt erhalten.
- **Parallelisierbar**: Teile des Algorithmus können parallel ausgeführt werden, was die Performance auf Mehrkernsystemen steigern kann.

## Implementierung

MergeSort kann sowohl für interne als auch für externe Sortierungen verwendet werden:

### Interne Sortierung

- Der gesamte Datensatz passt in den Hauptspeicher und wird dort sortiert.

### Externe Sortierung (External Memory MergeSort)

- **Blöcke im Hauptspeicher sortieren**: Einzelne Blöcke von Daten werden in den Hauptspeicher geladen, dort sortiert und wieder auf den externen Speicher (z.B. Dateien) geschrieben.
- **K-Way-Merges**: Die sortierten Blöcke werden dann durch K-Way-Merges kombiniert, wobei die Daten sofort zurückgeschrieben werden.

## Rekursionskosten und Speicherbedarf

Obwohl MergeSort selbst O(n) zusätzlichen Speicherplatz benötigt, sind bei der Implementierung rekursive Aufrufe erforderlich, die Platz auf dem Stack belegen. Diese versteckten Kosten können insbesondere bei großen Datenmengen oder tiefen Rekursionen (z.B. bei einem sehr langen Sortierprozess) eine Rolle spielen.

### Beispiel: Rekursive Funktionen

Eine einfache rekursive Funktion, die eine Zahl von N herunterzählt, hat eine Zeitkomplexität von O(N), benötigt aber auch O(N) Speicherplatz für den Aufrufstack. Der Speicherbedarf wächst mit der Anzahl der rekursiven Aufrufe.

- **Stack Limits**: Die maximale Stacktiefe ist oft begrenzt; zu viele rekursive Aufrufe führen zu einem Stack Overflow.

### Vergleich mit nicht-rekursiven Ansätzen

Ein Ansatz mit einer einfachen Schleife, der die gleiche Aufgabe erfüllt (z.B. den Countdown einer Zahl), hat eine Speicherkomplexität von O(1), da keine zusätzlichen Stack-Speicher benötigt werden.

## Speicherbedarf von Sortieralgorithmen

Unterschiedliche Sortieralgorithmen haben unterschiedliche Speicheranforderungen, die oft in Bezug auf den verwendeten Speicher betrachtet werden:

- **Intern (In-Place)**: Der Algorithmus benötigt nur eine konstante Menge an zusätzlichem Speicher. Alle Datenelemente sind bekannt und im Hauptspeicher verfügbar.
- **Extern**: Der Algorithmus muss mit Daten umgehen, die nicht vollständig in den Hauptspeicher passen. Nur ein Teil der Daten ist zu einem Zeitpunkt bekannt, und der Algorithmus verwendet externe Speicher (wie Festplatten), um die Daten zu sortieren.
