## 📌 Merkmale der verbindungslosen Kommunikation

1. **Kein Verbindungsaufbau**: 
    - Bei der verbindungslosen Kommunikation werden Daten ohne vorherigen Aufbau einer Verbindung übertragen. Es gibt keine initialen Handshake-Schritte wie bei der verbindungsorientierten Kommunikation.
   
2. **Unzuverlässig**: 
    - Es gibt keine Garantie dafür, dass die Daten in der richtigen Reihenfolge ankommen oder überhaupt ankommen. Es erfolgt keine Rückmeldung oder Bestätigung (ACK) vom Empfänger.
   
3. **Keine Flusskontrolle**: 
    - Der Sender sendet Daten so schnell wie möglich, ohne Rücksicht auf die Verarbeitungsgeschwindigkeit des Empfängers. Dies kann zu Überlastungen oder Datenverlusten führen.
   
4. **Effizienz**: 
    - Verbindungslose Kommunikation ist effizienter in Bezug auf Netzwerkressourcen, da kein Aufwand für die Verbindungsherstellung und -aufrechterhaltung erforderlich ist.

## ⚙️ Funktionsweise der verbindungslosen Kommunikation

1. **Direkter Datenaustausch**: 
    - Der Sender sendet Datenpakete direkt an die Adresse des Empfängers, ohne vorherige Einrichtung einer Verbindung oder Überprüfung der Erreichbarkeit.
   
2. **Keine Bestätigung**: 
    - Es erfolgt keine Bestätigung, ob die Datenpakete erfolgreich angekommen sind. Der Sender sendet die Daten und geht davon aus, dass sie entweder ankommen oder verloren gehen können.
   
3. **Verwendete Protokolle**: 
    - Ein Beispiel für ein verbindungsloses Protokoll ist UDP (User Datagram Protocol). UDP wird häufig für Anwendungen verwendet, bei denen eine schnelle Übertragung und geringe Latenz wichtiger sind als Zuverlässigkeit.

## 📋 Beispiele für verbindungslose Kommunikation

- **Streaming**: 
    - Beim Streaming von Audio oder Video über das Internet werden Datenpakete verbindungslos übertragen. Eine perfekte Wiedergabe ohne Unterbrechungen ist wichtiger als die garantierte Zustellung jedes Pakets.
  
- **DNS (Domain Name System)**: 
    - DNS-Anfragen werden oft mit UDP gesendet, da eine schnelle Antwort wichtiger ist als die Gewährleistung, dass jede Anfrage erfolgreich beantwortet wird.
