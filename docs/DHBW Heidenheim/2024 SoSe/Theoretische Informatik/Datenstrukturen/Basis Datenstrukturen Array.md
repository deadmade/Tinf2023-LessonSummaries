## Allgemeines

Das Array ist eine grundlegende Datenstruktur in der Informatik, bestehend aus n gleichen Datenelementen, die dicht aneinander im Speicher angeordnet sind. Der Index eines Arrays identifiziert die Position eines Datenelements innerhalb des Arrays.
![[Pasted image 20240723184843.png]]

## Geschwindigkeit
- Geschwindigkeit wird durch die Anzahl der Schritte gemessen, nicht durch absolute Zeit.
- Beispiel: Wenn Operation A 5 Schritte und Operation B 500 Schritte benötigt, ist Operation A immer schneller.

## Synonyme  Performance
- Geschwindigkeit
- (Zeit-)Komplexität
- Effizienz
- Performance

## Operationen
### **Lesen/Ändern**: 
Zugriff auf Daten an einer bestimmten Stelle erfolgt in konstanter Zeit (O(1)).
  => Zugriff Maximal ein Schritt
  ![[Pasted image 20240723185106.png]]

### **Suche**
Um ein Element zu finden, muss man potenziell alle Elemente durchsuchen (O(n)). 
![[Pasted image 20240723185202.png]]

### **Einfügen**:
Ein weiteres Element wird zur Datenstruktur hinzugefügt. Im schlimmsten Fall, wenn das Einfügen am Anfang erfolgt, sind (n+1) Schritte erforderlich (O(n)).
![[Pasted image 20240723185242.png]]

### **Löschen**: 
Elemente können nur am Ende effizient gelöscht werden (O(1)). Um ein Element an einer anderen Position zu löschen, müssen die verbleibenden Elemente verschoben werden, was im schlimmsten Fall n-1 Schritte erfordert (O(n)).
![[Pasted image 20240723185317.png]]

## Array Sets
- **Sets** sind spezielle Arrays, die keine doppelten Datenwerte zulassen.
- Die Komplexität für Zugriff/Lesen, Suchen und Löschen entspricht der von Arrays.
- Beim Einfügen muss zuerst das gesamte Set durchsucht werden, was doppelt so lange dauert wie bei einem normalen Array (O(2n)).
- Das Schreiben (Wert verändern) dauert n+1 Schritte (O(n)).




