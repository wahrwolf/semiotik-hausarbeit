# Theorie
## Level ist technisch lösbar
Shannon und Weaver schlagen einen "Semantisches Empfangsgerät" vor, der die Nachricht im weiteren Schritt semantsich verarbeitet.

Ich stelle im folgenden ein semantsiches Empfangs- beziehungsweise Sendegerät als Kodierer beziehungsweise Dekodierer vor.

Dafür sind die folgenden Schritte notwendig:
* Einführung einer allgemeinen Kodierfunktion
* Aufteilung des Kodiervorgangs in die semantische Kodierung und die technische Kodierung
* Definition und Abgrenzung eienr semantischen Störung von einer technischen Störung

## Vorstellung des Modells/Grundsätze
In dem bereits vorgestellten Modell von Shannon und Weaver hält der Sender eine Nachricht, die er mithilfe eines Sendegeräts verschicken möchte.

Hierbei wird das Senden in das Kodieren, als Umwandeln der Nachricht in zum Beispiel Morsecode und dann das eigentliche verschicken als physikalische Aktion unterteilt.

In meinem Modell gehe ich noch einen Schritt weiter und setzte 3 Schritte an:
Zunächst wird die Information in eine Nachricht kodiert.
Anschließend wird die Nachricht zu einem Signal transformiert.
Das eigentliche Senden ist dann die physikalische Veränderung des Kanals um das Signal darzustellen.

Dieser Kodierschritt entspricht der semantischen Kodierung.
Der Transformationsschritt entspricht der technischen Kodierung.

Beide Kodierungen sind Funktionen die eine Reihe von Symbolen erzeugen.
Die semantische Kodierfunktion nimmt aber eine Reihe von Axiomen und kodiert.
Das Ziel dieses Kodierungsschrittes ist es ein Axiom grundsätzlich abzubilden.
Die semantische Kodierung ist eine Sprache, die 

Die technische Kodierfunktion übersetzt eine Reihe von Symbolen in eine andere Reihe.


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
Daher erweitert sich das Modell auf folgende Begriffe:

#### Kommunkationspartner
Ein Kommunikationspartner K sei ein Tupel aus Empfangsgerät, Sendegerät, einer Menge an Kodiergeräten und einer Menge an Dekodiergeräten

#### Information
Die Information H sei ein endliches Tupel von Wahrheitswerten.
Sie stellt die virtuell zu übermittelnde Information dar und ist eine Reihe von Axiomen.
Eine Information ist einzigartig und hat nur eine Darstellungsweise.
Als Beispiel kann man hier das Axiom "Die Tasse ist blau" nehmen.

#### Nachricht
Eine Nachricht M sei eine endliche Reihe von Symbolen.
Sie stellt die formulierte und kontexbezogene Information da.
Eine Information kann in mehrere Nachrichten formuliert werden.
Gleichzeitig können aus einer Nachricht verschiedene Informationen extrahiert werden.
Als Beispiel kann man hier einen Satz aus verschiedenen Worten nehmen.

### Kanal
Ein Kanal C sei eine endliche Matrix mit Symbolen aus der Menge R.
Der Kanal stellt den physikalischen Raum dar, indem Sender und Empfänger kommunizieren.
Als Beispiel kann man hier alle Moleküle in einem Raum nehmen.

#### Signal
Ein Signal S sei ein Vektor von Symbolen aus der Menge R 
Es stellt die physikalische Darstellung einer Nachricht innerhalb eines Kanals da.
Als Beispiel kann man hier einen Ton oder einen elektrischen Impuls nehmen.

#### Emfpangsgerät
Das Empfangsgerät sei ein Tupel aus den Funktionen receive(C): S und transform(S): M
Hierbei wird zunächst ein Signal aus dem Kanal wahrgenommen und dann als eine Nachricht emfpangen.
Die Funktionen sind stabil, aber unabhängig.
So wird zwar aus dem gleichen Kanal stets das gleiche Signal wahrgenommen, und aus dem gleichen Signal stets die gleiche Nachricht empfangen, aber mehrere Signale können als die gleiche Nachricht empfangen werden.
Ein perfekter Empfangsgerät transformiert K in S ohne Verluste.
Ein Kommunikationspartner hat nur ein unveränderliches Empfangsgerät.
Zu jedem Empfangsgerät kann man ein inverses Sendegerät definieren so, dass transform(receive(send(transform(M)))) = M
Wenn dies gilt so sprechen wir von einem "kompatiblen" Sende- beziehungsweise Empfangsgerät.
Als Beispiel kann man hier einen Lautsprecher oder die Muskeln eines Menschen nehmen.

#### Sendegerät
Das Sendegerät sei ein Tupel aus den Funktionen send(S, C_i): C_q und transform(M): S
Die Funktionen sind stabil und erzeugen bei gleichem Kanal stets die gleiche Nachricht.
Die Funktion transform stellt die Vorbereitung des Sendens da. Ein perfektes Sendegerät verändert den Kanal so, dass S enthalten ist.
Ein Kommunikationspartner hat nur ein unveränderliches Sendegerät.
Zu jedem transform eines sendegeräts exisitiert ein inverses transform eines emfpangsgeräts, so dass transform(transform(M)) = M
Als Beispiel kann man hier Ohren, oder sogar die Kombination der Sinne (Hören, Sehen, Schmecken, Riechen, Fühlen, ...) nehmen.

#### Kodiergerät
Das Kodiergerät sei eine Funktion encode(H): M
Die Funktion stellt da wie ein Kommunikationspartner eine Information als Nachricht formuliert.
Ein Kodiergerät ist hierbei stets stabil und erzeugt aus einer Information stets die gleiche Nachricht.
Mehrere Kodiergeräte können eine Informationen aber unterschiedlich darstellen.
Das bedeutet auch, dass die Nachricht aus verschiedenen Informationen kodiert sein kann.
Ein Kommunikationspartner hat eine endliche Menge an Kodiergeräten zur Verfügung.
Als Beispiel kann man hier verschiedene Sprachen nehmen. Teekesselchen wie "Der Boxer berührt den Ring" verdeutlichen die Varianz.

#### Dekodiergerät
Das Dekodiergerät sein eine Funtkon decode(M): H
Diese Funktion stellt dar, wie ein Kommunikationspartner eine Nachricht versteht.
Ein Kodiergerät ist ebenfalls stabil und erzeugt aus einer Nachricht stets die gleiche Information.
Es ist aber wieder möglich, dass mehrere Dekodiergeräte eine Nachricht unterschiedliche interpretieren.
Zu jedem Dekodiergerät exisitert ein Kodiergerät, so dass decode(encode(H)) = H ist.
Gilt dies so ist die Kodierung "nachvollziehbar".
Ein Kommunikationspartner hat eine endliche Menge an Kodiergeräten zur Verfügung.
Als Beispiel kann man hier verschiedene Sprachen nehmen. Teekesselchen wie "Der Boxer berührt den Ring" verdeutlichen die Varianz.


#### Störung
Eine Störung ist vom Aufbau identisch wie ein Signal und wir auf den Kanal angelegt.


### Ablauf
Eine Kommunikation zwischen Sender und Empfänger läuft in dem Modell folgene Schritte ab:

Der Sender möchte eine Information H_A übertagen.
Diese Information wird durch das Kodiergerät zu einer Nachricht M_A.
Das Sendegerät verändert den Kanal K durch den Signalvektor S_A.

Das Emfpangsgerät extrahiert aus dem Kanal den Signalvektor S_B.
Das Signal wird durch das Empfangsgerät zu der Nachricht M_B

Im Dekodierschritt wird mithilfe des Dekodiergeräts die Nachricht zu einer Information H_B umbgewandelt.
Diese Information kann schließlich durch den Emfpäger wahrgenommen werden.

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
