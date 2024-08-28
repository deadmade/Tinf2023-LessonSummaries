Eine Prioritäts-Queue ist eine spezielle Art von Queue (Warteschlange), in der die Elemente nach ihrer Priorität geordnet sind, anstatt einfach nur in der Reihenfolge ihres Eintreffens. Eine Prioritäts-Queue kann mithilfe verschiedener Datenstrukturen implementiert werden, wobei ein **Heap** besonders effizient ist, wenn es darum geht, das größte oder kleinste Element zu verwalten.

## Eigenschaften der Prioritäts-Queue

- Die **Queue** ist eine Datenstruktur, in der Elemente nach dem FIFO-Prinzip (First In, First Out) bearbeitet werden.
- In einer **Prioritäts-Queue** erfolgt die Entnahme von Elementen wie in einer klassischen Queue (an der Spitze der Queue), aber das Einfügen erfolgt wie in ein sortiertes Array (die Daten bleiben stets sortiert).

### Anwendungsbeispiel: Notaufnahme (Triage)

Ein klassisches Beispiel für eine Prioritäts-Queue ist die Triage in einer Notaufnahme. Hier werden Patienten nicht in der Reihenfolge ihrer Aufnahme behandelt, sondern nach Dringlichkeit einsortiert. 

- **Annahme**: Der Schweregrad der Erkrankung der Patienten wird auf einer Skala von 1 bis 10 eingeteilt, wobei 10 der schwerste Grad ist.
- Der Patient mit der höchsten Dringlichkeit (z. B. Patient C) steht an der Spitze der Queue.
- Ein neu eintreffender Patient (z. B. Patient E mit Schweregrad 3) wird entsprechend seiner Dringlichkeit einsortiert.
![[Pasted image 20240828075541.png]]

> [!EXAMPLE]- **C# Beispiel zur Implementierung einer Prioritäts-Queue mit einem Heap:**
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class Program
> {
>     static void Main()
>     {
>         // Erstelle eine neue Prioritäts-Queue
>         PriorityQueue<Patient> priorityQueue = new PriorityQueue<Patient>();
>
>         // Patienten in die Queue einfügen
>         priorityQueue.Enqueue(new Patient("Patient A", 2));
>         priorityQueue.Enqueue(new Patient("Patient B", 5));
>         priorityQueue.Enqueue(new Patient("Patient C", 10));
>         priorityQueue.Enqueue(new Patient("Patient D", 1));
>
>         // Patienten in der Reihenfolge ihrer Priorität behandeln
>         while (priorityQueue.Count > 0)
>         {
>             Patient nextPatient = priorityQueue.Dequeue();
>             Console.WriteLine($"Behandeln von: {nextPatient.Name} mit Dringlichkeit {nextPatient.Priority}");
>         }
>     }
> }
>
> class Patient : IComparable<Patient>
> {
>     public string Name { get; set; }
>     public int Priority { get; set; }
>
>     public Patient(string name, int priority)
>     {
>         Name = name;
>         Priority = priority;
>     }
>
>     // Vergleichsmethode für die Sortierung im Heap
>     public int CompareTo(Patient other)
>     {
>         return Priority.CompareTo(other.Priority);
>     }
> }
>
> class PriorityQueue<T> where T : IComparable<T>
> {
>     private List<T> data;
>
>     public PriorityQueue()
>     {
>         data = new List<T>();
>     }
>
>     public void Enqueue(T item)
>     {
>         data.Add(item);
>         int childIndex = data.Count - 1;
>         
>         // Bubble up
>         while (childIndex > 0)
>         {
>             int parentIndex = (childIndex - 1) / 2;
>             
>             if (data[childIndex].CompareTo(data[parentIndex]) >= 0)
>             {
>                 break;
>             }
>             
>             T tmp = data[childIndex];
>             data[childIndex] = data[parentIndex];
>             data[parentIndex] = tmp;
>             
>             childIndex = parentIndex;
>         }
>     }
>
>     public T Dequeue()
>     {
>         // Get the min item (root of the heap)
>         int lastIndex = data.Count - 1;
>         T frontItem = data[0];
>         data[0] = data[lastIndex];
>         data.RemoveAt(lastIndex);
>         lastIndex--;
>
>         // Bubble down
>         int parentIndex = 0;
>         while (true)
>         {
>             int leftChildIndex = 2 * parentIndex + 1;
>             int rightChildIndex = 2 * parentIndex + 2;
>             int minIndex = parentIndex;
>
>             if (leftChildIndex <= lastIndex && data[leftChildIndex].CompareTo(data[minIndex]) < 0)
>             {
>                 minIndex = leftChildIndex;
>             }
>
>             if (rightChildIndex <= lastIndex && data[rightChildIndex].CompareTo(data[minIndex]) < 0)
>             {
>                 minIndex = rightChildIndex;
>             }
>
>             if (minIndex == parentIndex)
>             {
>                 break;
>             }
>
>             T tmp = data[parentIndex];
>             data[parentIndex] = data[minIndex];
>             data[minIndex] = tmp;
>
>             parentIndex = minIndex;
>         }
>
>         return frontItem;
>     }
>
>     public int Count => data.Count;
> }
> ```


## Effizienz-Analyse der Prioritäts-Queue

Es gibt zwei primäre Operationen in einer Prioritäts-Queue: **Entnehmen** und **Einfügen**.

### Entnehmen

- Entnahme am Anfang eines Arrays: **O(N)**, da alle Elemente für das Schließen der Lücke verschoben werden müssen.
- Entnahme am Ende eines Arrays: **O(1)** – deshalb wird die Entnahme (maximale Priorität) am Ende durchgeführt.

### Einsortieren

- Das Einfügen in ein sortiertes Array hat die Komplexität **O(N)**, da alle Elemente verglichen werden müssen und bei einem frühen Einfügen alle anderen verschoben werden müssen.

In Summe ergibt sich für die Prioritäts-Queue mit einem sortierten Array eine Komplexität von **O(N)**, was bei vielen Elementen eine unwillkommene Verzögerung bedeutet.

### Bessere Datenstruktur: HEAP

Ein **Heap** ist eine effizientere Datenstruktur zur Implementierung einer Prioritäts-Queue, da er das Einfügen und Entfernen von Elementen in logarithmischer Zeit **O(log N)** ermöglicht.
