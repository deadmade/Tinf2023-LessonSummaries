![](https://youtu.be/pvDIqjQgowk)

Counting Sort ist ein nichtvergleichendes Sortierverfahren, das in Linearzeit arbeitet, also eine Zeitkomplexität von **O(n + k)** hat. Es eignet sich besonders für die Sortierung von natürlichen Zahlen innerhalb eines begrenzten Intervalls, wie zum Beispiel Alter oder Distanzen.

## Eigenschaften von Counting Sort

- **Nichtvergleichendes Sortieren**: Counting Sort verzichtet auf direkte Vergleiche zwischen den zu sortierenden Elementen.
- **Lineare Laufzeit**: Die Zeitkomplexität beträgt **O(n + k)**, wobei `n` die Anzahl der zu sortierenden Elemente und `k` der Wertebereich der Schlüssel ist.
- **Speicherbedarf**: Der Speicherbedarf beträgt **O(k)**, da ein zusätzliches Arbeitsarray (eine Art Hashtabelle) für die Zählung der Elemente benötigt wird.

## Funktionsweise

Die grundlegende Idee von Counting Sort besteht darin, für jedes Element des Eingabearrays `A` die Häufigkeit jedes Werts zu zählen und diese in einem Arbeitsarray `C` zu speichern. Anschließend wird dieses Zählarray verwendet, um die Elemente in das sortierte Ausgabearray `B` zu platzieren.

1. **Initialisierung**: Erstelle ein Zählarray `C[0..k]` und setze alle Elemente auf 0.
2. **Zählen**: Durchlaufe das Eingabearray `A` und erhöhe für jeden Wert den entsprechenden Zähler in `C`.
3. **Kumulatives Zählen**: Transformiere das Zählarray `C`, sodass jedes Element die Summe der vorherigen Zählwerte enthält. Dies hilft, die korrekte Position eines jeden Elements im Ausgabearray `B` zu bestimmen.
4. **Sortierung**: Durchlaufe das Eingabearray `A` erneut und platziere jedes Element basierend auf den kumulierten Zählwerten in das Ausgabearray `B`.

### Beispiel in C#

> [!example]- 
> ```csharp  
> using System;  
>  
> public class CountingSortExample  
> {  
>     public static void CountingSort(int[] array)  
>     {  
>         int max = array.Max();  
>         int[] count = new int[max + 1];  
>         int[] output = new int[array.Length];  
>  
>         // Zählen der Vorkommen jedes Elements  
>         for (int i = 0; i < array.Length; i++)  
>         {  
>             count[array[i]]++;  
>         }  
>  
>         // Kumulatives Zählen  
>         for (int i = 1; i <= max; i++)  
>         {  
>             count[i] += count[i - 1];  
>         }  
>  
>         // Sortieren der Elemente  
>         for (int i = array.Length - 1; i >= 0; i--)  
>         {  
>             output[count[array[i]] - 1] = array[i];  
>             count[array[i]]--;  
>         }  
>  
>         // Kopieren des sortierten Arrays  
>         for (int i = 0; i < array.Length; i++)  
>         {  
>             array[i] = output[i];  
>         }  
>     }  
>  
>     public static void Main()  
>     {  
>         int[] array = { 4, 2, 2, 8, 3, 3, 1 };  
>         CountingSort(array);  
>         Console.WriteLine("Sortiertes Array: " + string.Join(", ", array));  
>     }  
> }  
> ```  

## Vor- und Nachteile

### Vorteile
- **Effizient für begrenzte Wertebereiche**: Der Speicherbedarf ist nur abhängig vom Intervall der zu sortierenden Werte, was es effizient macht, wenn der Wertebereich klein ist.
- **Lineare Laufzeit**: Counting Sort kann in Linearzeit arbeiten, wenn der Wertebereich `k` im Verhältnis zu `n` klein ist.

### Nachteile
- **Begrenzte Anwendung**: Nicht geeignet für große Wertebereiche, da der Speicherbedarf stark ansteigt.
- **Kompositdaten**: Die Sortierung kompositer Daten (wie Tupel oder Objekte) ist möglich, aber erfordert zusätzlichen Aufwand und ist daher langsamer.

Counting Sort ist daher besonders gut geeignet, wenn die zu sortierenden Daten einen kleinen Wertebereich haben und eine schnelle, lineare Sortierung gewünscht wird.
