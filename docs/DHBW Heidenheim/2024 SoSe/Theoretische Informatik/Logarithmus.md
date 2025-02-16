## Definition und Grundkonzepte

> [!info]
> **Der Logarithmus** ist die Umkehrfunktion der Exponentialfunktion.
> 
> **Exponentialfunktion**: $(2^3 = 2 \times 2 \times 2 = 8)$
> 
> **Logarithmus**: $\log_2(8)$
> - **Frage**: Wie oft muss ich 2 mit sich selbst multiplizieren, um 8 zu erhalten?
> - **Antwort**: 3
> - **Anwendung**: Wie viele Bits braucht man für 8 verschiedene binäre Zahlen (0...7)?
> - **Antwort**: 3

## Beispiele zur Verdeutlichung

> [!example]- Beispiel 1
> - $2^6 = 2 \times 2 \times 2 \times 2 \times 2 \times 2 = 64$
> - $\log_2(64)$
>   - **Frage**: Wie oft muss ich 2 mit sich selbst multiplizieren, um 64 zu erhalten?
>   - **Antwort**: 6
>   - **Anwendung**: Wie viele Bits braucht man für 64 verschiedene binäre Zahlen (0...63)?
>   - **Antwort**: 6

> [!example]- Beispiel 2
> **$\log_2(8)$**:
> - Teilen wir 8 solange durch 2, bis wir 1 erhalten:
>   - $8 / 2 = 4$
>   - $4 / 2 = 2$
>   - $2 / 2 = 1$
> - **Frage**: Wie oft müssen wir 8 halbieren, bis wir 1 erhalten?
> - **Antwort**: 3

> [!example]- Beispiel 3
> **$\log_2(64)$**:
> - Teilen wir 64 solange durch 2, bis wir 1 erhalten:
>   - $64 / 2 = 32$
>   - $32 / 2 = 16$
>   - $16 / 2 = 8$
>   - $8 / 2 = 4$
>   - $4 / 2 = 2$
>   - $2 / 2 = 1$
> - **Frage**: Wie oft müssen wir 64 halbieren, bis wir 1 erhalten?
> - **Antwort**: 6

## Zusammenhang mit Informatik und Algorithmen

> [!tip]
> **Big O Notation: \(O(\log N)\)**
> - $O(\log N)$ ist die verkürzte Ausdrucksform für $O(\log_2 N)$.
> - $O(\log N)$ bedeutet, dass ein Algorithmus für $N$ Datenelemente $\log_2 N$Schritte benötigt.
> - **Beispiel**:
>   - Für $N = 8$ Elemente benötigt der Algorithmus 3 Schritte, weil $\log_2 8 = 3$.
> - **Erklärung**:
>   - $O(\log N)$ bedeutet, dass der Algorithmus so viele Schritte benötigt, wie es dauert, die Datenelemente so lange zu halbieren, bis man bei der unteilbaren 1 ankommt.

