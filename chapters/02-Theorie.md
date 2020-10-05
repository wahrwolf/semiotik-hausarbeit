\chapter{Theorie}
Wie im voherigen Kaptiel gezeigt, behandeln Shannon&Weaver andere Aspekte der Kommunikation als Peirce.
Obwohl die Modelle aus sehr unterschiedlichen Forschungsrichtungen kommen, verwenden sie kompatible Begriffe.

Im nächsten Teil werde ich diese Begriffe zusammenführen und die Modelle miteinander kombinieren.
Hierzu verwende ich das "Sender-Empfänger" mit den beiden Phasen "Kodieren" und "Übertragen" als Grundlage.
Anschließend erweitere breche ich diese Phasen mithilfe des infitien semitoischen Regresses auf um es in ein drei phasiges "Sender-Kodierer-Empfänger" Modell zu überführen.

Ich stelle im folgenden ein semantischenes Empfangs- beziehungsweise Sendegerät als Kodierer beziehungsweise Dekodierer vor.

# Definitionen
Da die Semiotik und die technische Informatik teilweise unterschiedliches Vokabular verwenden, definiere ich zunächst ein paar Begriffe.
Die Erläuterung und Verwendung im Modell folgt nach allen Defintionen.

## Grundlagen
Bevor wir über Kommunikation sprechen, müssen wir erst ein paar Begriffe aus der Informationstheorie und Mathematik einführen.

### Axiom
Ein Axiom sei eine atomare Aussage die zu einem finiten Zeitpunkt genau einen Wahrheitswert (wahr, falsch, unbekannt) haben kann.

### Theorem
Eine aus mindestens einem Axiom nach dem boolschen Algebra abgeleitete Aussage.

### Information
Eine Information sei eine Menge von Aussagen

### Axiomsystem
Ein Axiomssystem sei ein Tupel aus einer Menge Variablen, einer Menge an Axiomen und einer Menge an Operationen zur Verknüpfung der Variablen


## Hilfsdefintionen
Im nächstne Abschnitt definiere ich ein paar Begriffe, die so weder in der Semiotik noch in der Informatik verwendet werden.
Der Aufbau der Definitonen sind die Grundlage für die folgende Modelldefinition und ermöglichen eine natürlichere Beschreibung des Modells ohne es in seiner Komplexität oder Gültigkeit einzuschränken.

### Realität
Eine Realität sein ein Axiomssystem mit folgenden Besonderheiten:

* Die Menge der Variablen sei endlich
* Die Operationen seien die der boolschen Algebra
* Die Axiome seien nach der boolschen Algebra widerspruchsfrei

### Situation
Eine Situation sei eine endliche Menge von deterministischen Aussagen, deren Wahrheitswerte ausschließlich wahr oder falsch sind.
Wenn es für jede Aussage einer Situation ein Theorem gibt, dass dieses aus den Axiomen einer Realiät ableitet, so gelte die Situation in Bezug zu der Realiät als möglich.

## Begriffe der Kommunikation
Der nächste Abschnitt enthält Definitionen für typische Begriffe in der Kommunikation.
Diese Definitionen basieren auf der eingeführten Terminologie und enthalten alle Bestandteile der Modellbeschreibung.

### Kommunikationskanal
Ein Kommunikationskanal oder kurz Kanal sei eine Realität in der mehr als eine Situation möglich sei.

### Signal
Ein Signal sei ein Tupel aus einem Kommunikationskanal und einer Situation.

### Symobl
Ein Symbol sei die Situation oder auch das Erscheinungsbild eines Signals.
Wenn ein Sybmol in einem Signal enthalten ist, so gelte es als ausdrückbar durch das Signal.

### Nachricht
Eine Nachricht sei eine Sequenz von Symbolen

## Modelspezifisch Begriffe
Im letzten Abschnitt benutze ich die eben definierten Begriffe der Kommunikationen um zunächst die Bestandteile des "Sender-Empfänger" Modells mit der eingeführten Terminologie zu beschreiben und anschließend den fehlenden "semantischen Kodierer" zu definieren.

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

# Differenzierung der Kommunikationsphasen
Mit den obigen Begriffen können wir jetzt die Kommunikation im Modell betrachten.
Das Modell der Korrelate erlaubt uns hier, die Beziehung der Komponenten in dem Kommunikationsprozess zu beschreiben.

## Betrachtung der Korrelate im Sender-Empfänger Modell
Die obigen Defintion eines Symbols beziehungsweise eine Signales lassen sich auch nach der triadischen Relation nach Peirce ausdrücken.

Nach dem Modell von \cite{Shannon:62} würde gelten:
- Das Signal entspricht dem Repräsntamen.
- Das Symbol entspricht dem Objekt
- Die Nachricht entspricht dem Interpretant

Nach dem infitinen semiotischen Regress ist der Prozess der Wahrnehmung der Signale aber nocht nicht abgeschlossen.
Also gilt im nächsten Abstraktionsschritt:

- Das Symbol entspricht dem Repräsntamen.
- Die Nachricht entspricht dem Objekt
- Die Information entspricht dem Interpretant

Wenn wir den Regress ein weiteres Mal verwenden kommen wir allerdings an die Grenzen unseres Modells:

- Die Nachricht entspricht dem Repräsntamen.
- Die Information entspricht dem Objekt
- Es gibt keine Interpretanten

Auch wenn der infinite Regress keinen Abschluss in der Korrelaten Kette findet, so gibt es  nach \cite{Nagl:91} die sogenannte "ultimate opinion".
Diese beschreibt er als Menge von nicht darstellbaren Aussagen, was sich mit unserer Defintion der Information deckt.

## Phasen der Kommunikation
Wenn wir die Abstraktionsebenen des Regresses als Ebenen oder Phasen der Kommunikation begreifen, können wir diese wie folgt benennen:

- Übertragung
   - Das Signal entspricht dem Repräsntamen.
   - Das Symbol entspricht dem Objekt
   - Die Nachricht entspricht dem Interpretant

- technische Kodierung (Transformation)
   - Das Symbol entspricht dem Repräsntamen.
   - Die Nachricht entspricht dem Objekt
   - Die Information entspricht dem Interpretant

- semantsiche Kodierung (Kodierung)
   - Die Nachricht entspricht dem Repräsntamen.
   - Die Information entspricht dem Objekt
   - Die Information ist durch die Axiomisierung die "ultimate Opinion" nach \cite{Nagl:91}


# Einführung des Sender-Kodierer-Empfänger Modells
Mithilfe der Definitionen für Sende- und Kodiergeräte sowie der Beschreibung der Kommunikationsphasen können wir das ursprüngliche Sender-Empfänger Modell um den Kodierschritt erweitern

## Formale Beschreibung eines Kommunikationsprozesses
Eine Kommunikation zwischen Sender und Empfänger läuft nach durch folgende Schritte:

1) Der Sender möchte eine Information $H_A$ übertagen.
2) Diese Information wird durch das Kodiergerät zu einer Nachricht $M_A$.
3) Die Nachricht wird zu dem Sginal $S_{A}^{K}$
4) Das Sendegerät verändert das Signal $S_{0}^{K}$ des Kanal $K$ zu dem Signal $S_{A'}^{K}$.
5) Eine Störung verändert das Signal zu $S_{\omega}^{K}$
6) Das Emfpangsgerät extrahiert aus dem Kanal das Signal $S_{B}^{K}$.
7) Das Signal wird durch das Empfangsgerät zu der Nachricht $M_B$.
8) Im Dekodierschritt wird mithilfe des Dekodiergeräts die Nachricht zu einer Information $H_B$ umbgewandelt.
9) Diese Information kann schließlich durch den Emfpäger wahrgenommen werden.

## Erläuterung und Vertiefung des Models
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
