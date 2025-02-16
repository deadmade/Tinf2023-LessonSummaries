**Bottom-Up-Rekursion** ist eine Technik, die oft in der dynamischen Programmierung verwendet wird. Im Gegensatz zur klassischen **Top-Down-Rekursion**, bei der ein großes Problem rekursiv in kleinere Teilprobleme zerlegt wird, beginnt die **Bottom-Up-Rekursion** mit den einfachsten Teilproblemen und arbeitet sich iterativ zu größeren Problemen vor.

## Was ist der Unterschied zur Top-Down-Rekursion?

Bei der Top-Down-Rekursion wird ein großes Problem in kleinere Teilprobleme zerlegt, und diese Teilprobleme werden rekursiv gelöst. Dies führt oft dazu, dass dieselben Teilprobleme mehrfach gelöst werden, was zu ineffizienter Laufzeit und hohem Speicherverbrauch führen kann.

In der **Bottom-Up-Rekursion** hingegen lösen wir das Problem iterativ, beginnend mit den einfachsten Teilproblemen und verwenden die Ergebnisse, um größere Probleme zu lösen. Dies reduziert die Anzahl der Berechnungen und spart Speicherplatz.

> [!warning] Hinweis
>  Bottom-Up-Ansätze sind oft effizienter als rekursive Top-Down-Ansätze, da sie die Berechnung von bereits gelösten Teilproblemen vermeiden.

## Beispiel: Fibonacci-Zahlen

Die Fibonacci-Sequenz ist ein klassisches Beispiel, das sowohl rekursiv als auch iterativ gelöst werden kann.

## Fibonacci mit Top-Down-Rekursion

Bei der klassischen rekursiven Definition der Fibonacci-Zahlen werden viele Berechnungen mehrfach durchgeführt:

$$
\text{Fib}(n) = 
\begin{cases} 
0 & \text{wenn } n = 0 \\
1 & \text{wenn } n = 1 \\
\text{Fib}(n-1) + \text{Fib}(n-2) & \text{wenn } n > 1 
\end{cases}
$$
Dies führt zu einer exponentiellen Zeitkomplexität von **O(2^n)**, da viele Teilprobleme mehrfach berechnet werden.

## Fibonacci mit Bottom-Up-Ansatz in C#

Im **Bottom-Up-Ansatz** verwenden wir eine iterative Methode, um die Fibonacci-Zahlen effizient zu berechnen:

>[!example]-
> ```csharp
> public int FibBottomUp(int n)
> {
>     if (n == 0) return 0;
>     if (n == 1) return 1;
>     
>     int[] fib = new int[n + 1];
>     fib[0] = 0;
>     fib[1] = 1;
> 
>     for (int i = 2; i <= n; i++)
>     {
>         fib[i] = fib[i - 1] + fib[i - 2];
>     }
> 
>     return fib[n];
> }
> ```

**Erklärung:**

1. **Initialisierung**: Die ersten beiden Werte der Fibonacci-Sequenz werden initialisiert: `fib[0] = 0` und `fib[1] = 1`.
2. **Iterative Berechnung**: Eine Schleife berechnet die Werte von `fib[2]` bis `fib[n]` schrittweise.
3. **Verwendung von Zwischenergebnissen**: Jedes neue Fibonacci-Zahlenpaar wird durch Addition der beiden vorhergehenden Werte berechnet.
4. **Effizienz**: Dieser Ansatz hat eine Zeitkomplexität von **O(n)** und eine Speicherkomplexität von **O(n)**. 

> [!info] **💡 Tipp:** 
> Man kann den Speicherbedarf auf **O(1)** reduzieren, indem man nur die letzten beiden berechneten Werte speichert und diese bei jedem Schritt aktualisiert.

## Wann sollte Bottom-Up-Rekursion verwendet werden?

Bottom-Up-Rekursion ist besonders nützlich, wenn:

- Das Problem durch die Zerlegung in kleinere Teilprobleme effizienter gelöst werden kann.
- Die Teilprobleme überlappen und mehrfach berechnet werden, wie im Fall des klassischen rekursiven Ansatzes.
- Iterative Lösungen bevorzugt werden, um Stack-Overflows zu vermeiden und den Speicher effizienter zu nutzen.

Typische Probleme, bei denen der Bottom-Up-Ansatz bevorzugt wird, umfassen dynamische Programmierungsprobleme wie das Rucksackproblem, die Berechnung von Pfaden in Gittern oder die Berechnung der längsten gemeinsamen Teilfolge.
