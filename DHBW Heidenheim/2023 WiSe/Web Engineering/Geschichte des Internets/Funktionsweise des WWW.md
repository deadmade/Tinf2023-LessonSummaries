# Standards Im WWW

- Kernstandards
	- **HTTP** als freies Protokoll
	- **HTML** als Auszeichnungssprache
	- **URI** als eindeutige Bezeichnung einer Ressource

- Spätere Standards
	- **CSS** zur Darstellung (_”Verschönerung”_)
	- **HTTPS** zur Verschlüsselung des Datentransfers
	- **DOM** als Schnittstelle für Skriptsprachen

---
# URI

- *Uniform Resource Identifier*
- Identifiziert Ressourcen im Internet
- Aufbau:
	- **Syntax**: `<scheme>:<scheme-specific-part>`
	- **Schema**: Definiert Kontext
	- **Schema**-spezifischer Teil: Enthält angaben zur Ressource
- Beispiele:
	- https://de.wikipedia.org/
	- tel:+1-816-555-1212

---
# URL

- *Uniform Resource Locator*
- Häufigste Art von URI
- Identifiziert + Lokalisiert Ressourcen im Internet
- Bekannte Schemata: `http`, `https`, `mailto`, `file`
- Beispiele: 
	- http://example.com/foo/bar.html
	- file://system/fonts/
	- mailto:tim@cern.ch

---
# URN

- *Uniform Resource Name*
- Benennt Ressource eindeutig (unabhängig vom Standort)
- Schema ist immer `urn`
- Beispiel:
	- urn:ISBN:978-0062515872

---
# TCP/IP Referenzmodell

[![Internet-Protokolle, Teil 1: TCP/IP, der Grundstein für  Anwendungsprotokolle | heise online](https://www.heise.de/imgs/18/1/4/3/3/4/1/8/Abb1_Network_Layer-bc2a5fa55308d5c0.png)
- Rahmen für Entwicklung von Netzwerkprotokollen
- Vier Schichten:
	1. Anwendungsschicht
	2. Transportschicht
	3. Netzwerkschicht
	4. Verbindingsschicht
- Grundlage für Web-Technologien: **Client-Server Modell**
- Datenaustausch muss über Protokolle geregelt werden

---
# HTTP

- *HyperText Transfer Protocol*
- Protokoll zur Übertragung von Daten
- Frage-Antwort Schema
	- Client & Server tauschen Nachrichten aus
	- **Request**: Client sendet Anfrage an Server
	- **Response**: Server Antwortet auf Anfrage
- Zwei wichtige Anfragemethoden
	- `GET`: Client empfängt Daten vom Server
	- `POST`: Client sendet Nachrichten am Server
- Nachrichten bestehen aus Request-/Status-Line, Header (Metadaten), Body

---
# TCP

- *Transmission Control Protocol*
- Kommunikationsprotokoll für Internet & Intranet
- Daten werden als Pakete übertragen
- Pakete kommen vollständig & in richtiger Reihenfolge an
- Verbindung eindeutig identifizierbar durch zwei Endpunkte
	- **Endpunkt**: Geordnetes Paar aus IP & Port (= Socket)
	- **TCP-Verbindung**: lokaler Rechner, lokaler Port, entfernter Rechner, entfernter Port
- Eigenschaften:
	- zuverlässig, verbindungsorientiert
	- Datenübertragung in beide Richtungen gleichzeitig möglich
	- Datenverluste werden erkannt + automatisch behoben

---
# HTTPS

- *HyperText Transfer Protocol Secure*
- Erweiterung von HTTP
	- Daten werden bei der Übertragung verschlüsselt
- Erweitert TCP um TLS (Transport Layer Security)
- Mittels URI-Schema genutzt 
	- Auch andere ungesicherte Protokolle können abgesichert werden
- Ziele:
	- **Vertraulichkeit**: Verschlüsselung der Daten (kein Mitlesen möglich)
	- **Integrität**: Daten während Übertragung unveränderbar
	- **Authentizität**: Kommunikationspartner über Zertifikate verifiziert

---
# IP

- *Internet Protocol*
- Definiert, wie Datenpakete erstellt, adressiert und versendet werden
- Öffentliche IP-Addressen weltweit eindeutig → Vergabe durch IANA
- Gruppierung von Rechnern innerhalb eines Netzwerks in logische Einheiten durch IP-Addressen
- IPv4
    - c.a. 4 Mrd. unterschiedliche Addressen → Addressraum zu klein
    - seit 2011 nichts mehr frei
    - Beispiel: `188.184.9.235`
- IPv6
	- c.a. 340 Sextillionen ($10^{38}$) unterschiedliche Addressen → Keine Konflikte mehr
	- Beispiel: `2607:f8b0:4004:836::2003`

---
# DNS

- *Domain Name System*
- Problem: IP-Adressen schwer merkbar
- DNS wandelt Webadressen in IP-Adressen um