## 📘 Einführung

**.NET MAUI** steht für ".NET Multi-platform App UI" und ist ein modernes UI-Framework von Microsoft. Es ermöglicht Entwicklern, plattformübergreifende Anwendungen für verschiedene Zielplattformen wie Windows, macOS, iOS, Android und Web zu erstellen.

![[Pasted image 20240706080729.png]]

## 🛠️ Hauptmerkmale von .NET MAUI

1. **Einheitliche Codebasis**: Erhöht die Entwicklungseffizienz durch die gemeinsame Nutzung des Großteils des Codes für alle unterstützten Plattformen.
2. **Native Benutzeroberflächen**: Ermöglicht die Erstellung nativer Benutzeroberflächen, die sich nahtlos in die spezifischen Betriebssysteme einfügen.
3. **XAML-basierte UI-Entwicklung**: Erstellung der Benutzeroberfläche (UI) über XAML, kombiniert mit C# zur Steuerung der Logik.
4. **Erweiterbarkeit und Anpassbarkeit**: Integration vorhandener nativer Funktionen und Bibliotheken in .NET MAUI-Anwendungen.
5. **Unterstützung für mobile und Desktop-Plattformen**: Entwicklung von Anwendungen für iOS, Android, Windows und macOS.

## ⚙️ Technische Details

### Projektstruktur

Ein .NET MAUI-Projekt besteht aus:
- Einem **Hauptprojekt** für die gemeinsame Logik und Benutzeroberfläche.
- **Spezifischen Projekten** für jede Zielplattform zur plattformspezifischen Anpassung und Konfiguration.

### Plattformintegration

- **Plattformspezifische APIs und Ressourcen** können direkt über Dependency Injection und Schnittstellen genutzt werden.

### Entwicklungsumgebung

- Visual Studio 2022
- Visual Studio Code

## 💡 Beispiel

Ein einfaches Beispiel für eine .NET MAUI-Anwendung:

```csharp
using Microsoft.Maui;
using Microsoft.Maui.Controls;

public partial class App : Application
{
    public App()
    {
        InitializeComponent();

        MainPage = new MainPage();
    }
}

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        var label = new Label
        {
            Text = "Hello, Maui!",
            HorizontalOptions = LayoutOptions.Center,
            VerticalOptions = LayoutOptions.Center
        };

        Content = new StackLayout
        {
            Children = { label }
        };
    }
}
```

