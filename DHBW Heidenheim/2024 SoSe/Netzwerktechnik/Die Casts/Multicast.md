## 📌 Merkmale von Multicast

1. **Punkt-zu-Mehrpunkt-Kommunikation**: 
    - Beim Multicast wird eine Nachricht von einem einzigen Sender an eine bestimmte Gruppe von Empfängern gesendet, die sich für die Multicast-Gruppe registriert haben.
2. **Gruppenbasierte Adressierung**: 
    - Multicast verwendet spezielle IP-Adressen, die eine Gruppe von Empfängern repräsentieren. Geräte, die diese Nachrichten empfangen möchten, treten der entsprechenden Multicast-Gruppe bei.
3. **Effizienz**: 
    - Multicast ist effizienter als Broadcast, da die Nachrichten nur an die Geräte gesendet werden, die Interesse daran haben, anstatt an alle Geräte im Netzwerk.
4. **Skalierbarkeit**: 
    - Multicast ist skalierbar, da die Netzwerkbelastung geringer ist als bei Broadcast, besonders wenn viele Empfänger dieselben Daten benötigen.

## ⚙️ Funktionsweise von Multicast

1. **Multicast-Adresse**: 
    - Multicast verwendet spezielle IP-Adressen aus dem Bereich 224.0.0.0 bis 239.255.255.255 (IPv4) und FF00::/8 (IPv6). Diese Adressen repräsentieren Gruppen von Empfängern.
2. **Beitritt zur Gruppe**: 
    - Geräte, die Multicast-Nachrichten empfangen möchten, melden sich bei einer bestimmten Multicast-Gruppe an, indem sie die IGMP (Internet Group Management Protocol) oder MLD (Multicast Listener Discovery) verwenden.
3. **Datenübertragung**: 
    - Der Sender schickt die Daten an die Multicast-Adresse. Die Netzwerk-Router leiten die Nachrichten nur an die Netzwerke weiter, die Mitglieder der Multicast-Gruppe enthalten.
4. **Optimierung**: 
    - Router optimieren den Datenfluss, indem sie die Nachrichten nur einmal über jeden Link senden, der für mehrere Empfänger in der Multicast-Gruppe verwendet wird.

## 📋 Beispiele für Multicast

- **IPTV (Internet Protocol Television)**: 
    - Fernsehsender verwenden Multicast, um TV-Signale an viele Abonnenten gleichzeitig zu senden, ohne die gleichen Daten an jeden einzelnen Empfänger separat zu übertragen.
- **Online-Spiele**: 
    - Multicast wird verwendet, um Spielstatus-Updates und andere Informationen gleichzeitig an mehrere Spieler zu senden.
- **Videokonferenzen**: 
    - Multicast ermöglicht es, Videostreams an alle Teilnehmer einer Konferenz zu senden, ohne für jeden eine separate Verbindung aufzubauen.
