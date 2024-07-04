## 📌 Merkmale der verbindungsorientierten Kommunikation

1. **Aufbau einer Verbindung**: 
    - Bevor Daten übertragen werden können, wird eine explizite Verbindung zwischen Sender und Empfänger etabliert. Dieser Aufbau beinhaltet in der Regel einen Austausch von Steuerinformationen, um die Kommunikationsparameter festzulegen.
   
2. **Zuverlässigkeit**: 
    - Verbindungsorientierte Kommunikation garantiert, dass Daten in der richtigen Reihenfolge und ohne Verluste übertragen werden. Dies wird durch Mechanismen wie Sequenznummern, Bestätigungen und erneute Übertragungen sichergestellt.
   
3. **Flusskontrolle**: 
    - Mechanismen zur Flusskontrolle regulieren den Datenfluss, um Überlastungen des Empfängers zu vermeiden. Der Sender passt die Übertragungsgeschwindigkeit an die Verarbeitungsfähigkeit des Empfängers an.
   
4. **Verbindungsabbau**: 
    - Nach der Datenübertragung wird die Verbindung ordnungsgemäß abgebaut. Dies ermöglicht eine Freigabe von Ressourcen und stellt sicher, dass beide Parteien wissen, dass die Kommunikation beendet ist.

## ⚙️ Funktionsweise der verbindungsorientierten Kommunikation

1. **Verbindungsaufbau**: 
    - Der Prozess beginnt mit einer Anfrage (SYN) des Senders an den Empfänger, gefolgt von einer Bestätigung (SYN-ACK) des Empfängers zurück an den Sender und einer abschließenden Bestätigung (ACK) vom Sender an den Empfänger.
   
2. **Datenübertragung**: 
    - Nach erfolgreicher Verbindungsaufbau sendet der Sender Datenpakete an den Empfänger. Jedes Paket wird durchnummeriert, und der Empfänger sendet Rückmeldungen (ACKs) zurück, um den Erhalt zu bestätigen.
   
3. **Flusskontrolle und Fehlerbehandlung**: 
    - Mechanismen wie Fenstersteuerung und erneute Übertragung von verlorenen oder beschädigten Paketen gewährleisten eine zuverlässige Übertragung.
   
4. **Verbindungsabbau**: 
    - Nach Abschluss der Datenübertragung wird die Verbindung durch einen Austausch von Abschlussnachrichten (FIN und ACK) beendet. Dieser Prozess stellt sicher, dass alle Daten vollständig übertragen wurden und die Ressourcen freigegeben werden können.

## 📋 Beispiele für verbindungsorientierte Kommunikation

- **TCP (Transmission Control Protocol)**: 
    - TCP ist ein prominentes Beispiel für verbindungsorientierte Kommunikation. Es stellt sicher, dass Daten zwischen Anwendungen über das Internet in der richtigen Reihenfolge und ohne Verluste übertragen werden.
  
- **Telefonie**: 
    - Bei traditionellen Telefonanrufen wird eine Verbindung zwischen den Anrufern hergestellt, die während des Gesprächs erhalten bleibt, bis sie von einer der Parteien beendet wird.
