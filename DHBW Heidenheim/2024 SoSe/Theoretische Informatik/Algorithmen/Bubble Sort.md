## Einleitung

Bubble Sort ist ein einfacher Vergleichs-basierter Sortieralgorithmus. Der Algorithmus arbeitet, indem er wiederholt benachbarte Elemente der Liste vergleicht und vertauscht, wenn sie in der falschen Reihenfolge sind. Dieser Prozess wird so lange wiederholt, bis die Liste sortiert ist.

## Funktionsweise

> [!info] 
> Der Name "Bubble Sort" kommt von der Art und Weise, wie größere Elemente durch die Liste "aufsteigen", ähnlich wie Blasen in einer Flüssigkeit aufsteigen.

### Algorithmus-Schritte

1. **Durchlaufe die Liste** von Anfang bis Ende.
2. **Vergleiche jedes Paar benachbarter Elemente**.
3. **Vertausche die Elemente**, wenn sie in der falschen Reihenfolge sind (das größere Element wird nach rechts verschoben).
4. Wiederhole die Schritte 1-3, bis keine Vertauschungen mehr notwendig sind (die Liste ist sortiert).

## Komplexität
- **Best Case**: $O(n)$ (Die Liste ist bereits sortiert)
- **Average Case**: $O(n^2)$
- **Worst Case**: $O(n^2)$ (Die Liste ist in umgekehrter Reihenfolge sortiert)

![[Pasted image 20240723194751.png]]

## Implementierung
> [!code]- Implementierung
> ```csharp
>using System;
>
>public class Program
>{
>    // Auswahl-Sortieralgorithmus
>    void SelectionSort(int[] array)
>    {
>        int n = array.Length;
>        
>        for (int i = 0; i < n - 1; i++)
>        {
>            // Finde das Minimum im unsortierten Bereich
>            int minIndex = i;
>            for (int j = i + 1; j < n; j++)
>            {
>                if (array[j] < array[minIndex])
>                {
>                    minIndex = j;
>                }
>            }
>
>            // Tausche das gefundene Minimum mit dem ersten unsortierten Element
>            if (minIndex != i)
>            {
>                int temp = array[i];
>                array[i] = array[minIndex];
>                array[minIndex] = temp;
>            }
>        }
>    }
>
>    public static void Main()
>    {
>        int[] array = { 64, 25, 12, 22, 11 };
>        Program program = new Program();
>
>        Console.WriteLine("Unsortiertes Array:");
>        Console.WriteLine(string.Join(", ", array));
>
>        program.SelectionSort(array);
>
>        Console.WriteLine("Sortiertes Array:");
>        Console.WriteLine(string.Join(", ", array));
>    }
>}
>```



## Video
![](https://www.youtube.com/watch?v=Cq7SMsQBEUw&list=PLZh3kxyHrVp_AcOanN_jpuQbcMVdXbqei&t=1s)