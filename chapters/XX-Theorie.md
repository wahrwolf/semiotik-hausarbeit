\chapter{Theorie}
# Level ist technisch lösbar
Shannon und Weaver schlagen einen "Semantisches Empfangsgerät" vor, der die Nachricht im weiteren Schritt semantsich verarbeitet.

Ich stelle im folgenden ein semantsiches Empfangs- beziehungsweise Sendegerät als Kodierer beziehungsweise Dekodierer vor.

Dafür sind die folgenden Schritte notwendig:

- Einführung einer allgemeinen Kodierfunktion
- Aufteilung des Kodiervorgangs in die semantische Kodierung und die technische Kodierung
- Definition und Abgrenzung eienr semantischen Störung von einer technischen Störung

Das es gerade im Bereich der Semiotik und Kommunikationstheorie sehr viele verschiedene Definitionen gibt, definiere ich zunächst alle nötigen Grundbegriffe.

# Definitionen
## Grundlagen
### Axiom
Ein Axiom sei eine atomare Aussage die zu einem finiten Zeitpunkt genau einen Wahrheitswert (wahr, falsch, unbekannt) haben kann.

### Theorem
Eine aus mindestens einem Axiom nach dem boolschen Algebra abgeleitete Aussage.

### Information
Eine Information sei eine Menge von Aussagen

### Axiomsystem
Ein Axiomssystem sei ein Tupel aus einer Menge Variablen, einer Menge an Axiomen und einer Menge an Operationen zur Verknüpfung der Variablen

### Realität
Eine Realität sein ein Axiomssystem mit folgenden Besonderheiten:

* Die Menge der Variablen sei endlich
* Die Operationen seien die der boolschen Algebra
* Die Axiome seien nach der boolschen Algebra widerspruchsfrei

### Situation
Eine Situation sei eine endliche Menge von deterministischen Aussagen, deren Wahrheitswerte ausschließlich wahr oder falsch sind.
Wenn es für jede Aussage einer Situation ein Theorem gibt, dass dieses aus den Axiomen einer Realiät ableitet, so gelte die Situation in Bezug zu der Realiät als möglich.

### Kommunikationskanal
Ein Kommunikationskanal oder kurz Kanal sei eine Realität in der mehr als eine Situation möglich sei.

### Signal
Ein Signal sei ein Tupel aus einem Kommunikationskanal und einer Situation.

### Symobl
Ein Symbol sei die Situation oder umgangssprachlicher der Zustand eines Signals.
Wenn ein Sybmol in einem Signal enthalten ist, so gelte es als ausdrückbar durch das Signal.

### Nachricht
Eine Nachricht sei eine Sequenz von Symbolen

## Modelspezifisch
### technische Kodierung (Transformation)
Eine technische Kodierung sei ein Paar aus den Funktionen $prepare(s, C): S$ sowie $revise(S): s$ mit $s$ sei ein Symbol, $C$ sei ein Kanal und $S$ sein ein Signal
Die Transformation sei also der Mechanismus der ein Symbol zu einem übertragbaren Signal vorbereitet und ebenso eine Möglichkeit bietet ein Symbol aus einem Signal zu lesen.
Für alle Transformationen gelte: $prepare(revise(S)) = S$.
Wenn $revise(prepare(s, C)) = s$ gilt so sei die Transformation eindeutig.

### Sendegerät
Ein Sendegerät sei ein Tupel aus einer technischen Kodierung und einer Funktion $transmit(S_c, S_i): S$ mit $S_c, S_i$ und $S$ seien Signale, $M$ eine Nachricht sowie $send( M, S)$ mit:
```
def send(M, S):
	for s in M:
		S_c = transmit(S, prepare(s, S.C))
	return S
```
Das Sendegerät sei also der Mechanismus mit dem ein Signal verändert wird um eine Nachricht zu verschicken.

### Empfangsgerät
Ein Empfangsgerät sei einer Tupel aus einer technischen Kodierung und einer Funktion $transceive(S_c): S_i$ sowie $receive(S_c)$ mit:
```
def receive(S_c):
	S_i = transceive(S_c)
	M = revise(S_i)
	return M
```
Das Empfangsgerät sei der Mechanismus mit dem eine Nachricht aus einem Signal extrahiert wird.
Ein Sende- und Empfangsgerät seien kompatibel wenn stets gilt $receive(send(M, S_c)) = M$.

### semantische Kodierung (Kodierung)
Eine semantsiche Kodierung oder einfach nur Kodierung sei ein Paar aus den Funktionen $encode(H): M$ und $decode(M): H$ mit $M$ sei eine Nachricht und H sei eine Information.
Für alle Kodierungen gelte $encode(decode(M)) = M$
Wenn $decode(encode(H)) = H$ gilt so sei die Kodierung eindeutig.
	
# Vorstellung des Modells/Grundsätze
In dem bereits vorgestellten Modell von Shannon und Weaver hält der Sender eine Information, die er mithilfe eines Sendegeräts verschicken möchte.

Hierbei wird das Senden in das Kodieren, als Umwandeln der Nachricht in zum Beispiel Morsecode und dann das eigentliche verschicken als physikalische Aktion unterteilt.

In meinem Modell gehe ich noch einen Schritt weiter und setzte 3 Schritte an:

1) Zunächst wird die Information in eine Nachricht kodiert.
2) Anschließend wird die Nachricht zu einem Signal transformiert.
3) Das eigentliche Senden ist dann die physikalische Veränderung des Kanals um das Signal darzustellen.

Dieser Kodierschritt entspricht der semantischen Kodierung.
Der Transformationsschritt entspricht der technischen Kodierung.

Im Kodierungsschritt wird eine Information erstmals zu einem darstellbaren Symbol beziehungsweise einer Reihe von Symbolen.
Dazu im Gegensatz wird im Transformationsschritt ein ausdrückbares Symbol für jedes Symbol einer Nachricht ausgewählt.
Dies ermöglicht es im nächsten Schritt diese Symbole direkt auf einen Kanal zu übertragen.

Sowohl Transformation als auch Kodierung beschreiben die Fähigkeit eine Information auszudrücken.
Die Kodierung ist Kanalunabähngig und ist ausschließlich durch die Menge an bekannten Symbolen eingeschränkt.
Die Transformation hingegen ist kanalgebunden und ist durch die Menge an in einem Kanal darstellbaren Symbolen eingeschränkt.

Das abschließende Senden beschreibt wie effizient die darstellbaren Symbole überhaupt auf den Kanal übertragen werden.
Die Fähigkeit den Kanal zu veränden ist stak von der aktuellen Situation des Kanals abhängig.
Über das Sendegerät können auch ungewollte Änderungen (sogenante Seiteneffekte) des Kanals abgebildet werden.
So ist ein (guter) Musiker zwar in der Lage seine Gefühle in Worte (Kodierung) zu fassen und diese theoretisch als Lied vorzutragen (Transformation), wird aber ohne Verstärkung neben einer startenden Rakete nie Laut genug sein um dieses Lied auch hörbar zu machen.
Seiteneffekte könnten beim Auftritt des Musikers zum Beispiel die Geräusche sein, die er beim Betreten der Bühne verursacht oder visuelle Reize durch das Kostüm und die Beleuchtung.

Parallel dazu muss der Empfänger beim Emfpangen physikalsich in der Lage sein, ein Signal auf einem Kanal wahrnehmen zu können.
Anschließend muss er aus dem physikalischen Signal eine Sequenz an Symbolen zusammensetzen.
Der (De)-Kodierungsschritt entspricht hier dem eigentlichen verarbeiten der Nachricht zu einer Information.
Um bei dem Beispiel des Musikers zu bleiben, muss ein Fan im Publikum zunächst den Auftritt des Künstlers physikalisch wahrnehmen.
Die Geräusche müssen dann zunächst als Worte erkannt (Transformation) und anschließend als Beschreibungen (Kodierungen) verstanden werden.
Die Menge der wahrgenommen physikalischen Signale ist abhängig von der Emfpangsfähigkeit des Empfängers.
Seiteneffekte oder Störungen können das wahrgenommene Signal die emfpangene Nachricht für unterschiedliche Emfpänger drastisch beeinflussen.

## Ablauf
Eine Kommunikation zwischen Sender und Empfänger läuft in dem Modell folgene Schritte ab:

1) Der Sender möchte eine Information $H_A$ übertagen.
2) Diese Information wird durch das Kodiergerät zu einer Nachricht $M_A$.
3) Die Nachricht wird zu dem Sginal $S_{A}^{K}$
4) Das Sendegerät verändert das Signal $S_{0}^{K}$ des Kanal $K$ zu dem Signal $S_{A'}^{K}$.
5) Eine Störung verändert das Signal zu $S_{\omega}^{K}$
6) Das Emfpangsgerät extrahiert aus dem Kanal das Signal $S_{B}^{K}$.
7) Das Signal wird durch das Empfangsgerät zu der Nachricht $M_B$.
8) Im Dekodierschritt wird mithilfe des Dekodiergeräts die Nachricht zu einer Information $H_B$ umbgewandelt.
9) Diese Information kann schließlich durch den Emfpäger wahrgenommen werden.

## Störungen und Crosstalk
### Störungen
Die Kommunikation kann an mehrern Stellen gestört werden.

#### Kodierung
Wenn sich die sozialen Kontexte von Sender und Empfänger zu stark unterscheiden, ist der Kodier-Dekodier Prozess gestört.
Das kommt insbesonders dann zustande, wenn zum Beispiel ein Objekt als Zeichen der Zeitheit durch Bob, aber als Zeichen der Drittheit für Alice geprägt sind.

Je mehr gemeinsame Erfahrungen und kulturellen Kontext Alice und Bob gemeinsam haben, desto eindeutiger kann die Kodierung erfolgen.
Technisch gesehen sprechen wir hier von Symboltabellen wie z.B. Morsezeichen.
Wenn die Kommunkationspartner aufeinander abgestimmt sind, dann können immer kompaktere und effizientere Kodierungen benutzt werden.

#### Senden
Der Sendeprozess ist die Art wie ein Objet zu einem Repräsantamen wird.
Hierbei stellt das Sendegerät die Möglichkeiten zur Veränderung des Kanals da.
Aus Sicht der Informationstheorie ist das Sendegerät eine Funktion, die einen Nachrichtenvektor und eine Kanalmatrix zu einer resultierenden Kanalmatrix verarbeitet.
Die Kanalmatrix kann nur mithilfe eines Emfpangsgerät wahrgenommen werden.
Daher ist der aktuellen Zustand und damit der eingeschränkte Zustandsraum für den Sender nicht einsehbar.
Das bedeutet, dass der Sender auch Nachrichtenvektoren übergeben kann, die den Kanal effektiv nicht verändern.

#### Empfangen
Beim Empfangen wird aus einer Kanalmatrix durch eine Funktion ein Nachrichtenvektor erstellt.
Die Kanalmatrix kann zusätliche und andere Dimensionen hab
