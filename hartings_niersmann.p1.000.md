---
author:
   name1: {Hartings, Robert, 1164453}
   name2: {Niersmann, Alexander, 1164424}
title:
   main: Software Engineering WS 2019/2020
   sub1: Praktikum Gruppe D
   sub2: Dokumentation Aufgabe 1
revision:
   doc: hartings_niersmann.p1.000.md
   level: 0
   date: 11.11.2019
lang: de
cssextra: doc1.css
---

# TEIL I: Voruntersuchung {.unnumbered .clDocPartHeader}

# Schätzung des Aufwands

## Zusammenstellung und Klassifizierung der Elementarprozesse

### Ausgaben

Prüfungsausschuss:
* Teilnehmerliste der Absolventen
* Teilnehmerliste der Mitarbeiter
* Auflistung der Abschlussarbeiten
* Prüfer des Studenten

Alle: 
* Informationen der Absolventenfeier 

### Eingaben

Absolventen:
* Passwort setzen
* Teilnahmestatus ändern 
* Anzahl der Begleitpersonen ändern

Mitarbeiter:
* Teilnahme bekunden

Prüfungsausschuss:
* Registrierung am ASF
* Absolventenfeier anlegen
* Absolventenfeier bearbeiten

## Daten

### Interne Datenbestände

* Weitere Absolventen-Informationen
* Teilnehmer Mitarbeiter
* Informationen Abschlussfeier
* Zugangsdaten Prüfungsausschuss

### Referenzdaten

* Absolventenliste vom Prüfungsamt

Diese Daten beinhalten den Namen, den Vornamen, die E-Mail sowie Informationen zur Abschlussarbeit (Titel, Art und Prüfer).

### Data Dictionary

feier ::= name + #datum + uhrzeit + ort;

absolventen_ex ::= name + vorname + #email + arbeitstitel + arbeitstyp + pruefer1 + pruefer2;

absolventen_in ::= @absolvent_ex + passwort + teilnahmestatus + anzahlBegleitperson;

mitarbeiter ::= name + vorname + #email;

zugangsdaten ::= name + vorname + #email + passwort;

name ::= string;  
datum ::= date;  
uhrzeit ::= time;  
ort ::= string;  

vorname ::= string;  
email ::= string;  
arbeitstitel  ::= string;  
arbeitstyp ::= [' Bachelor '|' Master '];  
pruefer1 ::= string;  * Professor *   
pruefer2 ::= string;  * FB Mitarbeiter und != Pruefer1 *  

passwort ::= string; * leer bei unregistreren Absolventen *  
teilnehmerstatus ::= boolean; * Standard ist false *  
anzahlBegleitperson ::= number;  


## Komplexität / Berechnung der unbewerteten FP

+-----------------------+--------+----------------+------------+------+
| Kategorie             | Anzahl | Klassifzierung | Gewichtung | Wert |
+=======================+========+================+============+======+
| Eingaben              |   7    | einfach        |     3      |  21  |
+-----------------------+--------+----------------+------------+------+
| Eingaben              |   0    | mittel         |     4      |   0  |
+-----------------------+--------+----------------+------------+------+
| Eingaben              |   0    | komplex        |     6      |   0  |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |   4    | einfach        |     4      |  16  |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |   1    | mittel         |     5      |   5  |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |   0    | komplex        |     7      |   0  |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |   0    | einfach        |     3      |   0  |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |   0    | mittel         |     4      |   0  |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |   0    | komplex        |     6      |   0  |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |   4    | einfach        |     7      |  28  |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |   0    | mittel         |    10      |   0  |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |   0    | komplex        |    15      |   0  |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |   1    | einfach        |     5      |   5  |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |   0    | mittel         |     7      |   0  |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |   0    | komplex        |    10      |   0  |
+-----------------------+--------+----------------+------------+------+
| Summe                 |  16    |                |            |  75  |
+-----------------------+--------+----------------+------------+------+

## Berechnung der bewerteten FP

Wenden Sie die passenden Einflussfaktoren an.

### Einflußfaktor (VAF/Value adjustment factor)

#### Systemmerkmale

14 allgemeine Systemmerkmale, mit denen die allgemeine Funktionalität einer Anwendung klassifiziert wird:

+--------------------------------+-----------------------------+
| Systemmerkmal                  |   Gewichtung                |
+================================+=============================+
+--------------------------------+-----------------------------+
| 1.  Datenkommunikation         |                 5           |
+--------------------------------+-----------------------------+
| 2.  Verteilte Verarbeitung     |                 0           |
+--------------------------------+-----------------------------+
| 3.  Leistungsfähigkeit         |                 1           |
+--------------------------------+-----------------------------+
| 4.  Begrenzte Kapazität        |                 1           |
+--------------------------------+-----------------------------+
| 5.  Transaktionsrate           |                 4           |
+--------------------------------+-----------------------------+
| 6.  Interaktive Dateneingabe   |                 4           |
+--------------------------------+-----------------------------+
| 7.  Benutzerfreundlichkeit     |                 3           |
+--------------------------------+-----------------------------+
| 8.  Interaktive Änderung       |                 3           |
+--------------------------------+-----------------------------+
| 9.  Komplexe Verarbeitung      |                 1           |
+--------------------------------+-----------------------------+
| 10.  Wiederverwendbarkeit      |                 0           |
+--------------------------------+-----------------------------+
| 11.  Installationshilfen       |                 0           |
+--------------------------------+-----------------------------+
| 12.  Betriebshilfen            |                 0           |
+--------------------------------+-----------------------------+
| 13.  Mehrfachinstallation      |                 0           |
+--------------------------------+-----------------------------+
| 14.  Änderungsfreundlichkeit   |                 0           |
+--------------------------------+-----------------------------+

#### Einflussgrade (DI/Degree of influence)

Formel zur Berechnung des Einflussgrades:
```
Skala von 0 (kein Einfluss) bis 5 (starker Einfluss)
Gesamteinflussgrad (TDI, engl. Total degree of influence): Summe der 14 Werte
VAF berechnet sich dann anhand folgender Formel: VAF = (TDI * 0.01) + 0.65

AFP (Adjusted FP Count) = VAF * UFP (Unadjusted FP)
```

Resultat:
```
TDI = 5 + 1 + 1 + 4 + 4 + 3 + 3 + 1 = 22
VAF = (22 * 0.01) + 0.65 = 0.87
AFP = 0.87 * 75 = 65.25
```

## Ermittlung Personalaufwand, Bearbeitungsdauer, Kosten

Formel zur Ermittlung des Personalaufwand:
```
Zur Abschätzung des Entwicklungsaufwands in Personenmonaten gibt es in der Literatur u.a. folgende Formel:
- Aufwand (Personenmonate) = FP^1.4^ / 150
```

Aufwand in Personenmonate = `65.25^(1.4) / 150 = 2.166 ~ 3`

Formel zur Berechnung der Kosten:
```
Projektkosten = Personenmonate * Gehalt * 2
```

Die Projektkosten belaufen sich auf `3 * 45000€ * 2 = 27000 €`

Das Projekt sollte von zwei Personen in 1.5 Monaten durchgeführt werden.

# TEIL II: Anforderungsanalyse {.unnumbered .clDocPartHeader}

# Zielbestimmung

Geben Sie die Ziele an, die mit der Entwicklung verfolgt werden

# Produkt-Einsatz    

## Anwendungsbereiche

Definieren Sie, in welchen Bereichen / wie das Produkt eingesetzt werden soll

## Zielgruppen

Geben Sie die Zielgruppen an und charakterisieren Sie die unterschiedlichen Rollen, die eingenommen werden

## Betriebsbedingungen

Geben Sie außergewöhnliche Betriebsbedingungen an (z.B. Besonderheiten in einem industriellen Umfeld)

# Produkt-Umgebung

Charakterisieren Sie wesentliche Aspekte der dv-technischen Umgebung des Produkts; gehen Sie dabei insbesondere die (fachlichen / dv-technischen) Schnittstellen zu anderen Produkten an

## Software

Geben Sie hier beispielsweise an, welche Software zum Betrieb der Anwendung zwingend erforderlich ist. Gehen Sie auf Besonderheiten ein, die über allgemein übliche Anforderungen hinausgehen.

## Hardware

Geben Sie hier beispielsweise an, welche Hardware zum Betrieb der Anwendung zwingend erforderlich ist. Gehen Sie auf Besonderheiten ein, die über allgemein übliche Anforderungen hinausgehen.

# Funktionale Produkt-Anforderungen

Definieren Sie die Anforderungen die Funktionalität des Produkts.

## Anwendungsfälle

Beschreiben Sie die Anwendungsfälle mit UML-Anwendungsfalldiagrammen und geben Sie dabei für jeden Anwendungsfall eine Beschreibung an. Ergänzen Sie die Beschreibung der Anwendungsfälle ggf. durch die Definition von Arbeitsflüssen (Workflows) und / oder der Beschreibung dynamischer Aspekte.

Geben Sie für jeden Fall eine Beschreibung in folgender Form an:

:(Anwendungsfall) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                        _konsistent zum UML-Diagramm_                        |
+======================+=============================================================================+
| Ziel                 | _beschreiben Sie das Ziel des Anwendungsfalls_                              |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | _geben Sie die Akteure an_                                                  |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | _warum wird der Anwendungsfall durchgeführt_                                |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | _Systemzustand, der vor der Ausführung des Anwendungsfalls vorliegen muss_  |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | _neuer Systemzustand, der nach der Ausführung des Anwendungsfalls vorliegt_ |
|                      | _(keine Angabe, wenn es keine neuen Systemzustand gibt)_                     |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | _primär, sekundär oder optional_                                            |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | _beschreibender Text_                                                       |
+----------------------+-----------------------------------------------------------------------------+

Achten Sie auf die Konsistenz der Bezeichnung der Anwendungsfälle zum UML-Anwendungsfalldiagramm.

_(Hinweis: zur Vereinfachung wird hier auf eine Beschreibung der Benutzungsschnittstelle verzichtet)_

## Datenbasis

Beschreiben Sie die fachlichen Anforderungen an die Struktur der Datenbasis. Gehen Sie dabei von der Datenbeschreibung aus, die Sie bei der Function-Point-Analyse erstellt haben. Verwenden Sie UML-Klassendiagramme und beschreiben Sie die einzelnen Klassen in folgender Form:

:(klasse )\: Zusammenstellung Attribute

+----------+-------+------------------------------------------------------------+
| Attribut |  Typ  |     Beschreibung                                           |
+==========+=======+============================================================+
| (name)   | (typ) | beschreibender Text                                        |
+----------+-------+------------------------------------------------------------+

&nbsp;

:(klasse )\: Zusammenstellung Methoden

+----------+------------+------------------------------------------------------------+
| Methode  |  Signatur  |     Beschreibung                                           |
+==========+============+============================================================+
| (name)   | (signatur) | beschreibender Text                                        |
+----------+------------+------------------------------------------------------------+

Ersetzen Sie die Platzhalter durch sinnvolle Angaben. Achten Sie bei der Benennung der Klassen auf Konsistenz zum Klassendiagramm. Geben Sie die Signaturen in Form einer Aufzählung von Parametern (Name und Typ) an, soweit das möglich und sinnvoll ist.

## Sonstige Anforderungen

Geben Sie hier fachliche Anforderungen an, die Sie keiner der zuvor genannten Rubriken zuordnen.

# Nichtfunktionale Produktanforderungen   

## Architektur

Beschreiben Sie bereits bekannte Anforderungen an die Architektur der Anwendung (ergibt sich z.B. aus der Anforderung "Web-Anwendung").

## Leistungsanforderungen

Beschreiben Sie Leistungsanforderungen, z.B.

- maximale Reaktionszeiten
- Transaktionsraten: wieviele gleichzeitige Benutzer nehmen Sie an
- voraussichtlicher Speicherbedarf (persistent): berechnen Sie diesen aus einer Abschätzung des Umfangs der Daten.

