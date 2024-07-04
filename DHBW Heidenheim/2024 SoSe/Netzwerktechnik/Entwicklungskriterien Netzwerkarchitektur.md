# 🌐 Entwicklungskriterien Netzarchitektur

## Bereich
**So allgemein wie möglich vs. Anwendungsspezifisch**: 
Eine Netzarchitektur kann entweder so gestaltet werden, dass sie für eine breite Palette von Anwendungen geeignet ist (allgemein), oder sie kann speziell für eine bestimmte Anwendung optimiert sein (anwendungsspezifisch). Eine allgemeine Architektur bietet Flexibilität und vielseitige Einsatzmöglichkeiten, während eine anwendungsspezifische Architektur bessere Leistung und Effizienz für die jeweilige Anwendung bieten kann.

## 📈 Skalierbarkeit
**Kein Unterschied zwischen klein oder groß ⇒ eventuell Nachteile**: 
Eine skalierbare Netzarchitektur kann effektiv mit einer wachsenden Anzahl von Benutzern oder Daten umgehen, ohne an Leistung einzubüßen. Wenn eine Architektur jedoch nicht richtig skaliert wird, könnte sie sowohl in kleinen als auch in großen Netzwerken ineffizient sein und Nachteile wie erhöhte Latenz oder Ressourcenverschwendung mit sich bringen.

## 🛡️ Robustheit
**Ausfälle tolerieren, unvollständige oder fehlerhafte Übertragung erkennen**: 
Eine robuste Netzarchitektur muss in der Lage sein, Ausfälle zu verkraften und trotzdem funktionsfähig zu bleiben. Sie sollte auch unvollständige oder fehlerhafte Datenübertragungen erkennen und entsprechend handeln, um Datenverlust oder -korruption zu vermeiden. Mechanismen wie Redundanz, Fehlererkennung und -korrektur sind hierfür entscheidend.

## 🔧 Selbstkonfigurierbarkeit
**Eigenständig, von selbst funktionieren**: 
Selbstkonfigurierbare Netzwerke können sich automatisch an veränderte Bedingungen anpassen, ohne manuelle Eingriffe. Dies umfasst die automatische Konfiguration von Netzwerkgeräten, das Anpassen an neue Topologien und das selbstständige Lösen von Problemen, was die Verwaltung erheblich erleichtert.

## ⚙️ Fähigkeit zur Feinabstimmung
**Konfigurierbare Parameter**: 
Eine Netzarchitektur mit der Fähigkeit zur Feinabstimmung erlaubt es Administratoren, verschiedene Parameter anzupassen, um die Leistung zu optimieren. Dies kann Netzwerkprotokolle, Bandbreitenzuweisungen, Sicherheitsrichtlinien und andere Einstellungen umfassen, um den spezifischen Anforderungen des Netzwerks gerecht zu werden.

## 🎯 Determinismus
**Identische Bedingungen führen zu identischen Ergebnissen**: 
Deterministische Netzwerke verhalten sich unter gleichen Bedingungen immer gleich, was Vorhersagbarkeit und Zuverlässigkeit in der Netzwerkleistung bedeutet. Dies ist besonders wichtig für Anwendungen, die konsistente Latenzzeiten und Datenübertragungsraten erfordern, wie Echtzeitanwendungen und industrielle Steuerungssysteme.

## 🔄 Migration
**Netzwerkentwürfe können z.B. nicht mehr zweckmäßig sein ⇒ Stück für Stück Migration**: 
Im Laufe der Zeit können bestehende Netzarchitekturen veraltet oder ungeeignet für aktuelle Anforderungen werden. Die Migration umfasst den schrittweisen Übergang von der alten zu einer neuen Netzarchitektur, um Ausfallzeiten zu minimieren und eine kontinuierliche Verfügbarkeit der Dienste zu gewährleisten. Dies kann durch parallele Inbetriebnahme, Umschalten und schrittweise Upgrades erfolgen.
