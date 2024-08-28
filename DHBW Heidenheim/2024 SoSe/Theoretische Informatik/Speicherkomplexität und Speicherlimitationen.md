Bei der Effizienzanalyse von Algorithmen konzentriert man sich nicht nur auf die Laufzeitkosten, sondern auch auf den Speicherbedarf. Der Speicherbedarf ist besonders wichtig, wenn:

- **Speicher knapp** ist, beispielsweise auf Geräten mit begrenztem Speicher.
- **Datenmengen sehr groß** sind, wie im Fall von Big Data.

Algorithmen sollten sowohl schnell als auch speichereffizient sein. Man muss jedoch entscheiden, ob man Geschwindigkeit über Speicherverbrauch stellt oder umgekehrt.

## Big-O-Notation für Speicherbedarf

Neben der Zeitkomplexität, die beschreibt, wie viele Schritte ein Algorithmus bei einer bestimmten Anzahl von Datenelementen (N) benötigt, gibt es die Speicherkomplexität, die sich darauf konzentriert, wie viele Speichereinheiten ein Algorithmus zusätzlich bei N Datenelementen benötigt.

### Beispiel: Funktion `MakeUppercase()`

Die Funktion `MakeUppercase()` nimmt ein Array von Strings und gibt ein neues Array zurück, in dem alle Strings in Großbuchstaben konvertiert sind.

- Eingabe: `["fred", "anna", "oskar", "gerda"]`
- Ausgabe: `["FRED", "ANNA", "OSKAR", "GERDA"]`

> [!example]- 📌 **Beispiel in C#:**
> ```csharp
> string[] MakeUppercase(string[] inputArray)
> {
>     string[] resultArray = new string[inputArray.Length];
>     for (int i = 0; i < inputArray.Length; i++)
>     {
>         resultArray[i] = inputArray[i].ToUpper();
>     }
>     return resultArray;
> }
> ```
> In diesem Fall werden zwei Arrays im Hauptspeicher gehalten: das Originalarray und das neu erzeugte Array. Der Gesamtspeicherbedarf ist proportional zur Menge der Eingangsdaten, also O(N).

### Speichereffiziente Version (In-Place)

Eine speichereffizientere Variante verzichtet auf die Erzeugung eines neuen Arrays und modifiziert das übergebene Array direkt ("in place").

> [!example]- 📌 **Beispiel in C#:**
> ```csharp
> void MakeUppercaseInPlace(string[] inputArray)
> {
>     for (int i = 0; i < inputArray.Length; i++)
>     {
>         inputArray[i] = inputArray[i].ToUpper();
>     }
> }
> ```
> In dieser Version wird kein zusätzlicher Speicher benötigt. Der Speicherbedarf ist konstant, also O(1).

## Vergleich der Implementierungen

| Version    | Zeitkomplexität | Speicherkomplexität |
|------------|-----------------|---------------------|
| Version #1 | O(N)            | O(N)                |
| Version #2 | O(N)            | O(1)                |

## Trade-offs zwischen Zeit und Speicher

Manchmal muss man zwischen Zeit und Speicher abwägen. Ein Algorithmus kann schneller sein, benötigt aber mehr Speicher, oder er ist langsamer, benötigt aber weniger Speicher.

### Beispiel: Überprüfung auf Duplikate in einem Array

#### Version #1

- **Zeitkomplexität:** O(N²) (verschachtelte Schleifen)
- **Speicherkomplexität:** O(1) (kein zusätzlicher Speicher)

#### Version #2

- **Zeitkomplexität:** O(N) (eine Schleife und ein zusätzliches Array)
- **Speicherkomplexität:** O(M), wobei M der Wertebereich des Arrays ist.

> [!example]- 📌 **Beispiel in C#:**
> ```csharp
> // Version #1: Ineffizient aber speicherschonend
> bool ContainsDuplicates(string[] array)
> {
>     for (int i = 0; i < array.Length; i++)
>     {
>         for (int j = i + 1; j < array.Length; j++)
>         {
>             if (array[i] == array[j])
>                 return true;
>         }
>     }
>     return false;
> }
>
> // Version #2: Effizient aber speicherintensiver
> bool ContainsDuplicatesEfficient(string[] array)
> {
>     var set = new HashSet<string>();
>     foreach (var item in array)
>     {
>         if (set.Contains(item))
>             return true;
>         set.Add(item);
>     }
>     return false;
> }
> ```

### Effizienz der verschiedenen Versionen

| Version    | Zeitkomplexität | Speicherkomplexität |
|------------|-----------------|---------------------|
| Version #1 | O(N²)           | O(1)                |
| Version #2 | O(N)            | O(M)                |
| Version #3 | O(N log N + N)  | O(log N)            |

- **Version #2** ist optimal, wenn Geschwindigkeit benötigt wird und der maximale Wertebereich bekannt und handhabbar ist.
- **Version #1** ist optimal, wenn der Speicher knapp ist oder der Wertebereich sehr groß oder unbekannt ist.
- **Version #3** bietet einen guten Kompromiss zwischen Zeit und Platz.

## Sortierung großer, externer Datenmengen

Bei der Sortierung externer Daten kann nicht die gesamte Datenmenge gleichzeitig in den Speicher geladen werden. Stattdessen werden Teilmengen sortiert, was zusätzliche Strategien wie "Divide and Conquer" (Teile, Sortiere und Erobere) erfordert. Dieser Ansatz erlaubt auch eine Parallelisierung auf mehrere Rechenkerne, wodurch die Effizienz weiter gesteigert werden kann.
