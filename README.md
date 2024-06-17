# 🌟 Tinf2023-LessonSummaries
Dies ist ein Obsidian Vault des Semesters Tinf2023 an der DHBW Heidenheim. Dieser Vault dient dazu, die im Unterricht erhaltenen Informationen für alle aus unserem Semester ordentlich und strukturiert zusammenzufassen, um jeden beim Lernen zu unterstützen sowie eine Wissensdatenbank zum Nachschlagen bereitzustellen. Er soll das OneNote-Notizbuch ablösen. Der Vault wird über GitHub synchronisiert, um Kosten zu sparen und eine Versionskontrolle sowie Branches zu bieten.

# 👨‍💼 Admins 
- Manuel 
  (Noch in Arbeit)

# 📂 Regeln für einzelne Ordner bzw. Notes
Die einzelnen Ordner und Notes, die erstellt wurden, sollten, wenn es ein passendes Icon gibt, mit einem solchen versehen werden. Es ist auch möglich, ein Custom Icon Pack hinzuzufügen, um Icons aus dem Internet zu verwenden.

# ✍️ Wie kann man beitragen?
Jeder Benutzer hat seinen eigenen Branch, in dem er Zusammenfassungen erstellen kann. Jeder Branch sollte den Namen des Benutzers tragen, z.B. für mich: ManuelSchülein, um eine bessere Identifikation zu ermöglichen. 

Sobald eine Zusammenfassung oder andere Änderung im Branch des jeweiligen Benutzers vorliegt und diese für alle zur Verfügung gestellt werden soll, muss ein Pull-Request erstellt werden. In diesem muss das Fach und der behandelte Stoff eingetragen werden. Bitte immer nur pro Stoffabschnitt einen Pull-Request stellen. 

Die Pull-Requests werden dann von den Admins überprüft, um sicherzustellen, dass alles Notwendige in der Zusammenfassung steht und um es zu ermöglichen, dass alle Zusammenfassungen ähnlich aufgebaut sind. Falls alles passt, wird der Pull-Request genehmigt und alle anderen können die Zusammenfassung in ihre Branches mergen.

# 🔌 Plugins
Um die Arbeit zu erleichtern, wurden einige nützliche Plugins in den Vault hinzugefügt, welche nachfolgend erklärt werden.

## 💻 Code Emitter
[Code Emitter](https://github.com/mokeyish/obsidian-code-emitter) ermöglicht es, auf jeder Plattform Code-Schnipsel auszuführen. Dies wird ermöglicht, indem der Code an externe Compiler gesendet wird.

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

Dieses Plugin ermöglicht es, für Ordner auch ein eigenes Note anzulegen. Dies ist möglich, indem man Rechtsklick auf den Ordner → Folder Notes Command → Create Markdown Folder Note wählt.

## 🖼 Iconize

Ermöglicht es, Ordnern oder Notes individuelle Icons hinzuzufügen.

## 🔍 Omnisearch

Bietet eine verbesserte Suche.

## 🧮 Quick LaTeX

[Quick LaTeX](https://github.com/joeyuping/quick_latex_obsidian) ermöglicht es, mathematisches LaTeX zu schreiben.

## 📊 TikZ Jax

[TikZ Jax](https://github.com/artisticat1/obsidian-tikzjax) ist ein Plugin, das es ermöglicht, LaTeX-Figuren in Obsidian zu erstellen.
