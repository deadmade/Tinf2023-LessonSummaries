## Aggregate-Funktionen
Funktionen, die Berechnungen auf Datensätzen durchführen und einen einzigen Wert zurückgeben.

### COUNT
Zählt die Anzahl der Zeilen.
> [!example] Beispiel
> ```sql
> SELECT COUNT(student_id) AS total_students FROM students;
> ```

### SUM
Summiert Werte einer Spalte.
> [!example] Beispiel
> ```sql
> SELECT SUM(salary) AS total_salary FROM employees;
> ```

### AVG
Berechnet den Durchschnittswert.
> [!example] Beispiel
> ```sql
> SELECT AVG(score) AS average_score FROM tests;
> ```

### MIN und MAX
Gibt den kleinsten bzw. größten Wert einer Spalte zurück.
> [!example] Beispiel
> ```sql
> SELECT MIN(price) AS lowest_price, MAX(price) AS highest_price FROM products;
> ```

---

## GROUP BY und HAVING
### GROUP BY
Gruppiert Daten basierend auf einer Spalte.
> [!example] Beispiel
> ```sql
> SELECT product_id, SUM(sales) AS total_sales
> FROM sales
> GROUP BY product_id;
> ```

### HAVING
Filtert Gruppenergebnisse (wird nach GROUP BY angewendet).
> [!example] Beispiel
> ```sql
> SELECT department_id, AVG(salary) AS avg_salary
> FROM employees
> GROUP BY department_id
> HAVING AVG(salary) > 50000;
> ```

---

## JOINs
Verknüpft Daten aus mehreren Tabellen.

### INNER JOIN
Zeigt nur übereinstimmende Daten an.
> [!example] Beispiel
> ```sql
> SELECT students.name, enrollments.course
> FROM students
> INNER JOIN enrollments
> ON students.student_id = enrollments.student_id;
> ```

### LEFT JOIN
Zeigt alle Daten der linken Tabelle und übereinstimmende der rechten Tabelle (NULL für keine Übereinstimmung).
> [!example] Beispiel
> ```sql
> SELECT students.name, enrollments.course
> FROM students
> LEFT JOIN enrollments
> ON students.student_id = enrollments.student_id;
> ```

### RIGHT JOIN
Analog zum LEFT JOIN, aber für die rechte Tabelle.
> [!example] Beispiel
> ```sql
> SELECT students.name, enrollments.course
> FROM students
> RIGHT JOIN enrollments
> ON students.student_id = enrollments.student_id;
> ```

### FULL OUTER JOIN
Kombiniert LEFT JOIN und RIGHT JOIN.
> [!example] Beispiel
> ```sql
> SELECT students.name, enrollments.course
> FROM students
> FULL OUTER JOIN enrollments
> ON students.student_id = enrollments.student_id;
> ```

---

## Tabellenmanagement

### Tabellen erstellen
Definiert die Struktur einer Tabelle, inklusive Spalten, Datentypen und Einschränkungen.
> [!example] Beispiel
> ```sql
> CREATE TABLE students (
>     student_id INT AUTO_INCREMENT PRIMARY KEY, -- Eindeutige ID
>     name VARCHAR(50) NOT NULL,                 -- Name, darf nicht NULL sein
>     email VARCHAR(100) UNIQUE,                 -- Eindeutige E-Mail-Adresse
>     enrollment_date DATE DEFAULT CURRENT_DATE, -- Standardwert ist das aktuelle Datum
>     age INT CHECK (age >= 18)                  -- Alter muss mindestens 18 sein
> );
> ```

#### Wichtige Parameter beim Erstellen:
- **NOT NULL**: Spalte darf keinen NULL-Wert enthalten.
- **DEFAULT**: Standardwert, wenn kein Wert angegeben wird.
- **AUTO_INCREMENT**: Automatische numerische Erhöhung (nur für Primärschlüssel sinnvoll).
- **UNIQUE**: Werte in der Spalte müssen eindeutig sein.
- **PRIMARY KEY**: Identifiziert jede Zeile eindeutig.
- **FOREIGN KEY**: Verknüpfung mit einer anderen Tabelle.
- **CHECK**: Überprüft Bedingungen auf Spaltenwerte.

### Tabellen aktualisieren
Fügt Spalten hinzu, ändert bestehende oder löscht sie.
> [!example] Spalte hinzufügen
> ```sql
> ALTER TABLE students ADD COLUMN phone_number VARCHAR(15);
> ```

> [!example] Spalte ändern
> ```sql
> ALTER TABLE students MODIFY COLUMN email VARCHAR(150) NOT NULL;
> ```

> [!example] Spalte löschen
> ```sql
> ALTER TABLE students DROP COLUMN phone_number;
> ```

---

## CRUD-Operationen

### SELECT mit ORDER BY und LIMIT
Sortiert und begrenzt die Anzahl der zurückgegebenen Zeilen.
> [!example] Sortieren und begrenzen
> ```sql
> SELECT * FROM students
> ORDER BY enrollment_date DESC
> LIMIT 10;
> ```

> [!example] Überspringen und begrenzen
> ```sql
> SELECT * FROM students
> ORDER BY name ASC
> LIMIT 5 OFFSET 10;
> ```

### INSERT
Fügt neue Datensätze ein.
> [!example] Beispiel
> ```sql
> INSERT INTO students (name, email, age) VALUES ('John Doe', 'john@example.com', 21);
> ```

### UPDATE
Aktualisiert bestehende Datensätze.
> [!example] Beispiel
> ```sql
> UPDATE students SET email = 'john.doe@example.com' WHERE student_id = 1;
> ```

### DELETE
Löscht Datensätze.
> [!example] Beispiel
> ```sql
> DELETE FROM students WHERE student_id = 1;
> ```

---

## Views
Virtuelle Tabellen, die Abfragen speichern und wiederverwendbar machen.
> [!example] View erstellen
> ```sql
> CREATE VIEW active_students AS
> SELECT name, email FROM students WHERE status = 'active';
> ```

> [!example] View verwenden
> ```sql
> SELECT * FROM active_students;
> ```

> [!example] View löschen
> ```sql
> DROP VIEW active_students;
> ```

---

## Schleifen in Stored Procedures
Schleifen ermöglichen wiederholte Operationen in Prozeduren.

### Beispiel mit LOOP
> [!example] Beispiel
> ```sql
> DELIMITER //
> CREATE PROCEDURE UpdateStorage()
> BEGIN
>     DECLARE done INT DEFAULT FALSE;
>     DECLARE product_id INT;
>     DECLARE cur CURSOR FOR SELECT id FROM products;
>     DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
>
>     OPEN cur;
>     read_loop: LOOP
>         FETCH cur INTO product_id;
>         IF done THEN
>             LEAVE read_loop;
>         END IF;
>         UPDATE products SET storage = 'Warehouse' WHERE id = product_id;
>     END LOOP;
>     CLOSE cur;
> END;
> //
> DELIMITER ;
> ```

---

## Transaktionen
Bündelung von SQL-Befehlen mit ACID-Eigenschaften.

### Beispiel
> [!example] Beispiel
> ```sql
> START TRANSACTION;
> UPDATE accounts SET balance = balance - 100 WHERE account_id = 1;
> UPDATE accounts SET balance = balance + 100 WHERE account_id = 2;
> COMMIT;
> ```

---

## Weitere nützliche Befehle

### DISTINCT
Eliminiert doppelte Werte in einer Spalte.
> [!example] Beispiel
> ```sql
> SELECT DISTINCT department FROM employees;
> ```

### CASE
Führt bedingte Logik in Abfragen aus.
> [!example] Beispiel
> ```sql
> SELECT name,
>        CASE
>            WHEN score >= 90 THEN 'A'
>            WHEN score >= 80 THEN 'B'
>            ELSE 'C'
>        END AS grade
> FROM students;
> ```

### UNION
Kombiniert Ergebnisse von zwei Abfragen.
> [!example] Beispiel
> ```sql
> SELECT name FROM students
> UNION
> SELECT name FROM teachers;
> ```

### EXPLAIN
Zeigt den Abfrageplan zur Optimierung von SQL-Befehlen.
> [!example] Beispiel
> ```sql
> EXPLAIN SELECT * FROM students WHERE enrollment_year = 2024;
> ```