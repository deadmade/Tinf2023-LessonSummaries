## Generisches Programmieren in C#

Generisches Programmieren in C# ermöglicht es, Klassen, Strukturen, Methoden und Interfaces zu erstellen, die mit verschiedenen Datentypen arbeiten können, ohne dass der Code für jeden Datentyp neu geschrieben werden muss. Dies fördert die Wiederverwendbarkeit und Typsicherheit des Codes.

### Einführung in Generics

Generics erlauben es, Platzhalter für Datentypen in Klassen, Strukturen, Methoden und Interfaces zu verwenden. Diese Platzhalter werden bei der Verwendung der generischen Typen zur Laufzeit durch konkrete Datentypen ersetzt.

### Beispiel für eine generische Klasse

Angenommen, wir möchten eine Klasse zur Verwaltung von Objekten erstellen, die unterschiedliche Typen enthalten kann, wie Fahrzeuge oder Wohnungen. Statt für jeden Typ eine separate Klasse zu erstellen, können wir eine generische Klasse verwenden:


>[!code]- **Beispiel: Generische Klasse**
> ```csharp
> public class RentalManager<T>
> {
>    private List<T> rentals = new List<T>();
 >   private List<T> booked = new List<T>();
>
>    public void Book(T item) { booked.Add(item); }
>    public bool CancelBooking(T item) { return booked.Remove(item); }
>    public void AddRentalObject(T item) { rentals.Add(item); }
>    public void RemoveRentalObject(T item) { rentals.Remove(item); }
>    public float CalculateCost(T item, DateTime from, DateTime to)
>    {
>        // Kostenberechnung implementieren
>        return 0f;
>    }
>}
>```

### Verwendung von Generics

Um diese generische Klasse für verschiedene Typen zu nutzen, erstellen wir Instanzen der Klasse mit den gewünschten Typen:

>[!code]- **Beispiel: Verwendung der generischen Klasse**
> ```csharp
> public class Vehicle
> {
>    public float PricePerDay { get; set; }
>    public int Seats { get; set; }
> }
>
> public class Home
> {
>    public float PricePerDay { get; set; }
>    public int SquareMeter { get; set; }
> }
>
>// Verwenden der generischen Klasse für verschiedene Typen
>RentalManager<Vehicle> vehicleManager = new RentalManager<Vehicle>();
>RentalManager<Home> homeManager = new RentalManager<Home>();
>```
### Generische Methoden

Generische Methoden können ähnlich wie generische Klassen Typ-Parameter verwenden. 

> [!code]- **Beispiel: Verwendung von Genrischen Methoden**
> ```code
> public T Max<T>(T x, T y) where T : IComparable<T>
> {
 >   return x.CompareTo(y) > 0 ? x : y;
> }
> ```

Hier ist `T` der Typ-Parameter, und `T` muss das `IComparable<T>` Interface implementieren, um den Vergleich durchzuführen.

### Typrestriktionen

Generische Typen können durch Restriktionen eingeschränkt werden.

> [!code]- **Beispiel: Typrestriktionen**
> ```csharp
> public class LimitedClass<T> where T : IComparable<T>
> {
>     // T muss IComparable<T> implementieren
> }
> ```

### Generische Interfaces

Generische Interfaces arbeiten auf ähnliche Weise wie generische Klassen:

> [!code]- **Beispiel: Generisches Interface**
> ```csharp
> public interface IRepository<T>
> {
>    void Add(T item);
>    T Get(int id);
> }
> ```

> [!code]- **Beispiel: Implementierung eines generischen Interfaces**
> ```csharp
> public class VehicleRepository : IRepository<Vehicle>
> {
>    public void Add(Vehicle item) { /* Implementierung */ }
>    public Vehicle Get(int id) { /* Implementierung */ return new Vehicle(); }
> }
> ```

