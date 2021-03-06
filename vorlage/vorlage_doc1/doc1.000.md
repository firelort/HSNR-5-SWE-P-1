---
author:
   name1: {Name1, Vorname1, Matrikelnr. 1}
   name2: {Name2, Vorname2, Matrikelnr. 2}
title:
   main: Software Engineering WS 2017/2018
   sub1: Praktikum Gruppe {??}
   sub2: Dokumentation Aufgabe 2
revision:
   doc: {Dateiname}
   level: {Versionsnummer, ab 0}
   date: {Datum der Gültigkeit der Version TT.MM.JJJJ}
lang: de
cssextra: doc1.css
---

# TEIL I: Voruntersuchung {.unnumbered .clDocPartHeader}

# Schätzung des Aufwands

## Zusammenstellung und Klassifizierung der Elementarprozesse

Geben Sie die Elementarprozesse an und beschreiben Sie diese. Ordnen Sie die Elementarprozesse den Kategorien zu.

### Ausgaben

### Abfragen

### Eingaben

## Daten

Benennen Sie Datenbestände und beschreiben Sie diese mit dem "Data-Dictionary"-Ansatz.

### Interne Datenbestände

### Referenzdaten

## Komplexität / Berechnung der unbewerteten FP

Wenden Sie die Zählregeln an und ermitteln Sie anhand der Tabelle die unbewertete Summe der FP.

+-----------------------+--------+----------------+------------+------+
| Kategorie             | Anzahl | Klassifzierung | Gewichtung | Wert |
+=======================+========+================+============+======+
| Eingaben              |        | einfach        |            |      |
+-----------------------+--------+----------------+------------+------+
| Eingaben              |        | mittel         |            |      |
+-----------------------+--------+----------------+------------+------+
| Eingaben              |        | komplex        |            |      |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |        | einfach        |            |      |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |        | mittel         |            |      |
+-----------------------+--------+----------------+------------+------+
| Ausgaben              |        | komplex        |            |      |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |        | einfach        |            |      |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |        | mittel         |            |      |
+-----------------------+--------+----------------+------------+------+
| Abfragen              |        | komplex        |            |      |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |        | einfach        |            |      |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |        | mittel         |            |      |
+-----------------------+--------+----------------+------------+------+
| Interne Datenbestände |        | komplex        |            |      |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |        | einfach        |            |      |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |        | mittel         |            |      |
+-----------------------+--------+----------------+------------+------+
| Referenzdaten         |        | komplex        |            |      |
+-----------------------+--------+----------------+------------+------+
| Summe                 |        |                |            |      |
+-----------------------+--------+----------------+------------+------+

## Berechnung der bewerteten FP

Wenden Sie die passenden Einflussfaktoren an.

### Einflußfaktor (VAF/Value adjustment factor)

#### Systemmerkmale

14 allgemeine Systemmerkmale, mit denen die allgemeine Funktionalität einer Anwendung klassifiziert wird:

1.  Datenkommunikation
2.  Verteilte Verarbeitung
3.  Leistungsfähigkeit
4.  Begrenzte Kapazität
5.  Transaktionsrate
6.  Interaktive Dateneingabe
7.  Benutzerfreundlichkeit
8.  Interaktive Änderung
9.  Komplexe Verarbeitung
10.  Wiederverwendbarkeit
11.  Installationshilfen
12.  Betriebshilfen
13.  Mehrfachinstallation
14.  Änderungsfreundlichkeit.

#### Einflussgrade (DI/Degree of influence)

- für jedes Merkmal
- auf einer Skala von 0 (kein Einfluss) bis 5 (starker Einfluss)
- Gesamteinflussgrad (TDI, engl. Total degree of influence): Summe der 14 Werte
- VAF berechnet sich dann anhand folgender Formel: VAF = (TDI * 0.01) + 0.65
- VAF maximal 1,35 bzw. minimal 0,65

## Ermittlung Personalaufwand, Bearbeitungsdauer, Kosten

Zur Abschätzung des Entwicklungsaufwands in Personenmonaten gibt es in der Literatur u.a. folgende Formel:

- Aufwand (Personenmonate) = FP^1.4^ / 150

Dabei geben bei Sie bei FP die bewerteten Function-Points an.

Geben Sie danach an, welcher Bearbeitungszeitraum und welche Projektkosten sich daraus nach Ihrer Meinung ergeben. Begründen Sie Ihre Ausführungen.

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

