\chapter{Literatur}
Ich stelle zunächst das Sender-Empfänger Modell von \citet{Shannon:62} aus der Informatik vor und anschließend das Korrelate Modell von \cite{Peirce:60} aus der Semiotik.
Bei beiden Modellen gehe ich außerdem kurz auf die aus dem Modell resultierenden Schlussfolgerungen und Fragestellungen ein.

# Shannon-Weaver
In der Kommunikationstheorie gilt das "Sender-Empfänger" Modell von  \citet{Shannon:62} als die Grundlage der technischen Kommunikation.
Es veranschaulicht die grundlegenden Probleme bei der Kommunikation.

\citet{Shannon:62} führen erstmals das Bit als Maßeinheit für Information ein und differenzieren Information von Bedeutung formal.

## Sender-Empfänger Modell
### Beschreibung des Models
Die Kommunikation findet stets zwischen zwei Teilnehmern statt, zwischen denen eine Nachricht übertragen wird.
Dieser Vorgang kann beliebig oft wiederholt werden.

Der Sender hat ein Sendegerät mit dem eine Nachricht verschicken werden kann.
Der Empfänger hat ein Empfangsgerät, mit dem eine Nachricht empfangen werden kann.
Zwischen dem Sender und dem Empfänger liegt ein sogenannter Kommunikationskanal oder kurz Kanal.
Das Sende- und das Empfangsgerät sind mit dem Kanal verbunden.

#### Ablauf einer Kommunikation
\citet{Shannon:62} modellieren Kommunikation wie folgt:

1) Ein Sender (Information Source) wählt eine Nachricht aus einer Menge von möglichen Nachrichten aus.
2) Die Nachricht wird mit dem Sendegerät (Transmitter) an den Kanal geschickt
3) Die Nachricht wird auf dem Kanal durch Störungen (Rauschen) verändert.
4) Das veränderte Signal wird mit dem Empfangsgerät als Nachricht empfangen
5) Der Empfänger verarbeitet die Nachricht weiter

#### Auftreten einer Störung
Während der Übertragung kann der Kommunikationskanal durch ein Rauschen gestört werden (Schritt 3).
Dies verändert das übertragene Signal und kann somit verhindern, dass eine Nachricht korrekt übertragen wird.

## Unterscheidung von Information und Bedeutung
\citet{Shannon:62} erläutern in ihrer Arbeit die Beziehung zwischen Bedeutung und Information einer Nachricht.
In ihrem Modell ist die Information definiert als die Anzahl der Ausdrucksmöglichkeiten, die eine Nachricht annehmen kann.
Kann eine Nachricht zum Beispiel nur zwei Symbole annehmen, hat diese Nachricht einen Informationsgehalt von 1 Bit.

Im Gegensatz dazu ist die Bedeutung definiert als der Inhalt der Nachricht.
Der Informationsgehalt einer Nachricht ist somit zunächst unabhängig von ihrer Bedeutung.
\citet{Shannon:62} beziehen hier den Empfänger mit ein um die Bedeutung quantifizieren zu können.
Der Empfänger hat eine Unsicherheit über den Inhalt der Nachricht, die mit jedem empfangen Signal reduziert wird.
Der Grad der Unsicherheitsreduktion für ein Signal ist abhängig von der Anzahl und der Wahrscheinlichkeitsverteilung der Symbole.

Diese Unsicherheit über den Inhalt der Nachricht wird auch als Entropie der Nachricht bezeichnet.

Demnach ist Kommunikation der Prozess der Entropiereduktion einer Nachricht, indem ein Sender Signale über einen Kanal zu einem Empfänger schickt.
Die Kommunikation ist abgeschlossen, wenn die Entropie der Nachricht durch das Empfangen weiterer Symbole nicht mehr verändert wird.

## Probleme der Kommunikation
Auf Basis des Sender-Empfänger Modells und der Unterscheidung von Information und Bedeutung unterscheiden \citet{Shannon:62} folgende Level der Kommunikationsprobleme.

### Level A: The technical problem
Auf dem technischen Level fragen \citet{Shannon:62}, wie präzise Signale bei der Kommunikation übertragen werden können.
Dieses Level beinhaltet das Optimierungsproblem der Signalübertragung, sowie Probleme bei der Verarbeitung von gestörten Signalen.
Zu dem technischen Problem stellen die Autoren verschiedene Lösungen vor, die hier nicht weiter ausgeführt werden.

### Level B: The semantic problem
Auf dem semantischen Level fragen \citet{Shannon:62}, wie präzise Signale die gewünschte Bedeutung vermitteln können.
Dieses Level enthält alle Probleme, die beim Empfänger nach der Übermittlung des Signals entstehen, wie das Entscheidungsproblem, Authenzität \citet{Simsons:84} oder Korrektheit einer Nachricht \cite{Baker:88}  oder die Verarbeitung von unbekannten Sprachen.

Das semantische Problem ist laut \citet{Shannon:62} abhängig von dem darunterliegenden technischen Problem und nicht allein technisch lösbar.

### Level C: The effectiveness problem
Auf dem Effizienz Level fragen \citet{Shannon:62}, wie effizient eine Übertragung eine Reaktion auslöst.
Dies umfasst verschiedene Optimierungsprobleme \citet{Gough:96} sowie das Quantifizierungsproblem von Erfolg \cite{Zhou:10}.
Laut den Autoren ist dieses Level nur in Abhängigkeit der anderen beiden Level lösbar.

# Peirce
In der Semiotik gilt Peirce als einer der prägenden Wissenschaftler \citet{Brent:98}.
Sein Modell der Korrelate sowie die Betrachtung der Wahrnehmung als infiniter semiotischer Regress sind der Grundstein aktueller Forschung.

## Korrelate Modell 
Das "Korrelate Modell" auch als triadische Zeichendeutung beschreibt \citet{Peirce:60} die Beziehung zwischen den Bedeutungsebenen von Symbolen.
Demnach hat jeder Gegenstand drei verschiedene Bedeutungsebenen, die ihn definieren.

### Objekt
Das Objekt bezeichnet die Bezugsebene des Gegenstands.
Es steht für das Individuum oder die Identität des Gegenstands.
Jeder Gegenstand ist ein einzigartiges Objekt.

### Repräsentamem
Der Repräsentamen bezeichnet die Wahrnehmungsebene des Gegenstands.
Er steht für das Aussehen oder die äußere Gestalt des Gegenstands.
Mehrere Gegenstände können ein gleiches Repräsentamen haben.

### Interpretant
Der Interpretant bezeichnet für die Botschaftfsebene des Gegenstands.
Er steht für die Bedeutung oder die Wirkung des Gegenstands.
Mehre Gegenstände können einen und ein Gegenstand kann mehrere Interpretanten haben.

### Beispiel
Die drei Bedeutungsebenen möchte ich kurz an einem Beispiel verdeutlichen.
In dem Beispiel eines Apfels auf einem Tisch gelten folgende Beziehungen:

- dieser Apfel ist als Objekt einzigartig.  Wenn jemand dazu aufgefordert werden würde den Apfel zu bewegen, so wäre das Objekt eindeutig und kein anderer Apfel gemeint.
- das Bild des Apfels als physikalische Reize stellt das Repräsentamen dar. Jede Beschreibung oder Wahrnehmung des Apfels in Form, Farbe, Geschmack bezieht sich ausschließlich auf das Repräsentamen. 
- Die Unterscheidung des Apfels von der Umwelt sowie das Verständnis über die Möglichkeiten der Interaktion mit dem Apfel sind das Interpretant. Über das Repräsentamen ist bekannt, dass der Apfel eine Frucht ist, die man essen kann.

## infiniter semiotischer Regress
Die Wahrnehmung eines jeden möglichen Gegenstands führt stets zu einer Aufteilung in Objekt, Repräsentamen und Interpretant. 
Das bedeutet aber, dass der Interpretant eines Objekts direkt wieder zu einem Repräsentamen wird.

Wird ein Apfel beobachtet, dann bilden die wahrgenommen Eigenschaften (zum Beispiel die Kombination aus Farbe und Form) eine anderes Repräsentamen des Apfels.
Form und Farbe sind ausreichend um den Apfel zu erkennen.
Im nächsten Schritt kann eine reduzierte oder veränderte wahrnehumung (zum Beispiel Kreis mit Biss) als Repräsentemn von Form und Farbe werden.
Dieser Prozess wiederholt sich theoretisch unendlich
Nach \citet{Noeth85} wird der Regress aber praktisch in einer frühen Stufe abgebrochen.

# Vergleich der Modelle
Das Sender-Empfänger Modell und das Korrelate Modell beziehen sich auf verschiedene Aspekte der Kommunikation.

Shannon und Weaver beschäftigen sich mit der Gesamt Situation während einer Übertragung während sich Peirce mit dem Verhältnis von Sender und Empfänger zu den Nachrichten befasst.

Beide verwenden Begriffe für physikalisch wahrnehmbare Phänomene. Peirce bezeichnet sie als Gegenstände und Shannon und Weaver als Signale

Shannon und Weaver beschreiben den Ablauf einer Übertragung, aber nicht das Verständnis von Nachrichten.
Peirce hingegen beschäftigt sich ausschließlich mit dem Verständnis und nicht mit der Übertragungausschließlich
