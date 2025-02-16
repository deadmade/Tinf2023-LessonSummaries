Superglobals in PHP sind spezielle globale Variablen, die in allen Gültigkeitsbereichen eines Skripts verfügbar sind. Sie bieten Zugriff auf verschiedene Arten von Daten, die oft im Kontext von Webanwendungen verwendet werden. Hier ist eine Übersicht der wichtigsten Superglobals in PHP:

## $GLOBALS

`$GLOBALS` ist ein Array, das alle Variablen im globalen Gültigkeitsbereich referenziert. Seit PHP 8.1.0 ist `$GLOBALS` schreibgeschützt.

>[!example]- Verwendung von `$GLOBALS`**
> ```php
> $foo = "123";
> function f() {
>     $bar = "456";
> }
> print_r($GLOBALS);
> // Ausgabe enthält $foo, aber nicht $bar
> ```

## $_SERVER

`$_SERVER` enthält Informationen über den Server und die Ausführungsumgebung. Diese Einträge werden vom Webserver erstellt und enthalten Details wie Header, Pfade und mehr.

>[!example]- Verwendung von `$_SERVER`**
> ```php
> // Beispiel-URL: http://example.com/seite.php?foo=bar
> echo $_SERVER["QUERY_STRING"]; // Ausgabe: foo=bar
> ```

## $_GET

`$_GET` ist ein Array, das alle GET-Parameter enthält. Du kannst auf die Werte mit `$_GET["parameter"]` zugreifen und überprüfen, ob ein Parameter gesetzt ist, indem du `isset($_GET["parameter"])` verwendest.

>[!example]- Verwendung von `$_GET`
> ```php
> if (isset($_GET["foo"])) {
>     echo "foo = " . $_GET["foo"];
> }
> ```

## $_POST

`$_POST` enthält Variablen, die per POST-Methode an den Server gesendet wurden. Diese Methode wird häufig für Formulare verwendet, bei denen Daten entweder als `application/x-www-form-urlencoded` oder `multipart/form-data` gesendet werden.

> [!example]- Verwendung von `$_POST`**
> ```php
> // Beispiel-Formular zur Datei-Upload
> // <form action="upload.php" method="post" enctype="multipart/form-data">
> // Select image to upload:
> // <input type="file" name="fileToUpload" id="fileToUpload">
> // <input type="submit" value="Upload Image" name="submit">
> // </form>
> ```

## $_COOKIE

`$_COOKIE` enthält die gesetzten Cookies. Cookies sind kleine Dateien, die vom Client gespeichert werden und bei jedem Besuch der Webseite wieder mitgeschickt werden. Sie werden oft zur Identifikation von Nutzern verwendet.

>[!example]- Verwendung von `$_COOKIE`**
> ```php
> // Setzen eines Cookies
> setcookie("user", "John Doe", time() + 3600); // Cookie läuft in 1 Stunde ab
> ```

## $_REQUEST

`$_REQUEST` enthält alle Daten von `$_GET`, `$_POST` und `$_COOKIE`. Es vereinfacht den Zugriff auf alle Anfragedaten.

>[!example]- Verwendung von `$_REQUEST`**
> ```php
> echo $_REQUEST["user"]; // Gibt den Wert des Parameters "user" aus, egal ob er über GET, POST oder COOKIE gesendet wurde
> ```

## $_SESSION

`$_SESSION` enthält alle Session-Variablen, die während der Sitzung des Nutzers verfügbar sind. Sessions speichern Daten auf dem Server und sind nützlich, um Informationen wie den Inhalt eines Warenkorbs oder Login-Status zu verwalten.

>[!example]- Verwendung von `$_SESSION`**
> ```php
> session_start();
> $_SESSION["cart"] = array("item1", "item2");
> ```

## $_FILES

`$_FILES` enthält Informationen über Dateien, die per POST-Methoden hochgeladen wurden. Die Datei-Uploads müssen in der `php.ini` aktiviert sein.

>[!example]- Verwendung von `$_FILES`**
> ```php
> // Beispiel-HTML-Formular für Datei-Upload
> <form action="upload.php" method="post" enctype="multipart/form-data">
> // Select image to upload:
>  <input type="file" name="fileToUpload" id="fileToUpload">
> <input type="submit" value="Upload Image" name="submit">
> </form>
> ```


