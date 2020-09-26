# Shannon-Weaver
Shannon und Weaver haben im \TODO{Zitat einfügen} ihr "Sender-Emfpänger" Model vorgestellt.

## Beschreibung des Models
### Ablauf einer Kommunikation
Wie in Abbildung \TODO{Bild einfügen} dargestellt modellieren Shannon und Weaver Kommunkation wie folgt:
Ein Sender (Information Source) wählt eine Nachricht aus einer Menge von möglichen Nachrichten aus.

Mithilfe eines Sendegeräts wandelt er die Nachricht in ein Signal um, dass über einen Kommunikationskanal zu einem Emfpangsgerät gesendet wird.

Das Empfangsgerät wandelt das Signal wieder in eine Nachricht, die von dem Empfänger verarbeitet werden kann.

### Auftreten einer Störung
Während der Übertragung kann der Kommunikationskanal durch ein Rauschen gestört werden.
Dies verändert das übertragene Signal und kann somit verhindern, dass eine Nachricht korrekt übertragen wird.

## Information und Entropie
In ihrer Arbeit erläutern Shannon und Weaver außerdem die Beziehung zwischen Bedeutung und Information einer Nachricht ein.
So ist in ihrer Definition die Information die Anzahl der Ausdrucksmöglichkeiten die eine Nachricht annehmen kann.
Die Entropie entspricht der Reduktion der Unsicherheit durch den Erhalt einer Nachricht.

Eine Nachricht hat also eine Information die in Bit gemessen wird und die Größe der Nachricht darstellt.
Die Kommunikation ist demnach der Prozess der Entropiereduktion einer Nachricht eines Senders zu einem Empfänger bis sich die Entropie der Nachricht durch das Empfangen weiterer Symbole nicht mehr verändert.

## Probleme der Kommunikation
### Level A: The technical problem
Als technisches Problem definieren Shannon und Weaver die Frage: Wie präzise können Symbole einer Kommunikation übertragen werden?
Mithilfe der obigen Definition der Information lässt sich zeigen, dass die Übertragung abhängig von dem Kanal und der verwendeten  Kodierung ist.
Für eine Menge aus Symbolen lässt sich die Kommunikation in Abhängikeit von der Wahrscheinlichkeitsverteilung der erwarteten Ereignisse optimieren.

### Level B: The semantic problem
Das semantische Problem fragt: Wie präzise können übertragene Symbole die gewünschte Bedeutung vermitteln?
Diese Frage ist laut Weaver von der Beanwortung des technischen Problems stark abhängig, aber zunächst nicht allgemein lösbar.
Auch wenn das Problem theoretisch nicht lösbar ist, da ein Fehler in der Semantik die Kommunikation und die Diagnose des Fehlers komplett verhindert, so sieht Weaver hier kein praktisches Problem.
In einer Konversation gäbe es selbst bei komplett verschiedenen Sprachen schon nach einigen Sätzen eine Konsens über die Wörter "ja" und "Nein". 

### Level C: The effectiveness problem
Das dritte Problem fragt: Wie effizient führt die übertragene Bedeutung zu einer gewünschten Aktion?
Aufbauend auf dem semantischen Problem sehen Shannon und Weaver große Schwierigkeiten bei dem Verhältnis zwischen empfangene Bedeutung und gewünschter Aktion.
Da Kommunikation sehr viele unterschiedliche Aktionen hervorrufen kann, sei es schwierig Erfolg allgemein zu quantifizieren.
