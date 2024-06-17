Ein [Algorithmus](Algorithmen.md) wird als **rekursiv** bezeichnet, wenn er sich selbst aufruft.

# Grundlegende Idee

Bei jedem Aufruf des Algorithmus wird das Problem *"einfacher"*. Der innerste Rekursionsschritt ist der **triviale Fall** (**Rekursionsanker**).

## Vorteile

- meist kürzer als iterativer Algorithmus
- übersichtlicher

## Nachteile

- Rekursionsanker muss richtig definiert werden
- Umsetzung: Höherer Speicherplatz & langsamer

# Typen von Rekursionen

## Direkte Rekursion
Eine Rekursion ruft sich selbst auf.

## Indirekte Rekursion
Eine Methode `foo` ruft eine Methode `bar` auf, die wiederum `foo` aufruft.

## Lineare Rekursion
Eine Rekursion ruft sich maximal einmal selbst auf.
Ein besonderer Fall ist die **Endrekursion**: Diese steht als letzte Anweisung in der Methode und es gibt einen äquivalenten iterativen Algorithmus dazu.

## Kaskadierende Rekursion
Eine Rekursion ruft sich mehr als einmal selbst auf.

# Fehler bei Rekursionen

- Kein Abbruchkriterium
- Abbruchkriterium wird nie Erfüllt
- Rekursion wird nicht einfacher, sondern komplexer