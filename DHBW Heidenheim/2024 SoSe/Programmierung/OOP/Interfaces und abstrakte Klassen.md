In C# sind Interfaces und abstrakte Klassen zwei grundlegende Konzepte zur Implementierung von Polymorphismus und zur Definition von Verträgen für Klassen. Beide Konzepte ermöglichen es, gemeinsame Schnittstellen für verschiedene Klassen zu definieren, aber sie haben unterschiedliche Eigenschaften und Anwendungsbereiche.

## Interfaces

Ein Interface in C# ist eine reine Abstraktion, die nur die Signaturen von Methoden, Eigenschaften, Ereignissen oder Indexern definiert. Es enthält keine Implementierungen. Klassen oder Strukturen, die ein Interface implementieren, müssen alle seine Mitglieder implementieren.

### Eigenschaften von Interfaces

- **Abstraktion**: Ein Interface enthält nur die Signaturen der Mitglieder (keine Implementierungen).
- **Mehrfachvererbung**: Eine Klasse oder Struktur kann mehrere Interfaces implementieren.
- **Sichtbarkeit**: Standardmäßig sind alle Mitglieder eines Interfaces öffentlich.
### Syntax
```csharp
public interface IExample
{
    void MethodA();
    int PropertyB { get; set; }
}
```

### Beispiel

```csharp
public interface IAnimal
{
    void MakeSound();
    void Move();
}

public class Dog : IAnimal
{
    public void MakeSound()
    {
        Console.WriteLine("Bark");
    }

    public void Move()
    {
        Console.WriteLine("Run");
    }
}
```

## Abstrakte Klassen

Eine abstrakte Klasse in C# ist eine Klasse, die nicht instanziiert werden kann und eine teilweise Implementierung enthalten kann. Abstrakte Klassen können abstrakte Methoden (ohne Implementierung) und konkrete Methoden (mit Implementierung) enthalten.

### Eigenschaften von abstrakten Klassen

- **Teilweise Implementierung**: Abstrakte Klassen können sowohl abstrakte als auch konkrete Mitglieder enthalten.
- **Vererbung**: Eine Klasse kann nur eine einzige abstrakte Klasse erben (Einfachvererbung), aber sie kann auch mehrere Interfaces implementieren.
- **Konstruktoren**: Abstrakte Klassen können Konstruktoren haben, um Basisklassen-Initialisierung durchzuführen.

### Syntax
```csharp
public abstract class ExampleBase
{
    public abstract void MethodA();
    public void MethodB()
    {
        Console.WriteLine("MethodB implementation");
    }
}
```

### Beispiel
```csharp
public abstract class Animal
{
    public abstract void MakeSound();
    public void Move()
    {
        Console.WriteLine("Move in an abstract way");
    }
}

public class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Meow");
    }
}
```

### Verwendung
```csharp
class Program
{
    static void Main(string[] args)
    {
        Animal myCat = new Cat();
        myCat.MakeSound(); // Ausgabe: Meow
        myCat.Move(); // Ausgabe: Move in an abstract way
    }
}
```

## Unterschiede zwischen Interfaces und abstrakten Klassen

- **Implementierung**: Interfaces enthalten keine Implementierungen, während abstrakte Klassen sowohl abstrakte als auch konkrete Implementierungen enthalten können.
- **Vererbung**: Eine Klasse kann mehrere Interfaces implementieren, aber nur eine abstrakte Klasse erben.
- **Anwendungsbereich**: Interfaces werden verwendet, um Verträge zu definieren, die von beliebigen Klassen oder Strukturen implementiert werden können, während abstrakte Klassen verwendet werden, um eine gemeinsame Basis für verwandte Klassen bereitzustellen.