## elementarprozesse

**interne db**

* absolventen meta infos referenziert zu absolvent von prufüngsamt
* teilnehmer (mitarbeiter) 
* information zur feier 

**externe db**
 
* absolventenliste von prüfungsamt (inkl. arbeit+prüfer)


**eingang**

* anmeldung/stornierung absolventen
* registrierung (passwort erstellen nach eingabevon email) absolventen
* anzahl begleitperson ändern absolvent
* mitarbeiter registrieren 
* 

---
**alles für prufungsausschluss**

* anmelden
* absolventen löschen
* absolventen editieren
* absolventen löschen
* zuweisung prüfer
* feierinfos


**ausgang**

* teilnehmerliste absolventen prüfungausschluss
* liste der abschlussarbeiten prüfungsausschluss 
* infos zur feier 



absolventen informationen
professoren aus externe db 


## datenstruktur

feier ::= name + #datum + uhrzeit + ort;

absolventen_ex ::= name + vorname + #email + arbeitstitel + arbeitstyp + pruefer1 + pruefer2;

absolventen_in ::= @absolvent_ex + passwort + teilnahmestatus + anzahlBegleitperson;

mitarbeiter ::= name + vorname + #email;

name ::= string;  
datum ::= date;  
uhrzeit ::= time;  
ort ::= string;  

vorname ::= string;  
email ::= string;  
arbeitstitel  ::= string;  
arbeitstyp ::= ['Bachelor'|'Master'];  
pruefer1 ::= string;  * Professor *   
pruefer2 ::= string;  * FB Mitarbeiter und != Pruefer1 *  

passwort ::= string; * leer bei unregisitreren absolventen *  
teilnehmerstatus ::= boolean; * Standard ist false *  
anzahlBegleitperson ::= number;  







