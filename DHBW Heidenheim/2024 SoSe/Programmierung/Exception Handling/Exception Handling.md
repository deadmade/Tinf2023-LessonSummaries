> [!info]- **Murphy's Law:**
> "Anything that can go wrong will go wrong."

## Einführung

Bei vielen Methodenaufrufen ist es realistisch und erforderlich, auf Störungen des normalen Ablaufs vorbereitet zu sein. Unterschiedliche Funktionen aus verschiedenen, getrennt entwickelten Modulen müssen zusammenarbeiten. Dies erfordert eine robuste Ausnahmebehandlung, um mit Laufzeitfehlern umzugehen.

## Definition von Ausnahmen

 Wenn eine Funktion während ihres Ablaufs eine "unübliche Situation" (Ausnahme, Exception) feststellt, kann dies durch Programmierfehler (z.B. ungültiger Indexzugriff, Division durch Null) oder besondere Umstände (z.B. Speichermangel, Netzwerkunterbrechung) verursacht werden. Die Reaktion kann unterschiedlich ausfallen:

 - **Fehlermeldung ausgeben und Programm abbrechen**
 - **Fehlerstatus zurückgeben**: Trennung von Fehlerfeststellung (in der Funktion) und Fehlerbehandlung (beim Aufrufer)

## Probleme bei der Rückgabe von Fehlerwerten

 - **Ein Rückgabewert**: Schwierig, Rückgabewerte von Fehlerwerten zu unterscheiden
 - **Mühsame Fehlerabfrage**: Jedes Mal muss der Erfolg des Aufrufs überprüft werden
 - **Vergessene Fehlerbehandlung**: Kann zu falschen Berechnungen führen
 - **Fehlererkennung und -behandlung nicht völlig getrennt**
 - **Bibliotheksfunktionen**: Sollten eine letzte Chance für Aufräumarbeiten bieten

## Fehlerdefinition

 Eine Fehlerklasse wird an der "Unfallstelle" erzeugt. Dies geschieht durch:

>[!implementation]- Implementation
> ```csharp
> public class COdieExcept : Exception {}
> public class CJonExcept : Exception {}
> public class CNermalExcept : Exception {}
> ```

Durch die Verwendung spezifischer Unterklassen können verschiedene Fehlerarten unterschieden und zusätzliche Informationen hinzugefügt werden.

## Fehlererkennung und -signalisierung

 Der Lösungsalgorithmus wird in einen `try`-Block eingeschlossen. Bei einer Ausnahmesituation wird ein Ausnahmeobjekt mit `throw` geworfen:

 ```csharp
 try
 {
     // Lösungsalgorithmus
 }
 catch (Exception e)
 {
     // Fehlerbehandlung
 }
 ```

## Fehlerfangen und -behandlung

 **Reaktionsmöglichkeiten:**

 - **Fortsetzung der Methode**: Angepasst oder mit erneuter Ausnahme
 - **Ignorieren der Ausnahme**: Ausnahmeobjekt wird dem Aufrufer überlassen

## Beispiel: Fakultätsberechnung

> [!example]- Beispiel
> **Beispiel:** Berechnung der Fakultät einer Zahl unter Verwendung der `try`, `catch` und `finally` Blöcke.
>
> ```csharp
> using System;
>
> static void Main(string[] args)
> {
>     if (args.Length == 0)
>     {
>         Console.WriteLine("Kein Argument angegeben");
>         Environment.Exit(1);
>     }
>
>     int argument = Kon2Int(args[0]);
>     if (argument != -1)
>     {
>         double fakul = 1.0;
>         for (int i = 1; i <= argument; i++)
>             fakul *= i;
>         Console.WriteLine("Fakultät von {0}: {1}", args[0], fakul);
>     }
>     else
>     {
>         Console.WriteLine("Keine ganze Zahl im Intervall [0, 170]: " + args[0]);
>     }
> }
>
> static int Kon2Int(string instr)
> {
>     try
>     {
>         int arg = Int32.Parse(instr);
>         if (arg < 0 || arg > 170)
>             throw new OverflowException();
>         return arg;
>     }
>     catch (OverflowException)
>     {
>         return -1;
>     }
>     catch (FormatException)
>     {
>         return -3;
>     }
> }
> ```

## Der `finally`-Block

Ein `finally`-Block wird unter fast allen Umständen ausgeführt:

 - **Nach der ungestörten Ausführung des `try`-Blocks**
 - **Nach einer Exceptionbehandlung in einem `catch`-Block**
 - **Nach dem Auftreten einer unbehandelten Exception im `try`-Block**
 - **Beim Verlassen der `try`-Anweisung durch eine `goto`-Anweisung**

Der `finally`-Block ist ideal zur Freigabe von Ressourcen:

```csharp
finally
{
    // Bereinigungsarbeiten
}
```

