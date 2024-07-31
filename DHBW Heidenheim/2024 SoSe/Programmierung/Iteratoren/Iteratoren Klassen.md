Eine aufzählbare Klasse in C# implementiert das `IEnumerable`-Interface, um benutzerdefinierte Iterationen über ihre Elemente zu ermöglichen. Im folgenden Beispiel zeigen wir, wie man eine einfache aufzählbare Klasse erstellt und verwendet.

## Beispiel: Aufzählbare Klasse `CPeople`

Wir definieren zunächst die Klasse `CPerson`, die einfache Geschäftsinformationen enthält. Dann erstellen wir die Klasse `CPeople`, die eine Sammlung von `CPerson`-Objekten verwaltet und das `IEnumerable<CPerson>`-Interface implementiert, um die Verwendung der `foreach`-Schleife zu ermöglichen.

> [!example]
> ```csharp
> using System;
> using System.Collections;
> using System.Collections.Generic;
>
> // Definiert eine einfache Geschäftsklasse für Personen
> public class CPerson
> {
>     public CPerson(string fName, string lName)
>     {
>         FirstName = fName;
>         LastName = lName;
>     }
>
>     public string FirstName { get; set; }
>     public string LastName { get; set; }
> }
>
> // Definiert eine aufzählbare Klasse für eine Sammlung von Personen
> public class CPeople : IEnumerable<CPerson>
> {
>     private CPerson[] people;
>
>     public CPeople(CPerson[] pArray)
>     {
>         people = new CPerson[pArray.Length];
>         for (int i = 0; i < pArray.Length; i++)
>         {
>             people[i] = pArray[i];
>         }
>     }
>
>     // Implementiert die GetEnumerator-Methode für IEnumerable<CPerson>
>     public IEnumerator<CPerson> GetEnumerator()
>     {
>         for (int i = 0; i < people.Length; i++)
>         {
>             yield return people[i];
>         }
>     }
>
>     // Implementiert die nicht-generische GetEnumerator-Methode für IEnumerable
>     IEnumerator IEnumerable.GetEnumerator()
>     {
>         return GetEnumerator();
>     }
> }
>
> class App
> {
>     static void Main()
>     {
>         CPerson[] peopleArray = new CPerson[3]
>         {
>             new CPerson("John", "Smith"),
>             new CPerson("Jim", "Johnson"),
>             new CPerson("Sue", "Rabon")
>         };
>
>         CPeople peopleList = new CPeople(peopleArray);
>         foreach (CPerson p in peopleList)
>         {
>             Console.WriteLine(p.FirstName + " " + p.LastName);
>         }
>         // Output:
>         // John Smith
>         // Jim Johnson
>         // Sue Rabon
>     }
> }
> ```
>
>In diesem Beispiel:
>
>1. **Klasse `CPerson`**: Definiert eine einfache Person mit Vor- und Nachnamen.
>2. **Klasse `CPeople`**: Enthält ein Array von `CPerson`-Objekten und implementiert das `IEnumerable<CPerson>`-Interface, um die Iteration über die Personen zu ermöglichen.
>3. **Methode `GetEnumerator`**: Gibt einen Iterator zurück, der es ermöglicht, die `CPerson`-Objekte in der Sammlung zu durchlaufen.
>4. **`Main`-Methode**: Erstellt ein Array von `CPerson`-Objekten, initialisiert eine `CPeople`-Sammlung und durchläuft diese mit einer `foreach`-Schleife, um die Namen der Personen auszugeben.


