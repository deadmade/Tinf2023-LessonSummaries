## Empfehlungen für Ausnahmeklassen

> [!tip] **Empfehlungen:**
> - **Basisklasse:**  
>   Als Basisklasse sollte `System.Exception` verwendet werden, z. B.:  
>   ```csharp
>   public class BadFaculArgException : Exception { ... }
>   ```
> - **Klassennamen:**  
>   Der Klassenname sollte mit dem Wort `Exception` enden.
> - **Konstruktoren:**  
>   Die folgenden allgemeinen Konstruktoren für Exceptions sollten mit `public`-Verfügbarkeit implementiert werden:
>   - **Parameterfreier Konstruktor:**  
>     ```csharp
>     public BadFaculArgException() { }
>     ```
>   - **Konstruktor mit einem `string`-Parameter für die Fehlermeldung:**  
>     ```csharp
>     public BadFaculArgException(string message) : base(message) { }
>     ```
>   - **Konstruktor mit einem `string`-Parameter für die Fehlermeldung und einem `Exception`-Parameter für eine innere Exception:**  
>     ```csharp
>     public BadFaculArgException(string message, Exception innerException) : base(message, innerException) { }
>     ```

## Eigene Exceptions definieren

> [!example] **Beispiel für eine benutzerdefinierte Exception:**
>
>```csharp
>using System;
>
>public class BadFaculArgException : Exception // Ableitung von Exception, bad argument in function faculty()
>{
 >   int type = -1, value = -1;
  >  string input;
>
 >   // Parameterfreier Konstruktor
  >  public BadFaculArgException() { }
>
 >   // Konstruktor mit String-Parameter für Fehlermeldung
>    public BadFaculArgException(string message) : base(message) { }
>
>    // Konstruktor mit der inner Exception
 >   public BadFaculArgException(string message, Exception innerException) : base(message, innerException) { }
>
>    // Konstruktor mit zusätzlichem Information
 >   public BadFaculArgException(string message, string input_, int type_, int value_, Exception innerException) 
 >       : base(message, innerException)
  >  {
   >     input = input_;
 >       // zu konvertierende Zeichenfolge
 >       if (type_ >= 0 && type <= 3) type = type_;
 >       // numerischer Indikator für die Fehlerart:
 >       if (type_ == 4 && (value_ < 0 || value_ > 170))
 >       {
 >           // 0: Unbekannt
 >           // 1: Argument hat den Wert null
 >           // 2: Zeichenfolge kann nicht konvertiert werden
 >           // 3: int-Überlauf
 >           // 4: int-Wert außerhalb [0, 170]
 >           type = type_;
 >           value = value_;
 >       }
 >   }
>
>    public string Input { get { return input; } }
>    public int Type { get { return type; } }
>    public int Value { get { return value; } }
>}
>```

