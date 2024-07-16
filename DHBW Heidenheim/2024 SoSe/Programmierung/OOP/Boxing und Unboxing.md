In C# gibt es zwei wichtige Konzepte, die es ermöglichen, Werte von Werttypen in Referenztypen und umgekehrt zu konvertieren: Boxing und Unboxing.

## Was ist Boxing?

**Boxing** ist der Prozess, bei dem ein Werttyp (z.B. `int`, `double`, `struct`) in ein Objekt vom Typ `object` oder einen anderen Referenztyp konvertiert wird. Dabei wird der Wert des Werttyps in eine Instanz eines Referenztyps verpackt (oder "boxed").

### Beispiel für Boxing:
```csharp
int number = 123;
object boxedNumber = number; // Boxing
```
In diesem Beispiel wird der `int`-Wert `number` in ein `object` konvertiert. Der Wert wird in einer neuen Speicherstelle gespeichert, die als Referenztyp behandelt wird.

### Internes Verhalten von Boxing:

1. Es wird ein Objekt auf dem Heap erstellt.
2. Der Wert des Werttyps wird in das neu erstellte Objekt kopiert.
3. Eine Referenz auf dieses Objekt wird zurückgegeben.

## Was ist Unboxing?

**Unboxing** ist der Prozess, bei dem ein Objekt, das zuvor "geboxt" wurde, zurück in einen Werttyp konvertiert wird. Dabei wird der Wert aus dem Referenztyp extrahiert und in eine Variable des Werttyps zurückkopiert.

### Beispiel für Unboxing:
```csharp
object boxedNumber = 123; // Boxing
int number = (int)boxedNumber; // Unboxing
```
In diesem Beispiel wird das `object` `boxedNumber`, das einen `int`-Wert enthält, zurück in einen `int` konvertiert.

### Internes Verhalten von Unboxing:

1. Die Referenz wird überprüft, um sicherzustellen, dass sie auf den korrekten Werttyp zeigt.
2. Der Wert wird aus dem Objekt auf dem Heap extrahiert.
3. Der Wert wird in die Zielvariable des Werttyps kopiert.

## Wichtige Punkte zu Boxing und Unboxing

- **Leistungsüberlegungen**: Boxing und Unboxing sind kostspielige Operationen, da sie Speicheroperationen auf dem Heap und zusätzliche Arbeit des Garbage Collectors erfordern. Daher sollte übermäßiges Boxing und Unboxing vermieden werden, insbesondere in performancekritischen Anwendungen.
- **Typkonvertierungsfehler**: Beim Unboxing muss sichergestellt werden, dass das `object` tatsächlich den Werttyp enthält, auf den es konvertiert werden soll. Andernfalls wird eine `InvalidCastException` ausgelöst.

### Beispiel mit Typkonvertierungsfehler:
```csharp
object boxedNumber = 123;
try
{
    double number = (double)boxedNumber; // Falscher Typ, löst InvalidCastException aus
}
catch (InvalidCastException ex)
{
    Console.WriteLine("Unboxing fehlgeschlagen: " + ex.Message);
}
```

## Beispiele für den praktischen Einsatz

### Einsatz in einer Liste:
```csharp
ArrayList list = new ArrayList();
list.Add(123); // Boxing
int number = (int)list[0]; // Unboxing
```

In diesem Beispiel wird ein `int`-Wert in eine `ArrayList` eingefügt, was Boxing erfordert, da `ArrayList` Objekte vom Typ `object` speichert. Beim Abrufen des Werts aus der Liste wird Unboxing durchgeführt.

### Einsatz in einer generischen Liste:
```csharp
List<int> list = new List<int>();
list.Add(123); // Kein Boxing
int number = list[0]; // Kein Unboxing
```

Durch die Verwendung einer generischen Liste (`List<T>`) wird Boxing und Unboxing vermieden, da die Liste speziell für den Werttyp `int` typisiert ist.

## Methoden
Wenn es um Methoden geht, können Boxing und Unboxing auftreten, wenn Werttypen als Parameter übergeben oder von Methoden zurückgegeben werden, die Referenztypen (wie `object`) erwarten oder liefern. Dies kann insbesondere bei nicht-generischen Sammlungen oder Methoden, die mit `object` arbeiten, vorkommen.

## Methodenparameter und Boxing/Unboxing

### Beispiel 1: Methoden mit `object`-Parametern

Wenn eine Methode einen Parameter vom Typ `object` hat und ein Werttyp als Argument übergeben wird, tritt Boxing auf.
```csharp
public void DisplayObject(object obj)
{
    Console.WriteLine(obj);
}

public void Example()
{
    int number = 123;
    DisplayObject(number); // Boxing tritt hier auf
}
```
In diesem Beispiel wird der `int`-Wert `number` boxed, um ihn als `object` an die `DisplayObject`-Methode zu übergeben.

### Beispiel 2: Methoden mit Rückgabewerten vom Typ `object`
```csharp
public object GetBoxedNumber()
{
    int number = 123;
    return number; // Boxing tritt hier auf
}

public void Example()
{
    object boxedNumber = GetBoxedNumber();
    int number = (int)boxedNumber; // Unboxing tritt hier auf
}
```