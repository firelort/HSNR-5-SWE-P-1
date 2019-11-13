## elementarprozesse

**interne db**

* absolventen meta infos referenziert zu absolvent von prufüngsamt
* teilnehmer (mitarbeiter) 
* information zur feier 
* prüfungsausschuss zugangsdaten

**externe db**
 
* absolventenliste von prüfungsamt (inkl. arbeit+prüfer)


**eingang**

* anmeldung/stornierung absolventen einfach 
* registrierung (passwort erstellen nach eingabevon email) absolventen einfach 
* anzahl begleitperson ändern absolvent einfach 
* mitarbeiter registrieren  mittel

---
**alles für prufungsausschluss**

* Registrierung am System mittel
* anmelden einfach
* feierinfos mittel
absolventenfeier anlegen niedrig
absolventenfeier bearbeiten niedrig


**ausgang**

* teilnehmerliste absolventen prüfungausschuss mittel
* teilnehmerliste Mitarbeiter prüfungsauschuss einfach
* liste der abschlussarbeiten prüfungsausschuss einfach
* Prüfer des Students prüfungsausschuss einfach 
* infos zur feier einfach 



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







