Ein binärer Heap ist ein spezieller binärer Baum, jedoch kein binärer Suchbaum. Es gibt zwei Typen von binären Heaps:

1. **Max-Heap**: Der Wert jedes Knotens ist größer als oder gleich den Werten seiner Kinder.
2. **Min-Heap**: Der Wert jedes Knotens ist kleiner als oder gleich den Werten seiner Kinder.

Ein binärer Heap muss folgende Bedingungen erfüllen:

- **Heap-Bedingung**: Der Wert jedes Knotens muss entweder größer/gleich (Max-Heap) oder kleiner/gleich (Min-Heap) als die Werte seiner Kinder sein.
- **Heap-Vollständigkeit**: Der Baum muss vollständig sein, d.h. alle Ebenen sind vollständig gefüllt, mit Ausnahme der letzten Ebene, die von links nach rechts gefüllt ist.
![[Pasted image 20240828080136.png]]

## Eigenschaften eines binären Heaps

- Ein binärer Heap ist anders strukturiert als ein binärer Suchbaum. Im binären Suchbaum ist jedes rechte Kind größer als sein Vorgänger. Im binären Heap gibt es keine solche Regel – es geht nur um die Heap-Bedingung.
- Ein binärer Heap ist immer vollständig und schwach geordnet im Vergleich zu einem binären Suchbaum, der stark geordnet ist.
- Der Wurzelknoten ist immer der größte (bei Max-Heap) oder kleinste (bei Min-Heap) Knoten im Baum.
- Der letzte Knoten ist der rechteste Knoten in der untersten Ebene.

## Operationen auf einem binären Heap

### Einfügen

1. Ein neuer Knoten wird am nächsten freien Platz auf der untersten Ebene eingefügt.
2. Vergleiche den neuen Knoten mit seinem Elternknoten.
3. Wenn der neue Knoten größer (Max-Heap) oder kleiner (Min-Heap) als sein Elternknoten ist, tausche sie und wiederhole den Vorgang.
4. Der Prozess endet, wenn die Heap-Bedingung erfüllt ist.
![[Pasted image 20240828080242.png]]

> [!EXAMPLE]- **C# Beispiel für das Einfügen in einen Max-Heap:**
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class MaxHeap
> {
>     private List<int> heap = new List<int>();
>
>     public void Insert(int value)
>     {
>         heap.Add(value);
>         HeapifyUp(heap.Count - 1);
>     }
>
>     private void HeapifyUp(int index)
>     {
>         while (index > 0)
>         {
>             int parentIndex = (index - 1) / 2;
>             if (heap[index] <= heap[parentIndex])
>                 break;
>
>             // Swap
>             int temp = heap[index];
>             heap[index] = heap[parentIndex];
>             heap[parentIndex] = temp;
>
>             index = parentIndex;
>         }
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         MaxHeap maxHeap = new MaxHeap();
>         maxHeap.Insert(40);
>         maxHeap.Insert(20);
>         maxHeap.Insert(30);
>         maxHeap.Insert(10);
>         maxHeap.Insert(25);
>         maxHeap.Insert(35);
>         maxHeap.Insert(15);
>
>         Console.WriteLine("Elemente wurden erfolgreich in den Heap eingefügt.");
>     }
> }
> ```

### Entnehmen

1. Entferne den Wurzelknoten (das Element mit der höchsten Priorität).
2. Ersetze den Wurzelknoten mit dem letzten Knoten im Heap.
	![[Pasted image 20240828080441.png]]
3. Versickere den neuen Wurzelknoten nach unten, bis die Heap-Bedingung wieder erfüllt ist.
![[Pasted image 20240828080450.png]]


> [!EXAMPLE]- **C# Beispiel für das Entfernen aus einem Max-Heap:**
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class MaxHeap
> {
>     private List<int> heap = new List<int>();
>
>     public void Insert(int value)
>     {
>         heap.Add(value);
>         HeapifyUp(heap.Count - 1);
>     }
>
>     public int ExtractMax()
>     {
>         if (heap.Count == 0)
>             throw new InvalidOperationException("Heap ist leer.");
>
>         int maxValue = heap[0];
>         heap[0] = heap[heap.Count - 1];
>         heap.RemoveAt(heap.Count - 1);
>
>         HeapifyDown(0);
>         return maxValue;
>     }
>
>     private void HeapifyUp(int index)
>     {
>         while (index > 0)
>         {
>             int parentIndex = (index - 1) / 2;
>             if (heap[index] <= heap[parentIndex])
>                 break;
>
>             int temp = heap[index];
>             heap[index] = heap[parentIndex];
>             heap[parentIndex] = temp;
>
>             index = parentIndex;
>         }
>     }
>
>     private void HeapifyDown(int index)
>     {
>         int lastIndex = heap.Count - 1;
>         while (index < lastIndex)
>         {
>             int leftChildIndex = 2 * index + 1;
>             int rightChildIndex = 2 * index + 2;
>             int largestIndex = index;
>
>             if (leftChildIndex <= lastIndex && heap[leftChildIndex] > heap[largestIndex])
>                 largestIndex = leftChildIndex;
>
>             if (rightChildIndex <= lastIndex && heap[rightChildIndex] > heap[largestIndex])
>                 largestIndex = rightChildIndex;
>
>             if (largestIndex == index)
>                 break;
>
>             int temp = heap[index];
>             heap[index] = heap[largestIndex];
>             heap[largestIndex] = temp;
>
>             index = largestIndex;
>         }
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         MaxHeap maxHeap = new MaxHeap();
>         maxHeap.Insert(40);
>         maxHeap.Insert(20);
>         maxHeap.Insert(30);
>         maxHeap.Insert(10);
>         maxHeap.Insert(25);
>         maxHeap.Insert(35);
>         maxHeap.Insert(15);
>
>         Console.WriteLine($"Maximales Element entfernt: {maxHeap.ExtractMax()}");
>         Console.WriteLine($"Maximales Element entfernt: {maxHeap.ExtractMax()}");
>     }
> }
> ```
#

## Finden des letzten Knotens in einem binären Heap

Ein binärer Heap wird oft als Array dargestellt, was die Verwaltung und die effiziente Suche nach Knoten erleichtert. In einem binären Heap ist der "letzte Knoten" der rechteste Knoten in der untersten Ebene des Baums. Dies ist wichtig, weil der letzte Knoten häufig bei Operationen wie dem Einfügen und Entfernen verwendet wird.

### Darstellung eines Heaps als Array

Ein vollständiger binärer Heap kann einfach als Array dargestellt werden. Bei dieser Darstellung hat jeder Knoten in der Baumstruktur eine entsprechende Position im Array. Der Index jedes Knotens im Array folgt einer spezifischen Ordnung:

1. **Wurzelknoten**: Index 0
2. **Linkes Kind eines Knotens**: Bei Index `i` hat das linke Kind den Index `2 * i + 1`.
3. **Rechtes Kind eines Knotens**: Bei Index `i` hat das rechte Kind den Index `2 * i + 2`.
4. **Elternknoten eines Knotens**: Bei Index `i` hat der Elternknoten den Index `(i - 1) / 2`.

### Finden des letzten Knotens

Der letzte Knoten in einem binären Heap ist einfach das letzte Element im Array, das den Heap darstellt. Der Grund dafür ist, dass der Heap vollständig ist und alle Ebenen vollständig gefüllt sind, außer möglicherweise der letzten Ebene. Daher:

- **Der letzte Knoten** befindet sich am letzten Index des Arrays.

#### Schritte zum Finden des letzten Knotens:

1. **Identifiziere das Array, das den Heap darstellt.**
2. **Bestimme die Länge des Arrays** (d.h. die Anzahl der Elemente im Heap).
3. **Der Index des letzten Knotens** ist einfach `array.Length - 1`.

![[Pasted image 20240828081001.png]]

### Beispiel in C#

> [!EXAMPLE]- **C# Beispiel zum Finden des letzten Knotens in einem Max-Heap:**
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class MaxHeap
> {
>     private List<int> heap = new List<int>();
>
>     public void Insert(int value)
>     {
>         heap.Add(value);
>         HeapifyUp(heap.Count - 1);
>     }
>
>     // Methode, um den letzten Knoten zu finden
>     public int FindLastNode()
>     {
>         if (heap.Count == 0)
>             throw new InvalidOperationException("Heap ist leer.");
>
>         return heap[heap.Count - 1]; // Der letzte Knoten im Array
>     }
>
>     private void HeapifyUp(int index)
>     {
>         while (index > 0)
>         {
>             int parentIndex = (index - 1) / 2;
>             if (heap[index] <= heap[parentIndex])
>                 break;
>
>             int temp = heap[index];
>             heap[index] = heap[parentIndex];
>             heap[parentIndex] = temp;
>
>             index = parentIndex;
>         }
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         MaxHeap maxHeap = new MaxHeap();
>         maxHeap.Insert(40);
>         maxHeap.Insert(20);
>         maxHeap.Insert(30);
>         maxHeap.Insert(10);
>         maxHeap.Insert(25);
>         maxHeap.Insert(35);
>         maxHeap.Insert(15);
>
>         Console.WriteLine($"Letzter Knoten im Heap: {maxHeap.FindLastNode()}");
>     }
> }
> ```

## Effizienz von Heaps

- Die Zeitkomplexität für das Einfügen und Entnehmen in einem binären Heap beträgt **O(log N)**, da die Operationen nur entlang des Pfades von der Wurzel zur tiefsten Ebene erfolgen.
- Die schwache Ordnung der Heaps ist ideal für die Verwendung in **Priority Queues**, wo die Operationen **Einfügen** und **Entnehmen** beide schnell sein müssen.

## Heaps für [[Prioritäts-Queue]]

Eine Priority Queue ist eine Warteschlange, die auf der Priorität der Elemente basiert. Heaps sind eine ausgezeichnete Wahl zur Implementierung von Priority Queues, da sie sowohl effizientes Einfügen als auch Entfernen von Elementen ermöglichen. Ein sortiertes Array wäre ineffizienter, da das Einfügen **O(N)** und das Entfernen **O(1)** erfordert, wohingegen ein Heap beide Operationen in **O(log N)** ausführt.
