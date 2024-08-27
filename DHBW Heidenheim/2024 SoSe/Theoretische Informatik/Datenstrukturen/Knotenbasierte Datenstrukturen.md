Knotenbasierte Datenstrukturen sind Datenstrukturen, die aus Knoten bestehen. Jeder Knoten speichert in der Regel einen Datenwert und Verweise (Referenzen) auf andere Knoten. Diese Strukturen werden häufig verwendet, um Elemente in einer bestimmten Reihenfolge oder Hierarchie zu organisieren und zu speichern.

> [!info] Typen von knotenbasierten Datenstrukturen

## 1. Verkettete Listen (Linked Lists)

Verkettete Listen bestehen aus Knoten, wobei jeder Knoten einen Datenwert und einen Verweis (Pointer) auf den nächsten Knoten enthält. Es gibt verschiedene Arten von verketteten Listen:

- **Einfach verkettete Liste**: Jeder Knoten verweist nur auf den nächsten Knoten.
- **Doppelt verkettete Liste**: Jeder Knoten verweist auf den vorherigen und den nächsten Knoten.
- **Zirkuläre Liste**: Die letzte Knoten verweist auf den ersten Knoten, wodurch eine Schleife entsteht.

> [!example] Beispiel einer einfach verketteten Liste in C#
> ```csharp
> public class Node
> {
>     public int Data;
>     public Node Next;
> 
>     public Node(int data)
>     {
>         Data = data;
>         Next = null;
>     }
> }
> 
> public class LinkedList
> {
>     private Node head;
> 
>     public void Add(int data)
>     {
>         Node newNode = new Node(data);
>         if (head == null)
>         {
>             head = newNode;
>         }
>         else
>         {
>             Node current = head;
>             while (current.Next != null)
>             {
>                 current = current.Next;
>             }
>             current.Next = newNode;
>         }
>     }
> 
>     public void PrintList()
>     {
>         Node current = head;
>         while (current != null)
>         {
>             Console.WriteLine(current.Data);
>             current = current.Next;
>         }
>     }
> }
> ```

## 2. Bäume (Trees)

Bäume bestehen aus Knoten, wobei jeder Knoten einen Datenwert und Verweise auf untergeordnete Knoten (Kinder) hat. Ein bekannter Typ ist der **Binärbaum**, bei dem jeder Knoten maximal zwei Kinder hat: ein linkes und ein rechtes.

> [!example] Beispiel eines Binärbaums in C#
> ```csharp
> public class TreeNode
> {
>     public int Data;
>     public TreeNode Left;
>     public TreeNode Right;
> 
>     public TreeNode(int data)
>     {
>         Data = data;
>         Left = null;
>         Right = null;
>     }
> }
> 
> public class BinaryTree
> {
>     public TreeNode Root;
> 
>     public void Insert(int data)
>     {
>         if (Root == null)
>         {
>             Root = new TreeNode(data);
>         }
>         else
>         {
>             InsertRec(Root, new TreeNode(data));
>         }
>     }
> 
>     private void InsertRec(TreeNode root, TreeNode newNode)
>     {
>         if (newNode.Data < root.Data)
>         {
>             if (root.Left == null)
>                 root.Left = newNode;
>             else
>                 InsertRec(root.Left, newNode);
>         }
>         else
>         {
>             if (root.Right == null)
>                 root.Right = newNode;
>             else
>                 InsertRec(root.Right, newNode);
>         }
>     }
> }
> ```

## 3. Graphen (Graphs)

Graphen sind allgemeinere Formen von knotenbasierten Strukturen, bei denen Knoten durch Kanten miteinander verbunden sind. Graphen können gerichtet oder ungerichtet sowie gewichtet oder ungewichtet sein.

> [!example] Beispiel eines ungerichteten Graphen in C#
> ```csharp
> public class Graph
> {
>     private int Vertices;
>     private List<int>[] adjList;
> 
>     public Graph(int vertices)
>     {
>         Vertices = vertices;
>         adjList = new List<int>[vertices];
>         for (int i = 0; i < vertices; i++)
>         {
>             adjList[i] = new List<int>();
>         }
>     }
> 
>     public void AddEdge(int source, int destination)
>     {
>         adjList[source].Add(destination);
>         adjList[destination].Add(source); // Für ungerichteten Graph
>     }
> 
>     public void PrintGraph()
>     {
>         for (int i = 0; i < Vertices; i++)
>         {
>             Console.Write($"Knoten {i}:");
>             foreach (var vertex in adjList[i])
>             {
>                 Console.Write($" -> {vertex}");
>             }
>             Console.WriteLine();
>         }
>     }
> }
> ```

> [!tip] Vorteile knotenbasierter Datenstrukturen
>
> - **Flexibilität**: Bieten dynamische Speicherverwaltung und können effizient auf Einfügungen und Löschungen reagieren.
> - **Effiziente Speicherverwaltung**: Speicher wird nur bei Bedarf verwendet.
> - **Anwendungsfreundlich für bestimmte Szenarien**: Besonders geeignet für hierarchische Datenstrukturen wie Dateisysteme oder für die Darstellung von Netzwerken.

## Komlexität Suche
- Worst-Case: O(N) -> Arrays O(1) Bei der Suche

## Komlexität Einfügen
- Verkettete Listen benötigen beim einfügen Überall lediglich O(1), da lediglich der Pointer geändert werden muss
- ![[Pasted image 20240827183720.png]]

## Komplexität Löschen
![[Pasted image 20240827183815.png]]