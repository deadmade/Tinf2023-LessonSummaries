## Integration in HTML

PHP-Code kann an jeder Stelle innerhalb einer HTML-Seite eingefügt werden. Dies ermöglicht eine nahtlose Mischung von HTML und PHP, wodurch dynamische Inhalte direkt in statische Webseiten eingebettet werden können.

## Spezielle Tags

PHP verwendet spezielle Tags, um PHP-Code von regulärem HTML-Code zu unterscheiden. Diese Tags werden vom PHP-Interpreter erkannt und der darin enthaltene Code wird ausgeführt. Die Ergebnisse der Ausführung werden in Text oder HTML umgewandelt und an den Browser gesendet.

### Beispiele für PHP-Tags

- `<?php ... ?>`: Dies ist der am häufigsten verwendete Tag für PHP-Code.
- `<? ... ?>`: Eine kürzere Schreibweise für PHP-Code.
- `<% ... %>`: Eine alternative Schreibweise, die jedoch weniger verbreitet ist.

### Beispiel:

```php
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Beispielseite</title>
</head>
<body>
    <h1>Willkommen auf meiner Webseite!</h1>
    <?php
        echo "<p>Dies ist ein dynamisch erzeugter Absatz.</p>";
    ?>
</body>
</html>
```
