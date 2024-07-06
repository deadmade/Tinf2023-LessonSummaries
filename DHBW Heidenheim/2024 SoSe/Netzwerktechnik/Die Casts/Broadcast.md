## 📌 Merkmale von Broadcast

1. **Punkt-zu-Mehrpunkt-Kommunikation**: 
    - Beim Broadcast wird eine Nachricht von einem einzigen Sender an alle Empfänger innerhalb eines bestimmten Netzwerkbereichs gesendet.
2. **Keine Zielgerichtete Adressierung**: 
    - Broadcast-Nachrichten werden an eine spezielle Broadcast-Adresse gesendet, die alle Geräte im Netzwerk erreicht, anstatt an eine spezifische IP-Adresse.
3. **Weitreichende Verbreitung**: 
    - Alle Geräte im selben Netzwerksegment (Subnetz) empfangen die Broadcast-Nachricht, unabhängig davon, ob sie die Nachricht angefordert haben oder nicht.
4. **Netzwerkbelastung**: 
    - Broadcast kann das Netzwerk stark belasten, insbesondere bei großen Netzwerken, da alle Geräte die gesendeten Nachrichten verarbeiten müssen.

## ⚙️ Funktionsweise von Broadcast

1. **Broadcast-Adresse**: 
    - Eine spezielle Adresse, die verwendet wird, um Nachrichten an alle Geräte im Netzwerk zu senden. Zum Beispiel ist die IPv4-Broadcast-Adresse für ein Subnetz häufig die letzte Adresse im Adressbereich, wie 192.168.1.255 für das Subnetz 192.168.1.0/24.
2. **Verbindungserstellung**: 
    - Im Gegensatz zu Unicast wird beim Broadcast keine direkte Verbindung zu einzelnen Empfängern hergestellt. Die Nachricht wird einfach an die Broadcast-Adresse gesendet.
3. **Datenübertragung**: 
    - Die Nachricht wird von allen Geräten im Netzwerksegment empfangen und verarbeitet. Jedes Gerät entscheidet dann, ob die Nachricht für es relevant ist.
4. **Keine Bestätigung**: 
    - Im Allgemeinen gibt es keine Rückmeldung oder Bestätigung vom Empfänger, dass die Broadcast-Nachricht empfangen wurde.

## 📋 Beispiele für Broadcast

- **ARP (Address Resolution Protocol)**: 
    - ARP-Anfragen verwenden Broadcast, um die MAC-Adresse eines Geräts zu ermitteln, dessen IP-Adresse bekannt ist. Die Anfrage wird an alle Geräte im Netzwerk gesendet, und das Gerät mit der passenden IP-Adresse antwortet.
- **DHCP (Dynamic Host Configuration Protocol)**: 
    - Wenn ein Gerät eine IP-Adresse von einem DHCP-Server anfordert, sendet es eine Broadcast-Anfrage, um den DHCP-Server im Netzwerk zu erreichen.
- **NetBIOS**: 
    - NetBIOS-Name-Registrierung und -Auflösung verwenden Broadcast, um NetBIOS-Namen in IP-Adressen umzuwandeln.
