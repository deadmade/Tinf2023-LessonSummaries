## Zweck
- **Lokale Hilfsmethoden**: Durch die Definition innerhalb einer Methode können Hilfsmethoden geschaffen werden, die nur lokal innerhalb dieser Methode benötigt werden. Diese lokalen Hilfsmethoden können spezielle Aufgaben übernehmen, die nur in diesem Kontext sinnvoll sind.
    
- **Stärkere Modularisierung**: Die Aufteilung des Codes in kleinere, klar abgegrenzte Module erhöht die Lesbarkeit und Wartbarkeit des Codes. Jede Methode kann klar abgegrenzte Aufgaben übernehmen, was den gesamten Code strukturierter und verständlicher macht.
    
- **Mehrfacher Aufruf innerhalb der äußeren Methode**: Hilfsmethoden, die innerhalb einer Methode definiert werden, können mehrfach aus der äußeren Methode heraus aufgerufen werden. Dies ermöglicht eine Wiederverwendung von Code innerhalb derselben Methode, ohne dass der Code global zugänglich sein muss.

## Beispiel
```csharp
using System;

class CProgram {
    void LiesZwei(out int z, out int n) {
        int Lies(string name) {
            Console.Write(name + " = ");
            return Convert.ToInt32(Console.ReadLine());
        }

        z = Lies("Erstes Argument");
        n = Lies("Zweites Argument");
    }

    static void Main(string[] args) {
        CProgram p = new CProgram();
        int x, y;
        p.LiesZwei(out x, out y);
        Console.WriteLine("\nx % y = " + (x % y));
    }
}
```