## 📌 Was ist Asynchrone Übertragung?

**Asynchrone Übertragung** ist eine Methode der Datenübertragung, bei der Datenpakete unabhängig voneinander gesendet werden, ohne dass ein synchronisierter Zeitplan zwischen Sender und Empfänger erforderlich ist. Jede Einheit der Datenübertragung wird separat mit Start- und Stoppbits versehen, um den Anfang und das Ende der Übertragung zu kennzeichnen.

## 🕰️ Merkmale der Asynchronen Übertragung

### Start- und Stoppbits

- **Startbit**: Ein Bit, das den Beginn eines Datenpakets signalisiert.
- **Stoppbit**: Ein oder mehrere Bits, die das Ende eines Datenpakets markieren.
- Diese Bits ermöglichen es dem Empfänger, die Ankunft und die Grenzen der Datenpakete zu erkennen.

### Kein fester Zeitplan

- **Kein fester Zeitplan**: Daten werden gesendet, sobald sie verfügbar sind, ohne dass der Sender und Empfänger synchronisiert sein müssen.
- Flexibilität: Asynchrone Übertragung ist flexibel und eignet sich gut für unregelmäßige und intermittierende Datenströme.

### Charakterbasierte Übertragung

- **Charakterbasierte Übertragung**: Häufig wird jedes Datenpaket als Zeichen (z.B. ein Byte) übertragen, das durch die Start- und Stoppbits eingerahmt wird.
- Einfachheit: Diese Methode ist einfach zu implementieren und weit verbreitet in der seriellen Kommunikation.

## 🚀 Anwendungen der Asynchronen Übertragung

### Serielle Kommunikation

- **Serielle Kommunikation**: Verwendung in RS-232- und UART-Verbindungen, die häufig in Computern, Mikrocontrollern und anderen elektronischen Geräten zu finden sind.
- Beispiel: Datenübertragung zwischen Computern und Peripheriegeräten wie Tastaturen und Mäusen.

### Modems

- **Modems**: Asynchrone Übertragung wird in Modems verwendet, um Daten über Telefonleitungen zu übertragen.
- Beispiel: Einwahl-Internetverbindungen, bei denen Datenpakete über analoge Telefonleitungen gesendet werden.

### Asynchrone Kommunikationsprotokolle

- **Asynchrone Kommunikationsprotokolle**: Protokolle wie XMODEM, YMODEM und ZMODEM nutzen asynchrone Übertragung für Dateiübertragungen über serielle Verbindungen.
- Beispiel: Dateiübertragungen zwischen Computern über serielle Schnittstellen.

## ⚖️ Vorteile und Nachteile der Asynchronen Übertragung

### Vorteile

- **Einfache Implementierung**: Asynchrone Übertragung erfordert keine komplexe Synchronisierung und ist daher einfach zu implementieren.
- **Flexibilität**: Geeignet für unregelmäßige und intermittierende Datenströme, da Daten gesendet werden, sobald sie verfügbar sind.
- **Geringe Kosten**: Hardwareanforderungen sind minimal, was zu geringeren Kosten führt.

### Nachteile

- **Overhead durch Start- und Stoppbits**: Jedes Datenpaket muss mit zusätzlichen Bits versehen werden, was zu einem höheren Overhead und einer geringeren Effizienz führt.
- **Begrenzte Übertragungsgeschwindigkeit**: Im Vergleich zu synchronen Methoden ist die Übertragungsgeschwindigkeit aufgrund des Overheads und der fehlenden Synchronisation niedriger.
- **Empfindlichkeit gegenüber Störungen**: Da die Synchronisation zwischen Sender und Empfänger fehlt, kann es bei Übertragungsstörungen zu Datenfehlern kommen.


