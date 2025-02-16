## Definition
Dynamische Programmierung (DP) ist eine Optimierungstechnik für rekursive Probleme, bei denen sich Teilprobleme überlappen. Durch das Speichern von Zwischenergebnissen (Memoisation) oder das schrittweise Aufbauen einer Lösung (Bottom-Up-Ansatz) kann die Laufzeit eines Algorithmus erheblich verbessert werden.

## Rekursive Probleme und Ineffizienz
Rekursive Algorithmen können ineffizient sein, wenn sie identische Teilprobleme mehrfach berechnen. Ein klassisches Beispiel ist die naive Berechnung der Fibonacci-Folge, bei der dieselben Werte mehrfach berechnet werden, was zu einer exponentiellen Laufzeit (O(2^n)) führt.

### Geschwindigkeitsfallen in rekursivem Code
- **Unnötige rekursive Aufrufe**: Bei einem rekursiven Ansatz, der dieselben Berechnungen mehrfach durchführt, entstehen unnötige Aufrufe, die vermieden werden sollten.
- **Beispiel**: Die naive Berechnung der größten Zahl in einem Array führt zu einer exponentiellen Anzahl von Aufrufen, wenn jedes Element mit allen anderen rekursiv verglichen wird.

## Optimierung durch dynamische Programmierung

### Memoisation (Top-Down-Ansatz)
Memoisation speichert die Ergebnisse von Funktionen in einer Datenstruktur wie einem Dictionary, sodass wiederholte Berechnungen vermieden werden. Bei der Berechnung der Fibonacci-Folge beispielsweise wird jedes Teilergebnis in einem Dictionary gespeichert und bei Bedarf wiederverwendet.

> [!example] C# Beispiel: Fibonacci-Berechnung mit Memoisation
> ```csharp
> using System;
> using System.Collections.Generic;
> 
> class Program
> {
>     static Dictionary<int, int> memo = new Dictionary<int, int>();
> 
>     static int Fibonacci(int n)
>     {
>         if (memo.ContainsKey(n))
>             return memo[n];
> 
>         if (n <= 2)
>             return 1;
> 
>         memo[n] = Fibonacci(n - 1) + Fibonacci(n - 2);
>         return memo[n];
>     }
> 
>     static void Main()
>     {
>         Console.WriteLine(Fibonacci(10)); // Output: 55
>     }
> }
> ```

- **Vorteil**: Reduziert die Laufzeit von O(2^n) auf O(n), da jedes Teilproblem nur einmal berechnet wird.
- **Nachteil**: Zusätzlicher Speicherbedarf für das Dictionary.


