Unter **Integrität** versteht man das Verhindern von unzulässiger oder unbefugter Änderung:
- von Daten oder Prozessen (Information, Verfügbarkeit)
- der Quelle von Daten (des Absenders)

### Präventionsmechanismen 🚫
Präventionsmechanismen zielen darauf ab, die Integrität der Daten aufrechtzuerhalten, indem sie alle unbefugten Versuche, die Daten zu ändern, verhindern:
- **Hash-Werte** 🔑: Ein Hash-Wert ist eine kryptografische Funktion, die aus einer Eingabe eine feste Ausgabe erzeugt. Er wird verwendet, um die Integrität von Daten zu überprüfen.
- **White-Listing** 📋: Eine Technik, bei der nur autorisierte Anwendungen oder Prozesse ausgeführt werden dürfen.
- **Access-Control** 🔒: Zugriffssteuerungssysteme, die den Zugriff auf Daten oder Systeme nur für autorisierte Benutzer erlauben.
- **Digitale Zertifikate** 📜: Elektronische Dokumente, die die Identität einer Person oder Organisation bestätigen und verschlüsselte Kommunikation ermöglichen.

### Detektionsmechanismen 🔍
Detektionsmechanismen melden, dass die Integrität der Daten nicht mehr vertrauenswürdig ist. Dabei können Systemereignisse (Benutzer- oder Systemaktionen) oder (häufiger) die Daten selbst analysiert werden, um Verletzungen zu erkennen:
- **Hash-Werte** 🔑: Die Verwendung von Hash-Werten, um zu überprüfen, ob Daten unverändert geblieben sind.

### Reaktive Mechanismen 🔄
Reaktive Mechanismen sind beispielsweise das Einspielen eines Backups, um die Datenintegrität wiederherzustellen.
