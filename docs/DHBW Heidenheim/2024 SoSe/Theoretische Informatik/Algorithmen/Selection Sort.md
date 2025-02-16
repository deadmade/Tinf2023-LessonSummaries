## Idee

Der Selection Sort Algorithmus basiert auf dem Prinzip, in jedem Durchlauf das kleinste Element im unsortierten Bereich zu finden und es an die erste Position des unsortierten Bereichs zu verschieben. Dies wird wiederholt, bis der gesamte Bereich sortiert ist.

## Vorgehensweise

1. **Finde das kleinste Element:**
    
    - Durchlaufe den unsortierten Teil des Arrays (von der aktuellen Position bis zum Ende) und finde das kleinste Element.
2. **Tausche das kleinste Element:**
    
    - Tausche das gefundene kleinste Element mit dem ersten Element des unsortierten Teils.
3. **Wiederhole den Vorgang:**
    
    - Bewege die Grenze des sortierten Bereichs einen Schritt weiter und wiederhole die Schritte 1 und 2, bis der gesamte Array sortiert ist.

## Zeitkomplexität

- **Vergleiche:** $O(N^2)$
- **Vertauschungen:** $O(N)$

Die gesamte Zeitkomplexität ist daher $O(N2)$

## Implementation
> [!code]- Implementation
> ```csharp
> void SelectionSort(int[] array)
>{
>    int n = array.Length;
>    
>    for (int i = 0; i < n - 1; i++)
>    {
>        // Finde das Minimum im unsortierten Bereich
>        int minIndex = i;
>        for (int j = i + 1; j < n; j++)
>        {
>            if (array[j] < array[minIndex])
>            {
>                minIndex = j;
>            }
>        }
>
>        // Tausche das gefundene Minimum mit dem ersten unsortierten Element
>        if (minIndex != i)
>        {
>            int temp = array[i];
>            array[i] = array[minIndex];
>            array[minIndex] = temp;
>        }
>    }
>}
>```

## Video
![](https://www.youtube.com/watch?v=92BfuxHn2XE&list=PLZh3kxyHrVp_AcOanN_jpuQbcMVdXbqei&index=11)