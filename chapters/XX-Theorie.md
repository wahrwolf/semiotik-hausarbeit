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
Wir erweitern das Modelbild des "Sender-Empfänger"-Models nach Shannon-Weaver um einen "Kodier Schritt".
Daher erweitert sich das Modell um folgende Begriffe:

Wie vorher auch exisitiert ein Sender und ein Empfänger als Kommunikationspartner.
Der Sender verfügt über ein Kodiergerät zum erstellen einer Nachricht und ein Sendegerät um es auf einen Kanal zu senden.

Der Kanal bezeichnet den Raum zwischenn Sender und Empfänger. Im einfachsten Fall handelt es sich z.B. um eine Leitung.

Spiegelbildlich dazu hat der Empfänger ein Empfangsgerät und ein Dekodiergerät.


### Ablauf
Im weiteren nennen wir den Sender Alice und den Empfänger Bob.

Eine Nachrichtenübertragung läuft dann nach folgendem Schema ab:
Alice möchte eine Information an Bob übermitteln.
Als erstes benutzt sie ihr Kodiergerät um die zu übermittelnde Information in eine Nachricht  umzuwandeln.
Hierzu wählt sie ein Objekt, nach der Definition von Peirce aus, dessen Interpretant der zu übermittelnden Information entspricht.
Diese Auswahl wird als "Kodieren" bezeichnet und ist abhängig von dem kulturellen Kontext von Alice.

Im nächsten Schritt, dem "Senden" wird mithilfe des Sendegeräts durch eine physikalische Veränderung des Kanals ein Repräsentamen erzeugt.

Nun kann der Kanal durch eine Störung physikalisch weiter verändert.

Auf der Empfängerseite wird nun durch Wahrnehmung des aktuellen Zusatand des Kanals ein Objekt erstellt.
Das Empfangsgerät definiert hierbei welche Dimensionen des Kanals interpretiert werden können.
Der Eingangsvektor des Empfangsgerät ist ebenfalls ein Repräsentamen.

Das Objekt wird im Dekodieren zu einem Interpretant abstrahiert.
Dies passiert durch das Dekodiergerät, was sich durch den kulturellen Kontext von Bob definiert.
Bob hat nun den interpretant empfangen.


### Störungen und Crosstalk
#### Störungen
Die Kommunikation kann an mehrern Stellen gestört werden.

##### Kodierung
Wenn sich die sozialen Kontexte von Sender und Empfänger zu stark unterscheiden, ist der Kodier-Dekodier Prozess gestört.
Das kommt insbesonders dann zustande, wenn zum Beispiel ein Objekt als Zeichen der Zeitheit durch Bob, aber als Zeichen der Drittheit für Alice geprägt sind.

Je mehr gemeinsame Erfahrungen und kulturellen Kontext Alice und Bob gemeinsam haben, desto eindeutiger kann die Kodierung erfolgen.
Technisch gesehen sprechen wir hier von Symboltabellen wie z.B. Morsezeichen.
Wenn die Kommunkationspartner aufeinander abgestimmt sind, dann können immer kompaktere und effizientere Kodierungen benutzt werden.

##### Senden
Der Sendeprozess ist die Art wie ein Objet zu einem Repräsantamen wird.
Hierbei stellt das Sendegerät die Möglichkeiten zur Veränderung des Kanals da.
Aus Sicht der Informationstheorie ist das Sendegerät eine Funktion, die einen Nachrichtenvektor und eine Kanalmatrix zu einer resultierenden Kanalmatrix verarbeitet.
Die Kanalmatrix kann nur mithilfe eines Emfpangsgerät wahrgenommen werden.
Daher ist der aktuellen Zustand und damit der eingeschränkte Zustandsraum für den Sender nicht einsehbar.
Das bedeutet, dass der Sender auch Nachrichtenvektoren übergeben kann, die den Kanal effektiv nicht verändern.

##### Empfangen
Beim Empfangen wird aus einer Kanalmatrix durch eine Funktion ein Nachrichtenvektor erstellt.
Die Kanalmatrix kann zusätliche und andere Dimensionen hab
