## 📝 Stack

Der Stack ist ein spezieller Speicherbereich, der verwendet wird, um die Ausführung von Programmen zu verwalten. Jede Funktion hat einen eigenen "Stack Frame", der beim Aufrufen der Funktion angelegt wird und lokale Variablen sowie Funktionsparameter speichert. Der Zugriff auf den Stack ist sehr schnell und effizient.

### Verwendung

Der Stack wird für die Speicherung von primitiven Datentypen (z.B. int, float, bool), Funktionsparametern und lokalen Variablen genutzt.

### Lebensdauer

Variablen im Stack leben nur innerhalb der Dauer des zugehörigen Funktionsaufrufs.

---

## 🗄️ Heap

Der Heap ist ein größerer und allgemeinerer Speicherbereich, der zur dynamischen Speicherung von Objekten und Datenstrukturen dient. Im Gegensatz zum Stack erfolgt die Speicherung im Heap zur Laufzeit und erfordert mehr Verwaltungsaufwand.

### Verwendung

Der Heap wird für die Speicherung von Objekten (Instanzen von Klassen), Arrays und anderen dynamischen Datenstrukturen verwendet.

### Lebensdauer

Objekte im Heap bleiben solange erhalten, bis sie nicht mehr referenziert werden und vom Garbage Collector eingesammelt werden.

---

## 🔄 Unterschiede zusammengefasst

### Zugriff und Geschwindigkeit

Der Zugriff auf den Stack ist schneller und direkter im Vergleich zum Heap, der langsamer aufgrund der dynamischen Allokation ist.

### Lebensdauer

Variablen im Stack haben eine begrenzte Lebensdauer, abhängig vom Funktionsaufruf. Objekte im Heap können eine längere Lebensdauer haben, basierend auf der Verwaltung ihrer Referenzen.
