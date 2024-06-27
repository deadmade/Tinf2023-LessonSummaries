## 🚀 Aufgabe 1: Schaltjahr prüfen

Schreiben Sie ein Programm, das eine Benutzereingabe einliest und prüft, ob es sich um ein Schaltjahr handelt.

**Ein Jahr ist ein Schaltjahr, wenn es den folgenden Bedingungen entspricht:**

- Teilbarkeit durch 4: Ein Jahr muss durch 4 teilbar sein, um ein Schaltjahr zu sein.
- Ausnahme: Teilbarkeit durch 100: Wenn ein Jahr durch 100 teilbar ist, ist es kein Schaltjahr, es sei denn, es erfüllt auch die nächste Bedingung.
- Teilbarkeit durch 400: Wenn ein Jahr durch 400 teilbar ist, ist es trotz der Teilbarkeit durch 100 ein Schaltjahr.

>[!example]- Beispiel 
>2000 und 2020 sind Schaltjahre. 1900 und 2022 sind keine Schaltjahre.

>[!tipp]- **Tipp:**
> Der Modulo-Operator `%` berechnet den Rest der Division zwischen zwei Zahlen. Ist der Rest 0, so ist der Dividend durch den Divisor restlos teilbar.

```python
inputNumber = 2024
inputInt = int(inputNumber)
if inputInt % 100 == 0 and inputInt % 400 != 0:
    print("Kein Schaltjahr")
elif inputInt % 400 == 0:
    print("Ist ein Schaltjahr")
elif inputInt %4 == 0:   
    print("Ist ein Schaltjahr")
else:
    print("Kein Schaltjahr")
```

## 🧮 Aufgabe 2: Summe der geraden Zahlen
Schreiben Sie ein Programm, das alle geraden Zahlen bis zur Zahl 100 aufsummiert.

```python
count = 0
for x in range(1, 101, 1):
    if x % 2 == 0:
        count += x
    
print(count)
```

## 🔤 Aufgabe 3: Vokale zählen
Schreiben Sie eine Funktion `countVowel`, die alle Vokale in einem String zählt und geben Sie die Anzahl zurück.

```python
stringDing = "Ich maaaaaaag eeeeeuch oooooder uuUUuuuns"
vocals = ["a", "e", "i", "o", "u"]
for vocal in vocals:
    lowerCase = stringDing.count(vocal)
    upperCase = stringDing.count(vocal.upper())
    print(lowerCase + upperCase)
```

## 🧮 Aufgabe 4: Einfacher Taschenrechner
Entwickeln Sie einen einfachen Taschenrechner, der zwei Zahlen vom Benutzer sowie eine der vier Grundrechenarten (Addition, Subtraktion, Multiplikation, Division) einliest, die Rechnung durchführt und das Ergebnis ausgibt.

```python
numberOne = 5
numerTwo = 5
calcualtor = "+"

numberOne = int(numberOne)
numerTwo = int(numerTwo)

if calcualtor == "+":
    print(numberOne + numerTwo)
elif calcualtor == "-":
    print(numberOne - numerTwo)
elif calcualtor == "*":
    print(numberOne * numerTwo)
elif calcualtor == "/":
    print(numberOne / numerTwo)
```

## 🌡️ Aufgabe 5: Temperaturumrechner
Schreiben Sie ein Programm, das die Temperatur von Celsius in Fahrenheit oder umgekehrt umrechnet. Der Benutzer sollte die Option haben, die Eingabeart (Celsius oder Fahrenheit) und die Temperatur einzugeben.

>[!Formeln]- Formeln
>- °C = (°F - 32) * 5/9 (von Fahrenheit in Celsius)
>-  °F = °C * 1,8 + 32 (von Celsius nach Fahrenheit)

```python
def celsius_to_fahrenheit(celsius):
    return celsius * 1.8 + 32 

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

print("Willkommen zum Temperaturumrechner!")
print("Geben Sie 1 ein, um von Celsius in Fahrenheit umzurechnen.")
print("Geben Sie 2 ein, um von Fahrenheit in Celsius umzurechnen.")
    
choice = "1"
    
if choice == '1':
    celsius = float(30)
    fahrenheit = celsius_to_fahrenheit(celsius)
    print(f"{celsius}°C entsprechen {fahrenheit}°F.")
elif choice == '2':
    fahrenheit = float(150)
    celsius = fahrenheit_to_celsius(fahrenheit)
    print(f"{fahrenheit}°F entsprechen {celsius}°C.")
else:
    print("Ungültige Eingabe. Bitte geben Sie 1 oder 2 ein.")
```

## 🔄 Aufgabe 6: Palindrom prüfen
Schreiben Sie eine Funktion, die prüft, ob ein String ein Palindrom ist. Ein Palindrom ist ein Text, der vorwärts und rückwärts gelesen dasselbe ergibt. Wenden Sie diese Funktion auf die Liste `words` an.

```python
def is_palindrome(s):
    # Entfernt Leerzeichen und macht den String kleinbuchstabig für eine genaue Überprüfung
    cleaned_string = ''.join(filter(str.isalnum, s)).lower()
    # Prüft, ob der bereinigte String ein Palindrom ist
    return cleaned_string == cleaned_string[::-1]

# Beispiel-Liste von Wörtern
words = ["Level", "Radar", "hello", "world", "madam", "racecar", "python"]

# Wendet die Funktion auf die Liste an und druckt die Ergebnisse
palindromes = [word for word in words if is_palindrome(word)]

print("Die Palindrome in der Liste sind:", palindromes)
```

## 🎲 Aufgabe 7: Zufallszahl raten
Schreiben Sie ein Python-Programm, das eine Zufallszahl zwischen 1 und 100 generiert. Der Benutzer soll dann die Möglichkeit haben, die Zahl zu erraten. Das Programm sollte den Benutzer über die Korrektheit seines Versuches informieren und ihm bei Bedarf Hinweise geben, ob die gesuchte Zahl größer oder kleiner ist.

```python
import random

def rate_die_zahl():
    # Schritt 1: Generiere eine Zufallszahl zwischen 1 und 100
    zufallszahl = random.randint(1, 100)
    
    # Initialisierung der Variablen
    geraten = False
    
    print("Willkommen zum Zahlenratespiel!")
    print("Ich habe eine Zahl zwischen 1 und 100 ausgewählt.")
    
    # Schritt 2 bis 6: Frage den Benutzer nach seiner Schätzung und gib Rückmeldungen
    while not geraten:
        tipp = int(input("Bitte geben Sie Ihre Schätzung ein: "))
        
        if tipp < zufallszahl:
            print("Die gesuchte Zahl ist größer als Ihre Schätzung.")
        elif tipp > zufallszahl:
            print("Die gesuchte Zahl ist kleiner als Ihre Schätzung.")
        else:
            geraten = True
            print("Herzlichen Glückwunsch! Sie haben die richtige Zahl erraten.")
            
# Aufruf der Funktion
rate_die_zahl()
```

## 🎮 Aufgabe 8: Hangman-Spiel
Implementieren Sie das Spiel "Hangman" (Galgenmännchen). Wählen Sie zufällig ein Wort aus der Liste und lassen Sie den Benutzer raten. Die Groß- und Kleinschreibung soll hierbei **keine** Rolle spielen. Nach 5 Fehlversuchen ist das Spiel vorbei.

```python
import random

def hangman():
    words = ['Python', 'Entwicklung', 'Programmierung', 'Galgenmännchen', 'Computer']
    word = random.choice(words).lower()
    word_display = ['_'] * len(word)
    attempts = 5
    guessed_letters = set()

    print("Willkommen zu Hangman!")
    
    while attempts > 0 and '_' in word_display:
        print("\nAktuelles Wort: " + ' '.join(word_display))
        print(f"Fehlversuche übrig: {attempts}")
        guess = input("Geben Sie einen Buchstaben ein: ").lower()

        if not guess.isalpha() or len(guess) != 1:
            print("Bitte geben Sie einen einzelnen Buchstaben ein.")
            continue
        
        if guess in guessed_letters:
            print("Sie haben diesen Buchstaben bereits geraten.")
            continue
        
        guessed_letters.add(guess)
        
        if guess in word:
            for i, letter in enumerate(word):
                if letter == guess:
                    word_display[i] = guess
            print(f"Richtig! '{guess}' ist im Wort.")
        else:
            attempts -= 1
            print(f"Falsch! '{guess}' ist nicht im Wort.")
        
    if '_' not in word_display:
        print("\nGlückwunsch! Sie haben das Wort erraten: " + word)
    else:
        print("\nLeider verloren! Das Wort war: " + word)

hangman()
```