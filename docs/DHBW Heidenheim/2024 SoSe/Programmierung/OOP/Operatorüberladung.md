In C# ermöglicht die Operatorüberladung, dass benutzerdefinierte Typen (wie Klassen und Strukturen) eigene Implementierungen für Standardoperatoren wie `+`, `-`, `*`, `/` usw. bereitstellen. Dies erlaubt es, diese Operatoren auf benutzerdefinierte Objekte in einer Weise anzuwenden, die deren Semantik entspricht.

## Grundlagen der Operatorüberladung

- Die Operatorüberladung wird durch die Verwendung des `operator`-Schlüsselworts in Verbindung mit dem zu überladenden Operator durchgeführt.
- Eine überladene Operator-Methode muss `public` und `static` sein.
- Die Parameter der Methode entsprechen den Operanden des Operators, und der Rückgabewert entspricht dem Ergebnis des Operators.

## Beispiel: Überladen des `+` Operators

Angenommen, wir haben eine Klasse `Complex`, die komplexe Zahlen repräsentiert, und wir möchten den `+` Operator überladen, um die Addition von zwei komplexen Zahlen zu ermöglichen.

### Definition der Klasse `Complex`
```csharp
using System;

public class Complex
{
    public double Real { get; set; }
    public double Imaginary { get; set; }

    public Complex(double real, double imaginary)
    {
        Real = real;
        Imaginary = imaginary;
    }

    // Überladen des + Operators
    public static Complex operator +(Complex c1, Complex c2)
    {
        return new Complex(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);
    }

    public override string ToString()
    {
        return $"{Real} + {Imaginary}i";
    }
}

class Program
{
    static void Main(string[] args)
    {
        Complex c1 = new Complex(1.0, 2.0);
        Complex c2 = new Complex(3.0, 4.0);

        Complex result = c1 + c2;

        Console.WriteLine(result); // Ausgabe: 4 + 6i
    }
}
```

## Weitere Beispiele für Operatorüberladungen

### Überladen des `==` und `!=` Operators

Für die Überladung der Vergleichsoperatoren `==` und `!=` müssen diese immer zusammen überladen werden.
```csharp
public class Complex
{
    // ... (andere Mitglieder der Klasse)

    // Überladen des == Operators
    public static bool operator ==(Complex c1, Complex c2)
    {
        return c1.Real == c2.Real && c1.Imaginary == c2.Imaginary;
    }

    // Überladen des != Operators
    public static bool operator !=(Complex c1, Complex c2)
    {
        return !(c1 == c2);
    }

    public override bool Equals(object obj)
    {
        if (obj is Complex)
        {
            Complex c = (Complex)obj;
            return this == c;
        }
        return false;
    }

    public override int GetHashCode()
    {
        return Real.GetHashCode() ^ Imaginary.GetHashCode();
    }
}
```

## Einschränkungen bei der Operatorüberladung

- Nicht alle Operatoren können überladen werden. Beispielsweise können die Bedingungsoperatoren (`&&` und `||`) nicht direkt überladen werden.
- Man kann keine neuen Operatoren erstellen, sondern nur vorhandene Operatoren überladen.
- Überladene Operatoren sollten sinnvoll und intuitiv sein, um den Code lesbar und wartbar zu halten.