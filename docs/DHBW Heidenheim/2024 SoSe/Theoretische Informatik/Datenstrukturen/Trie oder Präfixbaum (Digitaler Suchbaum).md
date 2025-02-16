Ein Trie (auch Präfixbaum oder digitaler Suchbaum genannt) ist eine spezielle Datenstruktur, die häufig in Anwendungen wie Autovervollständigung, IP-Adress-Lookup und Telefonnummernsuche verwendet wird. Ein Trie ermöglicht eine effiziente Suche nach Zeichenketten, wobei die Zeitkomplexität unabhängig von der Anzahl der gespeicherten Wörter ist.

## Funktionsweise des Autocomplete-/Autovervollständigungs-Features

Ein Beispiel für die Verwendung von Tries ist das Autovervollständigungs-Feature. Bei der Eingabe eines Präfixes, wie z.B. „Fr“, könnte der Benutzer Vorschläge wie „Frau“ und „Freitag“ erhalten. Ein Trie kann diese Funktionalität effizient unterstützen.

### Annahmen für die Implementierung

- Die Applikation hat Zugriff auf ein vollständiges Wörterbuch.
- Alle Wörter sind in einem Array gespeichert.

Bei einem unsortierten Array wären die Zugriffskosten O(N), was für große N (Anzahl der Wörter im Wörterbuch) ineffizient wäre. Eine Hash-Tabelle hilft in diesem Fall auch nicht, da die Hash-Funktion auf das gesamte Wort abzielt. Ein Trie ermöglicht jedoch eine schnellere Suche, da es eine O(K) Zeitkomplexität hat, wobei K die Länge des Suchstrings ist.

## Aufbau eines Trie-Knotens

Ein Trie besteht aus einer Menge vernetzter Knoten, die keine binäre Baumstruktur bilden. Jeder Trie-Knoten kann beliebig viele Kinder haben. In dieser Implementierung besteht jeder Knoten aus einer Hash-Tabelle, deren Keys die Buchstaben des Alphabets sind und deren Werte auf andere Knoten zeigen.

![[{35F23EFD-015A-46E7-8040-1A3FE34C854D}.png]]

> #### Beispiel in C#
> ```csharp
> // Initialisierung eines Trie-Knotens
> void InitNode (trieNode *root)
> {
>     root->children = NULL;
> }
> ```

Die Hash-Tabelle für den Trie könnte so aussehen:

> #### Beispiel in C#
> ```csharp
> {
>     'a': &nodeA,
>     'b': &nodeB,
>     'c': &nodeC
> }
> ```
> Die Keys sind Zeichen und die Werte sind Zeiger auf andere Hash-Tabellen.

## Suche in einem Trie

Die Suche in einem Trie kann zwei Ziele haben:
1. Überprüfen, ob ein String ein vollständiges Wort ist.
2. Überprüfen, ob ein String das Präfix eines oder mehrerer Wörter ist.

### Suchalgorithmus

1. Initialisiere die Variable `currentNode`, die auf den Wurzelknoten zeigt.
2. Iteriere über jedes Zeichen des Suchstrings.
3. Für jedes Zeichen überprüfe, ob der `currentNode` ein Kind mit diesem Zeichen als Key hat.
4. Falls nicht, gib `None` zurück, da der Trie den String nicht enthält.
5. Falls vorhanden, setze `currentNode` auf dieses Kind und fahre mit dem nächsten Zeichen fort.
6. Wird das Ende des Suchstrings erreicht, wurde er gefunden.

> #### Beispiel in C#
> ```csharp
> // Pseudocode für die Suche in einem Trie
> bool SearchInTrie(TrieNode root, string word)
> {
>     TrieNode currentNode = root;
>     foreach (char letter in word)
>     {
>         if (!currentNode.children.ContainsKey(letter))
>         {
>             return false; // String ist nicht im Trie
>         }
>         currentNode = currentNode.children[letter];
>     }
>     return true; // String wurde gefunden
> }
> ```

## Effizienzanalyse

Die Trie-Suche hat eine Zeitkomplexität von O(K), wobei K die Anzahl der Zeichen im Suchstring ist. Dies ist unabhängig von der Anzahl der Wörter im Trie und somit effizienter als eine binäre Suche in einem sortierten Array (O(log N)).

## Einfügen in einen Trie

Das Einfügen eines neuen Wortes in einen Trie erfolgt ähnlich der Suche:

1. Initialisiere `currentNode`, der auf den Wurzelknoten zeigt.
2. Iteriere über jedes Zeichen des neuen Wortes.
3. Prüfe, ob der `currentNode` ein Kind mit diesem Zeichen als Key hat.
4. Falls ja, setze `currentNode` auf dieses Kind und fahre mit dem nächsten Zeichen fort.
5. Falls nein, erstelle einen neuen Kindknoten und setze `currentNode` auf diesen.
6. Nach dem letzten Zeichen füge ein „*“-Kind zum letzten Knoten hinzu, um das Ende des Wortes zu signalisieren.

> #### Beispiel in C#
> ```csharp
> // Pseudocode für das Einfügen in einen Trie
> void InsertInTrie(TrieNode root, string word)
> {
>     TrieNode currentNode = root;
>     foreach (char letter in word)
>     {
>         if (!currentNode.children.ContainsKey(letter))
>         {
>             currentNode.children[letter] = new TrieNode();
>         }
>         currentNode = currentNode.children[letter];
>     }
>     currentNode.children['*'] = null; // Ende des Wortes markieren
> }
> ```

## Erweiterung des Tries mit Popularität

Um die am häufigsten verwendeten Begriffe als Autovervollständigung vorzuschlagen, kann die Popularität der Begriffe im Trie gespeichert werden. Das „*“-Zeichen kann dabei verwendet werden, um die Popularität zu speichern und bei der Ausgabe der gefundenen Wörter zu berücksichtigen.


