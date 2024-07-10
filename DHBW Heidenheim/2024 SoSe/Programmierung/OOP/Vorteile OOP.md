## Datenkapselung
- Methoden kapseln direkte Zugriffe auf Klassendaten.
- Öffentliche Methoden bilden die Schnittstelle der Klasse nach außen.
- Dies erleichtert das Testen und die Fehlerbeseitigung durch reproduzierbare Unit Tests.
- Innovationsoffenheit bei Implementierungsdetails ohne Gefährdung der Zusammenarbeit mit anderen Klassen.
- Steigerung der Produktivität durch wiederverwendbare Klassen.
- Unterstützung erfolgreicher paralleler Teamarbeit durch abgeschottete Verantwortungsbereiche und vorabdefinierte Interfaces.

## Vererbung
- Ermöglicht die Ableitung spezialisierter Klassen aus einer Basisklasse zur Lösung neuer Aufgaben.
- Abgeleitete Klassen erben alle Member der Basisklasse, was die Wiederverwendung von Software erleichtert.
- Die Designänderung einer abgeleiteten Klasse kann sich auf neue Member beschränken oder Modifikationen an bestehenden Mitgliedern vornehmen, solange die Kontrakte der Basisklasse eingehalten werden.

## Open-Closed-Principle
- Dieses Prinzip besagt, dass Klassen offen für Erweiterungen (Verwendung als Basisklasse) sein sollten, aber geschlossen für Änderungen an ihrem bereits implementierten Verhalten.

## Polymorphie
- Erlaubt es Objekten unterschiedlicher Klassen, die von derselben Basisklasse abgeleitet sind, bei gleichen Methodenaufrufen unterschiedliches Verhalten zu zeigen.
- Methoden können in abgeleiteten Klassen überschrieben werden, wodurch jedes Objekt entsprechend seiner spezifischen Implementierung reagiert.
- Diese polymorphen Verhaltensweisen werden zur Laufzeit entschieden (späte Bindung), was zu einer verbesserten Wiederverwendbarkeit von Code und einer losen Kopplung zwischen Klassen führt.
