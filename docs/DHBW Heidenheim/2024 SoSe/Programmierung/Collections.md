Generische Collections in C# bieten leistungsstarke Container für verschiedene Datentypen und -strukturen. Sie befinden sich im Namensraum `System.Collections.Generic`. Im Vergleich zu nicht-generischen Collections sind sie typsicher und bieten bessere Leistung und Flexibilität.

## Übersicht

### Namensräume

- **`System.Collections.Generic`**: Enthält generische Collections wie `List<T>`, `Dictionary<TKey, TValue>`, `HashSet<T>`, und mehr.
- **`System.Collections.Concurrent`**: Bietet thread-sichere Collections wie `BlockingCollection<T>`, `ConcurrentDictionary<TKey, TValue>`, `ConcurrentQueue<T>`, und `ConcurrentStack<T>`.

### Veraltete Klassen

Vermeide die Verwendung von nicht-generischen Klassen aus `System.Collections`, wie z.B. `ArrayList`, `HashTable`, `Queue`, und `Stack`, da sie nicht typsicher sind.

---

## Arrays vs. Collections

### Schwächen von Arrays

- **Feste Größe**: Die Größe muss beim Erstellen festgelegt werden und kann nicht mehr verändert werden.
- **Aufwand beim Einfügen/Entfernen**: Das Einfügen und Entfernen von Elementen ist aufwändig.
- **Kovarianz**: Arrays unterstützen Kovarianz, was zu Laufzeitfehlern führen kann.

>[!example]- **Beispiel für Kovarianz:**  
> ```csharp  
> object[] oarr = new string[] { "a", "b" };  
> oarr[0] = 13;  // Laufzeitfehler: System.ArrayTypeMismatchException  
> ```  

---

## Collection Klassen

Hier sind einige der wichtigsten Collection-Klassen in C#:

| Klasse | Beschreibung |
|--------|--------------|
| **`Dictionary<TKey, TValue>`** | Key-Value-Paare (Hash-Tabelle) |
| **`HashSet<T>`** | Duplikatfreies, ungeordnetes Set |
| **`LinkedList<T>`** | Doppelt verlinkte Liste |
| **`List<T>`** | Stark typisierte Liste mit Indexzugriff |
| **`PriorityQueue<TElement, TPriority>`** | Elemente mit Wert und Priorität |
| **`Queue<T>`** | First-in, First-out (FIFO) Collection |
| **`SortedDictionary<TKey, TValue>`** | Key-Value-Paare, nach Key sortiert |
| **`SortedList<TKey, TValue>`** | Sortierte Key-Value-Paare |
| **`SortedSet<T>`** | Sortierte Collection ohne Duplikate |
| **`Stack<T>`** | Last-in-First-out (LIFO) Collection |

---

## `ICollection<T>` Interface

### Methoden

| Methode | Beschreibung |
|---------|--------------|
| **`Add(T element)`** | Fügt ein Element hinzu. |
| **`Contains(T element)`** | Überprüft, ob ein Element vorhanden ist. |
| **`Remove(T element)`** | Entfernt das erste Vorkommen eines Elements. |
| **`CopyTo(T[] array, int index)`** | Kopiert die Elemente in ein Array. |
| **`Clear()`** | Entfernt alle Elemente. |

### Eigenschaften

| Eigenschaft | Beschreibung |
|-------------|--------------|
| **`Count`** | Gibt die Anzahl der Elemente zurück. |
| **`IsReadOnly`** | Gibt an, ob die Collection schreibgeschützt ist. |

---

## Verwaltung einer Liste (`List<T>`)

- **`List<T>`** speichert Elemente in einem dynamischen Array `T[]`, das bei Bedarf vergrößert wird.
- **`Capacity`** ist meist größer als **`Count`**.

### Wichtige Methoden und Eigenschaften

| Methode | Beschreibung |
|---------|--------------|
| **`IndexOf(T element)`** | Gibt den Index des ersten Vorkommens zurück. |
| **`Insert(int pos, T element)`** | Fügt ein Element an der angegebenen Position ein. |
| **`RemoveAt(int pos)`** | Entfernt das Element an der angegebenen Position. |
| **`AsReadOnly()`** | Gibt eine schreibgeschützte Sicht auf die Liste zurück. |

>[!example]- **Beispiel für `List<T>`:**  
> ```csharp  
> List<string> names = new List<string> { "Alice", "Bob", "Charlie" };  
> names.Add("Diana");  
> names.RemoveAt(1); // Entfernt "Bob"  
> int index = names.IndexOf("Charlie"); // Gibt den Index von "Charlie" zurück  
> ```  
![[Pasted image 20240730112759.png]]

### Suchen und Sortieren

| Methode | Beschreibung |
|---------|--------------|
| **`BinarySearch`** | Sucht ein Element in der sortierten Liste. |
| **`Find`** | Findet das erste Vorkommen eines Elements, das den angegebenen Bedingungen entspricht. |
| **`Sort`** | Sortiert die Liste nach den angegebenen Vergleichskriterien. |

>[!example]- **Beispiel für Suchen und Sortieren:**  
> ```csharp  
> List<int> numbers = new List<int> { 4, 2, 9, 1, 5 };  
> numbers.Sort(); // Sortiert die Liste  
> int index = numbers.BinarySearch(5); // Gibt den Index von 5 zurück  
> bool exists = numbers.Exists(n => n > 8); // Überprüft, ob ein Wert größer als 8 existiert  
> ```  

---

## Verwaltung einer Liste (`LinkedList<T>`)

- **`LinkedList<T>`** verwendet doppelt verkettete Elemente für effizientes Einfügen und Entfernen.

### Wichtige Methoden

| Methode | Beschreibung |
|---------|--------------|
| **`AddFirst(T element)`** | Fügt ein Element am Anfang hinzu. |
| **`AddLast(T element)`** | Fügt ein Element am Ende hinzu. |
| **`AddBefore(LinkedListNode<T> node, T element)`** | Fügt ein Element vor einem bestimmten Knoten hinzu. |
| **`AddAfter(LinkedListNode<T> node, T element)`** | Fügt ein Element nach einem bestimmten Knoten hinzu. |
| **`RemoveFirst()`** | Entfernt das erste Element. |
| **`RemoveLast()`** | Entfernt das letzte Element. |

>[!example]- **Beispiel für `LinkedList<T>`:**  
> ```csharp  
> LinkedList<string> linkedList = new LinkedList<string>();  
> linkedList.AddLast("Alice");  
> linkedList.AddFirst("Bob");  
> LinkedListNode<string> node = linkedList.Find("Alice");  
> linkedList.AddAfter(node, "Charlie");  
> linkedList.RemoveFirst(); // Entfernt "Bob"  
> ```  

---

## Verwaltung eines Sets
![[Pasted image 20240730112823.png]]
### `HashSet<T>`

- **`HashSet<T>`** verwendet eine Hash-Tabelle für schnelle Existenzprüfungen.

### Wichtige Methoden

| Methode | Beschreibung |
|---------|--------------|
| **`Add(T element)`** | Fügt ein Element hinzu, wenn es noch nicht existiert. |
| **`Contains(T element)`** | Überprüft, ob ein Element vorhanden ist. |
| **`IntersectWith(IEnumerable<T> other)`** | Intersectiert das Set mit einem anderen. |
| **`UnionWith(IEnumerable<T> other)`** | Vereinigt das Set mit einem anderen. |
| **`ExceptWith(IEnumerable<T> other)`** | Entfernt Elemente, die in einem anderen Set enthalten sind. |

>[!example]- **Beispiel für `HashSet<T>`:**  
> ```csharp  
> HashSet<string> set1 = new HashSet<string> { "A", "B", "C" };  
> HashSet<string> set2 = new HashSet<string> { "B", "C", "D" };  
> set1.UnionWith(set2); // Vereinigt set1 mit set2  
> set1.ExceptWith(set2); // Entfernt Elemente, die in set2 vorhanden sind  
> bool contains = set1.Contains("A"); // Überprüft, ob "A" vorhanden ist  
> ```  

### `SortedSet<T>`

- **`SortedSet<T>`** verwendet einen balancierten Binärbaum, um Elemente sortiert zu halten.

---

## Verwaltung von (Schlüssel-Wert) – Paaren
![[Pasted image 20240730112852.png]]

### `Dictionary<TKey, TValue>`

- **`Dictionary<TKey, TValue>`** speichert Key-Value-Paare ohne Duplikate.

### Wichtige Methoden

| Methode | Beschreibung |
|---------|--------------|
| **`Add(K key, V value)`** | Fügt ein Paar hinzu. |
| **`ContainsKey(K key)`** | Überprüft, ob ein Schlüssel vorhanden ist. |
| **`TryGetValue(K key, out V value)`** | Versucht, den Wert für einen Schlüssel abzurufen. |

>[!example]- **Beispiel für `Dictionary<TKey, TValue>`:**  
> ```csharp  
> Dictionary<string, int> dictionary = new Dictionary<string, int>();  
> dictionary.Add("Alice", 25);  
> dictionary.Add("Bob", 30);  
> if (dictionary.TryGetValue("Alice", out int age)) {  
>     Console.WriteLine($"Alice ist {age} Jahre alt.");  
> }  
> ```  
