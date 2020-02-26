# inhalt
- vergleich zwischen shannon-weaver und peirce am beispiel eines gespräches

# aufbau
- zunächst beschreibung einer Kommunikation zwischen Alice und Bob
- beschreibung in den worten von shannon-weaver
- beschreibung in den worten von peirce
- betrachung gemeinsamkeiten
- betrachung unterschiede

# szenario:
alice und bob leben in einer WG.

# ablauf
## kommunikation von appellen (imperativen)
- realität ist eine Menge von widerspruchsfreien axiomen
- ein ereignis ist eine ausprägung einer eigenschaft als schlussfolgerung einer Menge an Axiomen
- Eine Handlung beschreibt, das Auslösen eines Ereignisses durch einen Akteur
- eine situation ist eine Menge an Eigenschaften und ihren Ausprägungen
- eine Szene ist eine Menge an Situationen und eine Menge an Aktueren
- ein Agent ist ein Akteuer, der versucht ein bestimte Ausprägung von Eigenschaften zu verwirklichen
- Ein Konflikt beschreibt eine Situation und die Tupel aus Agent und ihren Zielen
- Ein begrenzter Aktuer kann nur eine endliche Menge an Handlungen in einer Sitation ausführen

### Kommunkation zweier Agenten nach Shannon-Weaver (interpretiert)
#### Die Information
- Im folgenden betachten wir nur begrenzte Akteuere
1) Ein Agent nimmt die aktuelle Situation mittels receive(szene, situation): [symbol] und decode(symbol, szene): 
2) Er bildet die Differenz zwischen seinem Ziel und der Sitation, als Menge von Handlungen
3) Er stellt die Handlungsmöglichkeiten für alle involvierten Akteure da.
4) Er bildet 2 Handlungsmengen: die er selbst erfüllen kann, und die er nicht selbsterfüllen kann
Ab hier hat der Agent Alice eine Information, die sie kommunzieren möchte!

#### Die Nachricht
5) Alice bildet eine Codier-Funktion: encode(handlung, kanal, akteur) -> symbol, kanal
6) Alice bildet eine Sende-Funktion: send(symbol, kanal) -> {Handlung}

#### Das Signal
7) Alice führt für jedes Elemnt in der zweiten Handlungsmenge; encode und send aus
8) Alice überführt die aktuelle Sitation dadurch in eine neue Sitation

#### Wahrnehmung:
9) repeat from the top

### Verwendete Symbole
- Die Codier- und Sendefuntkion ist situanstionsabhängig
- 
