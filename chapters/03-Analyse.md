\chapter{Analyse}
# Lösungsvorschlag für das semants
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

