Wir stellen uns einige zentrale Fragen:
- Arbeitet ein [Algorithmus](Algorithmen.md) genauso, wie es in der Spezifikation vorgesehen ist?
- Gibt ein [Algorithmus](Algorithmen.md) zu einer **Eingabedatenmenge** die richtige **Ausgabedatenmenge** aus?
- Sind alle möglichen Fälle eines Problems durch den [Algorithmus](Algorithmen.md) abgedeckt?
- Ist der [Algorithmus](Algorithmen.md) frei von Fehlern?

# Fehlerarten

## Syntaktische Fehler
Konstrukte der Programmiersprache wurden nicht richtig angewandt. Diese werden vom Compiler abgefangen.

## Semantische Fehler
Logische Fehler. Diese werden (meist) nicht vom Compiler abgefangen.  Im besten Fall tauchen diese bei Laufzeit auf, im schlimmsten Fall garnicht.

# Terminiertheit

Ein Algorithmus heißt **terminierend**, wenn er für jede Eingabe terminiert (d.h. ein Ende hat).

# Arten der Korrektheit

## Partielle Korrektheit
Wenn ein Ergebnis ausgegeben wird, dann muss dieses korrekt sein.

## Totale Korrektheit
Wenn partiell Korrekt und terminiert.

## Ausführbar
Betriebsmittel reichen aus, um den Algorithmus durchzuführen.

# Nachweisen der Korrektheit
Mögliche Vorgehensweisen, um die Korrektheit eines [Algorithmus](Algorithmen.md) zu zeigen:
## [[Testen]]
- einfach, aber fehleranfällig  
- meist von Wissen/Erfahrung des Testers abhängig  
- totale Korrektheit kann nicht gezeigt werden (nur partielle Korrektheit)
## Beweisen
- schwierig, aber totale Korrektheit kann gezeigt werden