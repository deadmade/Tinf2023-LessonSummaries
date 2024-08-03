
```php
<!DOCTYPE html>
<html>
<head>
    <title>Hello World</title>
</head>
<body>
    <?php
    $randomAge = rand(0,40);  // Generiert eine Zufallszahl zwischen 0 und 40
    echo "Zufallsalter: $randomAge <br>";  // Gibt das Zufallsalter aus
    if($randomAge==1) {
        echo "Baby";  // Wenn das Alter 1 ist, wird "Baby" ausgegeben
    }
    elseif ($randomAge<10) {
        echo "Kind";  // Wenn das Alter kleiner als 10 ist, wird "Kind" ausgegeben
    }
    elseif ($randomAge<=20) {
        echo "Teenager";  // Wenn das Alter kleiner oder gleich 20 ist, wird "Teenager" ausgegeben
    }
    else {
        echo "Erwachsener";  // Für alle anderen Fälle wird "Erwachsener" ausgegeben
    }
    ?>
</body>
</html>

```