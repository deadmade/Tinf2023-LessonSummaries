# Statisches Testen

Mit den statischen Testverfahren kann überprüft werden:
- [[Komplexität]]
- Erreichbarkeit (können überhaupt alle Programmteile erreicht werden)
- [Syntax](Korrektheit.md#Syntaktische%20Fehler)
- [Semantik](Korrektheit.md#Semantische%20Fehler)
- Programmierrichtlinien
Beispiele:
- Schreibtischtests
- Code-Walkthroughs
- Code-Inspection

# Dynamisches Testen

Testen eines Programms am Computer.

## Black-Box Testing
- beim Testen ist der Inhalt einer Funktion nicht bekannt  
- es werden Testdaten zusammengestellt, die aus Eingabedaten und den zugehörigen korrekten Ergebnissen bestehen  
- diese Daten werden dann mit der Funktion verarbeitet und die Ergebnisse verglichen  
- Vorsicht: es ist nicht sichergestellt, dass der Algorithmus immer korrekt arbeitet, sondern nur für die Fälle, an die man gedacht hat  
- möglicherweise wurden Teile des Algorithmus gar nicht getestet  
- in der Praxis sinnvoll, es muss nur angegeben werden, für welche Fälle der Algorithmus korrekt arbeitet

## White-Box Testing
- beseitigt Schwächen des Black-Box Tests dadurch, dass der Inhalt der getesteten Funktion bekannt ist
- es ist nun möglich alle möglichen Situationen zu testen  
- es wird jeder mögliche Pfad mindestens einmal durchlaufen
- aufwendiger als BBT

# Beweisen (Formales Testen)

Z.B. mit Hilfe eines speziellen Kalküls oder einer speziellen Testsprache durchgeführt. Nur Formales Testen kann die Korrektheit eines Algorithmus sicherstellen.

# Testen von Komplexen Systemen

Für komplexe Systeme gilt:
- Testen des Gesamtsystems oft nicht vollständig möglich
- Test von logischen Funktionseinheiten / Modulen
- für einzelne Module wird die Korrektheit bewiesen und Zusicherungen gemacht
	- **pre-condition**: was geht rein, in welchem Zustand befindet sich das System
	- **post-condition**: was kommt raus, in welchem Zustand befindet sich das System
	- andere Module verlassen sich auf diese Korrektheit

Man kann nun auf zwei Arten testen: [Top Down](Entwurf%20von%20Algorithmen.md#Top%20Down) und [Bottom Up](Entwurf%20von%20Algorithmen.md#Bottom%20Up).