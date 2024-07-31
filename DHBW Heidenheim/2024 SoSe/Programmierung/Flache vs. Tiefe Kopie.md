
In C# können Sie das Interface `ICloneable` verwenden, um Objekte zu klonen. Es bietet eine Methode `Clone()`, die verwendet wird, um Kopien von Objekten zu erstellen. Hier zeigen wir, wie man flache und tiefe Kopien mithilfe des `ICloneable`-Interfaces implementiert.

## Flache Kopie mit `ICloneable`

Eine flache Kopie (shallow copy) erstellt eine neue Instanz des Objekts, wobei die Felder der neuen Instanz die gleichen Werte wie die Felder der Originalinstanz enthalten. Bei einer flachen Kopie werden jedoch nur die Referenzen auf die Objekte kopiert, nicht die Objekte selbst.

> [!example]
> ```csharp
> using System;
> 
> public class Address : ICloneable
> {
>     public string City { get; set; }
>     
>     // Implementierung von Clone() für flache Kopie
>     public object Clone()
>     {
>         return this.MemberwiseClone();
>     }
> }
> 
> public class Person : ICloneable
> {
>     public string Name { get; set; }
>     public Address Address { get; set; }
>     
>     // Implementierung von Clone() für flache Kopie
>     public object Clone()
>     {
>         Person clone = (Person)this.MemberwiseClone();
>         clone.Address = (Address)this.Address.Clone(); // Flache Kopie der Adresse
>         return clone;
>     }
> }
> 
> class Program
> {
>     static void Main()
>     {
>         Address address = new Address { City = "Berlin" };
>         Person original = new Person { Name = "John", Address = address };
>         
>         // Erstellen einer flachen Kopie
>         Person shallowCopy = (Person)original.Clone();
>         
>         // Ändern der Adresse in der Kopie
>         shallowCopy.Address.City = "Munich";
>         
>         Console.WriteLine($"Original City: {original.Address.City}"); // Output: Munich
>         Console.WriteLine($"Copy City: {shallowCopy.Address.City}");   // Output: Munich
>     }
> }
> ```

In diesem Beispiel verwendet die Methode `Clone()` von `Person` und `Address` eine flache Kopie. Das `Address`-Objekt wird ebenfalls mithilfe der flachen Kopie geklont. Änderungen an der Adresse in der Kopie beeinflussen auch das Originalobjekt, weil sie beide auf dasselbe `Address`-Objekt zeigen.

## Tiefe Kopie mit `ICloneable`

Eine tiefe Kopie (deep copy) erstellt nicht nur eine neue Instanz des Objekts, sondern auch neue Instanzen aller untergeordneten Objekte. Dies bedeutet, dass Änderungen an den untergeordneten Objekten in der Kopie keine Auswirkungen auf das Originalobjekt haben.

> [!example]
> ```csharp
> using System;
> 
> public class Address : ICloneable
> {
>     public string City { get; set; }
>     
>     // Implementierung von Clone() für tiefe Kopie
>     public object Clone()
>     {
>         return new Address { City = this.City };
>     }
> }
> 
> public class Person : ICloneable
> {
>     public string Name { get; set; }
>     public Address Address { get; set; }
>     
>     // Implementierung von Clone() für tiefe Kopie
>     public object Clone()
>     {
>         Person clone = (Person)this.MemberwiseClone();
>         clone.Address = (Address)this.Address.Clone(); // Tiefe Kopie der Adresse
>         return clone;
>     }
> }
> 
> class Program
> {
>     static void Main()
>     {
>         Address address = new Address { City = "Berlin" };
>         Person original = new Person { Name = "John", Address = address };
>         
>         // Erstellen einer tiefen Kopie
>         Person deepCopy = (Person)original.Clone();
>         
>         // Ändern der Adresse in der Kopie
>         deepCopy.Address.City = "Munich";
>         
>         Console.WriteLine($"Original City: {original.Address.City}"); // Output: Berlin
>         Console.WriteLine($"Copy City: {deepCopy.Address.City}");    // Output: Munich
>     }
> }
> ```

In diesem Beispiel stellt die Methode `Clone()` von `Address` eine tiefe Kopie sicher, indem sie ein neues `Address`-Objekt erstellt. Daher zeigen die `Address`-Referenzen in der Kopie und im Originalobjekt auf unterschiedliche Objekte. Änderungen an der Adresse in der Kopie beeinflussen nicht die Adresse im Originalobjekt.

## Zusammenfassung

- **Flache Kopie**: Kopiert die Werte und Referenzen auf untergeordnete Objekte. Änderungen an den untergeordneten Objekten in der Kopie beeinflussen das Originalobjekt.
- **Tiefe Kopie**: Erstellt vollständige Kopien des Objekts und aller untergeordneten Objekte, sodass Änderungen an der Kopie keine Auswirkungen auf das Original haben.

Verwenden Sie flache Kopien, wenn die Referenzen auf untergeordnete Objekte unverändert bleiben sollen. Verwenden Sie tiefe Kopien, wenn Sie eine vollständige und unabhängige Kopie eines Objekts benötigen.

