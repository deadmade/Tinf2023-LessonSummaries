In C# sind Konstruktoren spezielle Methoden, die verwendet werden, um Objekte einer Klasse zu initialisieren. Sie haben den gleichen Namen wie die Klasse und werden automatisch aufgerufen, wenn eine Instanz der Klasse erstellt wird. Konstruktoren spielen eine entscheidende Rolle bei der Zuweisung von Startwerten zu den Datenfeldern eines Objekts und bei der Ausführung anderer Initialisierungsvorgänge.

## Arten von Konstruktoren

Es gibt verschiedene Arten von Konstruktoren in C#:

### 1. Standardkonstruktor (Parameterloser Konstruktor)

Ein Standardkonstruktor hat keine Parameter und wird verwendet, um ein Objekt mit Standardwerten zu initialisieren.
```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // Standardkonstruktor
    public Person()
    {
        Name = "Unbekannt";
        Age = 0;
    }
}
```

### 2. Parametrisierter Konstruktor

Ein parametrisierter Konstruktor akzeptiert Argumente, die verwendet werden, um die Datenfelder des Objekts zu initialisieren.

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    // Parametrisierter Konstruktor
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
```

### 3. Statischer Konstruktor

Ein statischer Konstruktor wird verwendet, um statische Daten der Klasse zu initialisieren oder eine bestimmte Aktion auszuführen, die nur einmal erfolgen muss. Er hat keinen Zugriffsmodifizierer und keine Parameter.

```csharp
public class Person
{
    public static int Population;

    // Statischer Konstruktor
    static Person()
    {
        Population = 0;
    }

    public Person()
    {
        Population++;
    }
}
```

### 4. Kopierkonstruktor

Ein Kopierkonstruktor erstellt ein neues Objekt als Kopie eines bestehenden Objekts.

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Kopierkonstruktor
    public Person(Person existingPerson)
    {
        Name = existingPerson.Name;
        Age = existingPerson.Age;
    }
}
```