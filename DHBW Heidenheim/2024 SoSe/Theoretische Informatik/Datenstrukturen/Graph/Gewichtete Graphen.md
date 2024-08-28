Gewichtete Graphen fügen ihren Kanten weitere Informationen, sogenannte "Gewichte", hinzu. Diese Gewichte können verschiedene Formen annehmen, wie zum Beispiel Entfernungen, Kosten, Laufzeiten, Bandbreiten, etc., und werden verwendet, um den "kürzesten", "billigsten", "schnellsten" oder "besten" Weg zu bestimmen.

## Beispiel: Routenplanung zwischen Großstädten

Ein gewichteter Graph kann z.B. verwendet werden, um Routen zwischen Großstädten in den USA darzustellen, wobei das Gewicht die Distanz in Meilen zwischen den benachbarten Knoten (Städten) darstellt.

> [!example]- 📌 **Beispiel in C#:**
> ```csharp
> var graph = new Dictionary<string, Dictionary<string, int>>
> {
>     { "Atlanta", new Dictionary<string, int> { { "Denver", 1200 }, { "Chicago", 700 } } },
>     { "Denver", new Dictionary<string, int> { { "El Paso", 900 } } },
>     { "Chicago", new Dictionary<string, int> { { "El Paso", 1000 } } }
> };
> ```

Gewichtete Graphen können sowohl gerichtet als auch ungerichtet sein. In einem gerichteten Graphen kann eine Kante unterschiedliche Gewichte in entgegengesetzten Richtungen haben.

### Beispiel: Flugkosten zwischen Städten

Obwohl ein Flug von Dallas nach Toronto nur 138$ kostet, kostet die andere Richtung 216$.

![[{059904C8-2A97-4689-8B82-8C2AA49653DC}.png]]

## Problem des kürzesten Weges ("Shortest Path Problem")

Das Problem des kürzesten Weges in gewichteten Graphen besteht darin, den Pfad zu finden, der die niedrigsten Gesamtkosten zwischen zwei Knoten hat. Dies kann die geringste Entfernung, die geringsten Kosten, die kürzeste Zeit, etc. sein.

### Beispiel: Kosten für Flüge zwischen 5 verschiedenen Städten

Wir sind in Atlanta und wollen nach El Paso fliegen. Es gibt aber keinen Direktflug. Mögliche Verbindungen sind:

![[{C5B181FE-78A9-475C-8BA9-15B401BBDEE3}.png]]
- **Atlanta – Denver - El Paso:** 300$
- **Atlanta – Denver – Chicago – El Paso:** 280$!

Um die günstigste Route zu finden, könnte ein Algorithmus verwendet werden, der die billigste Strecke unabhängig von der Anzahl der Zwischenstopps bestimmt.

> [!example]- 📌 **Beispiel in C#:**
> ```csharp
> // Implementierung des Dijkstra-Algorithmus zur Berechnung der kürzesten Wege
> public Dictionary<string, int> Dijkstra(Dictionary<string, Dictionary<string, int>> graph, string start)
> {
>     var cheapestPrices = new Dictionary<string, int>();
>     var visited = new HashSet<string>();
>     cheapestPrices[start] = 0;
>
>     while (visited.Count < graph.Count)
>     {
>         var currentNode = cheapestPrices
>             .Where(n => !visited.Contains(n.Key))
>             .OrderBy(n => n.Value)
>             .First().Key;
>
>         var currentPrice = cheapestPrices[currentNode];
>         foreach (var neighbor in graph[currentNode])
>         {
>             var newPrice = currentPrice + neighbor.Value;
>             if (!cheapestPrices.ContainsKey(neighbor.Key) || newPrice < cheapestPrices[neighbor.Key])
>             {
>                 cheapestPrices[neighbor.Key] = newPrice;
>             }
>         }
>         visited.Add(currentNode);
>     }
>
>     return cheapestPrices;
> }
> ```

## Algorithmus von Dijkstra

Der Dijkstra-Algorithmus, formuliert von Edsger Dijkstra im Jahr 1959, ist einer der bekanntesten Algorithmen zur Lösung des kürzesten Weges in gewichteten Graphen. Der Algorithmus verwendet eine Prioritätswarteschlange, um den Knoten mit dem derzeit niedrigsten Preis auszuwählen und iterativ den billigsten Preis zu jedem anderen Knoten zu bestimmen.

### Schritte des Dijkstra-Algorithmus

1. Initialisiere die `Cheapest-Price-Table` mit dem Startknoten und setze alle anderen auf unendlich (`∞`).
2. Prüfe die Preise vom Startknoten zu jedem benachbarten Knoten.
3. Wenn der Preis zu einem Nachbarknoten günstiger ist als der aktuelle Preis in der `Cheapest-Price-Table` (oder der Nachbar ist noch nicht in der Tabelle enthalten):
   - Aktualisiere die `Cheapest-Price-Table`, um den günstigeren Preis aufzunehmen.
   - Aktualisiere die `Cheapest-Previous-Stopover-City-Table`, um die vorhergehende Stadt zu speichern.
4. Besuche dann den noch nicht besuchten Knoten mit dem geringsten Preis zum Startknoten und mache ihn zum "currentNode".
5. Wiederhole die Schritte 2-4, bis jeder Knoten besucht wurde.

### Effizienz des Dijkstra-Algorithmus

Die Effizienz des Dijkstra-Algorithmus hängt von der verwendeten Datenstruktur ab:
- Mit einem einfachen Array für unbesuchte Knoten: O(V^2) im schlimmsten Fall (jeder Knoten ist mit jedem verbunden).
- Mit einer Prioritätswarteschlange für unbesuchte Knoten: leicht bessere Effizienz.

In jeder Implementierung erreicht der Dijkstra-Algorithmus jedoch das gewünschte Ziel, den kürzesten oder günstigsten Weg zu finden.
