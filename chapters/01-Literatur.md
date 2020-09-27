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
Charles Sanders Peirce prägte die Semiotik insbesondere durch die Einführung der Kateogrienlehre und der triadischen Zeichenbedeutung.

## triadische Zeichendeutung
In der Semiotik nach \cite{Peirce:02} besteht ein Gegenstand aus 3 Teilen, die ihn als Zeichen definieren.

### Objekt
Das Objekt bezeichnet das Bezugsobjekt. Dies entspricht der Identität des Gegenstands, nicht aber deren Aussehen.

### Repräsentamem
Der Repräsentamen bezeichnet die äußere Gestalt des Zeichens. Hiermit ist die Wahrnehmung oder das Aussehen des Gegenstands gemeint.

### Interpretant
Der Interpretant bezeichnet die innere Bedeutung des Gegenstands. Der Interpretant ist die Wirkung die ein Repräsentamen beim einwirken uaf einen Interpretant verursacht. Andere Übersetzungen nehmen hier die "Bedeutung" oder den Inhalt des Zeichens an.

In einem Beispiel eines Apfels auf einem Tisch gelten folgende Beziehungen:

- der Apfel als solcher ist ein Objekt. Der Apfel ist als Objekt einzigartig. Es mag andere Äpfel geben, aber als Objekt gesehen ist er einzigartig. Wenn jemand dazu augefordert werden würde den Apfel zu bewegen, so würde das Objekt gemeint sein und kein anderer Apfel
- das Bild des Apfels als physikalische Reize stellen das Repräsentamen dar. Jede Beschreibung oder Wahrnehmung des Apfels in Form, Farbe, Geschmack bezieht sich ausschließlich auf das Repräsentamen. 
- Die Unterscheidung des Apfels von der Umwelt sowie das Verständnis über die Möglichkeiten der Interaktion mit dem Apfel sowie das Wissen über mögliche Eigenschaft die aus dem Repräsentamen wahrgenommen werden können sind das Interpretant. Das Wissen darüber das und wie der Apfel bewegt werden schließen dies ein.



## infiter semiotischer Regress
Die Wahrnehmung eines jeden möglichen Gegenstands führt stets zu einer Aufteilung in Objekt, Interpretant und Repräsentamen.
Das bedeutet aber, dass der Interpretant eines Objekts direkt wieder zu einem Repräsentamen wird.

Wird ein Apfel beobachtet, dann werden die wahrgenommen Eigenschaften (zum Beispiel die Kombination aus Farbe und Form) eine anderes Repräsentamen des Apfels.
Form und Farbe sind ausreichend um den Apfel zu erkennen.
Im nächsten Schritt kann eine reduzierte oder veränderte wahrnehumung (zum Beispiel Kreis mit Biss) als Repräsentemn von Form und Farbe werden.
Dieser Prozess ist theoretisch endlich tief.
Nach \cite{Noeth85} wird dieser aber ab einer frühen Stufe abgebrochen.
