# KV-Diagramm
#Definition
Gegeben sei eine $n$-Stellige Bool'sche Funktion (siehe: [Prädikat](Prädikatenlogik.md#Prädikat)). Ein **KV_Diagramm** besteht aus $2^n$ Feldern, die zu einem Rechteckschema angeordnet sind. Jedem Feld ist eine [Belegung](Erfüllbarkeit.md#Belegung) der Variablen zugeordnet.

>[!tip] Schema für $n=1$
>
>| $A$ | $\overline{A}$ |
| --- | -------------- |
| $1$ | $0$            |

>[!tip] Schema für $n=2$
>
|                | $A$  | $\overline{A}$ |
| -------------- | ---- | -------------- |
| $B$            | $11$ | $01$           |
| $\overline{B}$ | $10$ | $00$           |

>[!tip] Schema für $n=3$
>
|                | $\overline{A}$ | $A$            | $A$   | $\overline{A}$ |
| -------------- | -------------- | -------------- | ----- | -------------- |
| $B$            | $010$          | $110$          | $111$ | $011$          |
| $\overline{B}$ | $000$          | $100$          | $101$ | $001$          |
|                | $\overline{C}$ | $\overline{C}$ | $C$   | $C$            |

>[!tip] Schema für $n=4$
>
|                | $\overline{A}$ | $A$            | $A$    | $\overline{A}$ |                |
| -------------- | -------------- | -------------- | ------ | -------------- | -------------- |
| $\overline{B}$ | $0000$         | $1000$         | $1010$ | $0010$         | $\overline{D}$ |
| $B$            | $0100$         | $1100$         | $1110$ | $0110$         | $\overline{D}$ |
| $B$            | $0101$         | $1101$         | $1111$ | $0111$         | $D$            |
| $\overline{B}$ | $0001$         | $1001$         | $1011$ | $0011$         | $D$            |
|                | $\overline{C}$ | $\overline{C}$ | $C$    | $C$            |                |

>[!example]- Beispiel
>Gegeben sei die Bool'sche Funktion $f(A, B, C) = (A \land \overline{B}) \lor (\overline{A} \land B \land \overline{C})$. Zuerst notieren wir die Wahrheitstabelle, zur übersicht:
>
>| $A$ | $B$ | $C$ | $A \land \overline{B}$ | $\overline{A} \land B \land \overline{C}$ | $f(A, B, C)$ |
| --- | --- | --- | ---------------------- | ----------------------------------------- | ------------ |
| 0   | 0   | 0   | 0                      | 0                                         | 0            |
| 0   | 0   | 1   | 0                      | 0                                         | 0            |
| 0   | 1   | 0   | 0                      | 1                                         | 1            |
| 0   | 1   | 1   | 0                      | 0                                         | 0            |
| 1   | 0   | 0   | 1                      | 0                                         | 1            |
| 1   | 0   | 1   | 1                      | 0                                         | 1            |
| 1   | 1   | 0   | 0                      | 0                                         | 0            |
| 1   | 1   | 1   | 0                      | 0                                         | 0            |
> 
>Jetzt können wir gut die entsprechende KV-Tabelle ablesen:
>
>|                | $\overline{A}$ | $A$            | $A$ | $\overline{A}$ |
| -------------- | -------------- | -------------- | --- | -------------- |
| $B$            | 1              | 0              | 0   | 0              |
| $\overline{B}$ | 0              | 1              | 1   | 0              |
|                | $\overline{C}$ | $\overline{C}$ | $C$ | $C$            |
