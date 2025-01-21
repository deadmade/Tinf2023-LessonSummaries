## Der von-Neumann-Rechner
- **Hintergrund**:
  - Konzept 1945 von John von Neumann veröffentlicht im Bericht „First Draft of a Report on the EDVAC“.
  - Grundlage aller speicherprogrammierten Rechner.
- **Hauptbestandteile**:
  1. **Arithmetic Logic Unit (ALU)**: Führt Berechnungen durch.
  2. **Control Unit (CU)**: Steuert die Befehlsausführung.
  3. **Memory (Speicherwerk)**: Beinhaltet sowohl Programme als auch Daten.
  4. **Input/Output (I/O)**: Ermöglicht Ein- und Ausgabe von Daten.
- **Wichtig**: Programmcode und Daten werden im gleichen Speicher behandelt.

![[{A0EDE061-8EF2-41E4-B2F7-23B48BC58266}.png]]
---

## Elemente eines einfachen Rechners
- **Memory (Speicher)**:
  - Speichert sowohl Befehle (Programmcode) als auch Daten (Operanden).
- **Program Counter (PC)**:
  - Hält die Adresse des nächsten Befehls.
- **Instruction Register (IR)**:
  - Speichert den aktuell auszuführenden Befehl.
- **Arithmetic Logic Unit (ALU)**:
  - Führt Berechnungen auf Operanden aus.
- **Accumulator (ACC)**:
  - Speichert Zwischenergebnisse der ALU.
- **Bus-System**:
  - **Adressbus**: Überträgt Adressen.
  - **Datenbus**: Überträgt Daten.
- **Control Unit (Steuerwerk)**:
  - Taktgeber für die Befehlsabarbeitung.
  - Koordiniert alle Komponenten.
  
![[{C3D781FA-6163-4ADB-95A1-A1D15C09F983}.png]]
---

## Speicheroperationen
- **Datenfluss-Logik**:
  - Blickrichtung: Steuerwerk und Register agieren aktiv, der Speicher ist passiv.
  - Steuerbefehle:
    - **Input Enable (ie)**: Register liest Daten ein.
    - **Output Enable (oe)**: Register gibt Daten aus.
  - Speicheroperationen:
    - **Lesen (RnW=1)**: Daten aus dem Speicher lesen.
    - **Schreiben (RnW=0)**: Daten in den Speicher schreiben.

![[{A59D9F70-7509-416D-AC34-BA3374DE048D}.png]]
---

## Speicher- und Buskonzepte
- **Hauptspeicher**:
  - Organisiert in Speicherstellen (Worte), adressierbar über den Adressbus.
  - Daten werden über den Datenbus transportiert.
- **Adressbus**:
  - Transportiert Adressen zu Speicherstellen.
- **Datenbus**:
  - Überträgt Daten zwischen Speicher und CPU.
- Einschränkungen:
  - Pro Buszyklus darf nur ein Element schreiben.

![[{8E9D20A3-4D3F-4CEB-A11F-6C0AF0EFE7EC}.png]]
---

## Steuerwerk und Befehlsabarbeitung
- **Komponenten des Steuerwerks**:
  - Program Counter (PC)
  - Instruction Register (IR)
  - Befehlsdecoder
  - Ablaufsteuerung
- **Befehlszyklus**:
  1. **Fetch**: Holen des Befehls aus dem Speicher.
  2. **Decode**: Dekodierung des Befehls.
  3. **Execute**: Ausführung der Anweisung.
- **Beispielablauf**:
  - **LDA #1**: Lädt die Zahl 1 in den Akkumulator.

---

## Der Befehlszyklus im Detail

![[{2F579886-7D4A-4507-8661-C2488D5663AA}.png]]

![[{8B76FC80-525D-4579-B83A-3F76548F128D}.png]]

1. **Fetch-Zyklus**:
   - Der Program Counter (PC) legt die Adresse des nächsten Befehls auf den Adressbus.
   - Der Befehl wird aus dem Speicher ins Instruction Register (IR) geladen.
   - Der PC wird inkrementiert.

![[{D1A2B149-44FE-4F7C-9854-893563366012}.png]]

2. **Decode/Execute/Write**:
   - Operandenadressen werden dekodiert.
   - Werte werden an die ALU übergeben:
     - Eingang A: Operanden aus dem Speicher.
     - Eingang B: Daten aus dem Akkumulator.
   - Das Ergebnis wird im Akkumulator (ACC) gespeichert.

![[{05352BEC-BF9E-41B0-B16B-67E4F133933C}.png]]
---

## Speichersteuerung und Signale
- **Signale zur Steuerung des Speichers**:
  - `MemReq`: Signalisiert, dass der Speicher angesprochen wird.
  - `RnW`: Gibt an, ob Daten gelesen (`1`) oder geschrieben (`0`) werden.
- **Speicherstruktur**:
  - Organisiert in adressierbare Speicherworte (Breite abhängig von der Datenbusbreite).

![[{0140C123-221D-4524-AF5A-9BAAA945C4BF}.png]]