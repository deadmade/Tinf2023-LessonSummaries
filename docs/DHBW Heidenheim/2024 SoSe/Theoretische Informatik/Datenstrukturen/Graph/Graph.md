Graphen sind vielseitige Datenstrukturen, die verwendet werden, um Beziehungen zwischen Datenobjekten darzustellen. Sie finden breite Anwendung in Bereichen wie sozialen Netzwerken, Transportnetzwerken, Internet-Routing und vielem mehr.

## Abbildung eines sozialen Netzwerks mit Graphen

Ein Beispiel für die Anwendung von Graphen ist die Modellierung eines sozialen Netzwerks. In einem sozialen Netzwerk werden Personen als Knoten (Nodes oder Vertices) und Freundschaften als Kanten (Edges) zwischen diesen Knoten dargestellt. Wenn Alice und Bob Freunde sind, gibt es eine ungerichtete Kante zwischen ihren Knoten. Dies bedeutet, dass die Beziehung in beide Richtungen besteht – wenn Alice mit Bob befreundet ist, ist Bob auch mit Alice befreundet.

### Ineffiziente Datenstrukturen für soziale Netzwerke

Eine naive Möglichkeit, Freundschaften in einem sozialen Netzwerk zu speichern, wäre ein zweidimensionales Array der Freundschaftslisten:

> [!example]- Beispiel einer Freundschaftsliste
> ```csharp
> char *friendships[] = {
>     {"Alice", "Bob"},
>     {"Bob", "Cynthia"},
>     {"Alice", "Diana"},
>     {"Bob", "Diana"},
>     {"Elise", "Fred"},
>     {"Diana", "Fred"},
>     {"Fred", "Alice"}
> };
> ```

Diese Darstellung ermöglicht es jedoch nicht, schnell alle Freunde einer bestimmten Person wie Alice zu finden, da alle Relationen durchsucht werden müssen. Dies führt zu einer Zeitkomplexität von O(N).

### Verwendung von Graphen zur Modellierung eines sozialen Netzwerks

Um dieses Problem zu lösen, verwenden wir Graphen, die speziell für die Darstellung von Beziehungen entwickelt wurden. In einem Graphen entspricht jede Person einem Knoten, und jede Freundschaft ist eine Kante zwischen zwei Knoten. Die Suche nach allen Freunden von Alice kann so in konstanter Zeit O(1) erfolgen, wenn die Datenstruktur optimal organisiert ist.
![[{42387CEE-8F9A-4823-BE7D-14EF5C7D6068}.png]]

> [!example]- Beispiel einer Graphenstruktur
> ```csharp
> var friends = new Dictionary<string, List<string>>()
> {
>     { "Alice", new List<string> { "Bob", "Diana", "Fred" } },
>     { "Bob", new List<string> { "Alice", "Cynthia", "Diana" } },
>     { "Cynthia", new List<string> { "Bob" } },
>     { "Diana", new List<string> { "Alice", "Bob", "Fred" } },
>     { "Elise", new List<string> { "Fred" } },
>     { "Fred", new List<string> { "Alice", "Diana", "Elise" } }
> };
> ```
> Mit dieser Struktur kann die Abfrage `friends["Alice"]` direkt alle Freunde von Alice zurückgeben.

## Eigenschaften von Graphen

Graphen haben mehrere Eigenschaften, die sie von anderen Datenstrukturen unterscheiden:

1. **Unterscheidung zwischen Knoten und Kanten**: Ein Knoten (vertex) repräsentiert ein Datenobjekt (z.B. eine Person), und eine Kante (edge) stellt eine Beziehung zwischen zwei Knoten dar (z.B. Freundschaft).
2. **Gerichtet vs. Ungerichtet**: In einem ungerichteten Graphen sind die Kanten symmetrisch (z.B. Freundschaften), während in einem gerichteten Graphen die Kanten eine Richtung haben (z.B. Follower-Beziehungen in sozialen Medien).
	![[{96D0DD68-7404-433C-B1FD-D98756F58B38}.png]]
3. **Gewichtet vs. Ungewichtet**: Kanten in einem gewichteten Graphen tragen zusätzliche Informationen wie Kosten oder Distanzen, während in einem ungewichteten Graphen alle Kanten gleich behandelt werden.
	   ![[{9199249A-49FF-4BBB-B392-CB165879DD51} 1.png]]
1. **Zyklen und Azyklizität**: Ein Zyklus in einem Graphen ist ein Pfad, der zu einem Knoten zurückkehrt, während azyklische Graphen keine solchen Rückkehrpfade enthalten (z.B. Bäume).
	   ![[{9A404CD6-D983-4014-8F1C-7AAFC1591A0D}.png]]

### Vergleich von Bäumen und Graphen

Bäume sind spezielle Graphen. Sie sind zyklenfrei und es gibt genau einen Pfad zwischen zwei Knoten. Im Gegensatz dazu können Graphen Zyklen haben und müssen nicht unbedingt vollständig verbunden sein. Ein Beispiel für einen Zyklus ist eine Freundschaftsbeziehung, die von Alice zu Diana, Diana zu Fred und dann Fred zurück zu Alice verläuft.

## Repräsentation von Graphen

Graphen können auf verschiedene Arten gespeichert werden, abhängig von den Anforderungen und der Struktur der Daten:

1. **Adjazenzliste**: Jede Liste speichert die Kantenliste eines Knotens (Nachbarn des Knotens).
	   ![[{198BF629-10FD-4438-BB08-168A3D9CAECD} 1.png]]
2. **Adjazenzmatrix**: Eine 2D-Matrix, bei der Zeilen und Spalten die Knoten darstellen und die Einträge die Existenz von Kanten angeben.
	   ![[{278D9418-99CB-4421-A814-29AB3E813743}.png]]
3. **Inzidenzmatrix**: Zeilen repräsentieren Knoten und Spalten repräsentieren Kanten.
	![[{4E954A86-0B06-4513-9E57-891493C8B612}.png]]

## Graphensuche

Die Suche in einem Graphen ist eine häufige Operation, die in verschiedenen Formen durchgeführt werden kann:

1. **Tiefensuche (DFS - Depth-First Search)**: Diese rekursive Suche beginnt bei einem Startknoten und erkundet so tief wie möglich entlang jeder Verzweigung, bevor sie zurückkehrt. Sie verwendet einen Stack zur Rückverfolgung.
   
   > [!example]- Algorithmus für Tiefensuche
   > ```csharp
   > void DepthFirstSearch(Dictionary<string, List<string>> graph, string start, HashSet<string> visited)
   > {
   >     if (visited.Contains(start)) return;
   >     visited.Add(start);
   >     Console.WriteLine(start);
   >     foreach (var neighbor in graph[start])
   >     {
   >         DepthFirstSearch(graph, neighbor, visited);
   >     }
   > }
   > ```
   
2. **Breitensuche (BFS - Breadth-First Search)**: Diese Suche durchläuft den Graphen in der Breite und verwendet eine Queue zur Verwaltung der Knoten. Sie eignet sich besonders gut zur Ermittlung der kürzesten Pfade in ungewichteten Graphen.
   
   > [!example]- Algorithmus für Breitensuche
   > ```csharp
   > void BreadthFirstSearch(Dictionary<string, List<string>> graph, string start)
   > {
   >     var visited = new HashSet<string>();
   >     var queue = new Queue<string>();
   >     visited.Add(start);
   >     queue.Enqueue(start);
   >
   >     while (queue.Count > 0)
   >     {
   >         var current = queue.Dequeue();
   >         Console.WriteLine(current);
   >         foreach (var neighbor in graph[current])
   >         {
   >             if (!visited.Contains(neighbor))
   >             {
   >                 visited.Add(neighbor);
   >                 queue.Enqueue(neighbor);
   >             }
   >         }
   >     }
   > }
   > ```

## Komplexität der Graphensuche

Die Effizienz von Suchalgorithmen in Graphen hängt von der Anzahl der Knoten (V - Vertices) und der Kanten (E - Edges) ab. Die Big-O-Notation für die Suche in einem Graphen lautet O(V + E), was bedeutet, dass sowohl alle Knoten als auch alle Kanten im schlimmsten Fall untersucht werden müssen.

## Anwendungen und Graph-Datenbanken

Graphen sind besonders nützlich in Szenarien, die starke Beziehungen oder Verbindungen zwischen Datenobjekten erfordern. Dazu gehören soziale Netzwerke, Verkehrswege und Netzwerk-Routing. Graph-Datenbanken wie Neo4j, ArangoDB und Apache Giraph sind optimierte Datenbanken, die speziell für die Arbeit mit Graphen entwickelt wurden und effiziente Abfragen sowie Modifikationen von Graphdaten ermöglichen.
****