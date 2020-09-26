# Einleitung
## Kommunikation ist schwierig
## Semantik kann technisch gelöst werden

# Literaturdiskussion
## Semantik kann technisch gelöst werden

## Shannon-Weaver Model
### Vorstellung des Modells/Grundsätze
- Wie genau kann ein Symbol übertragen werden?
	- Übertragung mittels Symbolen und Mustern, die auf einen Kanal gelegt werden
- Wie genau kann ein Symbol verstanden werden?
	- Kein Problem was technisch lösbar ist
- Wie effektiv eine Nachricht sein?
	- Einführung von H als Maß der Information

### Modelbild
- Sender
- Sendegerät
- Empfänger
- Empfangsgerät
- Kanal
- Störung

### Ablauf
- Der Sender übergibt eine Nachricht seinem Sendegerät
- Das Sendegerägt erstellt aus der Nachricht ein Signal
- Das Signal wird auf den Kanal übetragen
- Die Störung verändert das Signal
- Das Empfängsgerät empfägt ein Signal aus dem Kanal
- Das Signal wird durch das Empfangsgerät in eine Nachricht umgewandelt
- Der Empfänger empfängt die Nachricht

## Peirce
### Vorstellung des Modells/Grundsätze
- triadische Relation
	- Ein Objekt (signal)
	- Repräsentamen (nachricht)
	- Interpretant (information)
- Arten von Zeichen
	- Erstheit (seen)
	- zweitheit (learned)
	- drittheit (meta)

### Modelbild
- Sender
- Zeichn
- Empfänger

### Ablauf
- Der Sender erstellt ein Zeichen als Repräsant
- Der Emfpänger interpretiert dieses Zeichen

## Die Lücke
- Shannon suckt weil Level B ignoriert wird
- Peirce suckt weil Level A ignoriert wird

# Theorie
## Level ist technisch lösbar
## Vorstellung des Modells/Grundsätze
- Level B können technisch gelöst werden
- Kodierer/Dekodierer als peircsche Erweiterung
	- Nachrichtenübertragung auf Baisis der Erstheit
	- Challenge-Response auf Basis der Drittheit


## Einführung des Kodierers
### Verwendung von Zeichen der Zweitheit
### Installation durch Zeichen der Erstheit
### Kalibirierung durch Hashing mit Zeichen der Drittheit

## Vorstellung des Gesamtmodells
### Modelbild
- Sender
- Kodierer
- Sendegerät
- Empfangsgerät
- Dekodierer
- Empfänger


### Ablauf
- Der Sender übergibt eine Information seinem Kodierer
- Der Kodierer erstellt daraus eine Nachricht
- Das Sendegerägt erstellt aus der Nachricht ein Signal
- Das Signal wird auf den Kanal übetragen
- Die Störung verändert das Signal
- Das Empfängsgerät empfägt ein Signal aus dem Kanal
- Das Signal wird durch das Empfangsgerät in eine Nachricht umgewandelt
- Die Nachricht wird durch den Dekodierer zu einer Information
- Der Empfänger empfängt die Information

# Analyse
## Abgrenzung zu Shannon-Weaver
## Vergleich mit Crosstalk Algorithmus

# Schlussfolgerung
