In C ist `unsigned char` eine Variante des `char`-Datentyps, bei dem alle 8 Bits des Bytes zur Darstellung von positiven Werten verwendet werden, ohne ein Vorzeichen zu berücksichtigen. Dies bedeutet, dass `unsigned char` nur nicht-negative Werte darstellen kann.

Hier sind einige wichtige Punkte zu `unsigned char`:

## Eigenschaften von `unsigned char` 📊

### **Wertbereich** 🌈:
    
 `unsigned char` kann Werte von 0 bis 255 speichern. Dies liegt daran, dass es 8 Bits verwendet und alle Bits für die Werte repräsentiert werden, ohne ein Vorzeichen zu berücksichtigen.
### **Speichergröße** 💾:
    
Wie `char` auch, belegt `unsigned char` typischerweise 1 Byte (8 Bit) im Speicher.
### **Verwendung** 🛠️:
    
`unsigned char` wird oft verwendet, wenn es wichtig ist, dass keine negativen Werte gespeichert werden und der gesamte Wertebereich für positive Zahlen benötigt wird. Häufige Anwendungen sind in der Datenmanipulation, bei der Arbeit mit Rohdaten oder beim Speichern von Binärdaten.
### **Modifikatoren** ⚙️:
    
`unsigned char` ist immer vorzeichenlos, daher gibt es keine `signed`-Alternative wie bei `signed char`.