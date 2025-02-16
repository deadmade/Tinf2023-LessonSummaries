Dieser Eintrag gibt einen Überblick über verschiedene Netzwerkangriffe und die entsprechenden Schutzmaßnahmen. Die Themen umfassen **DHCP Spoofing Angriff**, **DHCP Snooping**, **DHCP Starvation**, **Dynamic ARP Inspection**, **MAC-ADDRESS-Flooding** und **IP-Spoofing**.

---

## DHCP Spoofing Angriff
Beim DHCP Spoofing antwortet ein Rogue-DHCP-Server schneller als der legitime Server. Der Angreifer gibt sich dabei als Default-Gateway und DNS-Server aus. Dies ermöglicht Angriffe wie **Man-in-the-Middle** oder **DNS Spoofing**.


![[{3C54F94F-169B-4401-8439-3123AAA5F34A}.png]]
### Schutzmaßnahme: DHCP Snooping
- **Trusted Ports**: Akzeptieren DHCP-Nachrichten nur von autorisierten Servern.
- **Untrusted Ports**: Blockieren alle eingehenden DHCP-Nachrichten.
- **Snooping-Datenbank**: Speichert MAC- und IP-Adressen von Clients.

![[{21FB5CDF-1FA0-4ED4-A8E2-946AFCAB3A51}.png]]
---

## DHCP Starvation
Ein Angreifer überlastet den DHCP-Server, indem er kontinuierlich IP-Adressen anfordert. Dies verhindert, dass legitime Geräte IP-Adressen erhalten.

![[{6747BD01-4695-4A80-A5A4-D518597376F7}.png]]

### Schutzmaßnahme: DHCP Snooping mit Begrenzung
- **Maximale Anfragen pro Port**: Beschränkung der DHCP-Requests auf untrusted Ports.
- **Konfiguration**: Port-Level-Sicherheit implementieren.

![[{857BC130-A249-44AC-8A8A-C91F63921DBF}.png]]

---

## Dynamic ARP Inspection (DAI)
ARP-Inspektion schützt vor **ARP-Spoofing**, bei dem Angreifer gefälschte ARP-Nachrichten senden, um den Netzwerkverkehr umzuleiten.

- Validiert ARP-Pakete basierend auf der DHCP-Snooping-Datenbank.
- Verhindert Flooding-Angriffe durch Limitierung der ARP-Nachrichten pro Port.

![[{7AF58D11-2D65-44EB-B601-6C5D4CBF4BF6}.png]]

---

## MAC-Address-Flooding
Angreifer überlasten die MAC-Adresstabelle eines Switches, wodurch dieser in einen „fail-open“-Modus wechselt und als Hub fungiert.

### Schutzmaßnahme: Port-Security
- Maximale MAC-Adressen pro Port begrenzen.
- Aktionen bei Verletzungen: `shutdown`, `restrict` oder `protect`.

![[{CD304A07-B768-4EE1-8517-46607EE2E2E6}.png]]

---

## IP-Spoofing
Angreifer fälschen ihre IP-Adresse, um sich als vertrauenswürdige Geräte auszugeben. In Kombination mit anderen Techniken kann dies zu DoS-Angriffen führen.

### Schutzmaßnahme: IP Source Guard
- Vergleich der IP/MAC-Adressen mit der Source Binding Tabelle.
- Blockiert Pakete mit ungültigen Kombinationen.
- Erfordert aktiviertes DHCP Snooping.
