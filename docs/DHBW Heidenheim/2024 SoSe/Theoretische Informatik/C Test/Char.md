In C ist `char` ein Datentyp, der verwendet wird, um einzelne Zeichen zu speichern. Hier sind einige wichtige Punkte:

## Größe und Speicherung 📏

Typischerweise belegt ein `char` 1 Byte (8 Bit) im Speicher. Die Größe kann je nach Plattform variieren, aber 1 Byte ist am häufigsten.

## Zeichenrepräsentation 🔡

Eine `char`-Variable kann jedes einzelne Zeichen aus der ASCII-Tabelle speichern, einschließlich Buchstaben, Ziffern, Satzzeichen und Steuerzeichen. Zum Beispiel: `char c = 'A';` speichert das Zeichen 'A' in der Variable `c`.

## Zeichenliterale 📜

Zeichenliterale sind in einfache Anführungszeichen eingeschlossen. Beispiele sind: `'a'`, `'1'`, `'$', '`.

## Ganzzahlige Repräsentation 🔢

Intern werden Zeichen durch Ganzzahlen gemäß ihren ASCII-Codes repräsentiert. Zum Beispiel wird `'A'` durch die Ganzzahl 65 im ASCII-Code dargestellt.

## Zeichenarrays und Strings 🧩

Eine Folge von Zeichen wird in einem `char`-Array gespeichert und oft verwendet, um Strings darzustellen. In C sind Strings nullterminiert, was bedeutet, dass sie mit einem speziellen Zeichen `'\0'` enden, um das Ende des Strings anzuzeigen. Zum Beispiel: `char str[] = "Hallo";` stellt den String "Hallo" mit einem impliziten Nullterminator am Ende dar.

## Modifizierer ⚙️

Der `char`-Datentyp kann mit den Schlüsselwörtern `signed` oder `unsigned` modifiziert werden. Standardmäßig kann `char` je nach Compiler entweder vorzeichenbehaftet (`signed`) oder vorzeichenlos (`unsigned`) sein. `signed char` kann Werte von -128 bis 127 speichern, während `unsigned char` Werte von 0 bis 255 speichern kann.

