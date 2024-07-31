In C# werden sowohl **Interfaces** als auch **abstrakte Klassen** verwendet, um die Struktur und das Verhalten von Klassen zu definieren. Hier sind die wesentlichen Unterschiede und Anwendungsfälle:

## Interfaces

> [!info]
> Ein **Interface** ist eine Sammlung von Methodensignaturen, die von einer Klasse implementiert werden müssen. Interfaces enthalten keine Implementierung, sondern nur die Definition von Methoden, Eigenschaften, Ereignissen oder Indexern.

### Merkmale

- **Mehrfachvererbung**: Eine Klasse kann mehrere Interfaces implementieren.
- **Zugriffsmodifizierer**: Alle Mitglieder eines Interfaces sind standardmäßig `public`.
- **Eigenschaften und Ereignisse**: Interfaces können Eigenschaften, Methoden, Ereignisse und Indexer deklarieren.
- **Standardmethoden (ab C# 8.0)**: Interfaces können Standardimplementierungen für Methoden enthalten.

### Beispiel

>[!example]- **Beispiel für ein Interface:**
>```csharp
> public interface IAnimal
> {
>     void Eat();
>     void Sleep();
> }
> 
> public class Dog : IAnimal
> {
>     public void Eat()
>     {
>         // Implementierung
>     }
> 
>     public void Sleep()
>     {
>         // Implementierung
>     }
> }
>```

## Abstrakte Klassen

>[!info]
>Eine **abstrakte Klasse** ist eine Klasse, die nicht direkt instanziiert werden kann und dazu dient, andere Klassen zu definieren. Sie kann sowohl abstrakte Methoden (Methoden ohne Implementierung) als auch nicht-abstrakte Methoden (Methoden mit Implementierung) enthalten.

### Merkmale

- **Teilweise Implementierung**: Abstrakte Klassen können sowohl abstrakte als auch nicht-abstrakte Methoden enthalten.
- **Vererbung**: Eine Klasse kann nur von einer abstrakten Klasse erben.
- **Zugriffsmodifizierer**: Mitglieder einer abstrakten Klasse können unterschiedliche Zugriffsmodifizierer haben (`public`, `protected`, `private`).
- **Konstruktoren**: Abstrakte Klassen können Konstruktoren haben.
- **Zustand**: Abstrakte Klassen können Felder und Eigenschaften mit Zustand definieren.

### Beispiel

> [!example]- **Beispiel für eine abstrakte Klasse:**
> ```csharp
>  public abstract class Animal
> {
>     public abstract void Eat();
> 
>     public void Sleep()
>     {
>         // Implementierung
>     }
> }
> 
> public class Dog : Animal
> {
>     public override void Eat()
>     {
>         // Implementierung
>     }
> }
> ```
## Vergleich

|Feature|Interface|Abstrakte Klasse|
|---|---|---|
|**Methoden**|Keine Implementierung|Kann Implementierung enthalten|
|**Mehrfachvererbung**|Ja, mehrere Interfaces möglich|Nein, nur eine Basisklasse|
|**Konstruktoren**|Nein|Ja|
|**Felder**|Nein|Ja, kann Felder enthalten|
|**Zugriffsmodifizierer**|Alle Mitglieder sind `public`|Verschiedene Modifizierer möglich|
|**Eigenschaften**|Ja|Ja|
|**Standardmethoden**|Ja, ab C# 8.0|Nein|

## Wann verwenden?

- **Interfaces**: Ideal, wenn du eine bestimmte Funktionalität bereitstellen möchtest, die von verschiedenen Klassen unabhängig implementiert werden soll. Sie sind nützlich für die Definition von Verträgen oder APIs.
    
- **Abstrakte Klassen**: Besser geeignet, wenn du eine Basisstruktur mit gemeinsamen Implementierungen für mehrere Klassen bereitstellen möchtest. Sie ermöglichen es dir, eine grundlegende Implementierung zu teilen und gleichzeitig spezifische Details zu vererben.
