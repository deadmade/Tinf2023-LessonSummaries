## Idee

Insertion Sort ist ein einfacher Sortieralgorithmus, der Elemente nacheinander in eine sortierte Liste einfügt. Man kann sich den Vorgang wie das Sortieren von Karten oder Büchern vorstellen:

1. **Kartenbeispiel**: Stellen Sie sich vor, Sie haben eine Hand von Karten, die bereits sortiert ist. Eine neue Karte wird aus einem Stapel entnommen und an der richtigen Stelle in der sortierten Hand eingefügt. Dies wiederholt sich, bis alle Karten sortiert sind.

2. **Bücherregal**: Wenn Sie ein neues Buch aus dem Regal nehmen, fügen Sie es an der richtigen Stelle in einem bereits sortierten Regal ein.

## Algorithmus

**Schritte zur Durchführung von Insertion Sort:**

1. **Entfernung und Speicherung**: Entfernen Sie den Wert am aktuellen Index und speichern Sie ihn in einer temporären Variable. Dies schafft eine Lücke an diesem Index.

2. **Schiebephase**: Verschieben Sie alle Werte links von der Lücke nach rechts, bis Sie den richtigen Platz für die temporäre Variable finden oder das Ende des Arrays erreichen.

3. **Einfügen**: Fügen Sie die temporär gespeicherte Variable an der gefundenen Stelle ein.

4. **Wiederholung**: Wiederholen Sie die Schritte 1 bis 3, bis das gesamte Array sortiert ist.

![](https://youtu.be/8oJS1BMKE64?list=PLZh3kxyHrVp_AcOanN_jpuQbcMVdXbqei)

## Implementierung

> [!code]- **C# Beispiel: Insertion Sort**
> 
> ```csharp
> // Insertion Sort Implementierung in C#
> public class InsertionSort
> {
>     public static void Sort(int[] array)
>     {
>         int n = array.Length;
>         for (int i = 1; i < n; i++)
>         {
>             int key = array[i];
>             int j = i - 1;
> 
>             // Verschieben der Elemente
>             while (j >= 0 && array[j] > key)
>             {
>                 array[j + 1] = array[j];
>                 j--;
>             }
>             array[j + 1] = key;
>         }
>     }
> }
> ```

## Effizienz

**Insertion Sort besteht aus folgenden Typen von Schritten:**

- **Vergleiche**: Jeder Wert wird mit allen vorherigen Werten verglichen. Im schlechtesten Fall führt dies zu `N^2/2` Vergleichen.
- **Verschiebungen**: Werte müssen möglicherweise verschoben werden, was ebenfalls zu `N^2/2` Verschiebungen im schlechtesten Fall führt.
- **Zwischenspeicherung und Einfügen**: Beide Operationen finden einmal pro Durchlauf statt, also `N-1` Durchläufe, was zu `2N - 2` Schritten führt.

**Gesamtkomplexität**:  
Worst-Case: `O(N^2)`. Dies bedeutet, dass Insertion Sort die gleiche Zeitkomplexität wie Bubble Sort und Selection Sort im schlechtesten Fall hat.

>[!info] **Hinweis**:
> Bei der Big-O-Notation betrachten wir nur die höchste Ordnung, daher wird der Ausdruck `O(N^2 + 2N - 2)` vereinfacht zu `O(N^2)`.

## Vergleich mit anderen Sortieralgorithmen

### Bubble Sort vs. Insertion Sort

| **Algorithmus**   | **Worst Case** | **Best Case**  | **Average Case** |
|-------------------|----------------|----------------|------------------|
| **Bubble Sort**   | `O(N^2)`       | `O(N)`         | `O(N^2)`         |
| **Insertion Sort**| `O(N^2)`       | `O(N)`         | `O(N^2)`         |

- **Worst Case**: Beide Algorithmen haben `N^2` Schritte.
- **Best Case**: Insertion Sort benötigt nur `N` Schritte, wenn das Array bereits sortiert ist.
- **Average Case**: Beide Algorithmen haben eine durchschnittliche Zeitkomplexität von `N^2/2` Schritten.

### Selection Sort vs. Insertion Sort

| **Algorithmus**   | **Worst Case** | **Best Case**  | **Average Case** |
|-------------------|----------------|----------------|------------------|
| **Selection Sort**| `O(N^2)`       | `O(N^2)`       | `O(N^2)`         |
| **Insertion Sort**| `O(N^2)`       | `O(N)`         | `O(N^2)`         |

- **Worst Case**: Selection Sort hat `N^2/2` Schritte, während Insertion Sort `N^2` Schritte benötigt.
- **Best Case**: Insertion Sort hat eine bessere Leistung bei einem bereits sortierten Array.
- **Average Case**: Beide Algorithmen haben ähnliche durchschnittliche Zeitkomplexitäten.

> [!info] **Empfehlung**: 
> Insertion Sort ist effizienter, wenn die Daten nahezu sortiert sind. Selection Sort ist besser, wenn die Daten weitgehend unsortiert sind und die Anzahl der Vergleiche reduziert werden soll.
