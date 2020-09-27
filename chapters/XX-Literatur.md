\chapter{Literatur}
# Shannon-Weaver
In der Kommunikationstheorie gilt das "Sender-Emfpänger" Modell von  \cite{Shannon:62} als die Grundlage der technischen Kommunikation.
Es veranschaulicht die grundlgenden Probleme bei der Kommunikation und führt erstmals Bit als Maßeinheit für Information ein.

## Beschreibung des Models
### Ablauf einer Kommunikation
Wie in Abbildung \TODO{Bild einfügen} dargestellt modellieren \cite{Shannon:62} Kommunkation wie folgt:
Ein Sender (Information Source) wählt eine Nachricht aus einer Menge von möglichen Nachrichten aus.

Mithilfe eines Sendegeräts wandelt er die Nachricht in ein Signal um, dass über einen Kommunikationskanal zu einem Emfpangsgerät gesendet wird.

Das Empfangsgerät wandelt das Signal wieder in eine Nachricht, die von dem Empfänger verarbeitet werden kann.

### Auftreten einer Störung
Während der Übertragung kann der Kommunikationskanal durch ein Rauschen gestört werden.
Dies verändert das übertragene Signal und kann somit verhindern, dass eine Nachricht korrekt übertragen wird.

## Information und Entropie
In ihrer Arbeit erläutern \cite{Shannon:62} außerdem die Beziehung zwischen Bedeutung und Information einer Nachricht ein.
So ist in ihrer Definition die Information die Anzahl der Ausdrucksmöglichkeiten die eine Nachricht annehmen kann.
Die Entropie entspricht der Reduktion der Unsicherheit durch den Erhalt einer Nachricht.

Eine Nachricht hat also eine Information die in Bit gemessen wird und die Größe der Nachricht darstellt.
Die Kommunikation ist demnach der Prozess der Entropiereduktion einer Nachricht eines Senders zu einem Empfänger bis sich die Entropie der Nachricht durch das Empfangen weiterer Symbole nicht mehr verändert.

## Probleme der Kommunikation
### Level A: The technical problem
Als technisches Problem definieren \cite{Shannon:62} die Frage: Wie präzise können Symbole einer Kommunikation übertragen werden?
Mithilfe der obigen Definition der Information lässt sich zeigen, dass die Übertragung abhängig von dem Kanal und der verwendeten  Kodierung ist.
Für eine Menge aus Symbolen lässt sich die Kommunikation in Abhängikeit von der Wahrscheinlichkeitsverteilung der erwarteten Ereignisse optimieren.

### Level B: The semantic problem
Das semantische Problem fragt: Wie präzise können übertragene Symbole die gewünschte Bedeutung vermitteln?
Diese Frage ist laut \cite{Shannon:62} von der Lösung des technischen Problems stark abhängig, aber zunächst nicht allgemein lösbar.
Dies gilt insbesondere da eine Störung in der Semantik die Kommunikation und die Diagnose des Fehlers komplett verhindert.
\cite{Shannon:62} sehen hier allerdings kein kein praktisches Problem.
In einer Konversation gäbe es selbst bei komplett verschiedenen Sprachen schon nach einigen Sätzen eine Konsens über die Wörter "ja" und "Nein". 
Um das Problem genauer zu untersuchen schlagen \cite{Shannon:62} die Verwendung eines "semantischen Kodierers" vor, deren Implementation sie aber offen lassen.

### Level C: The effectiveness problem
Das dritte Problem fragt: Wie effizient führt die übertragene Bedeutung zu einer gewünschten Aktion?
Aufbauend auf dem semantischen Problem sehen Shannon und Weaver große Schwierigkeiten bei dem Verhältnis zwischen empfangene Bedeutung und gewünschter Aktion.
Da Kommunikation sehr viele unterschiedliche Aktionen hervorrufen kann, sei es schwierig Erfolg allgemein zu quantifizieren.

# Peirce
Charles Sanders Peirce stellt in seinen Werken der Semiotik insbesondere in der Kategorienlehre
