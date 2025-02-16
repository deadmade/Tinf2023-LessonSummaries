Wir stellen uns die folgende Fragen:

- Gibt es für jedes denkbare Problem ein [Algorithmus](Algorithmen.md) der das Problem löst?
- Gibt es einen [Algorithmus](Algorithmen.md), der für alle Eingaben eine gegebene Funktion berechnet?
- Wenn nicht, gibt es wenigstens einen [Algorithmus](Algorithmen.md), der das Problem für die üblicherweise benötigten Eingaben löst?
- Wie kann man zeigen, dass ein Problem **berechenbar** ist?

# Kategorien der Berechenbarkeit

- **berechenbar**: ein Algorithmus liefert für jede Eingabe ein Ergebnis in endlicher Zeit
- **entscheidbar**: für jede Eingabe [terminiert](Korrektheit.md#Terminiertheit) in endlicher Zeit mit dem Ergebnis ja/nein (wahr/falsch)

# Nachweis der Berechenbarkeit

Probleme, bei denen die [[Komplexität]] bestimmt werden kann, sind berechenbar.

>[!tip] Church-Turing These
>*Alle intuitiv berechenbaren Funktionen sind auch mit einer Turingmaschine berechenbar.*

Also: Falls es eine Turingmaschine gibt, die ein Problem lösen kann, so ist das Problem berechenbar.

# Nicht-Berechenbare Probleme

Nicht alle Probleme sind berechenbar. Beweis hierfür ist allerdings nicht trivial und wird hier nicht behandelt.
## Beispiele

- Halte-Problem
- Totalitätsproblem
- Äquivalenzprogramm