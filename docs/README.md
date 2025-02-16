# 🌟 Tinf2023-LessonSummaries

Dies ist ein Obsidian Vault für das Semester Tinf2023 an der DHBW Heidenheim. Dieser Vault dient dazu, die im Unterricht vermittelten Informationen ordentlich und strukturiert zusammenzufassen. Er unterstützt alle beim Lernen und bietet eine Wissensdatenbank zum Nachschlagen. Ziel ist es, das OneNote-Notizbuch zu ersetzen. Der Vault wird über GitHub synchronisiert, um Kosten zu sparen und Versionskontrolle sowie Branches zu ermöglichen.

# 👨‍💼 Admins

- Manuel
  (Noch in Arbeit)

# 📂 Regeln für einzelne Ordner und Notizen

Erstellte Ordner und Notizen sollten, falls vorhanden, mit passenden Icons versehen werden. Es ist auch möglich, ein Custom Icon Pack hinzuzufügen, um Icons aus dem Internet zu verwenden.

# ✍️ Wie kann man beitragen?

Für jede Zusammenfassung sollte ein eigener Branch erstellt werden. Der Name des Branches sollte das Fach und die jeweilige Überschrift der Zusammenfassung enthalten. Bei anderen Änderungen, wie dem Hinzufügen von Plugins, sollte der Name ebenfalls sinnvoll formuliert werden.

Sobald eine Zusammenfassung oder andere Änderung im Branch des jeweiligen Benutzers vorliegt und diese für alle zur Verfügung gestellt werden soll, muss ein Pull-Request erstellt werden. Bitte immer nur pro Stoffabschnitt einen Pull-Request stellen.

Die Pull-Requests werden von den Admins überprüft, um sicherzustellen, dass alle notwendigen Informationen in der Zusammenfassung enthalten sind und dass alle Zusammenfassungen ähnlich aufgebaut sind. Falls alles passt, wird der Pull-Request genehmigt.

# 🔌 Plugins

Um die Arbeit zu erleichtern, wurden einige nützliche Plugins in den Vault hinzugefügt, die nachfolgend erklärt werden.

## 💻 Code Emitter

[Code Emitter](https://github.com/mokeyish/obsidian-code-emitter) ermöglicht es, auf jeder Plattform Code-Schnipsel auszuführen, indem der Code an externe Compiler gesendet wird.

Beispiel C:
```cpp
#include <stdio.h>

void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int main() {
    int numbers[] = {10, 20, 30, 40, 50, 60};
    int size = sizeof(numbers) / sizeof(numbers[0]);
    printArray(numbers, size);
    return 0;
}
```

## 🗂 Folder Notes

Dieses Plugin ermöglicht es, für Ordner eigene Notizen anzulegen. Dies ist möglich, indem man mit einem Rechtsklick auf den Ordner → Folder Notes Command → Create Markdown Folder Note wählt.

## 🖼 Iconize

Ermöglicht es, Ordnern oder Notizen individuelle Icons hinzuzufügen.

## 🔍 Omnisearch

Bietet eine verbesserte Suche.

## 🧮 Quick LaTeX

[Quick LaTeX](https://github.com/joeyuping/quick_latex_obsidian) ermöglicht es, mathematische Formeln in LaTeX zu schreiben.

## 📊 TikZ Jax

[TikZ Jax](https://github.com/artisticat1/obsidian-tikzjax) ist ein Plugin, das es ermöglicht, LaTeX-Figuren in Obsidian zu erstellen.

## 📅 Full Calendar

Full Calendar ist ein Plugin, das es ermöglicht, iCal-Kalender einzubinden. Zum aktuellen Zeitpunkt sind die Zeiten jedoch noch etwas ungenau.

## 📈 Timeline

Timeline ist ein Plugin, um eine Zeitleiste zu erstellen, beispielsweise hier: [[2. C, wie alles begann]]

