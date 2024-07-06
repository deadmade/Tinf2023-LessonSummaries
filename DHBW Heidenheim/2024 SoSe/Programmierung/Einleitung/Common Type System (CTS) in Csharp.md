## 📘 Einführung

Das **Common Type System (CTS)** ist ein grundlegender Bestandteil der .NET-Architektur, das sicherstellt, dass in verschiedenen .NET-Sprachen definierte und verwendete Datentypen miteinander kompatibel sind. Es definiert eine Reihe von Datentypen und Regeln für die Arbeit mit diesen Typen, um Interoperabilität und Sicherheit zu gewährleisten.

## 🛡️ Regeln und Konzepte des CTS

Das CTS definiert mehrere Regeln und Konzepte, die die Verwendung von Datentypen standardisieren:

1. **Typensicherheit**: Das CTS sorgt dafür, dass Operationen nur auf kompatiblen Datentypen ausgeführt werden, was Laufzeitfehler verhindert.
2. **Vererbung**: Referenztypen können von anderen Typen erben und deren Mitglieder verwenden.
3. **Boxing und Unboxing**: Werttypen können in Referenztypen umgewandelt werden (Boxing) und wieder zurück (Unboxing).
4. **Gemeinsame Typenbibliothek (Base Class Library, BCL)**: Eine Sammlung vordefinierter Klassen und Typen, die alle .NET-Sprachen nutzen können.

## 🔄 Beispiele für Boxing und Unboxing

Boxing wandelt einen Werttyp in einen Referenztyp um:
```csharp
int number = 123;
object boxedNumber = number; // Boxing
```

Unboxing wandelt einen Referenztyp wieder in einen Werttyp um:
```csharp
object boxedNumber = 123;
int number = (int)boxedNumber; // Unboxing
```

## 🌍 Interoperabilität zwischen .NET-Sprachen

Durch das CTS können verschiedene .NET-Sprachen (z.B. C#, VB.NET, F#) nahtlos miteinander arbeiten, da alle Sprachen die gleichen Typen und Regeln verwenden. Dies ermöglicht die Verwendung von Bibliotheken und Modulen, die in einer Sprache geschrieben wurden, in einer anderen Sprache.