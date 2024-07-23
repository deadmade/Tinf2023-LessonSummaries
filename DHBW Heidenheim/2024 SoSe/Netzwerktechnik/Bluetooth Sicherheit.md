Bluetooth-Technologie bietet verschiedene Sicherheitsmechanismen, die in drei Sicherheitsmodi (Security Modes) unterteilt sind. Diese Modi definieren, wie und wann Sicherheitsmaßnahmen angewendet werden, um die Integrität, Vertraulichkeit und Authentizität der Bluetooth-Verbindungen zu gewährleisten. Hier sind die drei Sicherheitsmodi im Detail:

### Sicherheitsmodus 1: Nicht sicher (Non-secure Mode)

- **Beschreibung:** In diesem Modus gibt es keine Sicherheitsmaßnahmen.
- **Verwendung:** Wird hauptsächlich in Anwendungen verwendet, bei denen Sicherheit keine Rolle spielt.
- **Merkmale:**
    - Keine Authentifizierung der Geräte.
    - Keine Verschlüsselung der Datenübertragung.
- **Risiken:** Daten sind anfällig für Abhören und Manipulationen durch unbefugte Geräte.

### Sicherheitsmodus 2: Service Level Security (Dienstebene-Sicherheit)

- **Beschreibung:** Sicherheitsmaßnahmen werden auf Dienstebene angewendet, nachdem die Verbindung hergestellt wurde.
- **Verwendung:** Ermöglicht flexiblere Sicherheitskonfigurationen basierend auf den Anforderungen der spezifischen Dienste.
- **Merkmale:**
    - Authentifizierung und Verschlüsselung können pro Dienst konfiguriert werden.
    - Sicherheitsanforderungen werden definiert, nachdem eine logische Verbindung hergestellt wurde, aber bevor Daten ausgetauscht werden.
- **Vorteile:**
    - Granulare Kontrolle über die Sicherheitseinstellungen für verschiedene Dienste.
    - Flexibilität bei der Anwendung unterschiedlicher Sicherheitsmaßnahmen für unterschiedliche Anwendungen.
- **Risiken:** Initiale Verbindungsherstellung erfolgt ohne Sicherheitsmaßnahmen, was kurzzeitig anfällig sein kann.

### Sicherheitsmodus 3: Link Level Security (Verbindungsebene-Sicherheit)

- **Beschreibung:** Sicherheitsmaßnahmen werden direkt auf der Verbindungsebene angewendet, bevor die Verbindung vollständig hergestellt wird.
- **Verwendung:** Höchste Sicherheit, da Authentifizierung und Verschlüsselung obligatorisch sind, bevor irgendeine Kommunikation stattfindet.
- **Merkmale:**
    - Authentifizierung und Verschlüsselung sind erforderlich, bevor eine Verbindung zugelassen wird.
    - Beide Geräte müssen sich gegenseitig authentifizieren, bevor sie Daten austauschen können.
- **Vorteile:**
    - Höchstes Maß an Sicherheit, da keine ungesicherte Verbindung möglich ist.
    - Geeignet für Anwendungen mit hohen Sicherheitsanforderungen.
- **Nachteile:** Kann weniger flexibel und etwas komplexer in der Handhabung sein, da alle Verbindungen abgesichert werden müssen.