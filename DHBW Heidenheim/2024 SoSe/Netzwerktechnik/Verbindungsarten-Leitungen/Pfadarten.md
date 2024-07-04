## 📌 Pfadarten

In der Netzwerktechnik gibt es verschiedene Arten von Pfaden, die für die Datenübertragung zwischen Knoten verwendet werden. Diese Pfade können entweder permanent, dynamisch oder virtuell sein, abhängig von der Art und Weise, wie sie eingerichtet und verwaltet werden.

### Permanent Virtual Circuit (PVC)

**Permanent Virtual Circuit (PVC)** ist ein fester, vorab eingerichteter virtueller Pfad in einem Netzwerk, der dauerhaft verfügbar ist. 

- **Fest eingerichteter Pfad**:
  - PVCs werden einmal konfiguriert und bleiben bestehen, bis sie manuell geändert oder gelöscht werden.
  - Sie bieten eine konstante und vorhersehbare Verbindung zwischen zwei Endpunkten.
  - Anwendung: Weitverkehrsnetzwerke (WANs), wo konstante und stabile Verbindungen erforderlich sind, wie z.B. bei festen Verbindungen zwischen Unternehmensstandorten.

### Switched Virtual Circuit (SVC)

**Switched Virtual Circuit (SVC)** ist ein virtueller Pfad, der bei Bedarf dynamisch aufgebaut und nach Abschluss der Kommunikation wieder abgebaut wird.

- **Dynamisch auf- und abgebauter Pfad**:
  - SVCs werden bei Bedarf eingerichtet und bestehen nur für die Dauer der Datenübertragung.
  - Sie bieten Flexibilität und Effizienz, da Ressourcen nur bei tatsächlicher Nutzung beansprucht werden.
  - Anwendung: Paketvermittelte Netzwerke wie Frame Relay oder ATM, wo Verbindungen häufig nur für kurze Kommunikationssitzungen benötigt werden.

### Virtual Circuit

**Virtual Circuit** ist ein allgemeiner Begriff für eine virtuelle Verbindung in einem Netzwerk, die wie eine physische Verbindung wirkt, aber tatsächlich über gemeinsam genutzte physische Infrastruktur realisiert wird.

- **Virtueller Pfad**:
  - Virtuelle Schaltkreise können sowohl PVCs als auch SVCs umfassen.
  - Sie nutzen logische Verbindungen innerhalb eines physischen Netzwerks, um Daten zwischen Endpunkten zu übertragen.
  - Virtuelle Schaltkreise gewährleisten eine geordnete und zuverlässige Datenübertragung, indem sie sicherstellen, dass Datenpakete in der richtigen Reihenfolge und ohne Duplikate ankommen.

## 🚀 Anwendungen von Virtual Circuits

### Frame Relay

Frame Relay ist ein WAN-Protokoll, das sowohl PVCs als auch SVCs unterstützt und virtuelle Schaltkreise verwendet, um effiziente und flexible Datenverbindungen zu ermöglichen.

### Asynchronous Transfer Mode (ATM)

ATM nutzt virtuelle Schaltkreise für die Übertragung von Daten in kleinen, festen Zellen. Es unterstützt sowohl PVCs als auch SVCs und bietet hohe Geschwindigkeit und Effizienz.

### Multi-Protocol Label Switching (MPLS)

MPLS verwendet virtuelle Schaltkreise, um Datenpakete durch ein Netzwerk basierend auf Labels zu leiten. Es bietet flexible und skalierbare Netzwerkverbindungen, die sowohl PVC- als auch SVC-ähnliche Eigenschaften haben können.

## ⚖️ Vorteile und Nachteile der Pfadarten

### Permanent Virtual Circuit (PVC)

**Vorteile**:
- Stabile und konstante Verbindung.
- Vorhersehbare Leistung und Zuverlässigkeit.

**Nachteile**:
- Ineffiziente Nutzung von Ressourcen, da die Verbindung ständig aufrechterhalten wird.
- Hohe Kosten für die Einrichtung und Wartung.

### Switched Virtual Circuit (SVC)

**Vorteile**:
- Effiziente Ressourcennutzung, da Verbindungen nur bei Bedarf hergestellt werden.
- Flexibilität und Anpassungsfähigkeit an wechselnde Netzwerkbedürfnisse.

**Nachteile**:
- Potenzielle Verzögerungen beim Verbindungsaufbau.
- Mögliche Schwankungen in der Verbindungsqualität und -stabilität.

### Virtual Circuit

**Vorteile**:
- Geordnete und zuverlässige Datenübertragung.
- Flexibilität in der Nutzung physischer Netzwerkressourcen.

**Nachteile**:
- Komplexität bei der Verwaltung und Konfiguration.
- Abhängigkeit von der zugrunde liegenden physischen Infrastruktur.


