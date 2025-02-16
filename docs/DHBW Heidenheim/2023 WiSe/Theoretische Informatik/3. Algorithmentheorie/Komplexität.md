Nicht alle Algorithmen, die [berechenbar](Berechenbarkeit.md) sind, sind auch mit Computerprogrammen sinnvoll auszuführen, da u.U. die Rechenzeiten viel zu lang sind.

# Rechenschritte von Algorithmen

Wir können die Rechenschritte von [[Algorithmen]] zählen. Je mehr Rechenschritte, desto größer die Komplexität, d.h. desto zeitaufwändiger sind die [[Algorithmen]].

Für [[Algorithmen]], die eine variable Anzahl an Rechenschritten haben (also die meisten [[Algorithmen]]) beschreiben wir die Anzahl an Rechenschritten mit einer Funktion.

# Landau-Symbole

**Landau-Symbole** werden in der Mathematik und in der Informatik verwendet, um das asymptotische verhalten von Funktionen und Folgen zu beschreiben. In unserem Fall werden wir die Landau-Symbole verwenden, um die Komplexität von [[Algorithmen]] zu beschreiben.

Im folgenden stellen wir nur einige Landau-Symbole dar, die für uns wichtig sind.

## Große-O-Notation

Die $\mathcal{O}$-Notation wird verwendet, um die asymptotische obere Schranke einer Funktion zu beschreiben.

Es sei $f:\mathbb{R} \to \mathbb{R}$ die Funktion, dessen obere Schranke ermittelt werden soll und es sei $g:\mathbb{R} \to \mathbb{R}^+$ die Funktion, die mit $f$ verglichen werden soll.
Dann schreiben wir
$$f(x) = \mathcal{O}(g(x)), \hspace{8pt} x \to \infty$$
falls es $M \in \mathbb{R}^+$ und $x_{0}\in \mathbb{R}$ gibt mit
$$|f(x)| \le Mg(x) \hspace{8pt} \forall x \ge x_0$$

## Kleine-o-Notation

Diese Notation ist ähnlich wie die $\mathcal{O}$-Notation. Was hier anders ist: $g$ steigt *deutlich* schneller als $f$:

Es seien $f$ und $g$ wie im oberen Beispiel. Wir schreiben
$$f(x) = o(g(x)), \hspace{8pt} x \to \infty$$
falls es für alle $\varepsilon \in \mathbb{R}^+$ ein $x_{0}\in \mathbb{R}$ gibt mit
$$|f(x)| \le \varepsilon g(x) \hspace{8pt} \forall x \ge x_0$$
Im Gegensatz zur $\mathcal{O}$-Notation muss hier die Bedingung **für alle** Konstanten gelten und nicht nur für mindestens eine. Also ist die $o$-Notation aussagekräftiger als die $\mathcal{O}$-Notation: Falls $f(x) = o(g(x))$, dann gilt automatisch $f(x) = \mathcal{O}(g(x))$, aber nicht anders rum!

## Große-Omega-Notation

Es gibt zwei verschiedene, inkonsistente Definitionen für die $\Omega$-Notation. Im folgenden erläutern wir die *Knuth*-Definition, benannt nach *Donald Knuth*. Diese Definition wird am häufigsten in der Informatik verwendet, nämlich um die *untere* Schranke einer Funktion zu beschreiben.

Es seien $f$ und $g$ wie im oberen Beispiel. Die Notation
$$f(x) = \Omega(g(x)), \hspace{8pt} x \to \infty$$
ist äquivalent zu:
$$g(x) = \mathcal{O}(f(x))$$

## Kleine-Omega-Notation

Analog zur $o$-Notation:

Es seien $f$ und $g$ wie im oberen Beispiel. Die Notation
$$f(x) = \omega(g(x)), \hspace{8pt} x \to \infty$$
ist äquivalent zu:
$$g(x) = o(f(x))$$

## Theta-Notation

Diese Definition ist ebenfalls per *Donald Knuth*.

Es seien $f$ und $g$ wie im oberen Beispiel. Wir schreiben
$$f(x) = \Theta(g(x)), \hspace{8pt} x \to \infty$$
falls gilt:
$$f(x) = \mathcal{O(g(x))} \hspace{8pt} \text{ und } \hspace{8pt} f(x) = \Omega(g(x))$$

# Komplexitätsklassen

Es ist für uns interessant zu wissen, welche Entscheidungsprobleme *"schnell"* lösbar sind und welche nicht. Hierzu gruppieren wir Probleme, die von Turing-Maschinen gelöst werden können, in sogenannten **Komplexitätsklassen**. Wir erläutern zunächst nur einige Klassen: **P**, **NP**, **NP-Hard** und **NP-Vollständig**.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/P_np_np-complete_np-hard.svg/600px-P_np_np-complete_np-hard.svg.png" style="background: white"/>

## P-Probleme

Als **P-Probleme** definiert man diejenigen Entscheidungsprobleme, die von einer deterministischen Turing-Maschine in Polynomialzeit gelöst werden können.

Diese Probleme sind (üblicherweise) "schnell" lösbar.

>[!example] Beispiel: QuickSort
>Wir können mithilfe des QuickSort-Algorithmus eine Liste in $\mathcal{O}(n \log_2(n))$ ordnen und wegen $n \log_{2}(n)= \mathcal{O}(n^2)$ in Polynomialzeit.

## NP-Probleme

Als **NP-Probleme** definiert man diejenigen Entscheidungsprobleme, bei denen es für "Ja"-Antworten Beweise gibt, die in Polynomialzeit von einer deterministischen Turing-Maschine verifiziert werden können.

*Alternativ*: Als NP-Probleme definiert man diejenigen Entscheidungsprobleme, die von einer nicht-deterministischen Turing-Maschine in Polynomialzeit gelöst werden können.

Somit ist NP also eine Generalisierung von P: Alle P-Probleme sind zugleich NP-Probleme. NP-Probleme sind auch die meisten, *"üblichen"* Probleme, die im Alltag auftauchen.

>[!example] Beispiel: Sudoku
>Wir kennen (bisher) keinen Algorithmus, der ein Sudoku in Polynomialzeit lösen kann, also ist das Sudoku-Problem (vermutlich) nicht in P.
>Wir können aber in Polynomialzeit prüfen, ob ein fertiges Sudoku richtig ist, also ein NP-Problem.

## NP-Hard-Probleme

Ein Entscheidungsproblem $H$ heißt **NP-hard**, falls es für *jedes* Problem $L$ in NP eine Überführung in Polynomialzeit von $L$ zu $H$ gibt.

Diese Komplexitätsklasse ist wichtig, da eine Lösung für ein NP-Hard-Problem auch eine Lösung für *alle* NP-Probleme ist.

>[!example] Beispiel: Halteproblem
>Wir kennen bereits das Halteproblem. Klar: Da das Halteproblem nicht [entscheidbar](Berechenbarkeit.md#Kategorien%20der%20Berechenbarkeit) ist kann es nicht in NP sein.
>Aber das Problem ist in NP-Hard: Es sei oBdA. $L$ ein Problem in NP und es sei $M$ eine nicht-deterministische Turing-Maschine, die $L$ lösen kann. Dann können wir $L$ zum Halteproblem überführen und zwar wie folgt:
>Es sei $M'$ eine Turing-Maschine, die für eine Eingabe $x$ genau dann terminiert, falls $x$ von $M$ akzeptiert wird. Überführe zunächst die Eingabe $x$ in die Eingabe $(M', x)$. Somit haben wir in Polynomialzeit $L$ in das Halteproblem überführt.
>---
>Hierbei ist es egal, ob $M'$ deterministisch oder nicht-deterministisch ist und es ist egal, ob $M'$ in Polynomialzeit läuft. Was relevant ist, ist das die *Überführung* $x \mapsto (M', x)$ in Polynomialzeit möglich ist.

## NP-Vollständige-Probleme

Falls ein Problem sowohl in NP als auch in NP-Hard ist, so ist das Problem **NP-vollständig**.

# P vs NP Problem

Dieses sehr bekannte, bisher ungelöste Problem Fragt ob es zu allen NP-Problemen eine äquivalente deterministische Turing-Maschine gibt, die das jeweilige Problem in Polynomialzeit lösen kann, also P = NP.

>[!tip] Was wir bisher nicht wissen
>Wir wissen nicht, ob es NP-Probleme gibt, die nicht NP-Vollständig sind. Falls wir das zeigen, dann gilt automatisch P = NP.