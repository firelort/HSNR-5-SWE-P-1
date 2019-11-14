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

```
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
```


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

Ausgabe mittel: `Teilnehmerlist der Absolventen`, da dort auf zwei Datenbestände zugegriffen wird und die Summe der Datenfelder zwischen 5 und 15 liegt.

## Berechnung der bewerteten FP

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

Der Prüfungsausschuss soll mit Hilfe der beschrieben Anwendung die Absolventenfeier verwalten können.
Die Mitglieder des Prüfungsausschuss können die Informationen der Abschlussfeier (ein-)pflegen sowie eine aktuelle Teilnehmerliste abrufen
Mitarbeitern des Fachbereichs und Absolventen können sich über die hier beschriebene Anwendung zur Absolventenfeier anmelden.

# Produkt-Einsatz    

## Anwendungsbereiche

Die beschriebene software Lösung soll im Universitätsumfeld genutzt werden um eine Verwaltung von Absolventenfeiern zu ermöglichen.

## Zielgruppen

Die beschriebene Anwendung richtet sich an drei Zielgruppen.

#### 1. Absolventen

Die Absolventen geben an, ob und mit wie vielen Begleitpersonen diese an der Absolventenfeier teilnehmen möchten.

#### 2. Mitarbeiter des Fachbereichs

Zu den Mitarbeitern des Fachbereichs zählen neben den Professoren auch alle anderen Angestellten, welche am Fachbereich tätig sind.
Diese können sich mit Hilfe der Anwendung auch an der Absolventenfeier anmelden.

#### 3. Mitglieder des Prüfungsausschuss

Die gewählten Mitglieder des Prüfungsausschusses stehen die selben Funktionen zur Verfügung, wie den Mitarbeitern des Fachbereichs.
Ihr Handlungsspielraum wird ergänzt durch die Möglichkeiten der Organisation der Absolventenfeier sowie einer Ausgabe von angemeldeten Gästen und eine Aufstellung der Bachelorarbeiten.

## Betriebsbedingungen

Die Anwendung soll (nur) im Intranet der Hochschule Niederrhein genutzt werden.
Damit die Anwendung ordnungsgemäß arbeiten kann, benötigt die beschriebene Anwendung die externen Daten des Prüfungsamtes.

Diese Daten müssen den Namen, den Vorname, die E-Mail-Adresse, den Titel der Arbeit, den Typ der Abschlussarbeit sowie den Erst- und Zweitprüfer enthalten. 

# Produkt-Umgebung

Charakterisieren Sie wesentliche Aspekte der dv-technischen Umgebung des Produkts; gehen Sie dabei insbesondere die (fachlichen / dv-technischen) Schnittstellen zu anderen Produkten an

## Software

Es wird ein Webserver benötigt sowie eine NoSQL-Datenbank-Software.

## Hardware

Zum Betreiben der Anwendung wird keine spezielle Hardware benötigt.

Da eine Verbindung zum Intranet der Hochschule benötigt wird und die Anwendung auf externe Daten zugreift, wird ein LAN-Adapter benötigt.
Dieser sollte jedoch Standard in allen Servern sein.

# Funktionale Produkt-Anforderungen

Definieren Sie die Anforderungen die Funktionalität des Produkts.

## Anwendungsfälle

![UML-Diagramm für Absolventenfeiersystem](use-cases-umlet.png "use-case")


:(Teilnahme Bekunden) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Mitarbeiter ist zur Absolventenfeier angemeldet                             |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Mitarbeiter, Prüfungsausschuss                                              |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Mitarbeiter möchten an der Feier teilnehmen                                 |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Absolventenfeier angelegt                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Mitarbeiter/Prüfungsausschuss zur Absolventenfeier angemeldet               |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | primär                                                                      |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Mitarbeiter und Prüfungsausschuss bekunden ihre Teilnahme an der            |
|                      | Absolventenfeier                                                            |
+----------------------+-----------------------------------------------------------------------------+


:(am AFS registrieren) 
TODO: wechseln auf Mitarbeiter? siehe letzte Übung
+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Prüfungsausschuss meldet sich zum Backend des AFS an                        |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Prüfungsausschuss möchte das Backend benutzen können                        |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Neues Prüfungsausschussmitglied registirert                                 |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         |  Ein Mirarbeiter registriert sich um zum Prüfungsausschuss zu gehören, um   |
|                      |  dann das Backend nutzen zu können                                          |
+----------------------+-----------------------------------------------------------------------------+


:(am AFS anmelden) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Prüfungsauschuss wird im AFS authentifiziert                                |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Prüfungsausschuss möchte das Backend benutzen                               |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Im AFS registriert sein                                                     |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | primär                                                                      |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Prüfungsamt wird im AFS angemeldet und kann das Backend benutzen            |
+----------------------+-----------------------------------------------------------------------------+


:(Absolventenfeier anlegen) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Eine neue Absolventenfeier anlegen                                          |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Eine neue Absolventenfeier findet statt und muss angelegt werden            |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | im AFS als Prüfungsausschuss angemeldet                                     |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | neue Absolventenfeier angelegt                                              |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | primär                                                                      |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Der Prüfungsausschuss legt eine neue Absolventenfeier an                    |
+----------------------+-----------------------------------------------------------------------------+


:(Absolventenfeier bearbeiten) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Ändern der Daten einer Absolventenfeier                                     |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Daten einer Absolventenfeier sollen geändert werden                         |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Absolventenfeier angelegt                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Die neuen Absolventenfeierdaten wurden übernommen                           |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Daten einer Absolventenfeier werden geändert                            |
+----------------------+-----------------------------------------------------------------------------+


:(Mitarbeiter anzeigen) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | List einsehen der zur Absolventenfeier angemeldeten Mitarbeiter             |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Mitarbeiter die angemeldet sind einsehen wollen                             |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | im AFS als Prüfungsausschuss angemeldet                                     |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | optional                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Mitarbeiter, die an der Absolventenfeier angemeldet sind werden         |
|                      | eingesehen                                                                  |
+----------------------+-----------------------------------------------------------------------------+


:(Absolventen anzeigen) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | List einsehen der zur Absolventenfeier angemeldeten Absolventen             |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Absolventen die angemeldet sind einsehen wollen                             |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | im AFS als Prüfungsausschuss angemeldet                                     |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Absolventen, die an der Absolventenfeier angemeldet sind werden         |
|                      | eingesehen                                                                  |
+----------------------+-----------------------------------------------------------------------------+


:(Abschlussarbeiten anzeigen) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Die Abschlussarbeiten einsehen                             |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Die Liste der Abschlussarbeiten einsehen                                    |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Absolventen vorhanden                                                       |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Abschlussarbeiten der Absolventen lassen sich einsehen nach vorgegebenen|
|                      | Kriterien                                                                   |
+----------------------+-----------------------------------------------------------------------------+


:(Prüfer kontrollieren) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Prüfer einer Absolventenarbeit kontrollieren                                |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Prüfungsausschuss                                                           |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Prüfer einer Absolventenarbeit sollen kontrolliert werden                   |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         |  Informationen zu Absolventenarbeit vorhanden                               |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Prüfer einer Absolventenarbeit können kontrolliert, sprich eingesehen   |
|                      | werden                                                                      |
+----------------------+-----------------------------------------------------------------------------+


:(Passwort setzen) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Das Passwort eines Absolventen wird gesetzt                                 |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Absolvent                                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Absolvent meldet sich zum ersten mal an                                     |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         |  Absolventendaten importiert                                                |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Der Absolvent hat ein Passwort hinterlegt                                   |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | primär                                                                      |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Der Absolvent hinterlegt für weitere Anmeldungen ein Passwort               |
+----------------------+-----------------------------------------------------------------------------+


:(am AFS anmelden) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Absolvent meldet sich im AFS an                                             |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Absolvent                                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Der Absolvent möchte Änderungen and Daten seinen Daten vornehmen            |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Passwort gesetzt                                                            |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        |                                                                             |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Der Absolvent meldet sich im AFS an um seine Daten ändern zu können         |
+----------------------+-----------------------------------------------------------------------------+


:(Teilnahmestatus ändern) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Der Teilnahmestatus wird geändert                                           |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Absolvent                                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Der Absolvent möchte seine Teilnahme bekunden oder stornieren               |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Passwort gesetzt                                                            |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Geänderter Teilnahmestatus                                                  |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Der Absolvent kann seinen Teilnahmestatus ändern                            |
+----------------------+-----------------------------------------------------------------------------+


:(Anzahl der Begleitpersonen ändern) 

+----------------------+-----------------------------------------------------------------------------+
|     Bezeichnung      |                                                                             |
+======================+=============================================================================+
| Ziel                 | Anzahl der Begleitpersonen ändern                                           |
+----------------------+-----------------------------------------------------------------------------+
| Akteure              | Absolvent                                                                   |
+----------------------+-----------------------------------------------------------------------------+
| Auslösendes Ereignis | Der Absolvent möchte Begleitpersonen mitbringen oder streichen              |
+----------------------+-----------------------------------------------------------------------------+
| Vorbedingung         | Teilnahme bekundet                                                          |
+----------------------+-----------------------------------------------------------------------------+
| Nachbedingung        | Die Anzahl der Begleitpersonen des Absolventen wurde geändert               |
+----------------------+-----------------------------------------------------------------------------+
| Kategorie            | sekundär                                                                    |
+----------------------+-----------------------------------------------------------------------------+
| Beschreibung         | Die Anzahl der Begleitpersonen wird vom Absolventen geändert                |
+----------------------+-----------------------------------------------------------------------------+


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

