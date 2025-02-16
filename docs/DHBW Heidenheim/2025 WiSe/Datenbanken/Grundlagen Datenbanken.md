## DBMS
### Definition
- Software zur effizienten Speicherung, Organisation, Verwaltung und Abfrage von Daten.
- Schnittstelle zwischen Benutzer und Datenbank.
- Hauptaufgaben:
  - Speicherung und Organisation von Daten.
  - Bearbeitung von Anfragen (CRUD).
  - Gewährleistung von Datenintegrität und Zugriffsrechten.

### Vorteile
- Zentralisierte Datenverwaltung.
- Reduktion von Redundanz.
- Einheitliche Schnittstellen (z. B. SQL).
- Skalierbarkeit für große Datenmengen.

---

## Datenbank-Modelle
### Eigenschaften
- **Datenstruktur:** Speicherung in Tabellen, Dokumenten, Graphen etc.
- **Operatoren:** Abfragen, Einfügen, Löschen, Ändern.
- **Integritätsbedingungen:** Primärschlüssel, referentielle Integrität.

### Beispiele für Modelle
- **Relational:** PostgreSQL, MySQL.
- **Dokumentenorientiert:** MongoDB.
- **Graphenbasiert:** Neo4j.

---

## Relationale DBMS (RDBMS)
- Daten in Tabellen gespeichert (Zeilen = Tupel, Spalten = Attribute).
- Unterstützung von Primär- und Fremdschlüsseln.
- Standard-Abfragesprache: SQL.
- Transaktionen und ACID-Konformität.

### ACID-Eigenschaften
- **Atomicity:** Alles oder nichts.
- **Consistency:** Daten bleiben gültig.
- **Isolation:** Unabhängigkeit von Transaktionen.
- **Durability:** Daten bleiben dauerhaft gespeichert.

---

## SQL
### Definition
- Deklarative Sprache für relationale Datenbanken.
- Hauptbestandteile:
  - **DDL:** Definition von Strukturen (CREATE, ALTER, DROP).
  - **DML:** Datenbearbeitung (INSERT, UPDATE, DELETE).
  - **DQL:** Abfragen (SELECT).
  - **DCL:** Rechteverwaltung (GRANT, REVOKE).
  - **TCL:** Transaktionskontrolle (COMMIT, ROLLBACK).

### Standards
- Wichtig: SQL-92 (Grundlegender Standard).
- Unterschiede zwischen DBMS (z. B. rekursive Abfragen, Window Functions).
![[Pasted image 20250114152444.png]]

---

## MariaDB
- Fork von MySQL mit besseren Funktionen und Performance.
- Vorteile: JSON-Support, erweiterte Storage Engines.
- Standard-Port: 3306.

### Datentypen
- **Integer:** Ganzzahlen.
- **VARCHAR/CHAR:** Zeichenketten.
- **DATE/DATETIME:** Zeitangaben.

### Speicher-Engines
- **InnoDB:** Standard, unterstützt ACID.
- **MyISAM:** Schnell, aber keine Transaktionen.
- **Aria:** Ersatz für MyISAM in MariaDB.

---

## Tabellenaufbau und Normalisierung
### Normalisierung
1. **1. Normalform:** Atomare Werte.
2. **2. Normalform:** Vollständige Abhängigkeit vom Primärschlüssel.
3. **3. Normalform:** Keine transitiven Abhängigkeiten.

### Beispiele
- Tabelle `students` mit Primärschlüssel `id`.
- Fremdschlüssel-Verknüpfungen: `students` → `classes`.

---

## SQL-Befehle
### Wichtige DDL-Befehle
- **CREATE TABLE:** Tabelle erstellen.
- **ALTER TABLE:** Tabelle ändern.
- **DROP TABLE:** Tabelle löschen.

### Wichtige DML-Befehle
- **INSERT INTO:** Datensätze einfügen.
- **UPDATE:** Datensätze ändern.
- **DELETE FROM:** Datensätze löschen.

### SELECT-Befehl
- Projektion: Bestimmte Spalten auswählen.
- Selektion: Zeilen mit Bedingungen filtern (`WHERE`).

---

## Referentielle Integrität
- **Primary Key:** Eindeutiger Identifikator.
- **Foreign Key:** Verknüpft Tabellen.
- Aktionen bei Lösch- und Update-Regeln:
  - **CASCADE:** Verknüpfte Einträge anpassen.
  - **SET NULL:** Fremdschlüssel auf NULL setzen.
  - **RESTRICT:** Änderungen verhindern.

