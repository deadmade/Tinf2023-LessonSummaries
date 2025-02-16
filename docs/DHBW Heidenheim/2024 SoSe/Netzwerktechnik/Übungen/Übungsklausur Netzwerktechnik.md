## Frage 1: Bandbreite und Übertragungsdauer
a) Berechnen Sie die Zeit, die benötigt wird, um 500 Gigabyte Daten über eine 100-Mbit/s-Verbindung zu übertragen.
-> 500GB = 500 000 / 100 = 5000s 

b) Sie haben einen Datenträger mit 1 Terabyte Daten, die Sie in eine 300 km entfernte Stadt bringen müssen. Sie haben zwei Möglichkeiten:

Die Daten über eine 50-Mbit/s-Verbindung zu übertragen.
Den Datenträger mit dem Auto zu transportieren, was 4 Stunden dauert.
Welche Methode ist schneller und warum? Berücksichtigen Sie bei Ihrer Berechnung, dass 1 Byte 8 Bit entspricht.

-> 50 Mb /s * 60 = 3000Mb/m
-> 3000Mb/m * 60 = 18 0000 Mb / h
-> 18 0000 Mb / h * 4 =72 000 MB in 4 Studen sind kleiner als 1000000 MB

## Frage 2: Manchester-Code
a) Erklären Sie die Funktionsweise des Manchester-Codes und geben Sie mindestens einen Grund an, warum er verwendet wird.

b) Stellen Sie die Bitfolge 1011001 grafisch im Manchester-Code dar.

## Frage 3: Aufteilung des Mediums und Kollisionsvermeidung
a) Erläutern Sie, wie sich ein Übertragungsmedium gerecht aufteilen lässt, um Kollisionen zu vermeiden.

b) Nennen und beschreiben Sie zwei Verfahren zur Kollisionsvermeidung.
CSMA/CA
Im initialen Zusand wird gewartet, sobald ein Gerät etwas senden möchte, wird zuerst eine Anfrage an den Verwalter des Netzes geschickt. (RTS). Sobald der Verwalter ein Packet zurückschickt mit der Bestätigung das gesendet werden darf (CTS) sendet das Gerät. Sobald die Übertragung beendet ist, schickt der Verwalter eine Bestätigung (ACK) das die Übertragung angekommen ist. 
Jeder Request enthält ein NAV. Dies sagt aus, wie lange die Leitung belegt ist, und die anderen Geräte nicht senden dürfen. Diese warten dann diese Zeit ab, bevor wieder gesendet wird. Falls eine Kollision auftritt, also kein ACK gesendet wird, wartet das gerät eine zufällig lange Zeit bis es wieder sendet.


Token Ring:
Jeder Rechner ist mit dem vorgänger und nachfolger verbunden
Immer nur ein Rechner darf senden, der jenige, der den "Stab hat". Sobald dieser Rechner fertig gesendet hat, darf der nächste Rechner in der Reihe senden.
## Frage 4: Subnetting
Ein Unternehmen hat den IP-Adressbereich 172.20.0.0/16 erhalten. Es benötigt 4 Subnetze unterschiedlicher Größe:

Subnetz 1: 500 Hosts -> 503
Subnetz 2: 250 Hosts -> 253
Subnetz 3: 100 Hosts -> 103
Subnetz 4: 50 Hosts -> 53
Führen Sie ein Subnetting durch und geben Sie für jedes Subnetz folgende Informationen an:

Netzadresse
Broadcast-Adresse
Bereich der nutzbaren IP-Adressen
Subnetzmaske


| Netzadresse     | Broadcast-Adresse | Bereich                     | Subnetzmaske |
| --------------- | ----------------- | --------------------------- | ------------ |
| 172.20.0.0/23   | 172.20.1.255/23   | 172.20.0.1 - 172.20.1.254   | 172.20.1.255 |
| 172.20.2.0/24   | 172.20.2.255      | 172.20.2.0-172.20.2.254     | 172.20.2.255 |
| 172.20.3.0/25   | 172.20.3.127/25   | 172.20.3.1-172.20.3.126     | 172.20.2.127 |
| 172.20.3.128/26 | 172.20.3.191/26   | 172.20.3.129 - 172.20.3.190 |              |

## Frage 5: IP-Adressvergabe und DHCP
a) Beschreiben Sie zwei Möglichkeiten, wie ein Knoten in einem Netzwerk eine IP-Adresse erhalten kann.
-> Einmal ist dies möglich über die manuelle Setzung der IP Adresse am Knoten oder die Automatische Zuweisung über einen DHCP Server

b) Erklären Sie die Funktionsweise des DHCP-Protokolls (Dynamic Host Configuration Protocol). Gehen Sie dabei auf die einzelnen Schritte der Kommunikation zwischen Client und Server ein.

-> Client kommt ins Netz und kennt DHCP nicht deswegen Broadcast zur Suche des Servers. 
-> Server auf diese Anfrage mit der IP Adresse
-> Client erhält die Anfrage von DHCP und antwortet darauf mit einer Bestätigung, das er diese IP Adresse nimmt 

## Frage 6: UDP und TCP
a) Vergleichen Sie die Protokolle UDP (User Datagram Protocol) und TCP (Transmission Control Protocol) hinsichtlich ihrer Eigenschaften und Anwendungsfälle.

UDP -> wartet nicht auf bestätigung vom Empfänger, schneller und weniger Resourcen. Anwendung in Online Videospiele wo es wichtig ist das es Flüssig ist, aber nicht das jedes Paket ankommt

TCP -> bestätigt, das Empfänger Paket erhalten hat, braucht länger und mehr overhead. Anwendung zumeist in Dateiübertragung, da dort jedes Paket anbkommen soll

b) Geben Sie für jedes Protokoll ein Beispiel für ein Szenario, in dem es sinnvoll eingesetzt wird, und begründen Sie Ihre Wahl.

## Frage 7: Three-Way-Handshake
Erklären Sie den Ablauf des Three-Way-Handshake beim Aufbau einer TCP-Verbindung. Gehen Sie dabei auf die Bedeutung der einzelnen Schritte und der ausgetauschten Nachrichten ein.

## Frage 8: DNS
a) Erläutern Sie den Ablauf einer DNS-Anfrage (Domain Name System).

b) Warum wird DNS benötigt?

Frage 9: ARP
a) Beschreiben Sie den Ablauf des ARP-Protokolls (Address Resolution Protocol).

b) Erklären Sie, warum ARP notwendig ist.