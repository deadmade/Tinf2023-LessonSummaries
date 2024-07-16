In C# sind Destruktoren spezielle Methoden, die verwendet werden, um Ressourcen freizugeben und Aufräumarbeiten durchzuführen, bevor ein Objekt endgültig aus dem Speicher entfernt wird. Destruktoren werden automatisch aufgerufen, wenn das Garbage Collection-System feststellt, dass ein Objekt nicht mehr verwendet wird.

## Eigenschaften von Destruktoren

- Destruktoren haben den gleichen Namen wie die Klasse, der sie angehören, jedoch mit einem Tilde-Präfix (`~`).
- Sie haben keine Parameter und keinen Rückgabewert.
- Sie können nicht überladen werden.
- Sie können nicht direkt aufgerufen werden. Sie werden vom Garbage Collector automatisch aufgerufen.
- Eine Klasse kann nur einen Destruktor haben.

## Syntax eines Destruktors

Die Syntax eines Destruktors ist einfach:
```csharp
public class ClassName
{
    // Destruktor
    ~ClassName()
    {
        // Aufräumarbeiten durchführen
    }
}
```

## Beispiel

Hier ist ein Beispiel, das zeigt, wie ein Destruktor in einer Klasse verwendet werden kann:
```csharp
public class FileManager
{
    private string fileName;

    public FileManager(string fileName)
    {
        this.fileName = fileName;
        // Datei öffnen oder andere Initialisierungsaufgaben
        Console.WriteLine($"Datei {fileName} geöffnet.");
    }

    // Destruktor
    ~FileManager()
    {
        // Datei schließen oder andere Aufräumarbeiten
        Console.WriteLine($"Datei {fileName} geschlossen.");
    }
}
```

### Verwendung des `FileManager`
```csharp
class Program
{
    static void Main(string[] args)
    {
        FileManager manager = new FileManager("example.txt");

        // Hier würde die Datei "example.txt" geöffnet sein

        // Das Ende des Gültigkeitsbereichs von `manager` wird erreicht
        // Der Destruktor wird automatisch aufgerufen, wenn der Garbage Collector das Objekt `manager` entfernt
    }
}
```

## Wichtige Hinweise zu Destruktoren

- In modernen C#-Programmen, insbesondere bei der Verwendung von .NET Framework und .NET Core, sollten Destruktoren selten verwendet werden. Stattdessen wird empfohlen, die `IDisposable`-Schnittstelle zu implementieren und die `Dispose`-Methode zu verwenden, um Ressourcen explizit freizugeben.
- Destruktoren können die Garbage Collection verlangsamen, da der Garbage Collector zwei Durchläufe benötigt, um Objekte mit Destruktoren zu entfernen: einen, um den Destruktor aufzurufen, und einen zweiten, um das Objekt tatsächlich zu entfernen.

## Beispiel mit `IDisposable`

Statt Destruktoren zu verwenden, implementiert man besser die `IDisposable`-Schnittstelle:
```csharp
public class FileManager : IDisposable
{
    private string fileName;
    private bool disposed = false;

    public FileManager(string fileName)
    {
        this.fileName = fileName;
        // Datei öffnen oder andere Initialisierungsaufgaben
        Console.WriteLine($"Datei {fileName} geöffnet.");
    }

    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    protected virtual void Dispose(bool disposing)
    {
        if (!disposed)
        {
            if (disposing)
            {
                // Freigabe von verwalteten Ressourcen
            }

            // Freigabe von nicht verwalteten Ressourcen
            Console.WriteLine($"Datei {fileName} geschlossen.");
            disposed = true;
        }
    }

    // Destruktor
    ~FileManager()
    {
        Dispose(false);
    }
}
```

### Verwendung des `FileManager` mit `IDisposable`
```csharp
class Program
{
    static void Main(string[] args)
    {
        using (FileManager manager = new FileManager("example.txt"))
        {
            // Hier würde die Datei "example.txt" geöffnet sein
        }
        // Datei wird automatisch geschlossen, wenn `Dispose` am Ende des using-Blocks aufgerufen wird
    }
}
```