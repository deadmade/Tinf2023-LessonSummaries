## Einführung

Der **Algorithmus von Kruskal** ist ein gieriger Algorithmus, der 1956 von Joseph Kruskal in der Zeitschrift "Proceedings of the American Mathematical Society" veröffentlicht wurde. Er wird verwendet, um den **minimalen Spannbaum (MST)** eines ungerichteten, kantengewichteten und zusammenhängenden Graphen zu finden. Ein minimaler Spannbaum ist ein Teilgraph, der alle Knoten des Graphen umfasst und die Summe der Kantenkosten minimiert, ohne dabei Zyklen zu bilden.

### Funktionsweise des Algorithmus von Kruskal

Der Algorithmus von Kruskal arbeitet nach dem gierigen Prinzip und folgt diesen Schritten:

1. **Sortieren der Kanten**: Alle Kanten des Graphen werden nach ihren Gewichten in aufsteigender Reihenfolge sortiert.
2. **Initialisierung**: Beginnen Sie mit einem leeren Teilgraphen, der keine Kanten enthält.
3. **Kantenauswahl**: Durchlaufen Sie die sortierten Kanten und fügen Sie jede Kante hinzu, die zwei verschiedene Komponenten verbindet, ohne dabei einen Zyklus zu bilden.
4. **Abbruchbedingung**: Der Prozess endet, wenn der Teilgraph genau \(V-1\) Kanten enthält (wobei \(V\) die Anzahl der Knoten im Graphen ist).

![[Pasted image 20240828083030.png]]

> [!EXAMPLE]- Beispiel in C#
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class KruskalAlgorithm
> {
>     // Repräsentiert eine Kante mit ihren beiden Enden (u, v) und dem Gewicht
>     public class Edge : IComparable<Edge>
>     {
>         public int U, V, Weight;
>         public Edge(int u, int v, int weight)
>         {
>             U = u;
>             V = v;
>             Weight = weight;
>         }
>         
>         // Zum Sortieren der Kanten nach Gewicht
>         public int CompareTo(Edge compareEdge)
>         {
>             return this.Weight.CompareTo(compareEdge.Weight);
>         }
>     }
>
>     // Finden des Wurzelknotens des Knotens u
>     static int Find(int[] parent, int u)
>     {
>         if (parent[u] != u)
>             parent[u] = Find(parent, parent[u]);
>         return parent[u];
>     }
>
>     // Vereinigung zweier Teilbäume
>     static void Union(int[] parent, int[] rank, int u, int v)
>     {
>         int rootU = Find(parent, u);
>         int rootV = Find(parent, v);
>
>         if (rank[rootU] < rank[rootV])
>             parent[rootU] = rootV;
>         else if (rank[rootU] > rank[rootV])
>             parent[rootV] = rootU;
>         else
>         {
>             parent[rootV] = rootU;
>             rank[rootU]++;
>         }
>     }
>
>     // Anwendung des Kruskal-Algorithmus
>     public static void KruskalMST(int nodes, List<Edge> edges)
>     {
>         List<Edge> result = new List<Edge>();
>         int[] parent = new int[nodes];
>         int[] rank = new int[nodes];
>
>         // Initialisieren der Teilbäume
>         for (int i = 0; i < nodes; i++)
>         {
>             parent[i] = i;
>             rank[i] = 0;
>         }
>
>         // Sortieren der Kanten nach Gewicht
>         edges.Sort();
>
>         foreach (Edge edge in edges)
>         {
>             int u = Find(parent, edge.U);
>             int v = Find(parent, edge.V);
>
>             if (u != v) // Kein Zyklus gebildet
>             {
>                 result.Add(edge);
>                 Union(parent, rank, u, v);
>             }
>         }
>
>         // Ausgabe der minimalen Spannbaumkanten
>         Console.WriteLine("Kanten im minimalen Spannbaum:");
>         foreach (Edge edge in result)
>             Console.WriteLine($"{edge.U} -- {edge.V} == {edge.Weight}");
>     }
> }
> ```

### Unterschiede zwischen Kruskal und Prim

| Kriterium                  | Algorithmus von Prim                     | Algorithmus von Kruskal                     |
|----------------------------|------------------------------------------|---------------------------------------------|
| Startpunkt                 | Beliebiger Startknoten                   | Startkante durch minimale Kosten gegeben    |
| Kreisvermeidung            | Durch Konstruktion von möglichen Kanten  | Muss aktiv geprüft und vermieden werden     |
| Kostenakkumulation         | Kosten statistisch gleichverteilt        | Spätestmögliche Budgetbindung              |
| Parallelisierbarkeit       | Höhere Parallelisierbarkeit              | Wenig Möglichkeiten zur Parallelisierung    |

### Anwendungsgebiete

- **Netzwerkdesign**: Minimale Verkabelungskosten beim Aufbau von Netzwerken.
- **Straßen- und Bahnnetze**: Planung von kosteneffizienten Verbindungswegen.
- **Vermeidung von Zyklen in Computernetzwerken**: Umleitung von Datenpaketen ohne Schleifen.

### Fazit

Der Algorithmus von Kruskal ist ideal für Graphen mit wenigen Kanten (sparsame Graphen) und bietet eine effiziente Möglichkeit, minimale Spannbäume zu berechnen, insbesondere wenn die Kanten bereits sortiert oder mit einer Datenstruktur wie einer Prioritätswarteschlange organisiert sind.
