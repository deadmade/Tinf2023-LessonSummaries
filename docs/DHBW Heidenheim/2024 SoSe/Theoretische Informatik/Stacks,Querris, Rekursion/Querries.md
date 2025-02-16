## Queue als Abstrakter Datentyp
Eine Queue ist eine Datenstruktur zur Verwaltung temporärer Daten und folgt dem FIFO-Prinzip (First In, First Out). Das bedeutet, dass das zuerst eingefügte Element auch als erstes wieder entnommen wird. Dies unterscheidet sich grundlegend vom LIFO-Prinzip (Last In, First Out) des Stacks.

## Eigenschaften einer Queue
- **FIFO-Prinzip**: Das erste Element, das hinzugefügt wird, wird als erstes entfernt.
- **Abstrakter Datentyp**: Die Queue bietet eine bestimmte Menge an Operationen, die auf einer anderen Datenstruktur basieren können.
- **Anwendungsbeispiel**: Eine Schlange von Menschen an einer Kinokasse.

## Operationen einer Queue
1. **Enqueue**: Einfügen eines Elements am Ende der Queue.
2. **Dequeue**: Entfernen eines Elements vom Anfang der Queue.
3. **Peek**: Lesen des ersten Elements, ohne es zu entfernen.

## Implementierung einer Queue in C#
In C# lässt sich eine Queue mit der `Queue<T>`-Klasse aus dem `System.Collections.Generic`-Namespace realisieren.

### Beispiel: Implementierung einer Queue
>[!example]- Beispiel
> ```csharp
> using System;
> using System.Collections.Generic;
> 
> class Program
> {
>     static void Main()
>     {
>         Queue<int> queue = new Queue<int>();
> 
>         // Elemente in die Queue einfügen (Enqueue)
>         queue.Enqueue(1);
>         queue.Enqueue(2);
>         queue.Enqueue(3);
> 
>         Console.WriteLine("Queue nach Enqueue-Operationen:");
>         foreach (var item in queue)
>         {
>             Console.WriteLine(item);
>         }
> 
>         // Erstes Element entfernen und zurückgeben (Dequeue)
>         int dequeuedElement = queue.Dequeue();
>         Console.WriteLine($"\nEntferntes Element: {dequeuedElement}");
> 
>         Console.WriteLine("\nQueue nach Dequeue-Operation:");
>         foreach (var item in queue)
>         {
>             Console.WriteLine(item);
>         }
> 
>         // Erstes Element lesen, ohne es zu entfernen (Peek)
>         int peekElement = queue.Peek();
>         Console.WriteLine($"\nErstes Element mit Peek: {peekElement}");
> 
>         Console.WriteLine("\nQueue nach Peek-Operation:");
>         foreach (var item in queue)
>         {
>             Console.WriteLine(item);
>         }
>     }
> }
> ```

### Erklärung
1. **Enqueue**: Fügt Elemente 1, 2 und 3 in die Queue ein.
2. **Dequeue**: Entfernt das erste Element (1) aus der Queue.
3. **Peek**: Liest das erste Element (2), ohne es zu entfernen.

## Weitere Anwendungen von Queues
- **Druckjobs**: Verwaltung von Druckaufträgen in der Reihenfolge ihres Eingangs.
- **Zwischenpuffer bei Kommunikationsprotokollen**: Zwischenspeicherung von Datenpaketen zur Verarbeitung in der Reihenfolge ihres Eingangs.
- **Modellierung realer Szenarien**: 
  - Verkehr an Ampelkreuzungen
  - Startfreigabe für Flugzeuge
  - Allgemeine Warteschlangenmodelle


