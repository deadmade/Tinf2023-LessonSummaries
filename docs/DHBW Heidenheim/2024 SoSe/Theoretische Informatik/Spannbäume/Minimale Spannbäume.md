## Definitionen

Ein **vollständiger Graph** ist ein ungerichteter, zusammenhängender Graph ohne Mehrfachkanten, in dem jeder Knoten mit jedem anderen Knoten durch eine Kante verbunden ist.

Ein **Spannbaum (Spanning Tree)** ist ein Teilgraph eines ungerichteten, zusammenhängenden Graphen, der ein Baum ist (zyklenfrei) und alle Knoten des Graphen enthält.

Ein **minimaler Spannbaum (Minimal Spanning Tree, MST)** ist ein Spannbaum eines kantengewichteten Graphen, der so gewählt ist, dass die Summe der Kantengewichte minimal ist. Es gibt keinen anderen Spannbaum im gleichen Graphen mit einem geringeren Gesamtgewicht.

## Formale Beschreibung

- Ein "Minimal Spanning Tree" (MST) ist ein Teilgraph eines kantengewichteten Graphen, bei dem die Gesamtlänge der Kanten, die alle Knoten verbinden, minimal ist.
- Gesucht wird ein Baum `T = (K, V')`, wobei `V'` die minimalen Verbindungen sind und `V' ⊆ V`.
- Gewichtsfunktion: `W(T) = ∑w(v)`, wobei `w` die Gewichte der Kanten sind.

## Beispiel eines minimalen Spannbaums

> [!EXAMPLE]- **C# Beispiel für die Darstellung eines minimalen Spannbaums:**
> ```csharp
> using System;
> using System.Collections.Generic;
> 
> class Graph
> {
>     public int Vertices { get; }
>     public List<(int, int, int)> Edges { get; } = new List<(int, int, int)>();
> 
>     public Graph(int vertices)
>     {
>         Vertices = vertices;
>     }
> 
>     public void AddEdge(int u, int v, int weight)
>     {
>         Edges.Add((u, v, weight));
>     }
> 
>     public void PrimMST()
>     {
>         var mstSet = new bool[Vertices];
>         var parent = new int[Vertices];
>         var key = new int[Vertices];
> 
>         for (int i = 0; i < Vertices; i++)
>         {
>             key[i] = int.MaxValue;
>             mstSet[i] = false;
>         }
> 
>         key[0] = 0;
>         parent[0] = -1;
> 
>         for (int count = 0; count < Vertices - 1; count++)
>         {
>             int u = MinKey(key, mstSet);
>             mstSet[u] = true;
> 
>             foreach (var (v1, v2, weight) in Edges)
>             {
>                 if (v1 == u || v2 == u)
>                 {
>                     int v = v1 == u ? v2 : v1;
>                     if (!mstSet[v] && weight < key[v])
>                     {
>                         parent[v] = u;
>                         key[v] = weight;
>                     }
>                 }
>             }
>         }
> 
>         PrintMST(parent);
>     }
> 
>     private int MinKey(int[] key, bool[] mstSet)
>     {
>         int min = int.MaxValue, minIndex = -1;
> 
>         for (int v = 0; v < Vertices; v++)
>         {
>             if (!mstSet[v] && key[v] < min)
>             {
>                 min = key[v];
>                 minIndex = v;
>             }
>         }
> 
>         return minIndex;
>     }
> 
>     private void PrintMST(int[] parent)
>     {
>         Console.WriteLine("Kante \t Gewicht");
>         for (int i = 1; i < Vertices; i++)
>             Console.WriteLine($"{parent[i]} - {i} \t {Edges.Find(e => (e.Item1 == i && e.Item2 == parent[i]) || (e.Item2 == i && e.Item1 == parent[i])).Item3}");
>     }
> }
> 
> class Program
> {
>     static void Main()
>     {
>         var graph = new Graph(4);
>         graph.AddEdge(0, 1, 10);
>         graph.AddEdge(0, 2, 6);
>         graph.AddEdge(0, 3, 5);
>         graph.AddEdge(1, 3, 15);
>         graph.AddEdge(2, 3, 4);
> 
>         graph.PrimMST();
>     }
> }
> ```


