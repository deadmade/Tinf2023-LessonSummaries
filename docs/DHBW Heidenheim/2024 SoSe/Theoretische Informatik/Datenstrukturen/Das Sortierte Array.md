Der Unterschied zu normalen Arrays ist das Werte nach jeder Operation wieder Sortiert werden müssen.

- Einfügen ist langsamer als bei unsortierten Arrays 
- Lineare Suche ist genauso schnell wie bei unsortierten Arrays 
- Binäre Suche ist wesentlich schneller als bei unsortierten Arrays!


## Lineare Suche
![[Pasted image 20240723185946.png]]

> [!faq]- Beispiel
> 
> ```csharp
> using System;
> 
> class Program
> {
>     static void Main(string[] args)
>     {
>         int[] array = { 3, 17, 75, 80, 202 };
>         int result = LinearSearch(array, array.Length, 202);
> 
>         if (result != -1)
>         {
>             Console.WriteLine($"Element gefunden an Position: {result}");
>         }
>         else
>         {
>             Console.WriteLine("Element nicht gefunden");
>         }
>     }
> 
>     static int LinearSearch(int[] array, int size, int searchValue)
>     {
>         bool continueLoop = true;
>         int result = -1;
>         for (int i = 0; i < size && continueLoop; i++)
>         {
>             if (array[i] == searchValue)
>             {
>                 // gefunden!
>                 continueLoop = false;
>                 result = i;
>             }
>             else if (array[i] > searchValue)
>             {
>                 // Hier bricht die Suche im sortierten Array u.U. früher ab!
>                 continueLoop = false;
>             }
>         }
> 
>         return result;
>     }
> }


## Binäre Suche
![[Pasted image 20240723190304.png]]
> [!faq]- Beispiel
> ```csharp
> using System;
> 
> class Program
> {
>     static void Main(string[] args)
>     {
>         int[] array = { 3, 17, 75, 80, 202 };
>         int result = BinarySearch(array, array.Length, 202);
> 
>         if (result != -1)
>         {
>             Console.WriteLine($"Element gefunden an Position: {result}");
>         }
>         else
>         {
>             Console.WriteLine("Element nicht gefunden");
>         }
>     }
> 
>     static int BinarySearch(int[] array, int size, int searchValue)
>     {
>         // Festlegen der unteren und oberen Schranke
>         int lowerBound = 0;
>         int upperBound = size - 1;
>         int midPoint = 0;
>         int result = -1;
>         bool notFound = true;
> 
>         // Schleife zum Durchsuchen der Werte zwischen den Schranken
>         while (lowerBound <= upperBound && notFound)
>         {
>             // Berechnung des Mittelpunkts
>             midPoint = (upperBound + lowerBound) / 2;
> 
>             // Überprüfen des Werts am Mittelpunkt
>             if (array[midPoint] == searchValue)
>             {
>                 result = midPoint;
>                 notFound = false;
>             }
>             else if (searchValue > array[midPoint])
>             {
>                 lowerBound = midPoint + 1;
>             }
>             else if (searchValue < array[midPoint])
>             {
>                 upperBound = midPoint - 1;
>             }
>         }
> 
>         return result;
>     }
> }
> ```

## Binäre vs. Lineare Suche
Lineare Suche (Worst case): 100 Vergleiche (=n)
Binäre Suche (Worst]case): 7 Vergleiche (=log2 n: Die Verdopplung der Länge erhöht die Zahl der Schritte um 1) 
![[Pasted image 20240723190639.png]]
![[Pasted image 20240723190811.png]]