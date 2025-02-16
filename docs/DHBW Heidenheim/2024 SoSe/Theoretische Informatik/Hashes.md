# Hashes und Hash-Tabellen erklärt

## Verwendung in einem Fast-Food-Bestellprogramm
Ein praktisches Beispiel, bei dem Hash-Tabellen verwendet werden können, ist ein Programm für Online-Bestellungen bei einem Fast-Food-Restaurant. Hier soll eine Speisekarte mit Preisen angeboten werden. Man könnte dies technisch mit einem Array von Strukturen (structs) umsetzen. 

> [!info] **Hinweis**:
>  Ist das Array unsortiert, benötigt die Suche nach dem Preis eines Gerichts \(O(N)\) Schritte für eine lineare Suche. Ist das Array nach den Namen der Gerichte sortiert, reduziert sich die Suche auf \(O(log N)\) Schritte für eine binäre Suche. Dennoch kann die Suche mit Hash-Tabellen auf \(O(1)\) reduziert werden.

## Grundlagen der Hash-Tabellen
Eine Hash-Tabelle ist eine Datenstruktur, die aus geordneten Schlüssel-Wert-Paaren besteht (z.B. Gericht und Preis). Die meisten modernen Programmiersprachen unterstützen Hash-Tabellen, auch bekannt unter verschiedenen Namen:
- Hashes (Ruby)
- Maps (JavaScript)
- Hash maps (Java)
- Dictionaries (C#, Python)
- Associative containers (C++)

> [!faq] **Wichtig**:
>  Das Nachschlagen eines Wertes in einer Hash-Tabelle hat im Durchschnitt eine Effizienz von \(O(1)\).

## Hashing und Hash-Funktionen
Hashing ist der Prozess, Zeichen oder große Zahlen in kleinere Zahlen zu konvertieren. Eine Hash-Funktion definiert die Vorschrift, nach der diese Konvertierung erfolgt. Beispiele für einfache Hash-Funktionen:
1. **Summenbildung**: Die Stellenzahlen der Buchstaben werden summiert. Zum Beispiel wird "BAD" zu 2+1+4 = 7.
2. **Produktbildung**: Die Stellenzahlen der Buchstaben werden multipliziert. Zum Beispiel wird "BAD" zu 2*1*4 = 8.

> [!info] **Hinweis**:
>  Eine gültige Hash-Funktion muss bei jeder Benutzung den gleichen Schlüssel (String) in die gleiche Zahl umwandeln.

## Komplexere Hash-Funktionen
Einige Beispiele für komplexere Hash-Funktionen sind:
- **Divisionsrestmethode**: $h(x) = x \mod \text{Hashgröße}$
- **Mitt-Quadrat-Methode**: Ein Wert wird quadriert und bestimmte Ziffern aus der Mitte des Quadrats werden als Hashwert entnommen.
- **Zerlegungsmethode**: Die Ziffern des Wertes werden in Blöcke geteilt und mathematische Operationen darauf angewendet.

## Behandlung von Kollisionen
> [!error]**Kollision**: 
> Eine Kollision tritt auf, wenn zwei Schlüssel denselben Hash-Wert ergeben. Es gibt verschiedene Methoden, um Kollisionen zu behandeln:

1. **Chaining (Verkettung)**: Jeder Eintrag in der Hash-Tabelle verweist auf eine Liste von Werten, die denselben Hash-Wert haben.
2. **Sondierung**: Eine alternative Position in der Hash-Tabelle wird gesucht, wenn der berechnete Platz bereits belegt ist.

## Methoden
Es gibt zwei Hauptmethoden des Hashings:
- **Offenes Hashing (Chaining)**: Jeder Behälter kann beliebig viele Elemente aufnehmen.
- **Geschlossenes Hashing (Sondierung)**: Jeder Behälter kann nur eine konstante Anzahl von Schlüsseln aufnehmen.

## Effizienz von Hash-Tabellen
Die Effizienz einer Hash-Tabelle hängt von drei Faktoren ab:
- Anzahl der gespeicherten Daten
- Anzahl der Zellen in der Hash-Tabelle
- Verwendete Hash-Funktion

> [!info] **Tipp**: 
> Ein gutes Verhältnis von Elementen zu Tabellengröße liegt bei etwa 7 Elementen pro 10 Zellen, was einem Lastfaktor von etwa 0.7-0.8 entspricht.

## Anwendungsbereiche von Hash-Tabellen
Hash-Tabellen eignen sich besonders gut für:
- Wörterbücher
- Lagerverwaltung (Waren und Anzahl)
- Abstimmungen (Kandidat und Stimmenzahl)
- HTTP-Statuscodes (Code und Bedeutung)

> [!info] **Hinweis**: 
> Auch wenn Daten nicht paarweise existieren, können Hash-Tabellen genutzt werden, um Implementierungen schneller zu machen. Beispielsweise können sie verwendet werden, um zu prüfen, ob ein Array ein Teilmengen eines anderen Arrays ist.


