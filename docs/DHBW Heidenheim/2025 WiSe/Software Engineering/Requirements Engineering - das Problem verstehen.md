## Einführung
- Anforderungen an Software entstehen aus einem Bedürfnis, ein spezifisches Problem zu lösen.
- Ziel von Requirements Engineering (RE): Das Problem verstehen und dafür die richtige Lösung entwickeln.

---

## Effektivität vs. Effizienz
- **Peter Drucker**: „Do the right things, not things right.“
- Effektivität bedeutet, das Richtige zu tun, während Effizienz nur beschreibt, wie gut man etwas tut.
- Beispiel: Es bringt nichts, etwas mit großem Aufwand perfekt umzusetzen, wenn die Aufgabe selbst irrelevant ist.

---

## Was ist Requirements Engineering?
- **Definition**: RE ist der Prozess, die Anforderungen an ein System zu ermitteln, zu dokumentieren und zu validieren.
- Kernaktivitäten:
  1. **Ermitteln**: Stakeholder-Bedürfnisse identifizieren.
  2. **Analysieren**: Anforderungen prüfen, priorisieren und strukturieren.
  3. **Spezifizieren**: Anforderungen in klarer und einheitlicher Form dokumentieren.
  4. **Validieren**: Anforderungen auf Richtigkeit und Vollständigkeit prüfen.

---

## Anforderungen (Requirements)
### Funktionale Anforderungen
- Beschreiben, **was das System tun soll**:
  - **Funktionsperspektive**: Input/Output, Fehlerbehandlung.
  - **Datenperspektive**: Datenstrukturen und Integritätsbedingungen.
  - **Verhaltensperspektive**: Zustandsübergänge, Ereignisse.

### Nichtfunktionale Anforderungen (NFRs)
- Geben Kriterien für die **Qualität des Systems** vor:
  - Beispiele:
    - Zuverlässigkeit
    - Performance
    - Benutzbarkeit
    - Änderbarkeit
    - Sicherheit
- NFRs wirken oft als Architekturtreiber und schränken die Gestaltungsmöglichkeiten ein.

---

## Rahmenbedingungen
- Einschränkungen, die die Realisierung beeinflussen:
  - **Technologisch**: IT-Infrastruktur, auf der das System laufen soll.
  - **Organisatorisch**: Abläufe und Verantwortlichkeiten der beteiligten Einheiten.
  - **Rechtlich**: Einhaltung von Datenschutzgesetzen und anderen Vorschriften.
  - **Ethisch**: Akzeptanz in bestimmten Kulturen, z. B. durch die Berücksichtigung von Farben und Anredeformen.

---

## Stakeholder
- **Definition**: Personen oder Organisationen mit Interesse am System.
- Beispiele:
  - Geldgeber
  - Nutzer
  - Entwickler
  - Regulierungsbehörden
- **Herausforderung**: Unterschiedliche Stakeholder haben oft widersprüchliche Anforderungen.

---

## Methoden zur Anforderungsermittlung
- **Techniken**:
  - Brainstorming
  - Interviews („5 x Warum“)
  - Beobachtungen
  - Prototyping
  - Workshops
  - Umfragen
- Ziel: Bedürfnisse und Probleme der Stakeholder klar verstehen.

---

## Anti-Patterns bei der Problembeschreibung
- Häufiger Fehler: Direkt eine Lösung definieren, ohne das Problem klar zu analysieren.
  - Beispiel: „Wir brauchen eine Knowledge-Database!“
  - Stattdessen: Warum wird diese benötigt? Welches Problem soll sie lösen?

---

## Schritte zur Problemanalyse
1. **Ist die Idee ein Problem oder eine Lösung?**
2. **Fokus auf das Kundenproblem legen.**
3. **Unbekannte Bereiche identifizieren.**
4. **Mehrere Lösungsoptionen erarbeiten.**
5. **MVP (Minimum Viable Product) testen.**

---

## User Stories
- **Format**: „Als <Rolle> möchte ich <Ziel>, damit <Nutzen>.“
- Anforderungen sollten sowohl funktionale als auch nichtfunktionale Aspekte umfassen.
- **Akzeptanzkriterien**:
  - Klare Kriterien, um festzustellen, ob eine Anforderung erfüllt ist.
  - Grundlage für Tests und Qualitätssicherung.

---

## Beispiele für User Stories
### Spendensammlung
- **Problem**: 13 % der Weltbevölkerung sind Analphabeten.
- **Ziel**: 2 Mio. € für Alphabetisierungsprogramme sammeln.
- **Lösungsoptionen**:
  - Ice Bucket Challenge
  - Quiz-App
  - Karaoke-Plattform

### Quiz-App User Stories
1. „Als Benutzer möchte ich vordefinierte Fragen beantworten, damit ich mein Wissen verbessern kann.“
2. „Als Benutzer möchte ich, dass das System meinen Highscore verwaltet, damit meine Ergebnisse sichtbar sind.“
3. „Als Benutzer möchte ich einen Avatar hinzufügen, um repräsentiert zu werden.“

---

## Nichtfunktionale Anforderungen (NFRs)
- Klassifikation nach **ISO/IEC 25010**:
  - **Availability**: Verfügbarkeit in % (z. B. 99,9 % = 8:45 Stunden pro Jahr Ausfallzeit).
  - **Usability**: Nutzerfreundlichkeit und User Experience.
  - **Security**: Schutz vor unbefugtem Zugriff.
  - **Scalability**: Erweiterbarkeit der Systemleistung durch zusätzliche Ressourcen.
  - **Legal Compliance**: Einhaltung von Gesetzen und Vorschriften.

---

## Akzeptanzkriterien und Testfälle
- **Akzeptanzkriterien**:
  - Definieren klare „Pass/Fail“-Ergebnisse.
  - Keine partielle Akzeptanz – eine Anforderung ist entweder erfüllt oder nicht.
- **Beispiel-Testfall**:
  - **Vorbedingung**: User ist angemeldet.
  - **Testschritte**:
    1. Frage stellen.
    2. Timeout messen.
  - **Erwartetes Ergebnis**: Zeit zwischen 30-31 Sekunden.

---

## Requirements Management
### Agile Methoden
- **Iterative Ansätze**:
  - Sprints mit Neubewertung der Anforderungen.
  - Time-Boxed Deadlines.
  
### Wasserfallmodell
- Frühe Festlegung des Umfangs und der Liefertermine.

### Stakeholder-Einbindung
- Change Control Board (CCB) einrichten.
- Regelmäßige Meetings zur Anpassung des Backlogs.

