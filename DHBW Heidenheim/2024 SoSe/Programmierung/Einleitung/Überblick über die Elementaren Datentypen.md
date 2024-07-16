C# bietet eine Vielzahl von elementaren Datentypen, die in zwei Hauptkategorien unterteilt sind: Werttypen und Referenztypen. Hier ist ein Überblick über die elementaren Datentypen in C#:

## 🧩 Werttypen

Werttypen speichern tatsächliche Werte direkt im Speicher. Zu den Werttypen gehören:

### 🔢 Ganzzahlige Typen

1. **`byte`**
   - **Speichergröße**: 1 Byte
   - **Wertebereich**: 0 bis 255

2. **`sbyte`**
   - **Speichergröße**: 1 Byte
   - **Wertebereich**: -128 bis 127

3. **`short`**
   - **Speichergröße**: 2 Bytes
   - **Wertebereich**: -32.768 bis 32.767

4. **`ushort`**
   - **Speichergröße**: 2 Bytes
   - **Wertebereich**: 0 bis 65.535

5. **`int`**
   - **Speichergröße**: 4 Bytes
   - **Wertebereich**: -2.147.483.648 bis 2.147.483.647

6. **`uint`**
   - **Speichergröße**: 4 Bytes
   - **Wertebereich**: 0 bis 4.294.967.295

7. **`long`**
   - **Speichergröße**: 8 Bytes
   - **Wertebereich**: -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807

8. **`ulong`**
   - **Speichergröße**: 8 Bytes
   - **Wertebereich**: 0 bis 18.446.744.073.709.551.615

### 🔢 Gleitkommazahlen

1. **`float`**
   - **Speichergröße**: 4 Bytes
   - **Wertebereich**: ±1,5 × 10^−45 bis ±3,4 × 10^38
   - **Genauigkeit**: ca. 6-9 Stellen

2. **`double`**
   - **Speichergröße**: 8 Bytes
   - **Wertebereich**: ±5,0 × 10^−324 bis ±1,7 × 10^308
   - **Genauigkeit**: ca. 15-17 Stellen

3. **`decimal`**
   - **Speichergröße**: 16 Bytes
   - **Wertebereich**: ±1,0 × 10^−28 bis ±7,9 × 10^28
   - **Genauigkeit**: 28-29 Stellen

### 🔤 Andere Werttypen

1. **`char`**
   - **Speichergröße**: 2 Bytes
   - **Wertebereich**: Ein einzelnes 16-Bit-Unicode-Zeichen (0 bis 65.535)

2. **`bool`**
   - **Speichergröße**: 1 Byte
   - **Wertebereich**: `true` oder `false`

## 🧩 Referenztypen

Referenztypen speichern Verweise auf die tatsächlichen Daten, die im Heap-Speicher gespeichert sind.

### 📄 Zeichenketten und Arrays

1. **`string`**
   - Eine Folge von Unicode-Zeichen.
   - Beispiel: `string name = "Hello, World!";`

2. **`object`**
   - Basistyp für alle Datentypen in C#.
   - Kann jeden Werttyp oder Referenztyp speichern.
   - Beispiel: `object obj = 42;`

3. **Arrays**
   - Sammlung von Elementen desselben Typs.
   - Beispiel: `int[] numbers = { 1, 2, 3, 4, 5 };`

## 🔧 Beispielcode

Hier ein kurzer Beispielcode, der die verschiedenen Datentypen zeigt:

```csharp
using System;

class Program
{
    static void Main()
    {
        // Ganzzahlige Typen
        byte a = 255;
        short b = -32768;
        int c = 2147483647;
        long d = 9223372036854775807;

        // Gleitkommazahlen
        float e = 3.14f;
        double f = 2.7182818284;
        decimal g = 1.6180339887m;

        // Andere Werttypen
        char h = 'A';
        bool i = true;

        // Referenztypen
        string j = "Hello, C#!";
        object k = 12345;
        int[] l = { 1, 2, 3, 4, 5 };

        // Ausgabe
        Console.WriteLine($"byte: {a}, short: {b}, int: {c}, long: {d}");
        Console.WriteLine($"float: {e}, double: {f}, decimal: {g}");
        Console.WriteLine($"char: {h}, bool: {i}");
        Console.WriteLine($"string: {j}, object: {k}, array: {string.Join(", ", l)}");
    }
}
```
