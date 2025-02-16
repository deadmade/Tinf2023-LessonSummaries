Schleifen sind ein grundlegendes Konzept in der Programmierung, das es dir ermöglicht, Code wiederholt auszuführen, bis eine bestimmte Bedingung erfüllt ist. PHP bietet mehrere Arten von Schleifen, die dir helfen können, verschiedene Aufgaben effizient zu bewältigen. Hier ist eine Übersicht der wichtigsten Schleifenarten in PHP.

## `for` Schleife

Die `for`-Schleife wird verwendet, wenn du genau weißt, wie oft der Code innerhalb der Schleife ausgeführt werden soll. Sie besteht aus drei Teilen: Initialisierung, Bedingung und Inkrement/Decrement.

>[!example]- **Beispiel: `for`-Schleife**
> ```php
> for ($i = 0; $i < 5; $i++) {
>     echo "Zähler: $i\n";
> }
> // Ausgabe:
> // Zähler: 0
> // Zähler: 1
> // Zähler: 2
> // Zähler: 3
> // Zähler: 4
> ```

## `while` Schleife

Die `while`-Schleife führt ihren Codeblock aus, solange die angegebene Bedingung `true` ist. Die Bedingung wird vor jedem Schleifendurchlauf überprüft.

>[!example]- **Beispiel: `while`-Schleife**
> ```php
> $i = 0;
> while ($i < 5) {
>     echo "Zähler: $i\n";
>     $i++;
> }
> // Ausgabe:
> // Zähler: 0
> // Zähler: 1
> // Zähler: 2
> // Zähler: 3
> // Zähler: 4
> ```

## `do...while` Schleife

Die `do...while`-Schleife ähnelt der `while`-Schleife, aber der Codeblock wird mindestens einmal ausgeführt, bevor die Bedingung überprüft wird.

>[!example]- **Beispiel: `do...while`-Schleife**
> ```php
> $i = 0;
> do {
>     echo "Zähler: $i\n";
>     $i++;
> } while ($i < 5);
> // Ausgabe:
> // Zähler: 0
> // Zähler: 1
> // Zähler: 2
> // Zähler: 3
> // Zähler: 4
> ```

## `foreach` Schleife

Die `foreach`-Schleife wird verwendet, um durch die Elemente eines Arrays zu iterieren. Sie ist besonders nützlich, wenn du alle Elemente eines Arrays durchlaufen möchtest.

>[!example]- **Beispiel: `foreach`-Schleife**
> ```php
> $fruits = array("Apfel", "Banane", "Kirsche");
> foreach ($fruits as $fruit) {
>     echo "Frucht: $fruit\n";
> }
> // Ausgabe:
> // Frucht: Apfel
> // Frucht: Banane
> // Frucht: Kirsche
> ```

## Schleifensteuerung

In PHP gibt es spezielle Anweisungen, um die Schleifensteuerung zu beeinflussen:

- **`break`**: Beendet die Schleife vorzeitig.
- **`continue`**: Überspringt den aktuellen Schleifendurchlauf und fährt mit dem nächsten fort.

>[!example]- **Beispiel: Verwendung von `break` und `continue`**
> ```php
> for ($i = 0; $i < 10; $i++) {
>     if ($i == 3) {
>         continue; // Überspringt den Rest des Schleifendurchlaufs
>     }
>     if ($i == 7) {
>         break; // Beendet die Schleife
>     }
>     echo "Zähler: $i\n";
> }
> // Ausgabe:
> // Zähler: 0
> // Zähler: 1
> // Zähler: 2
> // Zähler: 4
> // Zähler: 5
> // Zähler: 6
> ```

