In PHP sind Funktionen ein zentrales Konzept, das dir erlaubt, wiederverwendbaren Code zu schreiben. Funktionen helfen dabei, den Code zu organisieren, die Lesbarkeit zu verbessern und die Wartung zu erleichtern. Hier ist eine Übersicht über die wichtigsten Aspekte von Funktionen in PHP.

## Definition einer Funktion

Eine Funktion in PHP wird mit dem Schlüsselwort `function` definiert, gefolgt von einem Namen, einer Parameterliste in runden Klammern und einem Block von Code in geschweiften Klammern.

> [!example]- ** Definition einer Funktion**
> ```php
> function greet($name) {
>     echo "Hallo, $name!";
> }
> ```

## Aufruf einer Funktion

Um eine Funktion aufzurufen, verwende einfach den Namen der Funktion und übergebe die benötigten Argumente.

>[!example]- **Beispiel: Aufruf einer Funktion**
> ```php
> greet("Max"); // Ausgabe: Hallo, Max!
> ```

## Rückgabewert einer Funktion

Eine Funktion kann einen Wert zurückgeben, der mit dem Schlüsselwort `return` spezifiziert wird. Wenn kein Rückgabewert angegeben ist, gibt die Funktion `NULL` zurück.

>[!example]- **Beispiel: Rückgabewert einer Funktion**
> ```php
> function add($a, $b) {
>     return $a + $b;
> }
> 
> $result = add(3, 4); // $result ist 7
> ```

## Parameter und Argumente

Funktionen können Parameter haben, die als Platzhalter für die übergebenen Argumente dienen. PHP erlaubt sowohl normale Parameter als auch optionale Parameter mit Standardwerten.

>[!example]- **Beispiel: Parameter und Argumente**
> ```php
> function multiply($a, $b = 1) {
>     return $a * $b;
> }
> 
> echo multiply(5);    // Ausgabe: 5 (weil $b den Standardwert 1 hat)
> echo multiply(5, 3); // Ausgabe: 15
> ```

## Variable Funktionen

In PHP können Funktionen auch als Variablen gespeichert und aufgerufen werden. Dies wird als "variable Funktionen" bezeichnet.

>[!example]- **Beispiel: Variable Funktionen**
> ```php
> function sayHello() {
>     echo "Hallo!";
> }
> 
> $functionName = 'sayHello';
> $functionName(); // Ausgabe: Hallo!
> ```

## Anonyme Funktionen

Anonyme Funktionen (auch als "Closure" bekannt) sind Funktionen ohne Namen und können direkt als Variablen zugewiesen werden.

>[!example]- **Beispiel: Anonyme Funktionen**
> ```php
> $square = function($n) {
>     return $n * $n;
> };
> 
> echo $square(4); // Ausgabe: 16
> ```

## Funktionen als Rückgabewerte

Funktionen können auch andere Funktionen zurückgeben.

>[!example]- **Beispiel: Funktionen als Rückgabewerte**
> ```php
> function createMultiplier($factor) {
>     return function($number) use ($factor) {
>         return $number * $factor;
>     };
> }
> 
> $double = createMultiplier(2);
> echo $double(5); // Ausgabe: 10
> ```

## Rekursive Funktionen

Funktionen können sich selbst aufrufen. Dies nennt man Rekursion. Es ist wichtig, eine Abbruchbedingung zu definieren, um eine unendliche Schleife zu vermeiden.

>[!example]- **Beispiel: Rekursive Funktionen**
> ```php
> function factorial($n) {
>     if ($n <= 1) {
>         return 1;
>     }
>     return $n * factorial($n - 1);
> }
> 
> echo factorial(5); // Ausgabe: 120
> ```
