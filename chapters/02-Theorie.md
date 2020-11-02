\chapter{Theorie}
Wie im vorherigen Kapitel gezeigt, behandeln Shannon&Weaver andere Aspekte der Kommunikation als Peirce.
Obwohl die Modelle aus sehr unterschiedlichen Forschungsrichtungen kommen, beschreiben die Autoren sie mit ähnlichen Begriffen.

Im nächsten Teil werde ich ihre Modelle zusammenführen.
Hierzu verwende ich das "Sender-Empfänger" Modell mit den beiden Phasen "Kodieren" und "Übertragen" als Grundlage.
Anschließend erweitere ich diese Phasen mithilfe des infiniten semiotischen Regresses um es in ein drei phasiges "Sender-Kodierer-Empfänger" Modell zu überführen.

Ich stelle im folgenden ein semantisches Empfangs- beziehungsweise Sendegerät als Kodierer beziehungsweise Dekodierer vor.

# Definitionen
Da die Semiotik und die technische Informatik teilweise unterschiedliches Vokabular verwenden, definiere ich zunächst die notwendigen Begriffe.
Die Erläuterung und Verwendung im Modell folgt nach Darstellung der Definitionen

## Grundlagen
Bevor wir über Kommunikation sprechen, müssen wir erst ein paar Begriffe aus der Informationstheorie und Mathematik einführen.
Diese Definitionen sind angelehtn an \citet{Cormen:09}

### Axiom
Ein Axiom sei eine atomare Aussage die zu einem finiten Zeitpunkt genau einen Wahrheitswert (wahr, falsch, unbekannt) haben kann.

### Theorem
Eine aus mindestens einem Axiom nach dem boolschen Algebra abgeleitete Aussage.

### Information
Eine Information sei eine Menge von Aussagen

### Axiomsystem
Ein Axiomsystem sei ein Tupel aus einer Menge Variablen, einer Menge an Axiomen und einer Menge an Operationen zur Verknüpfung der Variablen


## Hilfsdefintionen
Im nächsten Abschnitt definiere ich Begriffe, die so weder in der Semiotik noch in der Informatik verwendet werden.
Diese Definitionen sind die Grundlage für die folgende Modelldefinition und ermöglichen eine natürlichere Beschreibung des Modells ohne es in seiner Komplexität oder Gültigkeit einzuschränken.
Diese Definitionen entstammen nicht der Literatur.

### Realität
Eine Realität sei ein Axiomsystem mit folgenden Besonderheiten:

* Die Menge der Variablen sei endlich
* Die Operationen seien die der boolschen Algebra
* Die Axiome seien nach der boolschen Algebra widerspruchsfrei

### Situation
Eine Situation sei eine endliche Menge von deterministischen Aussagen, deren Wahrheitswerte ausschließlich wahr oder falsch sind.
Wenn es für jede Aussage einer Situation ein Theorem gibt, dass dieses aus den Axiomen einer Realität ableitet, so gelte die Situation in Bezug zu der Realität als möglich.
Diese Definitionen basieren auf meinen eigenen Hilfsdefinitionen und stammen nicht aus der Literatur.

## Begriffe der Kommunikation
Im nächsten Abschnitt folgen Begriffe der Kommunikation.
Diese Definitionen basieren auf der eingeführten Terminologie und enthalten alle Bestandteile der Modellbeschreibung.
Sie entstammen nicht der Literatur.

### Kommunikationskanal
Ein Kommunikationskanal oder kurz Kanal sei eine Realität in der mehr als eine Situation möglich sei.

### Signal
Ein Signal sei ein Tupel aus einem Kommunikationskanal und einer Situation.

### Symbol
Ein Symbol sei die Situation oder auch das Erscheinungsbild eines Signals.
Wenn ein Symbol in einem Signal enthalten ist, so gelte es als ausdrückbar durch das Signal.

### Nachricht
Eine Nachricht sei eine Sequenz von Symbolen

## Modellspezifische Begriffe
Im nächsten Abschnitt benutze ich die eben definierten Begriffe der Kommunikationen um zunächst die Bestandteile des "Sender-Empfänger" Modells mit der eingeführten Terminologie zu beschreiben und um anschließend den fehlenden "semantischen Kodierer" zu definieren.
Diese Definitionen basieren auf meinen eigenen Hilfsdefinitionen und stammen nicht aus der Literatur.

### technische Kodierung (Transformation)
Eine technische Kodierung sei ein Paar aus den Funktionen $prepare(s, C): S$ sowie $revise(S): s$ mit $s$ sei ein Symbol, $C$ sei ein Kanal und $S$ sein ein Signal
Die Transformation sei also der Mechanismus, der ein Symbol zu einem übertragbaren Signal vorbereitet und ebenso eine Möglichkeit bietet ein Symbol aus einem Signal zu lesen.
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

### Semantische Kodierung (Kodierung)
Eine semantische Kodierung oder einfach nur Kodierung sei ein Paar aus den Funktionen $encode(H): M$ und $decode(M): H$ mit $M$ sei eine Nachricht und H sei eine Information.
Für alle Kodierungen gelte $encode(decode(M)) = M$
Wenn $decode(encode(H)) = H$ gilt, so sei die Kodierung eindeutig.

# Differenzierung der Kommunikationsphasen
Mit den obigen Begriffen möchte ich jetzt die Kommunikation im Modell betrachten.
Das Modell der Korrelate erlaubt hier, die Beziehung der Komponenten in dem Kommunikationsprozess zu beschreiben.

## Betrachtung der Korrelate im Sender-Empfänger Modell
Die obige Definition eines Symbols beziehungsweise eine Signales lässt sich auch nach der triadischen Relation von Peirce ausdrücken.

Nach dem Modell von \citet{Shannon:62} würde gelten:

- Das Signal entspricht dem Repräsentamen.
- Das Symbol entspricht dem Objekt
- Die Nachricht entspricht dem Interpretant

Nach dem infiniten semiotischen Regress ist der Prozess der Wahrnehmung der Signale aber noch nicht abgeschlossen.
Also gilt im nächsten Abstraktionsschritt:

- Das Symbol entspricht dem Repräsentamen.
- Die Nachricht entspricht dem Objekt
- Die Information entspricht dem Interpretant

Wird der Regress ein weiteres Mal angewendet, stößt er  an die Grenzen des Modells:

- Die Nachricht entspricht dem Repräsentamen.
- Die Information entspricht dem Objekt
- Es gibt keine Interpretant

Auch wenn der infinite Regress keinen Abschluss in der Korrelaten Kette findet, so gibt es  nach \citet{Nagl:91} die sogenannte "ultimate opinion".
\citet{Nagl:91} beschreibt die "ultimate opinion" als Menge von nicht darstellbaren Aussagen, was sich mit der obigen Definition der Information deckt.

## Phasen des Empfangens
Nimmt man die Abstraktionsebenen des Regresses als Ebenen oder Phasen der Wahrnehmung beziehungsweise des Empfangens, können sie wie folgt benannt werden:

- Wahrnehmung einer Übertragung
   - Das Signal entspricht dem Repräsentamen.
   - Das Symbol entspricht dem Objekt
   - Die Nachricht entspricht dem Interpretant

- Lesen von Symbolen
   - Das Symbol entspricht dem Repräsentamen.
   - Die Nachricht entspricht dem Objekt
   - Die Information entspricht dem Interpretant

- Verstehen einer Nachricht
   - Die Nachricht entspricht dem Repräsentamen.
   - Die Information entspricht dem Objekt
   - Die Information ist durch die Axiomatisierung die "ultimate Opinion" nach \citet{Nagl:91}

## Modellierung des Sendens als inversives Empfangen
Die oben definierten Phasen des Sendens beschreiben den Extraktionsprozess von Information aus Signalen.
Unter der Annahme eines symmetrischen Prozesses können wir die Phasen invertieren und kommen so zu sechs Schritten:

1) Formulierung einer Nachricht
2) Auswählen von Symbolen
3) Verschicken einer Übertragung
4) Wahrnehmung einer Übertragung
5) Lesen von Symbolen
6) Verstehen einer Nachricht

Die Symmetrie Paare in diesem Prozess können dann als die Kommunikationsphasen Kodierung, Transformation und Übertragung bezeichnet werden.

# Einführung des Sender-Kodierer-Empfänger Modells
Mithilfe der Definitionen für Sende- und Kodiergeräte sowie der Beschreibung der Kommunikationsphasen erweitere ich das ursprüngliche Sender-Empfänger Modell um den Kodierschritt.

## Formale Beschreibung eines Kommunikationsprozesses
Eine Kommunikation zwischen Sender und Empfänger im neuen Modell läuft in folgenden Schritten:

1) Der Sender möchte eine Information $H_A$ übertagen.
2) Diese Information wird durch das Kodiergerät zu einer Nachricht $M_A$.
3) Die Nachricht wird zu dem Signal $S_{A}^{K}$
4) Das Sendegerät verändert das Signal $S_{0}^{K}$ des Kanal $K$ zu dem Signal $S_{A'}^{K}$.
5) Eine Störung verändert das Signal zu $S_{\omega}^{K}$
6) Das Empfangsgerät extrahiert das Signal $S_{B}^{K}$ aus dem Kanal.
7) Das Signal wird durch das Empfangsgerät zu der Nachricht $M_B$.
8) Die Nachricht wird mithilfe des Dekodiergeräts zu einer Information $H_B$ umgewandelt.
9) Diese Information kann schließlich durch den Empfänger wahrgenommen werden.

## Erläuterung und Vertiefung des Models
In dem bereits vorgestellten Modell von Shannon und Weaver hat der Sender eine Information, die er mithilfe eines Sendegeräts verschicken möchte.

Hierbei wird das Senden in das Kodieren, als Umwandeln der Nachricht in zum Beispiel Morsecode und dann das eigentliche Verschicken als physikalische Aktion unterteilt.

### Phasen der Kommunikation
Im neuen "Sender-Kodierer-Empfänger"-Modell gehe ich noch einen Schritt weiter und setzte 3 Schritte an:

1) Die Information wird als Nachricht kodiert
2) Die Nachricht wird zu einem Signal transformiert
3) Das Signal wird auf einen Kanal gesendet

Der 1. Schritt ist die semantische Kodierung oder einfach nur Kodierung.
Der 2. Schritt ist die technische Kodierung oder Transformation.
Der 3. Schritt ist die Übertragung.

#### Kodierung
Bei dem Kodierschritt wird eine Information erstmals zu einem darstellbaren Symbol beziehungsweise einer Reihe von Symbolen.
Im Gegensatz dazu wird im Transformationsschritt ein ausdrückbares Symbol für jedes Symbol einer Nachricht ausgewählt.
Dies ist notwendig um die Nachricht im Übertragungsschritt als Signal zu versenden.

#### Transformation
Sowohl Transformation als auch Kodierung beschreiben die Fähigkeit eine Information auszudrücken.
Die Kodierung ist kanalunabähngig und nur durch die Menge an bekannten Symbolen eingeschränkt.
Die Transformation hingegen ist kanalgebunden und auf die darstellbaren Symbolen des Kanals eingeschränkt.

#### Übertragung
Die Übertragung beschreibt, wie effizient die darstellbaren Symbole überhaupt auf den Kanal gesendet werden.
Die Fähigkeit den Kanal zu verändern ist von der aktuellen Situation des Kanals abhängig.

#### Erläuterung am Beispiel
Über das Sendegerät können auch ungewollte Änderungen (sogenannte Seiteneffekte) des Kanals abgebildet werden.
So ist ein (guter) Musiker zwar in der Lage seine Gefühle in Worte (Kodierung) zu fassen und diese theoretisch als Lied vorzutragen (Transformation), wird aber ohne Verstärkung neben einer startenden Rakete nie laut genug sein um dieses Lied auch hörbar zu machen.
Seiteneffekte könnten beim Auftritt des Musikers zum Beispiel die Geräusche sein, die er beim Betreten der Bühne verursacht oder visuelle Reize durch das Kostüm und die Beleuchtung.

Parallel dazu muss der Empfänger beim Empfange physikalisch in der Lage sein, das Signal auf einem Kanal wahrnehmen zu können.
Anschließend muss er aus dem Signal eine Sequenz an Symbolen herauslesen.
Der (De)-Kodierungsschritt entspricht hier dem eigentlichen Verarbeiten der Nachricht zu einer Information.
Im Beispiel des Musikers  muss ein Fan im Publikum zunächst den Auftritt des Künstlers physikalisch wahrnehmen.
Die Geräusche werden dann als Worte erkannt (Transformation) und anschließend als Beschreibungen (Kodierungen) verstanden werden.
Die Menge der wahrgenommen physikalischen Signale ist abhängig von dem Empfangsgerät des Empfängers.
Seiteneffekte oder Rauschen beeinflussen das wahrgenommene Signal für jeden Empfänger unterschiedlich.
