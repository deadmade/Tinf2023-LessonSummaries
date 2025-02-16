# PHP Datentypen

| Datentyp    | Bezeichnung      | Beispiel                           |
|-------------|------------------|------------------------------------|
| `int`       | Ganzzahl         | `123`, `-456`, `0`                 |
| `float`     | Gleitkommazahl   | `1.23`, `-4.56`, `0.0`             |
| `string`    | Zeichenkette     | `"Hallo Welt"`, `'PHP'`, `""`      |
| `bool`      | Boolean          | `true`, `false`                    |
| `array`     | Array            | `[1, 2, 3]`, `["a", "b", "c"]`     |
| `object`    | Objekt           | `$obj = new Klasse()`              |
| `NULL`      | Null-Wert        | `NULL`                             |
| `resource`  | Ressource        | `fopen("datei.txt", "r")`          |
| `callable`  | Aufrufbar        | `function() { return true; }`      |
| `iterable`  | Iterierbar       | `array`, `Traversable`             |

## Beispiele

> [!example]- Ganzzahl (`int`)
> ```php
> <?php
> $zahl = 123;
> echo $zahl; // Ausgabe: 123
> ?>
> ```

> [!example]- Gleitkommazahl (`float`)
> ```php
> <?php
> $kommazahl = 1.23;
> echo $kommazahl; // Ausgabe: 1.23
> ?>
> ```

> [!example]- Zeichenkette (`string`)
> ```php
> <?php
> $text = "Hallo Welt";
> echo $text; // Ausgabe: Hallo Welt
> ?>
> ```

> [!example]- Boolean (`bool`)
> ```php
> <?php
> $wahr = true;
> echo $wahr; // Ausgabe: 1
> ?>
> ```

> [!example]- Array (`array`)
> ```php
> <?php
> $liste = array(1, 2, 3);
> print_r($liste); // Ausgabe: Array ( [0] => 1 [1] => 2 [2] => 3 )
> ?>
> ```

> [!example]- Objekt (`object`)
> ```php
> <?php
> class Klasse {
>     public $eigenschaft = "Wert";
> }
> $obj = new Klasse();
> echo $obj->eigenschaft; // Ausgabe: Wert
> ?>
> ```

> [!example]- Null-Wert (`NULL`)
> ```php
> <?php
> $leer = NULL;
> var_dump($leer); // Ausgabe: NULL
> ?>
> ```

> [!example]- Ressource (`resource`)
> ```php
> <?php
> $datei = fopen("datei.txt", "r");
> var_dump($datei); // Ausgabe: resource(3) of type (stream)
> ?>
> ```

> [!example]- Aufrufbar (`callable`)
> ```php
> <?php
> function meineFunktion() {
>     return true;
> }
> $aufrufbar = 'meineFunktion';
> echo $aufrufbar(); // Ausgabe: 1
> ?>
> ```

> [!example]- Iterierbar (`iterable`)
> ```php
> <?php
> function generator() {
>     yield 1;
>     yield 2;
>     yield 3;
> }
> $iterierbar = generator();
> foreach ($iterierbar as $wert) {
>     echo $wert; // Ausgabe: 1 2 3
> }
> ?>
> ```

