## Stack als Abstrakter Datentyp 
Ein Stack ist eine besondere Datenstruktur, die im Wesentlichen zwei Hauptoperationen unterstützt:
- **Push**: Ein Element wird oben auf den Stack gelegt.
- **Pop**: Das oberste Element wird vom Stack entfernt.

Im Gegensatz zu Arrays ermöglicht ein Stack keinen Direktzugriff über Indizes. Stattdessen arbeitet man nur mit dem obersten Element. Dadurch unterscheidet sich die Datenstruktur Stack wesentlich von einem Array, obwohl ein Stack intern oft auf einem Array oder einer verketteten Liste basiert.

## Einsatz von Stacks in der Lexikalanalyse
Ein praktisches Anwendungsbeispiel für Stacks ist die lexikale Analyse bei der Überprüfung der syntaktischen Korrektheit von Programmcode. Ein solcher "Lint"-Prozess prüft z.B. JavaScript-Programmzeilen auf korrekte öffnende und schließende Klammern `()`, `{}` und `[]`.

### Fehlerhafte Situationen
Es können drei Hauptfehler auftreten:
>[!example]  
> **Syntax Error Typ #1:** Eine öffnende Klammer ohne entsprechende schließende Klammer.
> ```javascript
> var x = 2;
> ```
> **Syntax Error Typ #2:** Eine schließende Klammer ohne vorhergehende öffnende Klammer.
> ```javascript
> var x = 2;)
> ```
> **Syntax Error Typ #3:** Eine schließende Klammer, die nicht zum Typ der letzten öffnenden Klammer passt.
> ```javascript
> var x = [1, 2, 3)];
> ```

### Regeln der Analyse
Die Analyse folgt einer festen Reihe von Regeln, um die Korrektheit der Klammerung zu überprüfen:

1. **Nicht-Klammer-Zeichen**: Werden ignoriert.
2. **Öffnende Klammer**: Wird auf den Stack gelegt (Push).
3. **Schließende Klammer**: Wird geprüft:
   - Wenn der Stack leer ist: Syntax Error Typ #2.
   - Wenn das oberste Element des Stacks nicht passt: Syntax Error Typ #3.
   - Wenn das oberste Element des Stacks passt: Pop vom Stack.
4. **Zeilenende**:
   - Wenn der Stack nicht leer ist: Syntax Error Typ #1.
   - Wenn der Stack leer ist: Kein Fehler.

### Beispiel
Für die Zeile `(var x = {y: [1, 2, 3]})` würde die Analyse wie folgt ablaufen:
>[!example]
> 1. Die erste öffnende Klammer `(` wird auf den Stack gelegt.
> 2. Die Zeichen `var x =` werden ignoriert.
> 3. Die öffnende geschweifte Klammer `{` wird auf den Stack gelegt.
> 4. Das Zeichen `y:` wird ignoriert.
> 5. Die öffnende eckige Klammer `[` wird auf den Stack gelegt.
> 6. Die Zeichen `1, 2, 3` werden ignoriert.
> 7. Die schließende eckige Klammer `]` wird geprüft und passt zur letzten öffnenden Klammer, also wird sie vom Stack entfernt.
> 8. Die schließende geschweifte Klammer `}` wird geprüft und passt zur letzten öffnenden Klammer, also wird sie vom Stack entfernt.
> 9. Die schließende runde Klammer `)` wird geprüft und passt zur letzten öffnenden Klammer, also wird sie vom Stack entfernt.
> 10. Am Zeilenende ist der Stack leer, daher gibt es keinen Fehler.

#### Fehlerhafte Zeilen
>[!bug]
> Die Zeile `( var x = { y: [1, 2, 3] ) }` würde den Fehler “Ungültige schließende Klammer `)` an Position 25” erzeugen.
> 
> Die Zeile `( var x = { y: [1, 2, 3] }` würde den Fehler “`(` hat keine schließende Klammer“ erzeugen.
