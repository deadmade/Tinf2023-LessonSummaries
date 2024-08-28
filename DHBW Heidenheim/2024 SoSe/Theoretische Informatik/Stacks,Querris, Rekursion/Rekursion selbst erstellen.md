## Kategorien geeigneter Probleme

Rekursion eignet sich gut für Probleme, bei denen Aufgaben wiederholt ausgeführt werden müssen, z.B. beim Countdown-Algorithmus der NASA. Die letzte Zeile der Funktion ist oft ein erneuter Aufruf der Funktion selbst.

## Rekursiver Trick: Übergabe zusätzlicher Parameter

Ein Beispiel für eine wiederholte Ausführung ist ein Algorithmus, der ein Array von Zahlen verdoppelt. Um dies rekursiv zu implementieren, können zusätzliche Parameter übergeben werden:

>[!example]- **Code: Array verdoppeln**
>
> ```csharp
> void DoubleArray(int[] arr, int index) {
>     if (index >= arr.Length) return;
>     arr[index] *= 2;
>     DoubleArray(arr, index + 1);
> }
> ```

## Rekursive Kategorien

### 1. Berechnungen

Rekursive Funktionen können zur Berechnung von Werten verwendet werden, indem sie auf Teilprobleme angewendet werden. Zum Beispiel:

- **Fakultät**: Die Fakultät von 6 ist `6 * 5 * 4 * 3 * 2 * 1`. Die rekursive Berechnung lautet:

>[!example]- **Code: Fakultät berechnen**
>
> ```csharp
> int Factorial(int number) {
>     if (number <= 1) return 1;
>     return number * Factorial(number - 1);
> }
> ```

### 2. Bottom-Up vs. Top-Down

- **Bottom-Up**: Beginnt mit den einfachsten Problemen und baut auf ihnen auf.
- **Top-Down**: Zerlegt das Problem in kleinere Teilprobleme.

Beispiel für Bottom-Up-Rekursion:

>[!example]- **Code: Bottom-Up Fakultät**
>
> ```csharp
> int Factorial(int number, int result = 1, int index = 1) {
>     if (index > number) return result;
>     return Factorial(number, result * index, index + 1);
> }
> ```

Beispiel für Top-Down-Rekursion (berechnet Fakultät):

>[!example]- **Code: Top-Down Fakultät**
>
> ```csharp
> int Factorial(int number) {
>     if (number <= 1) return 1;
>     return number * Factorial(number - 1);
> }
> ```

## Top-Down-Rekursion: Lösung von Teilproblemen

Beim Top-Down-Ansatz stellt man sich vor, dass die Funktion bereits implementiert ist. Beispiele:

### Summe von Array-Elementen

>[!example]- **Code: Array-Summe berechnen**
>
> ```csharp
> int Sum(int[] arr, int size) {
>     if (size == 0) return 0;
>     return arr[0] + Sum(arr[1..], size - 1);
> }
> ```

### Umkehren eines Strings

>[!example]- **Code: String umkehren**
> ```csharp
> void Reverse(char[] str, int start, int end) {
>     if (start >= end) return;
>     (str[start], str[end]) = (str[end], str[start]);
>     Reverse(str, start + 1, end - 1);
> }
> ```

### Zählen von 'x' in einem String

>[!example]- **Code: Anzahl der 'x' zählen**
> ```csharp
> int CountX(string str) {
>     if (string.IsNullOrEmpty(str)) return 0;
>     return (str[0] == 'x' ? 1 : 0) + CountX(str[1..]);
> }
> ```

## Schöne Rekursionsprobleme

### Treppenproblem

Anzahl der Wege, um eine Treppe mit `n` Stufen zu erklimmen:

>[!example]- **Code: Anzahl der Wege zählen**
>
> ```csharp
> int CountWays(int n) {
>     if (n == 0) return 1;
>     if (n < 0) return 0;
>     return CountWays(n - 1) + CountWays(n - 2) + CountWays(n - 3);
> }
> ```

**Abbruchkriterien:**

- `CountWays(0)` gibt 1 zurück.
- `CountWays(-1)` gibt 0 zurück.

Zusammenfassend: Die Rekursion ist ein mächtiges Werkzeug zur Problemlösung, besonders wenn Probleme in kleinere, handhabbare Teilprobleme zerlegt werden können. Es ist wichtig, sowohl die Abbruchkriterien als auch die richtige Strategie (Bottom-Up oder Top-Down) zu verstehen und anzuwenden.
