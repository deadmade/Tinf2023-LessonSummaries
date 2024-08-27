![[Pasted image 20240827180852.png]]

## Allgemein
- Ist ein extrem schneller Sortieralgorrithmus, besonders effizient für Average Szenarien
- Performed in Worst-Case Szenarien gleich zu Insertion und Selection Sort

## Effizenz
- Best Case: O(n log n)
- Average Case: O(n log n)
- Worst Case: O(n²)

## Code-Beispiel
```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        int[] array = { 34, 7, 23, 32, 5, 62 };
        Console.WriteLine("Unsortiertes Array:");
        PrintArray(array);

        QuickSort(array, 0, array.Length - 1);

        Console.WriteLine("\nSortiertes Array:");
        PrintArray(array);
    }

    static void QuickSort(int[] array, int low, int high)
    {
        if (low < high)
        {
            int pivotIndex = Partition(array, low, high);
            QuickSort(array, low, pivotIndex - 1);
            QuickSort(array, pivotIndex + 1, high);
        }
    }

    static int Partition(int[] array, int low, int high)
    {
        int pivot = array[high];
        int i = (low - 1);

        for (int j = low; j < high; j++)
        {
            if (array[j] < pivot)
            {
                i++;
                Swap(array, i, j);
            }
        }

        Swap(array, i + 1, high);
        return i + 1;
    }

    static void Swap(int[] array, int a, int b)
    {
        int temp = array[a];
        array[a] = array[b];
        array[b] = temp;
    }

    static void PrintArray(int[] array)
    {
        foreach (var item in array)
        {
            Console.Write(item + " ");
        }
        Console.WriteLine();
    }
}
```

