
### Nachteile der Nutzung von Returnwerten für Fehlerrückgabe

> [!fail] **Nachteile:**
> - **Ungesicherte Beachtung von Rückgabewerten:**  
>   Gut gesetzte Rückgabewerte nützen nichts, wenn sich die Aufrufer nicht darum kümmern.
> - **Umständliche Weiterleitung von Fehlern:**  
>   Wenn ein Fehler nicht an Ort und Stelle behandelt werden soll, muss die Fehlerinformation aufwändig entlang der Aufrufersequenz nach oben gemeldet werden.
> - **Beschränkung auf Methoden:**  
>   Die Rückgabe eines Fehlerindikators ist keine Option bei Eigenschaften, Indexern, Ereignissen oder überladenen Operatoren.

### Vorteile von Exceptions

> [!done] **Vorteile:**
> - **Bessere Lesbarkeit des Quellcodes:**  
>   Bessere Trennung zwischen den Anweisungen für den normalen Programmablauf und den Exceptionbehandlungen im Quellcode.
> - **Garantierte Beachtung von Ausnahmen:**  
>   Exceptions können nicht ignoriert werden. Reagiert ein Programm nicht darauf, wird es vom Laufzeitsystem beendet.
> - **Automatische Weitermeldung bis zur bestgerüsteten Methode:**  
>   Oft ist der unmittelbare Verursacher nicht gut gerüstet zur Behandlung einer Ausnahme, z. B. nach dem vergeblichen Öffnen einer Datei. Dann entscheidet eine „höhere“ Methode über das weitere Vorgehen und erfragt z. B. beim Benutzer eine alternative Datei.
> - **Bessere Fehlerinformationen für den Aufrufer/Ausgabe:**  
>   Über ein Exception-Objekt kann der Aufrufer sehr genau über den aufgetretenen Fehler informiert werden (bei einem traditionellen Rückgabewert nicht der Fall).
