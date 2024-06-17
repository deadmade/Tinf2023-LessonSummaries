# Tinf2023-LessonSummaries
Dies ist ein Obsidian Vault des Semesters Tinf2023 an der DHBW Heidenheim. Dieser Vault dient dazu, die im Unterricht erhaltenen Informationen für alle aus unserem Semester ordentlich und Strukturiert zusammenzufassen um jeden beim lernen zu unterstützen sowie eine Wissensdatenbank zum nachschlagen bereit zu stellen. Er soll das OneNote Notizbuch ablösen. Synchronisiert werden soll der Vault über GitHub um kosten zu sparen und eine Versionskontrolle sowie Branches bieten.

# Admins
- Manuel 
- Renè

# Regeln für einzelne Ordner bzw. Notes
Die einzelnen Ornder und Notes welche erstellt wurden, sollten wenn es ein Passendes Icon gibt, mit einem Versehen werden. Es ist auch möglich ein Custom Icon Pack hinzuzufügen um selbst Icons aus dem Internet zu verwenden.

# Wie kann man beitragen?


# Plugins
Um die Arbeit zu erleichtern wurden einige Nützliche Plugins in den Vault hinzugefügt welche Nachfolgend erklärt werden.
- [Code Emitter](https://github.com/mokeyish/obsidian-code-emitter)
- Folder notes
- Iconize
- Minimal Theme Settings
- Omnisearch
- [Quick Latex](https://github.com/joeyuping/quick_latex_obsidian)
- [TikZ Jax](https://github.com/artisticat1/obsidian-tikzjax)

## Code Emitter
Mithilfe von Code Emitter ist es möglich auf jeder Plattform Code Schnipsel auszuführen.  Dies wird ermöglicht, indem der Code an Externe Compiler gesendet wird.
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

## Folder Notes
Dieser Plugin ermöglicht es, für Ordner auch ein eigenes Note anzulegen. Dies ist möglich, indem Rechtsklick auf Folder → Folder Notes Command → Create Markdown Folder Note

## Iconize
Ermöglicht es Ordnern oder Notes individuelle Icons hinzuzufügen

## Omnisreach
Bietet eine Verbesserte Suche

## Quick Latex
Ermöglicht es Mathematisches Latex zu schreiben

## TIKZ Jax
Es ist ein Plugin, welches ermöglicht Latex Figuren in Obisidan zu erstellen