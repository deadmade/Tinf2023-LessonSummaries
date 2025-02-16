![[Pasted image 20240803084203.png]]

## **Anfrage vom Client**:
Der Client, typischerweise ein Webbrowser, sendet eine Anfrage für eine PHP-Datei (z.B. `beispiel.php`) an den Webserver. Dies wird durch den ersten Schritt im Bild dargestellt.

## **Webserver lädt Datei von der Server-Festplatte**:
Der Webserver empfängt die Anfrage und lädt die angeforderte PHP-Datei von der Festplatte des Servers. Dieser Vorgang ist im Bild als Schritt 2 markiert.

## **Übergabe der Datei**:
Die geladene PHP-Datei wird an den PHP-Interpreter übergeben, der für die Ausführung von PHP-Skripten verantwortlich ist. Dies ist Schritt 3 im Bild.

## **PHP-Interpreter erzeugt Datei**:
Der PHP-Interpreter führt das PHP-Skript aus. Dabei wird je nach Skript eine Ausgabe generiert, die meist im HTML-Format vorliegt, aber auch andere Formate wie PDF sein können. Dies ist Schritt 4 im Bild.

## **Rückgabe des erzeugten Codes**:
Der vom PHP-Interpreter erzeugte Code wird zurück an den Webserver gegeben. Dies ist Schritt 5 im Bild.

## **Antwort an den Client**:
Der Webserver sendet die erzeugte Ausgabe (z.B. HTML, PDF) über das Internet zurück an den Client. Dies ist Schritt 6 im Bild.