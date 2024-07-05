## 📌 Merkmale von Unicast

1. **Punkt-zu-Punkt-Kommunikation**: 
    - Bei Unicast wird eine direkte Verbindung zwischen zwei Netzwerkgeräten hergestellt – dem Sender und dem Empfänger.
2. **Eindeutige Adressierung**: 
    - Jedes Gerät im Netzwerk hat eine eindeutige IP-Adresse, und die Daten werden an diese spezifische Adresse gesendet.
3. **Effizienz**: 
    - Für Anwendungen, bei denen Daten nur an einen bestimmten Empfänger gesendet werden müssen, ist Unicast sehr effizient.
4. **Skalierbarkeit**: 
    - Unicast ist skalierbar, da jede neue Verbindung unabhängig von anderen besteht. Dies bedeutet jedoch auch, dass bei einer großen Anzahl von Empfängern die Netzwerkbelastung steigen kann, da für jeden Empfänger eine separate Kopie der Daten gesendet wird.

## ⚙️ Funktionsweise von Unicast

1. **Adressierung**: 
    - Der Sender erhält die IP-Adresse des Empfängers. Diese IP-Adresse ist eindeutig und identifiziert das Zielgerät im Netzwerk.
2. **Verbindungserstellung**: 
    - Eine Verbindung wird zwischen dem Sender und dem Empfänger hergestellt. Dies kann über verschiedene Transportprotokolle wie TCP (Transmission Control Protocol) oder UDP (User Datagram Protocol) geschehen.
3. **Datenübertragung**: 
    - Die Daten werden vom Sender zum Empfänger über das Netzwerk übertragen. Bei TCP wird die Integrität und Reihenfolge der Daten garantiert, während bei UDP die Übertragung schneller, aber weniger zuverlässig ist.
4. **Bestätigung**: 
    - Bei TCP-basierter Kommunikation bestätigt der Empfänger den Erhalt der Datenpakete. Wenn der Sender keine Bestätigung erhält, können die Pakete erneut gesendet werden.

## 📋 Beispiele für Unicast

- **Web-Browsing**: 
    - Wenn du eine Webseite besuchst, sendet dein Computer eine Anfrage an den Webserver, und der Server sendet die Webseite nur an deinen Computer zurück.
- **E-Mail**: 
    - Wenn du eine E-Mail sendest, wird sie von deinem E-Mail-Server direkt an den E-Mail-Server des Empfängers gesendet.
- **FTP (File Transfer Protocol)**: 
    - Beim Herunterladen einer Datei von einem FTP-Server werden die Daten direkt von diesem Server an deinen Computer übertragen.
