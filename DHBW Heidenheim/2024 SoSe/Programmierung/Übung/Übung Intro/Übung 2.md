Experimentieen Sie mit dem Hallo-Beispielprogramm

- Ergänzen Sie weitere Ausgabeanweisungen#
```csharp
using System;

class Program {
    static void Main() {
        Console.WriteLine("Hello, World!");
        Console.WriteLine("Hello, Cake");
        Console.WriteLine("Mr. Cake!!");
    }
}

```

- Erstellen Sie eine Variante ohne using-Direktive
```csharp


class Program {
    static void Main() {
        System.Console.WriteLine("Hello, World!");
        System.Console.WriteLine("Hello, Cake");
        System.Console.WriteLine("Mr. Cake!!");
    }
}
```