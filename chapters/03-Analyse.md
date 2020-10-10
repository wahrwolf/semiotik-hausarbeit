\chapter{Analyse}
# Klassifizierung von Störungen
Mit dem neuen Modell lassen sich jetzt Störungen und Fehler in einem Kommunikationsprozess in verschiedene Klassen einteilen.
Die Klassifizierung orientiert sich an den Kommunikations-Phasen und Geräten von Sender und Empfänger.

## Erfolgreiche Kommunikation
Eine erfolgreiche Kommunkation setzt folgende Punkte voraus:

- Sende- und Empfangsgerät sind kompatibel
- Kodier- und Dekodiergerät sind kompatibel
- Trotz eines Rauschens gilt $receive(S_{B}) = M$ mit $send(M) + S_{\omega} = S_B$

## Rauschen
Bei einem Rauschen sind Empfangsgerät sowie Kodier- und Dekodiergerät kompatibel, aber eine im Kanal auftretende Störung verändert das Signal stark.
Im Beispiel des Musikers verhindert das Kreischen seines Nachbarn, dass der Fan den Musiker hören kann.
Alle Störungen die ein Signal nach dem Senden durch den Sender verändern, können als Kanalrauschen oder einfach Rauschen bezeichnet werden.

## Übertragungsstörung
Bei einer Übertragungsstörung ist das Sendegerät entweder nicht in der Lage den Kanal so zu verändern, dass er das transformierte Signal darstellt oder das Empfangsgerät kann das Signal nicht korrekt aus dem Kanal extrahieren.
Dies beinhaltet:

- fehlerhafte Koordination der Kommunikation
- eine zu hohe oder niedrige Sendeleistung
- eine zu hohe oder niedrige Filterempflindlichkeit
- eine falsche Kanalbreite (eine Nachricht wird sowohl visuell, als auch akustisch übertragen, aber der Empfänger wertet nur den akustischen Teil aus)

Übertagungsstörungen können nur vom Sender durch ein erneutes Übermitteln des Signals behoben werden.
Im Transformationsschritt kann die Verwendung von Prüfsummen \cite{tomasi93} die Erkennung und Behebung von Übertragungsstörungen ermöglichen.
In Protokollen wie TCP \cite{Stevens:93} werden Kommunikationsprozesse verschachtelt um Übertragungsstörungen zu reduzieren.

## Tranformationsstörung
Bei dieser Art von Störung funktioniert zwar die Übertragung der Signale, aber die Sende- und Empfangsgeräte benutzen nicht die gleichen Symbolen und die Transformation schlägt fehl.
In diese Klasse fallen Transformationsfehler durch die Verwendung von Akzente, Teekesselchen, Spitznamen und Abkürzungen.
Die Transformationsstörungen sind sehr ähnlich zu den semantischen Störungen und oft miteinander verschränkt.
Im Gegensatz zum Kodiergerät kann die Transformation für einen Kanal allerdings nicht geändert werden.
Mit dieser Aussage lässt sich die Abgrenzung klarer definieren: Wenn die Störung behoben werden kann ohne das sich der Kanal verändern muss, handelt es sich um eine semantische Störung.
Wenn also der Sender einfach die Sprache wechseln kann oder eine andere Formulierung verwendet handelt es sich um eine semantische Störung.
Wenn der Sender zusätzlich zu seinen Worten auch noch seine Körpersprache einsetzten muss um die Störung zu beheben, handelt es sich um eine Transformationsstörung.
Transformationsstörungen sind sehr schwer zu erkennen und zu beheben. Die Verwendung eines phonetischen Alphabets \cite{international99} oder öhnlichem kann hier helfen.

## semantische Störung
Bei einer semantischen Störung sind das Kodier- und Dekodiergerät nicht kompatibel.
Dies bedeutet, dass die Signale zwar ohne Verlust übertragen werden, aber die Dekodierung der Nachricht zu der eigentlichen Information gestört ist.
In einem Beispiel wurden zwar alle Worte gehört, aber die Kommunikationspartner sprechen eine unterschiedliche Sprache.
Eine semantische Störung kann sowohl durch den Sender erkannt und durch Wechsel des Dekodiergerätes behoben werden.
Um im Beispiel zu bleiben kann, der Empfänger versuchen die Nachricht in verschiedenen Sprachen (formal korrekt mit verschiedenen Kodiergeräten) zu verstehen.
Da eine Kommunikation in der Regel ein Nachrichtenaustausch und somit Interaktion auslösen kann, könnte der Sender Abweichungen von dem erwarteten Verhalten beobachten.
Die Informatik und insbesondere die Kommunikationstechnik bieten hier verschiedene Algorithmen wie Hashing und Handshakes an \cite{krawczyk97}.

# Bedeutung des neuen Modells
Mit dem neuen Modell und der Aufschlüsselung der Störungsklassen können bereits etablierte Modelle neu evaluiert.
Bekannte Probleme und Strategien in den Modellen können neu aufbereitet und analysiert werden.
Dies schafft erstmal eine Vergleichbarkeit von Modellen aus technischen und sozialen Wissenschaften

## Ausblick
Grundsätzlich können alle bestehenden Modelle und Algorithmen betrachtet werden.
Für besonders interessant halte ich Ansätze und Modelle aus der Psychologie und der Pädagogik.

- "Vier Seiten"-Modell von \cite{Thun:13} zur Untersuchung der Seiteneffekte bei einer Übertragung
- "Gesprächsblockierer" nach \cite{Gordon:12} als Analyse von Transformationsfehlern.
- "Dreikomponenten"-Modell nach \cite{Rosenberg:60} um die Einstellung als Teil der Übertragungsgeräte zu analysieren und praktische Kommunikationsstrategien zu entwickeln
