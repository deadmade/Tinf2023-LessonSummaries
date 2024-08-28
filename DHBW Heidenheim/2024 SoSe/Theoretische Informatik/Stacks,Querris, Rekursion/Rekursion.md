## Einführung in die Rekursion
Rekursion ist ein Konzept in der Programmierung, bei dem eine Funktion sich selbst aufruft, um ein Problem zu lösen. Dies kann oft anstelle von Schleifen verwendet werden. Stellen Sie sich vor, Sie arbeiten für die NASA und müssen einen Countdown für den Start eines Raumschiffs programmieren. Die Funktion soll eine Zahl als Input erhalten und die Zahlen von dieser Zahl bis 0 anzeigen. Zum Beispiel:

> [!code-csharp]- 
> ```csharp
> using System;
>
> class Program
> {
>     static void Main()
>     {
>         countdown(10);
>     }
>
>     static void countdown(int number)
>     {
>         if (number < 0)
>         {
>             return;
>         }
>         Console.WriteLine(number);
>         countdown(number - 1);
>     }
> }
> ```

## Erster Versuch mit Rekursion- 
Der erste naive Versuch könnte so aussehen:

> [!code-csharp]-
> ```csharp
> using System;
>
> class Program
> {
>     static void Main()
>     {
>         countdown(10);
>     }
>
>     static void countdown(int number)
>     {
>         Console.WriteLine(number);
>         countdown(number - 1);
>     }
> }
> ```

Dies führt jedoch zu einem Problem: Die Funktion wird endlos weiterlaufen und immer negativere Zahlen ausgeben. Nur weil man Rekursion verwenden kann, heißt das nicht, dass man sie unbedingt verwenden sollte.

## Korrektur mit Abbruchbedingung
Um den Countdown korrekt zu implementieren, benötigen wir eine Abbruchbedingung, die die Rekursion stoppt, sobald 0 erreicht wird:

> [!code-csharp]-
> ```csharp
> using System;
>
> class Program
> {
>     static void Main()
>     {
>         countdown(10);
>     }
>
>     static void countdown(int number)
>     {
>         if (number < 0)
>         {
>             return;
>         }
>         Console.WriteLine(number);
>         countdown(number - 1);
>     }
> }
> ```

In dieser Version überprüft die Funktion zuerst, ob die Zahl kleiner als 0 ist. Wenn ja, beendet sie die Rekursion.

## Beispiel: Berechnung der Fakultät
Ein klassisches Beispiel für rekursive Funktionen ist die Berechnung der Fakultät einer Zahl \( n! \):

> [!code-csharp]-
> ```csharp
> using System;
>
> class Program
> {
>     static void Main()
>     {
>         int result = factorial(5);
>         Console.WriteLine(result); // Ausgabe: 120
>     }
>
>     static int factorial(int n)
>     {
>         if (n == 1)
>         {
>             return 1;
>         }
>         return n * factorial(n - 1);
>     }
> }
> ```

Für die Berechnung der Fakultät von 5 würde der rekursive Aufruf wie folgt aussehen:
- factorial(5) -> 5 * factorial(4)
- factorial(4) -> 4 * factorial(3)
- factorial(3) -> 3 * factorial(2)
- factorial(2) -> 2 * factorial(1)
- factorial(1) -> 1

Die Rückkehrwerte werden dann multipliziert:
- 1 (von factorial(1))
- 2 * 1 = 2
- 3 * 2 = 6
- 4 * 6 = 24
- 5 * 24 = 120

## Rekursion verstehen
Zum Verstehen von rekursivem Code sind zwei Fähigkeiten erforderlich:
1. **Rekursiven Code lesen**: Identifizieren des Abbruchkriteriums und Nachverfolgen der Aufrufe.
2. **Rekursiven Code schreiben**: Erstellen von Funktionen mit einer klaren Abbruchbedingung und einer Rekursionsregel.

## Rekursion aus Sicht des Computers
Rekursive Aufrufe werden im Callstack des Computers gespeichert. Jeder Aufruf legt eine neue Ebene auf den Stack, die die Rückkehradresse und die aktuellen Parameter enthält. Bei endloser Rekursion kann der Stack überlaufen, was zu einem "Stack Overflow" führt.

## Anwendungsbeispiele der Rekursion
Rekursion eignet sich besonders für Probleme, die in verschachtelte Ebenen unterteilt sind, deren Anzahl vorher nicht bekannt ist. Ein typisches Beispiel ist die Traversierung eines Dateisystems:

> [!code-csharp]-
> ```csharp
> using System;
> using System.IO;
>
> class Program
> {
>     static void Main()
>     {
>         Traverse
