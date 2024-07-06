Schreiben Sie ein Programm, das aufgrund der folgenden Variablendeklaration und -initialisierung

int i = 4711, j = 471, k = 47, m = 4;

mit zwei WriteLine() - Aufrufen diese Ausgabe produziert:

Rechtsbündig:
i = 4711
j= 471
k= 47
m= 4

Linksbündig:
4711 (i)
471 (j)
47 (k)
4 (m)

```csharp
using System;

class Prog {
	static void Main() {
		int i = 4711, j = 471, k = 47, m = 4;

		string rightAligned = $"Rechtsbündig:\ni = {i,5}\nj = {j,5}\nk = {k,5}\nm = {m,5}\n";
        string leftAligned = $"Linksbündig:\n{i,-5} (i)\n{j,-5} (j)\n{k,-5} (k)\n{m,-5} (m)";

        Console.WriteLine(rightAligned);
        Console.WriteLine(leftAligned);
		}

}
```




