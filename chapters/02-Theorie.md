\chapter{Theorie}
# Level ist technisch lösbar
\cite{Shannon:62} schlagen einen "Semantisches Empfangsgerät" vor, der die Nachricht im weiteren Schritt semantisch verarbeitet.

Ich stelle im folgenden ein semantischenes Empfangs- beziehungsweise Sendegerät als Kodierer beziehungsweise Dekodierer vor.

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
Ein Symbol sei die Situation oder auch das Erscheinungsbild eines Signals.
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



# Einführung des Kodierers
Die obigen Defintion eines Symbols beziehungsweise eine Signales lassen sich auch nach der triadischen Relation nach Peirce ausdrücken.
Nach dem Modell von \cite{Shannon:62} würde gelten:

## triadische Relation des Sender-Emfpänger Models
- Das Signal entspricht dem Repräsntamen.
- Das Symbol entspricht dem Objekt
- Die Nachricht entspricht dem Interpretant

Nach dem infitinen semiotischen Regress gilt damit:

- Das Symbol entspricht dem Repräsntamen.
- Die Nachricht entspricht dem Objekt
- Die Information entspricht dem Interpretant

Bis wir im nächsten Schritt an den Abbruch kommen:

- Die Nachricht entspricht dem Repräsntamen.
- Die Information entspricht dem Objekt
- Die Information ist durch die Axiomisierung die "ultimate Opinion" nach \cite{Nagl:91}

Nun können wir die 3 Schritte bennen und bereits bekannten Definitionen zuordnen

## Phasen der Kommunikation
Für die Übertragung und die Transformation passen die Defintionen für Sende- und Empfangsgerät schon.
Für die Kodierung können wir die Definition aus \autoref{semantische-kodierung-kodierung} heranziehen.

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


Die so definierten Schritte lassen sich auch als Phasen einer Kommunikation begreifen.

# Ablauf
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

# Erläuterung und Vertiefung des Models
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

# Störungen
Wie in \autoref{ablauf} gezeigt und von \cite{Shannon:62} beschrieben kann auf einem Kanal eine Störung auftreten.
Diese verändert das empfangene Signal und stört oder verhindert damit die Kommunikation.

Durch die Erweiterung des Models und die Aufteilung in Kodierung, Transformation und Übertragung können wir die Auswirkungen eines Rauschen genauer betrachten.

## Erfolgreiche Kommunikation
Eine erfolgreiche Kommunkation setzt folgende Punkte voraus:

- Sende- und Empfangsgerät sind kompatibel
- Kodier- und Dekodiergerät sind kompatibel
- trotz der Störung gilt $receive(S_{B}) = M$ mit $send(M) + S_{\omega} = S_B$

## semantische Störung
Bei einer semantischen Störung sind das Kodier- und Dekodiergerät nicht kompatibel.
Dies bedeutet, dass die Signale zwar ohne störung übertragen werden, aber die Übersetzung der Nachricht zu der eigentlichen Information gestört ist.
In einem Beispiel wurden zwar alle Worte gehört, aber die Kommunikationspartner sprechen eine unterschiedliche Sprache.
Eine semantische Störung muss die Kommunkation aber nicht vollständig verhindern und kann in einigen Fällen erkannt und behoben werden.
Um im Beispiel zu bleiben kann, der Sender versuchen die Nachricht in verschiedenen Sprachen (formal korrekt mit verschiedenen Kodiergeräten) formulieren.
Da eine Kommunikation in der Regel ein Nachrichtenaustausch und somit Interaktion auslösen kann, könnte der Sender Abweichungen von dem erwarteten Verhalten beobachten.
Die Informatik und insbesondere die Kommunikationstechnik bieten hier verschiedene Algorithmen wie Hashing und Handshakes an \cite{krawczyk97}.

## Übertragungsstörung
Bei einer Übertragungsstörung ist das Sendgerät entweder nicht in der Lage den Kanal so zu verändern, dass er das transformierte Signal darstellt oder das Empfangsgerät kann das Signal nicht korrekt aus dem Kanal extrahieren.
Dies beinhaltet sowohl fehlerhafte Koordination der Kommunikation, eine zu hohe oder niedrige Sendeleistung, eine zu  hohe oder niedrige Filterempflindlichkeit oder eine falsche Kanalbreite (eine Nachricht wird sowohl visuell, als auch akustisch übertragen, aber der Empfänger wertet nur den akustischen Teil aus).
Übertragungsstörung können zum Teil durch Sender oder Emfpänger eigenständig behoben werden, indem zum Beispiel versucht wird ein gesendetes Signal selbst zu emfpangen.
Die Verwendung von Prüfsummen \cite{tomasi93} kann die Erkennung und Behebung von Übertragungsstörung stark vereinfachen.

## Tranformationsstörung
Bei dieser Art von Störung funktioniert zwar die physikalische Übertragung der Signale, aber die Sende- und Empfangsgeräte benutzen nicht die gleiche Menge von Symbolen.
Hierzu Zählen zum Beispiel Akzente oder auch Teekesselchen, die Verwendung von Spitznamen und Abkürzungen.
Die Transformationsstörungen sind sehr ähnlich zu den semantschen Störungen und oft miteinander verschränkt.
Im Gegensatz zum Kodiergerät kann die Transformation für einen Kanal allerdings nicht geändert werden.
Mit dieser Aussage lässt sich die Abrenzung klarer definieren: Wenn die Störung behoben werden kann ohne das sich der Kanal verändern muss, handelt es sich um eine semantische Störung.
Wenn also der Sender einfach die Sprache wechseln kann oder eine andere Formulierung verwendet handelt es sich um eine semantische Störung.
Wenn der Sender zusätzlich zu seinen Worten auch noch seine Körpersprache einsetzten muss um etwas zu beschreiben, handelt es sich um eine Transformationsstörung.
Transformationsstörungen sind sehr schwer zu erkennen und zu beheben. Die Verwendung eines phonetischen Alphabets \cite{international99} oder öhnlichem kann hier helfen.

## Rauschen
Bei einem Rauschen sind Empfangsgerät sowie Kodier- und Dekodiergerät kompatibel, aber eine im Kanal auftretende Störung verändert das Signal stark.
In einem Beispiel kann der Emfpänger zum Beispiel wegen eines lauten Geräuches nur einige oder gar keine Worte hören.
In der Realität ist es schwierig Rauschen von Übertragungsstörungen zu unterscheiden.

