## ref Parameter
Der Parameter wird als Referenz übergeben und ist sowohl lesbar als auch schreibbar. Der Parameter muss vor dem Aufruf initialisiert sein.

### Beispiel
```csharp
using System;

class Prog {
    void Tausche(ref int a, ref int b) {
        int temp = a;
        a = b;
        b = temp;
    }

    static void Main() {
        Prog p = new Prog();
        int x = 1, y = 2;
        Console.WriteLine("Vorher: x={0}, y={1}", x, y);
        p.Tausche(ref x, ref y);
        Console.WriteLine("Nachher: x={0}, y={1}", x, y);
    }
}

```

## out Parameter
Der Parameter wird als Referenz übergeben und ist in der Methode nur schreibbar. Der Parameter muss vor dem Aufruf nicht initialisiert sein.

### Beispiel
```csharp
using System;

class Prog {
    void Lies(out int x, out int y) {
        Console.Write("x = ");
        x = Convert.ToInt32("1"); //Eingabe Konsole
        Console.Write("y = ");
        y = Convert.ToInt32("2"); // Eingabe Konsole
    }

    static void Main() {
        Prog p = new Prog();
        int x, y;
        p.Lies(out x, out y);
        Console.WriteLine("\nx % y = " + (x % y));
    }
}
```

## in Parameter
Der Parameter wird als Referenz übergeben, ist aber in der Methode nur lesbar. Der Parameter muss vor dem Aufruf initialisiert sein.

### Beispiel
```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 5;
        int y = 10;
        PrintValues(in x, in y);
    }

    static void PrintValues(in int a, in int b)
    {
        Console.WriteLine($"a: {a}, b: {b}"); // Ausgabe: a: 5, b: 10
        // a und b sind nur lesbar und können hier nicht geändert werden.
    }
}
```

## Params-Parameter 
-  Der `params`-Modifikator erlaubt die Übergabe einer variablen Anzahl von Parametern gleichen Typs an eine Methode.
- Der Parameter muss in der Definition durch das Schlüsselwort `params` gekennzeichnet werden.
- Der `params`-Parameter muss der letzte Parameter in der Parameterliste sein.
- Beim Aufruf der Methode wird `params` nicht angegeben; die Werte werden einfach durch Kommas getrennt.

### Beispiel
```csharp
using System;

class Prog {
    void PrintSum(params double[] args) {
        double summe = 0.0;
        foreach (double arg in args) {
            summe += arg;
        }
        Console.WriteLine("Die Summe ist = " + summe);
    }

    static void Main() {
        Prog p = new Prog();
        p.PrintSum(1.2, 1.0);
        p.PrintSum(1.2, 1.0, 3.6);
    }
}
```
