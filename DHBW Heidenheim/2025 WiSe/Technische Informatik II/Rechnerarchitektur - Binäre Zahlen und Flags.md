### 1. Ganze positive Zahlen
- Die Menge der ganzen positiven Zahlen ist unendlich, jedoch durch die Wortbreite eines Rechners begrenzt.
- Zahlenkreis (4 Bit, 0–15): 
  - **Beispiel:** `0000` bis `1111`
- Darstellung:
![[{6C6CA457-0E3F-4845-B03B-4EE73C20DE79} 1.png]]

---

### 2. Addition und Subtraktion im Zahlenkreis
- Addition und Subtraktion können als Drehungen im Zahlenkreis interpretiert werden.
- **Beispiel für Addition:** 9 + 9 = 2 (mit Carry).
![[{FABF907D-0D54-4DBE-ADFE-7AB628E087DA}.png]]

---

### 3. Überschreitungen des Zahlenbereichs
- Addition außerhalb des Zahlenbereichs führt zu einem Carry-Flag (`C`), um den Übertrag zu kennzeichnen.
- **Beispiel:** 9 + 9 = 2 + Carry = 2 + 16 = 18
![[{267F5D68-32DF-4D73-BDA4-608E72A1F559}.png]]

---

### 4. Einführung von negativen Zahlen
- Negative Zahlen werden durch das höchstwertige Bit (MSB) als Vorzeichen dargestellt.
- Zahlenkreis für Vorzeichenbit (2er-Komplement):
- Positive Zahlen: `0000` bis `0111`
- Negative Zahlen: `1000` bis `1111`
![[{874AD2C4-FDDF-449B-8F48-8A91672676B9}.png]]

---

### 5. Die Negation (2er-Komplement)
- Umwandlung einer Zahl in ihr negatives Pendant durch:
1. Bilden des 1er-Komplements.
2. Hinzufügen von `1`.
- **Beispiel:** Dezimal: 1 -> Binär: 0001 -> Negiert: 1111 (-1) Dezimal: 4 -> Binär: 0100 -> Negiert: 1100 (-4)

![[{4E524BD5-A2DB-45FF-A0D3-9CA62BCAE9EE}.png]]

---

### 6. Flags
1. **Carry-Flag (C):**
 - Zeigt Überträge bei Operationen mit vorzeichenlosen Zahlen an.
 - Beispiel: Linksschieben, bei dem das höchste Bit im Carry gespeichert wird.

2. **Overflow-Flag (V):**
 - Wird gesetzt, wenn:
   - Summe zweier positiver Zahlen negativ wird.
   - Summe zweier negativer Zahlen positiv wird.
 - Berechnungstipp: `CarryIn != CarryOut`.

3. **Zero-Flag (Z):**
 - Zeigt an, ob das Ergebnis einer Operation `0` ist.
 - **Anwendung:** Schleifenbedingungen.

4. **Negativ-Flag (N):**
 - Wird gesetzt, wenn das MSB = 1 ist (negatives Ergebnis).
 
![[{2417C67D-A81A-4F76-9EAD-74E930A0ADF5}.png]]

---

### 7. Logische Operationen
- **AND:** Bitweises UND.
  ![[{BCFB307C-61F2-40A9-AA67-B7FBD09439B0}.png]]
- **OR:** Bitweises ODER.
  ![[{CEB62453-7A53-44D6-9BFB-D5764E0422C0}.png]]
- **XOR:** Bitweises exklusives ODER (genau ein Operand ist `1`).
  ![[{A2E8DCC2-2AE6-4CED-885C-0AE91B4AD8DE}.png]]
- **NOT:** Bitweises Negieren (nicht bei allen Prozessoren vorhanden).

---

### 8. Multiplikation mit 2
- Entspricht einer Linksschiebeoperation im binären System.
- Übertrag wird im Carry-Flag gespeichert.

![[{2DB7AC36-2623-465C-BE6A-A87017230AA6}.png]]


