Benannte Iteratoren in C# verwenden die `yield return`-Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Dabei wird die aktuelle Codeposition plus aller lokalen Variablen auf dem Stack gespeichert. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position gestartet.

> [!NOTE]
> In einer Iteratormethode darf kein `return` ohne `yield` verwendet werden.

> [!TIP]
> `yield break` bricht die Speicherung in einem Zyklus ab.

## Beispiel 1: Einfache Iteratormethode

> [!example]-
> ```csharp
> using System;
> using System.Collections;
>
> class Program
> {
>     static void Main()
>     {
>         foreach (int number in NextNumber())
>         {
>             Console.Write(number.ToString() + " ");
>         }
>         // Output: 3 5 8
>     }
>
>     public static IEnumerable NextNumber()
>     {
>         yield return 3;
>         yield return 5;
>         yield return 8;
>     }
> }
> ```
>
>In diesem Beispiel gibt die Methode `NextNumber` nacheinander die Zahlen 3, 5 und 8 zurück. Der `foreach`-Loop in der `Main`-Methode gibt diese Zahlen aus.

## Beispiel 2: Iteratormethode mit Bedingungen

> [!example]-
> ```csharp
> using System;
> using System.Collections.Generic;
>
> class Program
> {
>     static void Main()
>     {
>         foreach (int number in EvenSequence(3, 12))
>         {
>             Console.Write(number.ToString() + " ");
>         }
>         // Output: 4 6 8 10 12
>     }
>
>     public static IEnumerable<int> EvenSequence(int firstNumber, int lastNumber)
>     {
>         for (int number = firstNumber; number <= lastNumber; number++)
>         {
>             if (number % 2 == 0)
>             {
>                 yield return number;
>             }
>         }
>     }
> }
> ```
>
>In diesem Beispiel erzeugt die Methode `EvenSequence` eine Sequenz von geraden Zahlen zwischen `firstNumber` und `lastNumber`. Nur die Zahlen, die durch 2 teilbar sind (d.h. gerade Zahlen), werden zurückgegeben. Der `foreach`-Loop in der `Main`-Methode gibt diese Zahlen aus.


