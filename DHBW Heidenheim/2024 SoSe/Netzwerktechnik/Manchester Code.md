Der Manchester-Code ist eine spezielle Art der Leitungscodierung, die in der digitalen Kommunikation verwendet wird. Er kombiniert das Taktsignal mit den Daten, sodass beide in einem einzigen Signal integriert sind. Dies ermöglicht eine zuverlässigere Datenübertragung, insbesondere über lange Distanzen oder in Umgebungen mit hohem Rauschen.

## Prinzip des Manchester-Codes

Beim Manchester-Code wird jedes Bit durch eine bestimmte Übergangssequenz dargestellt, die innerhalb eines einzigen Taktzyklus erfolgt. Es gibt zwei gängige Varianten des Manchester-Codes: den **G.E. Thomas Manchester-Code** und den **IEEE 802.3 Manchester-Code**. Hier konzentrieren wir uns auf den IEEE 802.3 Manchester-Code, der in Ethernet-Netzwerken verwendet wird.

### Darstellung von Bits

- **Bit 0:** Ein Übergang von High (1) nach Low (0) in der Mitte des Taktzyklus.
- **Bit 1:** Ein Übergang von Low (0) nach High (1) in der Mitte des Taktzyklus.

## Vorteile des Manchester-Codes

1. **Taktsynchronisation:** Da jeder Bitwert durch einen Übergang dargestellt wird, kann der Empfänger den Takt einfach aus den Übergängen des Signals rekonstruieren.
2. **Fehlersicherheit:** Die ständige Signaländerung hilft, die Wahrscheinlichkeit von Fehlern durch Signalverzerrungen oder Rauschen zu verringern.
3. **Keine Gleichstromkomponente:** Der ständige Wechsel des Signals bedeutet, dass keine Gleichstromkomponente vorhanden ist, was die Übertragung über Transformatoren und lange Kabel erleichtert.

## Beispiel

Um den Manchester-Code besser zu verstehen, betrachten wir ein einfaches Beispiel. Angenommen, wir wollen die Binärfolge `1010` codieren.

1. **Bit 1:** Übergang von Low (0) nach High (1) in der Mitte des Taktzyklus.
2. **Bit 0:** Übergang von High (1) nach Low (0) in der Mitte des Taktzyklus.
3. **Bit 1:** Übergang von Low (0) nach High (1) in der Mitte des Taktzyklus.
4. **Bit 0:** Übergang von High (1) nach Low (0) in der Mitte des Taktzyklus.

## Signalverlauf
![[Pasted image 20240712101318.png]]


Hier ist eine detaillierte Darstellung des Signalverlaufs:

- Für Bit 1: Das Signal beginnt mit einem Low-Zustand und wechselt in der Mitte des Taktzyklus in den High-Zustand.
- Für Bit 0: Das Signal beginnt mit einem High-Zustand und wechselt in der Mitte des Taktzyklus in den Low-Zustand.