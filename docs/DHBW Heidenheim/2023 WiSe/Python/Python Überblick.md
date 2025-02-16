## 🚀 Mein Erstes Projekt

In Python werden Codezeilen **nicht** mit `;` beendet. Mithilfe der `print()`-Funktion können Werte ausgegeben werden.

→ Das folgende Programm gibt _Hello World_ auf die Konsole aus:

```python
print("Hello World")`
```

## 🧮 Variablen

Datentypen werden nicht explizit angegeben, sondern dynamisch bestimmt. Diese Eigenschaft in Programmiersprachen wird als _dynamically typed_ bezeichnet.

Mithilfe der `type(x)`-Funktion kann der Typ einer Variable `x` bestimmt werden:


```python
# Integer
x = 42  
print(type(x))

# String
y = "DHBW Heidenheim"  
print(type(y))

# Boolean
z = True
print(type(z))

```

Der Typ einer Variable kann sich zur Laufzeit ändern:

```python
# Integer
x = 42
print(type(x))
  
# String
x = "DHBW Heidenheim"
print(type(x))
```

In bestimmten Situationen möchten wir aber den Typ einer Variable explizit ändern. Hier kommen **Cast-Operationen** ins Spiel:

```python
# Integer 42
x = 42
print(type(x))  

# Cast von Integer 42 zu String "42"
y = str(x)
print(type(y))
```

Eine solche Situation ist beispielsweise das Einlesen von Werten. Hierfür kann in Python die `input()`-Funktion verwendet werden. Diese liest Werte aber immer als Typ `str` ein:

```python
inputA = input("Gebe Zahl 1 ein")
inputB = input("Gebe Zahl 2 ein")

print(int(inputA) * int(inputB))
```

Es ist nicht ungewöhnlich, dass Funktionen auch kein Ergebnis liefern können oder sollen. Für solche Fälle gibt es `None` sowie den dazugehörigen Typ `NoneType`. `None` wird verwendet, um die Abwesenheit eines Wertes zu zeigen.

In anderen Programmiersprachen werden ähnliche Konzepte oft mit _Null_ abgebildet:

```python
result = print("Hello World")
print(result)
```

## ➕ Operatoren

[Liste der Python Operatoren](https://www.w3schools.com/python/python_operators.asp)

Obwohl Python _dynamically typed_ ist, werden zur Laufzeit trotzdem Typüberprüfungen durchgeführt. So können einige Operationen nicht auf unverträglichen Typen durchgeführt werden.

❗ Der folgende Code ist ein solches Beispiel und wirft einen `TypeError`:

```python
zahl = 42
text = "Hallo" 

ergebnis = zahl + text  # Dies führt zu einem TypeError
```

In Python haben **logische Operatoren** eine andere Syntax als in vielen populären Programmiersprachen:

||Logisches Und|Logisches Oder|Invertierung|
|---|---|---|---|
|Python|`and`|`or`|`not`|
|C#, Java, JavaScript, uvm.|`&&`|`||

```python
def truth_table_or():
    print("A     | B     | A OR B")
    print("----------------------")
    for A in [True, False]:
        for B in [True, False]:
            result = A or B
            print(f"{A:<5} | {B:<5} | {result}")

def truth_table_and():
    print("A     | B     | A AND B")
    print("-----------------------")
    for A in [True, False]:
        for B in [True, False]:
            result = A and B
            print(f"{A:<5} | {B:<5} | {result}")

def truth_table_not():
    print("A     | NOT A")
    print("----------------")
    for A in [True, False]:
        result = not A
        print(f"{A:<5} | {result}")

print("Truth Table for OR:")
truth_table_or()
print()

print("\nTruth Table for AND:")
truth_table_and()
print()

print("\nTruth Table for NOT:")
truth_table_not()
```

### 🔍 Identitätsoperatoren

**Identitätsoperatoren** prüfen, ob zwei Objekte tatsächlich dasselbe Objekt (dasselbe im Speicher) sind. Diese Operatoren sind `is` und `is not`.

⚠ **_Hinweis:_** Die Operatoren `is` und `==` sind unterschiedlich. `is` vergleicht, ob zwei Objekte dasselbe im Speicher sind, `==` vergleicht, ob der Wert der Objekte identisch ist.

```python
a = 1234
b = 12345
c = a  

print(a is c)
print(a is b)
print(b is not c)
```

❗ Im folgenden Beispiel wird der `is`-Operator falsch eingesetzt. Er sollte **nicht** zum Vergleich von Werten eingesetzt werden:

```python
x = 10  
y = 10

print(x == y)
print(y is x)
```

## 📋 Listen

⚠ **_Hinweis:_** Python hat kein _Array_ als _built-in_ Datenstruktur. Listen werden deswegen oft ähnlich wie Arrays aus anderen Programmiersprachen verwendet.

Mithilfe der `len(x)`-Funktion kann die Anzahl von Elementen in einer Liste `x` bestimmt werden:

```python
fruits = ["apple", "banana", "cherry"]  

# Indizierung startet bei 0
print(fruits[0])
print(fruits[2])
print(len(fruits))
```

```python
fruits = ["apple", "banana", "cherry"]  

fruits.append("peach")
fruits.remove("apple")  

print(fruits)
```

```python
fruits = ["apple", "banana", "cherry"]

fruits.append("peach")
fruits.append("peach") 

print(fruits.count("peach"))
```
## 🔄 Schleifen

`continue` bricht die aktuelle Iteration ab, `break` bricht die gesamte Schleife ab:

```python
i = 0
while i < 10:
    i += 1
    
    if i == 2:
        continue

    if i == 8:
        break
    
    print(i)
```

Eine `for`-Schleife kann in Kombination mit einem Mitgliedsoperator über eine Liste iterieren. Mithilfe der `range`-Funktion kann auch eine "zählende" `for`-Schleife realisiert werden:

```python
# Iteration über Einträge einer Liste
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
  print(fruit)

print()

# Numerisches Zählen mit Range
for x in range(2, 6, 1):
  print(x)
```

## 🔧 Funktionen

```python
def add(x, y):
    sum = x + y
    return sum

result = add(2,5)
result = add(y=2, x=5)

print(result)
```

Funktionen müssen definiert werden, **bevor** diese aufgerufen werden. Wenn nicht, wird ein Fehler ausgelöst:

```python
result = add(2,5)
print(result)
def add(x, y):
    sum = x + y
    return sum

```