![[Pasted image 20240704111230.png]]
## 📝 Allgemeine Beschreibung 

Das .NET-Framework ist eine Entwicklungsplattform von Microsoft, die es Entwicklern ermöglicht, Anwendungen für Windows zu erstellen und auszuführen. Es unterstützt mehrere Programmiersprachen und bietet eine einheitliche Laufzeitumgebung. Im Bild werden die verschiedenen Ebenen der .NET-Architektur sowie deren Entsprechungen auf Mac- und Linux-Systemen mittels Mono-Framework dargestellt.

## 🧩 Komponenten und Beschreibung

1. **Programmiersprachen und IL-Codes**
    - **C#, J#, VB**: Dies sind Beispiele für .NET-Programmiersprachen, die zur Erstellung von Anwendungen verwendet werden können.
    - **IL-Codes**: IL (Intermediate Language) ist der Zwischencode, in den .NET-Programme kompiliert werden, bevor sie auf der CLR ausgeführt werden.

2. **Mono**
    - **Mono Class Library (<.NET6)**: Eine Open-Source-Implementierung der .NET-Framework-Klassenbibliothek, die auf mehreren Betriebssystemen läuft.
    - **Mono Runtime**: Die Laufzeitumgebung, die es ermöglicht, .NET-Anwendungen auf nicht-Windows-Plattformen (z.B. Linux, macOS) auszuführen.

3. **Common Language Runtime (CLR)**
    - Dies ist die Laufzeitumgebung von .NET, die IL-Codes ausführt. Sie bietet Dienste wie Speicherverwaltung, Sicherheit und Ausnahmebehandlung.

4. **Framework Class Library (FCL) / Base Class Library (BCL)**
    - Die Basisklassenbibliothek bietet eine Vielzahl von grundlegenden Klassen und Methoden, die für die Entwicklung von .NET-Anwendungen benötigt werden.

5. **Common Intermediate Language (CIL)**
    - Auch bekannt als Microsoft Intermediate Language (MSIL). Es handelt sich um einen plattformunabhängigen Zwischencode, in den .NET-Sprachen kompiliert werden.

6. **Common Language Specification (CLS)**
    - Eine Menge von Regeln und Best Practices, die sicherstellen, dass verschiedene .NET-Sprachen miteinander interoperabel sind.

7. **Betriebssysteme und Hardware**
    - **Windows OS**: Das Betriebssystem, auf dem das .NET-Framework hauptsächlich ausgeführt wird.
    - **Mac**: Zeigt die Unterstützung von Mono für MacOS an.
    - **Linux**: Zeigt die Unterstützung von Mono für Linux an.
    - **Hardware**: Die physische Ebene, auf der das Betriebssystem läuft.

## 💡 Zusätzliche Informationen

- **Portabilität und Interoperabilität**: 
  - Durch die Verwendung von IL und CLR ist es möglich, .NET-Anwendungen auf verschiedenen Plattformen auszuführen, ohne den Quellcode zu ändern. Dies wird durch das Mono-Framework noch erweitert, das die Ausführung auf anderen Betriebssystemen ermöglicht.

- **Leistung und Sicherheit**: 
  - CLR bietet eine optimierte Laufzeitumgebung, die sowohl die Leistung der Anwendung als auch die Sicherheit durch Funktionen wie Garbage Collection und Code Access Security verbessert.

- **Framework-Erweiterungen**: 
  - Das .NET-Framework wird kontinuierlich erweitert und aktualisiert. Mit .NET Core und später .NET 5/6 wurden viele Verbesserungen und neue Funktionen eingeführt, die Cross-Platform-Kompatibilität weiter verbessern.

- **Entwicklungstools**: 
  - Visual Studio ist die integrierte Entwicklungsumgebung (IDE) von Microsoft, die umfassende Unterstützung für die .NET-Entwicklung bietet, einschließlich Debugging, Refactoring und Performance-Analyse.
