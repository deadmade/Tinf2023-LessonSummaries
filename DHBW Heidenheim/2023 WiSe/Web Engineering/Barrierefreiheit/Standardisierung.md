#BarrierFree 
# Web Accessibility Initiative (WAI)

- Bereich innerhalb des W3C
- Beschäftigt sich seit 1997 mit barrierefreiem Zugang zum Web und seinen Inhalten
- Web Content Accessibility Guidelines (WCAG)
	- Richtlinien für barrierefreie Webinhalte
	- Definieren Anforderungen bzgl. Webseitenprogrammierung, Inhaltsarchitektur, Layout-Grundlagen und Technik-Verwendung

---
# WCAG 2.1

- *Web Content Accessibility Guidelines*
- Richtlinien für Barrierefreies Webdesign
	- Enthält 13 Richtlinien
	- Unterteilt in 4 Prinzipien
	- Bewertet nach 78 Erfolgskriterien (testbare Anforderungen)
	- Eingeteilt in 3 Konformitätsstufen (Level A, AA, AAA)
- Vier Prinzipien:
	- Wahrnehmbar
	- Bedienbar
	- Verständlich
	- Robust
## Konformitätsstufen

- **Level A**: 30 Kriterien
	- Mindestanforderungen für Barrierefreiheit
- **Level AA**: 20 Kriterien
	- Mindestanforderungen nach EU-Norm
- **Level AAA**: 28 Kriterien
	- Maximum des technisch Möglichen

## Prinzip Wahrnehmbarkeit

- Textalternativen:
	- Textuelle Beschreibungen für alle Nicht-Text-Inhalte angeben (z.B. Bilder)
- Zeit-basierte Medien:
	- Alternativen für zeit-basierte Medien zur Verfügung stellen (z.B. Untertitel bei Videos)
- Anpassbar:
	- Inhalte können auf verschiedenen Arten dargestellt werden (z.B. einfacheres Layout)
- Unterscheidbar:
	- Inhalte können leichter wahrgenommen werden (z.B. durch hohe Kontraste)

## Prinzip Bedienbarkeit

- Funktionen per Tastatur bedienbar
- Genügend Zeit zum Lesen & Nutzen der Inhalte
- Trigger für (z.B. epileptische) Anfälle vermeiden
- Unterstützung bei Navigation & suchen von Inhalten

## Prinzip Verständlichkeit

- **Lesbar**: Verständliche Inhalte (Darstellung, Struktur, Formulierung)
- **Vorhersehbar**: Aussehen & Funktionsweise (Konventionen)
- **Hilfestellung bei Eingabe**: Fehlervermeidung & Korrektur

## Prinzip Robustheit

- **Kompatibilität**: Aktuelle & Zukünftige Technologien

---
# EU-Norm EN 301 549

- Europäischer Standard zur barrierefreien Gestaltung von digitalen Inhalten
- Erfüllung der 50 Erfolgskriterien der WCAG 2.1 auf Stufe AA
- Umsetzung in Deutschland:
	- Behindertengleichstellungsgesetz (BGG)
	- Barrierefreie Informationstechnik-Verordnung (BITV 2.0)
	- Gleichstellungsgesetze & IT-Verordnungen der Länder

# BITV 2.0

- Erweiterung gegenüber EU-Normen
	- Anwendung des Stands der Technik, wenn keine Vorgabe in EU-Norm existiert
	- Zentrale Navigation / Einstiegsseiten sowie Formulare und interaktive Prozesse nach Level AAA
	- Startseite muss wesentliche Informationen in Gebärden- und leichter Sprache enthalten

---
# ARIA

- *Accessible Rich Internet Applications*
- Ziel: Inhalte für Technologien (z.B. Screenreader) zugänglich machen

>[!tip] Don't use ARIA!
>Nur verwenden wenn HTML-Elemente kein Accessibility-Support bieten. Besser: Semantische HTML-Elemente.

>[!tip] No ARIA is better than bad ARIA
>Keine Widersprüche erzeugen! Attribute korrekt verwenden. Keine falschen & redundanten Rollen.
>- Schlecht: `<footer role="button">...`
>- Besser: `<footer><button>...`