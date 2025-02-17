# Folge 237 - Warum ist Software(-Architektur) eigentlich immer so schlecht?
Hallo, ich bin Eberhard Wolff.
Freitags mache ich, oder Lisa Moritz, einen Livestream zum Thema Software-Architektur, oft zusammen mit Gästen.
Dieser Podcast ist das Audio des Streams.
Weitere Folgen, Sketchnotes und vieles mehr findet ihr unter software-architektur.tv.
Software-Architektur im Stream.
Herzlich willkommen zu einer weiteren Episode von Software-Architektur im Stream.
## Einführung in die Problematik der Software-Architektur

Heute geht es um das Thema, warum Software-Architektur immer so schlecht ist.
Bevor ich loslege, zeige ich ein paar Worte in eigener Sache.
Es gibt einen Spreadshirt-Shop für Software-Architektur im Stream.
Mit T-Shirts, Rucksäcken, Hoodies und allem Möglichen, was das Herz begeht für Software-Architektur im Stream.
Ich packe das nochmal kurz in den Chat und in die Links und verlinke das auf der Webseite.
Wer Lust darauf hat, sich mit dem Logo von Lisa zu zieren, das wäre da eure Chance.
Inhaltlich geht es heute um das Thema mit der Software-Qualität.
Das ist ein kompliziertes Thema, darüber kann man lange reden.
Tatsächlich habe ich im Stream auch schon lange darüber geredet an verschiedenen Stellen.
Ich werde hier ein paar Meinungen zum Besten geben und möglicherweise die Diskussion an einigen Stellen verkürzen.
## Die Motivation hinter der Beratung

Eine Motivation für die ganze Geschichte ist, dass ich Berater bin.
Das heißt, ich sehe häufig suboptimale Software.
Das Kreuz des Beraters ist, dass er Dinge sieht, die Beratung bedürfen, sodass genauso was wie suboptimale Software ein Tätigkeitsschwerpunkt von mir ist.
## Definition von Software-Qualität

Die Frage ist, was müsste sich bei uns ändern, damit ich arbeitslos wäre oder etwas Neues suchen muss.
Was ich mit der Qualität genau meine, da bin ich froh, dass ein bisschen Feedback oder Fragen gekommen sind, die in eine andere Richtung gehen.
Ich meine damit insbesondere Systeme, die keine vernünftige Struktur haben, wo die Geschäftslogik überall verstreut ist, nicht vernünftig strukturiert ist.
Damit geht es insbesondere um Wartbarkeit.
### Aspekte der Software-Qualität

Softwarequalität hat natürlich auch noch andere Aspekte, Performance, Zuverlässigkeit, Sicherheit und viele andere Dinge.
Die will ich ein bisschen aussparen.
### Qualitätsgetriebene Softwareentwicklung

Qualitätsgetriebene Softwareentwicklung bedeutet, dass ich diese verschiedenen Qualitäten zum Übereinstimmen bringe.
Aber ich will mich insbesondere um Wartbarkeit und Struktur der Software kümmern, weil das die Kosten der Weiterentwicklung im Wesentlichen beeinflusst.
Und damit auch die Kosten für die Anpassung an neuen Featuren darstellt.
Martin Egli bei LinkedIn hat auch geschrieben, was ist denn eine schlechte Softwarearchitektur oder wie gut muss die Softwarearchitektur sein?
Wann ist die Softwarearchitektur gut genug?
Barry O'Reilly spricht von Criticality, ist das das Ziel?
Ich kann noch mal wiederholen, das ist genau eigentlich die richtige Frage.
Wir wollen Software bauen, die insbesondere in Bezug auf die nicht funktionalen Anforderungen vernünftig funktioniert.
Aber es ist eben auf der anderen Seite so, dass die meisten Sachen, die ich in der freien Wildbahn sehe, insbesondere in Bezug auf die Strukturierung, deutlich zu schlecht sind.
Darum will ich mich insbesondere kümmern.
Hamburg hat geschrieben, vielleicht liegt es an der Qualitätssicherung.
Da meine ich nicht, guck mal, ich habe G-Unit-Test für das Qualitätsbewusstsein.
Bin ich mir nicht sicher.
Und das passt vielleicht auch zu dem, was ich mir eigentlich als nächstes vorgenommen hatte zu sagen.
Das nervt halt viele beim Weiterentwickeln, das nervt halt vor allem TechnikerInnen.
### Techniker und ihre Herausforderungen

Und es ist tatsächlich auch einigen peinlich.
Das war für mich auch eine Motivation, diese Episode zu machen.
## Herausforderungen bei der Software-Architektur

Ich komme mir häufig genug in Consulting-Einsätze und mir wird mal wieder eine suboptimale Architektur gezeigt.
Kein Wunder, weil sonst brauche ich keine Beratung.
Und es scheint dem Menschen peinlich zu sein, nahezu.
Was ja bedeutet, dass das Qualitätsbewusstsein da ist.
Die stellen sich im Prinzip hin und sagen, okay, wir wissen, dass es verguckt.
Sorry, wissen wir, guck mal, so sieht es bei uns aus.
Und genau, die in Hamburg hat ja auch geschrieben, eine interessante Frage.
Wer kann denn berichten lernen, wie es richtig gemacht wird?
Die, die schon mal richtig missgebaut haben und Lehrgeld bezahlt haben, große Fehler gemacht haben, ohne dem jetzt vorgreifen zu wollen.
Ich würde behaupten, ein Fehler, und das ist für mich auch motivatorisch, ist, dass man glaubt, man kann überhaupt eine sehr gute Qualität über das gesamte System erreichen.
Und die in Hamburg fragt weiter, oder die, die noch nie große Fehler gemacht haben und somit scheinbar wissen, wie man es macht.
Ich bin nicht sicher, ob es die sozusagen gibt.
### Die Verantwortung des Managements

Also es gibt so diese Ausnahmesysteme.
Mir würde halt immer Tech einfallen.
Wie nennt man das auf Deutsch?
Das Layout-System, Type-Setting-System, was der Donald Knus gebaut hat.
Das muss halt wirklich extrem sauber sein.
Es gibt sicherlich auch ein paar Beispiele, die halt irgendwie extrem sauber sind.
Aber meistens ist die Qualität suboptimal.
Und vielleicht ist das halt auch etwas Positives, weil wenn einem die Dinge, die man vor ein paar Jahren gemacht hat, nicht peinlich sind, ist man irgendwie auch stehen geblieben.
Von daher ist das vielleicht sogar was Positives.
Und ich hatte schon gesagt, dass es gegebenenfalls verkürzt.
Der Peter Sommerlath hat auf Mastodon geschrieben bezüglich diesem, wieso ist die Softwarequalität immer so schlecht.
Da frage ich mich nach fast 30 Jahren Posa 1 auch immer mal wieder.
Patterns of Software Architecture, das ist halt ein Buch.
Und er hatte dann weitergeschrieben, Plan eine Feier nächstes Jahr auf der Europlop.
Und das passt glaube ich zu dem, was auch die in Hamburg gerade sagte.
Das würde ja nur helfen.
Also nicht ein Buch wie das Posa-Buch, was tatsächlich wichtig ist.
Hilft halt nur dann, wenn wir es nicht besser wissen.
Ich bin mir aber sehr unsicher, ob das wirklich der Kern des Problems ist.
Meine Behauptung wäre, dass in vielen Fällen die Menschen, die da dran sitzen an dem System, wissen, wie es besser geht.
Aber vielleicht ist eben auch das ein Teil der Lösung.
Also ich laufe ja irgendwie rum und mache mir ganz viel zum Thema Modernisierung.
Das sind irgendwie krasse Grundlagen.
Und hoffe halt, dass ich dadurch tatsächlich dazu beitragen kann, dass es eben besser wird.
### Fokus auf technische Exzellenz

Von daher ja, vielleicht ist das eben auch ein Teil der Lösung.
Ich wollte hier eben offen darüber sprechen, weil wie gesagt, das ist dazu ein Tabuthema.
## Zukunftsvisionen für die Software-Qualität

Und eine andere Auslöser für die Episode ist, ich hatte die Ehre die Kino bei den XP Days in Stuttgart zu halten.
Und da ging es halt irgendwie darum, warum irgendwie Agilität so ein Problem ist.
Und warum sich das halt nicht durchgesetzt hat.
Ich habe irgendwie auf einer Folie gesagt, das Streben nach technischer Exzellenz, das halt im Manifest drin steht, ist meiner Meinung nach ein Problem.
Und das ist in gewisser Weise tatsächlich etwas, wo ich, also ich habe daraufhin Feedback bekommen.
Da war halt auch jemand am Stand, mindestens eine oder sogar zwei Personen, die sich glaube ich insbesondere an dem Thema so ein bisschen aufgehangen haben.
Und ich bin dann irgendwie zu mir, also habe das sozusagen für mich auch nochmal Revue passieren lassen und habe halt festgestellt, dass da tatsächlich etwas, glaube ich, bei dieser Folie nicht so schön war, um es mal vorsichtig zu sagen.
Denn eigentlich versuche ich immer die typischen Probleme zu diskutieren, die da draußen bei den Kundinnen, die ich halt sehe, auch tatsächlich die Probleme sind.
Um dann zu sagen, die typischen Probleme, die ich so sehe, die würde ich halt folgendermaßen lösen.
Und das typische Problem da draußen ist halt nicht technische Exzellenz, übertriebene technische Exzellenz, sondern eher suboptimale Qualität und mangelnde technische Exzellenz.
Und deswegen ist es ein bisschen komisch dann zu sagen, hey, das Streben nach technischer Exzellenz ist ein Problem.
Tatsächlich ist es etwas komplizierter und in gewisser Weise stehe ich halt auch noch hinter dieser Aussage, dass das Streben nach technischer Exzellenz ein Problem ist.
Aber gleichzeitig ist eben der Mangel an technischer Exzellenz eben auch ein Problem.
Und vielleicht noch, ich hatte ja damals die Folge gemacht mit dem Hillel Wayne, darüber, ob wir eigentlich Engineers sind, also ob wir Ingenieure sind, so wie andere Ingenieursdisziplinen auch.
Und subjektiv habe ich halt immer das Gefühl, dass Ingenieursprodukte, die man halt da draußen sieht, so eine hohe Qualität haben.
Ich kaufe mir ein tolles Rennrad, das sieht irgendwie super aus, funktioniert super und hat irgendwie eine hohe wahrgenommene Qualität.
Wenn ich mir Software und wie soll ich sagen, es ist halt auch ein ästhetisch sauber ansprechend.
Die meisten Softwarearchitekturen, die ich sehe, sind gerade nicht so, sondern sind irgendwie so, dass sie viel Optimierungspotenzial haben.
Gleichzeitig muss man aber eben auch dazu sagen, die Software und die Architekturen lösen viele Geschäftsprobleme.
Und mein Rechner, der vor mir steht, ist halt im Wesentlichen zuverlässig.
Wenn der ein Problem hat, dann eher ein Hardwareproblem.
Das heißt, so schlimm kann es eigentlich nicht sein.
So, und der Danny Steinbrecher, auch tatsächlich noch, von Mastodon, hat auch noch mal so ein Ding geschrieben, weil wir die falschen Technologien nutzen.
Deswegen sei es halt schlecht, bin ich sehr unsicher.
Ich würde behaupten, man kann in jeder Technologie guten oder schlechten Code schreiben und Dinge bauen, die gut oder schlecht behaltbar sind.
Oder zu wenig Meetings, fand ich spannend.
Kommunikation hatten wir ja auch mal bei dieser Erfolge vom Java Forum Stuttgart als Problem identifiziert.
Vielleicht ist das immer noch tatsächlich das Problem.
Im Zweifel ist die Regulatorik oder die fehlende Zeit schuld.
Und das ist genau dieser letzte Punkt, den der Danny da anspricht.
Nämlich die fehlende Zeit ist tatsächlich das, was ich glaube, wie gesagt, ich verkürze das halt ein bisschen, möglicherweise dafür verantwortlich ist, dass wir halt das Problem haben, was wir haben.
## Die Rolle von Zeitdruck in der Software-Entwicklung

Zeitdruck habe ich mir aufgeschrieben.
Ich habe mir auch noch aufgeschrieben, falsche technische Entscheidungen, die aber manchmal auf Management-Ebene gefällt werden.
### Management-Entscheidungen

Also, dass ich sage, ich benutze halt Microservices, weil heute macht man das ja so.
Und das ist etwas, was auf dieser Granularität nach Management kompatibel ist.
Oder vielleicht auch solche Sachen, dass man sagt, ich habe eine Aufteilung von Aufgaben auf irgendwelche Teams.
Auch eine Management-Entscheidung.
Aber das ist eben auch eine Architektur-Entscheidung, weil diese Teams jeweils an einem Teil des Systems arbeiten werden.
Also insgesamt ist es so ein bisschen nicht.
Also in erster Instanz würde ich jetzt, dass den schwarzen Peter, ich glaube, viele Leute, die jetzt aus der Technik-Ecke kommen, erstmal sozusagen dem Management halt zuweisen.
Würde halt sagen, naja, das Management erzeugt halt Zeitdruck.
Das Management trifft irgendwelche grobgranularen technischen Entscheidungen.
Wir machen Microservices, die halt irgendwie schwierig sind.
Und sagt halt, wir haben ein Team, das sich um den Kunden kümmert.
Und dann habe ich halt eine Kundenkomponente.
Und wir wissen halt, die Verwaltung von solchen Daten ist vielleicht ein Problem.
Und das ist eben eine Architektur-Entscheidung, die halt indirekt gefällt wird, weil eben eine Management-Entscheidung zugunsten des Aufgabenbereiches eines Teams getroffen wird.
So, und das bedeutet und in einigen Stellen führt das auch tatsächlich zu Dingen, die, wie soll ich sagen, intuitiv irgendwie klar sind und sinnvoll und logisch, aber dann halt verheerende Konsequenzen haben.
Also wenn ich mich hinstelle und sage, ich kann halt dafür sorgen, dass das Team irgendwelche Dinge schneller produziert, ist das ja erstmal eine sinnvolle Entscheidung.
Also ich kann eben schneller irgendwelche Werte generieren.
Ich kann Business-Logik implementieren.
Und ich wüsste nicht, warum man das nicht tun sollte.
Aber genau durch dieser Zeitdruck, der dann entsteht, ist halt potenziell ein Problem.
Und ich glaube tatsächlich, dass das eben ein Grundproblem ist.
### Der Einfluss von Deadlines

So, und da gab es noch ein interessantes Feedback eben genau am Stand von den XP Days.
Da berichtete halt die Person, mir ist ehrlich gesagt der Name entfallen, dass sie die Erfahrung gemacht hat, dass es so künstliche Deadlines sind.
Also das war die Deadlines, wo man sich hinterfragt, also dass es halt zwar eine Deadline gibt nicht, also wir müssen zum 1.1. oder zum 1.5. live gehen, aber das sind künstliche Sachen.
Man kann nicht herausfinden, warum denn nun diese Deadline ex act gilt.
Und diese Person hat dann selber mal einen Management-Job übernommen und hat dann tatsächlich angefangen und hat Deadlines hinterfragt.
Und dann ist das so ein bisschen in sich zusammengebrochen.
Sprich, dann wurde halt offenbar, dass diese Deadlines künstlich sind.
Und ich will gar nicht sagen, ob das halt nun stimmt oder nicht.
Ich halte das aber für glaubwürdig, also ob das ein allgemeines Konzept ist.
Die Aussage, glaube ich, ist auf jeden Fall glaubwürdig.
Und vielleicht ist es daneben so, dass Deadlines eher so ein Leistungsbeweis sind.
Also unter meiner Leitung mit dem Team, das ich habe, können wir halt wahnsinnig schnell irgendwelche Dinge halt auf die Reihe bekommen.
Und dann entsteht halt eigentlich ein Zeitdruck, der halt nicht wirklich notwendig ist durch eine Deadline im Sinne von, wir müssen halt nun wirklich zu diesem Zeitpunkt online sein, weil sonst haben wir halt irgendwelche Schäden, die halt entstehen durch Gesetze, die wir brechen.
Oder weil nun tatsächlich irgendjemand im Markt die Marktpositionen übernimmt oder was auch immer.
So, also das bedeutet, dieser Zeitdruck ist vielleicht oft irreal.
Und ich glaube, das andere Problem, was uns da irgendwie sozusagen so ein bisschen zu einem Problem führt, ist irgendwie die Sichtbarkeit technischer Probleme.
Also wenn ein Rennrad irgendwie komisch ist, dann kriege ich das mit, weil ich das halt einfach sehen kann.
Ich kann es halt visuell wahrnehmen.
Und ich kann ja auch irgendwie sehen, wie es sich sozusagen verhält.
Bei Code, mindestens bei Codequalität, kann ich das nicht direkt sehen, wenn ich eben von draußen drauf gucke.
Also beim Rennradzentral hat die Bauernzüge irgendwie verlegt.
Und ich habe halt irgendwie das Rad und die Speichen und all diese ganzen Geschichten.
Und ich kann irgendwie sehen, ob das halt irgendwie vernünftig funktioniert und halt irgendwie vernünftig aussieht, die Sachen halt irgendwie gut verlegt sind oder eben auch nicht.
Und beim Code ist es eben so, dass ich in den Editor reingucken muss und ich sehe es von draußen eben nicht.
So, und auch diese anderen Sachen sind nicht so richtig offensichtlich.
Also dass ich halt nur, weil ich Teams Aufgaben gebe, die Architektur beeinflusse.
Uns ist das klar.
Das ist Conway's Law.
Ob das Management klar ist, ist irgendwie nicht so sicher.
Das sind irgendwie Leute, die einen anderen Hintergrund haben.
Und auch so eine technische Entscheidung.
Also warum ist der Microservices eine problematische technische Entscheidung?
Also vielleicht ist sie das ja auch irgendwie gar nicht.
Und das führt irgendwie dazu, dass halt diese Dinge, die halt dann tatsächlich dort herausgemacht werden oder die halt dazu führen, dass wir halt diese massiven Probleme haben, dass die halt nicht auf den ersten Blick sofort zu diesen Problemen führen.
Und diese Probleme sind halt erst mal nicht sichtbar.
Also ich kann ein Microservices System bauen, auch wenn Microservices nicht die sinnvolle Lösung sind.
Es ist nur viel aufwendiger und es sorgt dafür, dass halt im Rechenzentrum mehr Server beteiligt sind und dass ja irgendwie vielleicht Antwortzeiten langsamer sind.
Davon sehe ich aber höchstens die langsamen Antwortzeiten.
So, und dazu passt dieses Thema rund um Technical Debt.
Ich habe tatsächlich ja mehrere Folgen zu diesem Thema gemacht.
Die kann ich auch sicher verlinken.
Und da gibt es halt eine ganze Menge an Diskussionen, die man darum führen kann.
Ich glaube mittlerweile, dass der Hauptgrund von Technical Debt ist, dass eben Druck entsteht auf das Team und dann gute Praktiken zurück zusammenbrechen.
Und das ist deswegen wichtig, weil diese Metapher, wenn man sie sozusagen profan versteht, sagt etwas anderes.
Technical Debt sagt, ich nehme eine Schuld aktiv auf, um sie später abzubezahlen.
Was ich jetzt behaupten würde ist, was in Wirklichkeit passiert ist, dass ich halt anfange und sage, wie kriege ich die Deadline denn jetzt doch noch hin?
Dann nehme ich irgendwelche wilden Abkürzungen und dann bin ich halt am Ende bei einem System, dass das, was irgendwie gefordert ist, tatsächlich tut.
So irgendwie hingehackt.
Aber ich habe irgendwie die Qualität des Systems kompromittiert.
Und das ist nicht so, dass ich mir jetzt aktiv gesagt habe, hier, hier, hier und hier gehe ich eine Schuld ein und ich werde sie irgendwann abbezahlen, sondern ich habe einfach dadurch, dass ich halt konsequent, schnell, abkürzend gearbeitet habe, diese Technical Debt Sachen erzeugt.
Und man kann darüber größer diskutieren.
Ich muss es hier verkürzen, weil ich habe halt nicht so wahnsinnig viel Zeit.
Ich habe irgendwie stundenlang tatsächlich über Technical Debt gesprochen.
Und dann ist eben tatsächlich der Zeitdruck, das zentrale Problem für diese schlechte Qualität oder eben analog diese Entscheidung, nicht Teamaufteilung oder die Benutzung von irgendwelchen Technologien, die hat dann dazu geführt, dass es einfach nicht passt und dass man dann zu einem Ergebnis kommt.
Das ist eine These, aber das ist gerade das Gegenteil von dem, was ich halt irgendwie in der Keynote gesagt habe.
Also das würde jetzt bedeuten, das Problem, was wir in erster Linie in der Industrie haben, ist durch hohen Zeitdruck, der nicht wirklich motivierbar ist und durch andere Entscheidungen, die auf Form of Management Ebene getroffen werden, kommen wir in eine Situation, dass das, was hinten rauskommt, suboptimal ist.
Und das ist leider nicht offensichtlich sichtbar.
Es ist nicht so, wie wenn das Rennrad jetzt irgendwie produziert wird und wir sehen, das kann offensichtlich nicht funktionieren, sondern es ist irgendwie Kot und ist dadurch nicht sichtbar.
Und deswegen haben wir da ein Kernproblem.
Und diese Dinge sind nicht so offensichtlich.
Und da ist wieder diese Geschichte mit dem, was ich am Anfang sagte.
Hilft es uns jetzt, wenn wir eine Stunde über Technical Debt reden und das halt irgendwie sozusagen detailliert verstehen?
Bin ich mir nicht sicher, weil beim nächsten Mal, wenn irgendwie der Zeitdruck auftritt oder halt irgendwelche Dinge da entschieden werden, werde ich wahrscheinlich wieder in dasselbe Verhalten und in dasselbe Problem reinlaufen.
So und jetzt kommt der Punkt, der so ein bisschen aus dieser Kino zurückkam.
Also es bedeutet jetzt, dass im Prinzip die Aussage kommt, Management entscheidet irgendetwas.
Wir stehen halt irgendwie da und sagen, cool, dass es diese Entscheidung gibt.
Die führt halt irgendwie in Chaos.
Wir wissen vielleicht auch, dass sie halt ins Chaos führt.
Jetzt ist halt die Frage, was ist eigentlich die Reaktion?
So und die Reaktion, auf die ich mich halt jetzt in der Kino bezogen habe, ist, wir machen einfach die maximale Qualität.
Punkt.
So, das heißt also, wenn man diese Idee, in diesem Fall kommt es aus Magie Manifest oder nicht aus Extreme Programming, hat das zum Beispiel auch.
Wir wollen halt irgendwie die Code-Qualität ganz hochdrehen.
Software Craftsmanship hat diese Idee auch.
Ich sage halt, ich möchte halt stolz auf das sein, was ich baue.
Das soll irgendwie nicht Craftsmanship, orientiert sich irgendwie an Handwerk und an den Ideen, die halt im Handwerk sind.
Ich möchte also handwerklich gute Sachen bauen und das bedeutet, ich will halt hohe Qualität liefern und das überall.
So und meine Behauptung ist, das ist auch übertrieben und das ist dasselbe, nur mit anderen Vorzeichen.
Also das heißt, wir haben im Prinzip zwei Extreme.
Wir haben halt einmal das Extreme, was halt sagt, mir ist das völlig egal, was da an Qualität herauskommt.
Ich verstehe diese Technik auch nicht.
Wir machen jetzt ein Microservices System unter hohem Druck und so ist die Teamaufteilung, was bedeutet, dass Techniker in sich dann letztendlich halt gefunden, in einem System gefangen sind, in dem sie gar nicht ein qualitativ hochwertiges System im Sinne von Wartbarkeit bauen können und die Reaktion ist halt zu sagen, nee, nee, nee, nee, das machen wir halt nicht, sondern wir drehen halt die Qualität auf Maximum.
So und das heißt, auf der einen Seite haben wir die Extremposition, die sagt, das mit der Qualität ist halt völlig egal, wir machen halt gar nichts und auf der anderen Seite haben wir die umgekehrte Maximalposition, die sagt, Qualität ist das Wichtigste ever und wir müssen halt da auf jeden Fall die beste Qualität ever liefern.
So und für mich ist da der wichtige Punkt, die Sache, die mir da sozusagen als erstes oder die, glaube ich, tatsächlich extrem zentral ist, ist diese Idee von der Core Domain, das, was halt Eric Evans eingeführt hat in Domain Design und was er halt sagt, ist, wir können eben nicht überall die maximale Qualität erreichen.
Und diese beiden Maximalpositionen, also die eine Position sagt, Qualität ist egal, wow, das bedeutet halt, dass wir halt am Ende in einem System tatsächlich landen, was irgendwie schwer weiterentwickelbar ist und das ist irgendwie auch ein Problem.
Und die andere Maximalposition sagt halt, wir müssen überall die Qualität hochdrehen.
Die sagt, stellt in Abrede, dass eben nicht alle Teile eines Systems die maximale Qualität haben können.
So und da kommt jetzt eben Eric Evans und sagt, es ist bedauerlicherweise so, also bedauerlicherweise hat er, glaube ich, nicht gesagt, aber es ist so, dass wir irgendwie nicht überall die maximale Qualität erreichen können, deswegen brauchen wir eine Core-Domain.
Wie vorhin nochmal gesagt, ist ein wichtiger Punkt, nicht hier auch zu definieren, was mal mit Qualität gemeint ist.
Ich hatte es am Anfang, glaube ich, versucht zu sagen, ich meine damit Qualität im Sinne von Wartbarkeit, Code-Qualität, diese Sachen, ich vernachlässige gerade die anderen Qualitäten im Sinne von Software-Qualität, also die ganzen Elites, nicht Scalability, Security und was halt sonst sollen, wie Performance, solche Sachen, sondern ich möchte mich hier irgendwie auf Code-Qualität und Wartbarkeit insbesondere fokussieren.
Wenn ich also sage, so wie Eric das sagt und ich habe überhaupt keinen Zweifel daran, dass das wahr ist, weil ich würde behaupten, es ist offensichtlich so, ich kann nicht überall die maximale Qualität erreichen, dann brauche ich ein Trade-Off und das bedeutet, ich muss einen Kompromiss eingehen und das bedeutet halt, dass genau diese Menschen, die jetzt irgendwie sagen, wir müssen aber überall die maximale Qualität erreichen, die wollen halt diesen Trade-Off nicht treffen und das schlägt, glaube ich, dann um.
Also wenn ich in einer Realität lebe, in der ich eben nicht überall die maximale Qualität erreichen kann, das aber versuche, dann werde ich scheitern und am Ende ist die Qualität irgendwie random über das System verteilt.
Das heißt, ich habe halt Teile, wo ich das mit meinen hohen Anstrengungen geschafft habe, das Ziel zu erreichen und andere Teile, wo ich das eben nicht habe und das war eigentlich für mich der Grund, warum ich halt genau dieses Thema in der Keynote diskutiert hatte, weil ich eben glaube, dieser Ansatz zu sagen, hey, wir wollen natürlich die höchste Qualität überall und wir wollen technische Exzellenz, das ist am Thema vorbei.
Wir müssen diese Kompromisse eingehen und wir müssen das aktiv steuern.
Vermutlich ist aber dieses Problem, ich versuche, überall sinnlos die höchste Qualität zu erreichen, kleiner ist das Problem, ich habe Zeitdruck und mir bricht das System insgesamt zusammen.
Von daher ist es, glaube ich, wie gesagt, eben so, dass wir insbesondere dieser Zeitdruck und diese Geschichte, glaube ich, ein wichtiges Thema sind.
Ein kurzer Ausflug, weil mir das sozusagen auch noch wichtig ist, wir haben dazu eine Episode gemacht.
Ich habe halt diese Episode gemacht zur Retrospektive von Extreme Programming und das Projekt, was ja Extreme Programming damals sozusagen aus der Taufe gehoben hat, war dieses C3-Projekt bei Chrysler.
Es gibt ja dieses sehr schöne Buch, über was eben Extreme Programming so ein bisschen in Frage stellt und da ist halt eine der Aussagen, dass eben dieses C3-Projekt am Ende gescheitert ist.
Also erstmal, da geht es halt um eine Payroll, da geht es um die Lohnabrechnung von Chrysler, war das damals.
Das war Chrysler kurz vor dem Zusammenschluss mit Daimler Ende der 90er und dieses Projekt ist halt letztendlich eingestellt worden und hat eben auch nie einen signifikanten Teil der Lohnabrechnung gemacht und ein Grund dafür kann durchaus sein, dass eben dieser hohe Qualitätsanspruch zusammen mit dem dauernden Refactoring dazu geführt hat, dass das Projekt eben nicht mehr besonders produktiv ist.
Das müsste man nochmal nachrecherchieren.
Ich habe das jetzt sozusagen mal gespart, aber sowas könnte eben eine Illustration dafür sein, dass dieser hohe Qualitätsanspruch wirklich zu Problemen führt.
Das bedeutet, wir können eben nicht überall die Qualität auf 100 Prozent stellen, so wie Extreme Programming das versucht, selbst wenn wir es wollten und ich glaube, wir wollen es auch nicht, weil es an einigen Stellen einfach unwirtschaftlich ist.
Das heißt, wir müssen an den wesentlichen Stellen so viel Qualität bauen, wie wirtschaftlich ist.
Das ist die einzige echte Möglichkeit.
Jetzt fängt es an und wir müssen eigentlich beide Seiten zusammenbekommen.
Das heißt, wir müssen jetzt auf der einen Seite Management, was zum einen sagt, wir reduzieren den Druck und zum anderen halt auch irgendwie sagt, wo brauchen wir denn eigentlich genau diese Nachhaltigkeit?
Also eigentlich ist Qualität im Sinne von Wartbarkeit und Kotqualität ein Thema von Nachhaltigkeit.
Ich kann also mit hoher Kotqualität und guter Wartbarkeit nachhaltig mit konstanter Geschwindigkeit Software entwickeln und das ist dann sinnvoll und hilfreich, wenn ich das muss.
Also wenn ich jetzt ein Stück Software baue für ein Business Case, ich weiß nicht, wir haben jetzt Weihnachten kurz vor uns, wo ich sage, zur Adventszeit, 1.12. will ich live damit sein, am 24.12. werfe ich es weg, dann ist es halt sehr egal, welche Qualität dieses Ding hat, weil ich werde es nie weiter warten müssen.
Es ist nur dann ein Problem, wenn die Qualität bereits zuschlägt, während ich es halt draus habe.
Also wenn ich jetzt irgendwie ab dem 1.12. bis zum 24.12. noch Änderungen daran machen muss und die sind bereits wahnsinnig schwer, dann ist es vielleicht gut, eine hohe Qualität zu liefern.
Aber nach dem 24.12. ist die Qualität völlig egal, weil dann mache ich halt irgendwie garantiert keine Änderungen mehr, sondern ich habe den Code weggeworfen.
Das könnte eben sein, dass ich so einen Fall habe.
Ich glaube, in vielen Fällen ist auch das Problem, dass man eben Management nicht glaubt, dass das so ist in diesem Fall, aber das ist ja genau das Problem.
Also ich muss jetzt aus Management Sicht eine glaubwürdige Aussage bekommen, die halt sagt, dann müssen wir es haben, also nicht künstlicher Zeitdruck, das ist etwas, was wir nachhaltig entwickeln wollen, das ist etwas, was wir garantiert nicht nachhaltig entwickeln wollen oder das wissen wir noch nicht so genau.
Das ist halt die eine Seite, die sozusagen diese Anforderungen stellt und das halt konkretisiert.
Das sind ja letztendlich Geschäftsentscheidungen, die dahinter stecken.
Das heißt also, ich muss mich jetzt entscheiden, will ich Features haben, will ich Erwartbarkeit haben und da muss ich da irgendwie sozusagen loslegen.
Die Entwicklung muss auf der anderen Seite die Qualitätsprobleme auch kommunizieren, sodass Management es versteht.
Und das ist auch einer der Punkte, die ich halt schwierig finde und auf die ich mich halt auch, wie soll ich sagen, beziehen wollte.
Beispiel, also so erlebt, ich habe also ein Team, dieses Team geht aus bestimmten Gründen an einer technischen Infrastrukturkomponente vorbei, weil sie die nicht nutzen darf.
Da gibt es also eine Architekturregel, die sagt, diese Infrastrukturkomponente ist für diesen Fall nicht zu nutzen.
Okay, ich bin nämlich Software Architekt, das heißt, was ich jetzt mental vor meinem Auge sehe, ist, da ist irgendein Ding, da ist ein Abhängigkeitspfeil, der darf jetzt nicht zu der technischen Komponente gehen.
Ich habe also einen Pfeil zu wenig, der irgendwie komisch ist.
Okay, so, das ist irgendwie unschön, aber nicht Abhängigkeit, die nicht da sein sollten oder so, das ist mein täglich Brot.
Also habe ich eigentlich Schulterzucken.
Später hat sich herausgestellt, dass das dazu geführt hat, dass dieses Team zusätzliche Aufwände hat und zwar eben auch Signifikante.
Damit wird das von, wir haben ja irgendwie ein Problem, irgendwie, wo irgendwelche Boxen und Freileit nicht zusammenpassen, zu einem Problem, das halt etwas Auswirkungen hat, potenziell auf eine Deadline und auf Aufwand.
Das heißt also, wenn ich dieses Problem kommuniziere als Techniker und sage, wir haben gerade so und so viel Aufwand verbraucht und wir haben deswegen so und so viel Verzug, habe ich eine andere Kommunikation und eine andere Basis, als wenn ich mich hinstelle und sage, da ist übrigens diese Abhängigkeit, wir dürfen diese Infrastrukturkomponente nicht benutzen.
Warum eigentlich?
Das ist doch eigentlich doof und inkonsistent.
Letzteres ist halt so ein abstraktes Qualitätsding, was irgendwie sagt, nicht irgendwie soll das halt so aussehen, wie die Architektur es vielleicht fordert.
Ersteres ist etwas, was ich sozusagen in Euros ausrechnen kann.
Ich kann in Euros ausrechnen, wie lange ich die Entwickler beschäftigt habe und überflüssig beschäftigt habe und ich kann in Euros ausrechnen, was es mich kostet, dass diese Software zu spät live geht.
Das ist etwas, woran wir als Technikerinnen arbeiten können, diese Kommunikation zu verbessern und das ist meiner Ansicht nach auch etwas, was mir in letzter Zeit irgendwie so auffällt.
Ich sehe bei Technikerinnen subjektiv in meinem Erlebensfeld in letzter Zeit zunehmend das Problem, dass solche Sachen halt ertragen werden.
Es wird nichts hinterfragt, es wird einfach stumpf ausgeführt und es wird kein Feedback gegeben.
Ja, liebe Leute, da müsst ihr euch ja auch nicht wundern, wenn es halt irgendwie komisch aussieht.
Also ich bin irgendwie Manager, ich habe keine Ahnung davon, was Softwarearchitektur ist.
Irgendjemand kommt zu mir und sagt, irgendwelche Abhängigkeiten sind komisch.
Okay, cool.
Was soll ich tun?
Das ist mir relativ egal und meiner Ansicht nach auch zu Recht egal.
Wenn jemand zu mir kommt und sagt, du hast da gerade den Deadline gerissen und hast da gerade irgendwie Geld ausgegeben, das war halt einfach unnötig.
Das ist ein anderes Thema.
Diese Art von Kommunikation können wir ändern und ich glaube auch tatsächlich, dass es unsere Pflicht ist.
Also wir können jetzt unmöglich von Menschen verlangen, die in so einer Position wie im Management sind, dass die sich halt irgendwie hinstellen und sagen, ich kann darüber hinaus alles, was so mit Technik zu tun hat.
Das sind zwei unterschiedliche Felder.
Wir brauchen Kommunikation und wir brauchen sozusagen zielgruppenorientierte Kommunikation.
Was eben bedeutet Kommunikation in Bezug auf Aufwand, Deadline, Kosten, solche Geschichten?
Weil das ist die Welt, in der die sich halt sozusagen bewegen.
Genau.
Der Adam hat gerade im YouTube-Chat gefragt, welche Methoden zur Förderung der kontinuierlichen Verbesserung sind empfehlenswert?
Also das, was ich hier irgendwie gerade anfange zu sagen, ist irgendwie Kommunikation.
Man kann das natürlich auch technisch angehen.
Wir haben zum Beispiel ganz viele Episoden, ich kann ja auch nochmal verlinken, zum Thema Architekturmanagement.
Da gibt es verschiedene Werkzeuge, um dafür zu sorgen, dass eben eine Architektur eingehalten wird und eine bestimmte Code-Qualität, dadurch eben bestimmte Abhängigkeiten sozusagen eingehalten werden.
Die Werkzeuge kann man irgendwie benutzen, einige davon sind irgendwie auch kostenlos.
Ich habe den Link gerade zu den Episoden in den Chat getan, aber ich packe das auch nochmal in die Zusammenfassung.
Und nicht so Werkzeuge, die halt Statische Code-Analyse betreiben, Sona ist da glaube ich das berühmte Beispiel, sind eben dann Werkzeuge, die ich halt zum Beispiel auch einführen könnte, um irgendwie auf dieser Ebene von Verbesserung und Code-Qualität zu optimieren.
Genau.
In dem Zusammenhang, also diese Folge ist ja auch bei Reiseforen angekündigt worden, da gibt es halt irgendwie die Reiseforen und ein Kommentar dort war eine Antwort, weil es dem Kunden nicht schnell, also eine Aussage dort war, eine Antwort auf die Frage, warum denn die Software-Qualität so schlecht ist, weil es dem Kunden nicht schnell und billig genug sein kann, da bleibt die Qualität schon mal auf der Strecke.
Das nächste Opfer dieses Um- oder Missstands ist dann die Dokumentation.
Ich weiß nicht, wie es dieser Person geht, aber wenn ich halt heute Abend einkaufen gehe oder überhaupt einkaufen gehe, dann kaufe ich das billige Produkt unter der Voraussetzung, dass es eben dieselbe Funktion erfüllt, die ich halt gerne haben möchte.
Anders gesagt, wenn es halt teurer ist, muss es irgendeinen Vorteil haben.
Also ich habe kein Problem damit, für ein Bio-Produkt mehr Geld auszugeben, weil es ist ein Bio-Produkt, es hat also eine gewisse andere Qualität, aber wenn ich zwei Bio-Produkte habe, die scheinbar dieselbe Qualität haben, kaufe ich das billigere.
Das ist die wirtschaftliche Welt, in der wir halt irgendwie leben und das bedeutet, wenn man nicht begründen kann, warum man irgendetwas macht, also welchen Vorteil das hat, dann wird es nicht passieren und einem Kunden vorzuwerfen, dass er gerne sein Zeug schnell und billig haben will, wie gesagt, ich würde gerne mal sehen, wie man dann beim Supermarkt einkaufen geht.
Also gehe ich jetzt hin und nehme halt das teuerste Produkt?
Nee, mache ich halt irgendwie nicht.
Ich mache es nur dann, wenn das teurere Produkt einen klaren Vorteil hat.
Das müssen wir also irgendwie kommunizieren und es kann nicht sein, wie man hier daraus jetzt irgendwie sozusagen, wie soll ich sagen, wenn ich dieser Person sozusagen das Wort im Mund umdrehen dürfte, würde ich halt sagen, was bedeutet das denn?
Qualität bedeutet, Software wird langsamer und teurer?
Das ist offensichtlich absurd.
Das heißt also, ich muss eine andere Art von Kommunikation haben und ich muss andere Vorteile in den Raum stellen.
Und das muss auch gehen, denn die Art und Weise, wie Techniker darunter leiden, dass irgendwie die Qualität schlecht ist, wird sich in Zahlen niederschlagen.
Es ist ja nicht so, dass man irgendwie da sitzt und sagt, wow, das ist langsam und frustrierend, aber es ist ja effizient aus einem wirtschaftlichen Aspekt heraus, sondern es geht ja Hand in Hand.
Das, wo wir Techniker frustriert sind und viel Zeit brauchen, ist etwas, was auch wirtschaftlich ineffizient ist.
Das bedeutet, dass man eigentlich sagen müsste, wenn es dem Kunden nicht schnell und billig genug sein kann, dann liefern wir gute Qualität, weil damit kriegen wir billige Software.
Und ich kann dir zeigen, mit welchen Maßnahmen wir diese Software billiger bekommen.
Und das bedeutet aber, dass da eben tatsächlich ein Kommunikationsproblem ist und es nicht klar ist, wie man das sozusagen klar kommunizieren kann.
Die in Hamburg hat geschrieben, aber wie kriegt man die Leute dazu, drohende Kosten früher anzugeben, wenn man das nicht genau schätzen kann?
Ich bin sozusagen nicht sicher, ob ich die Frage so ganz richtig verstehe.
Ich sage mal was dazu und es gibt ja immer die Möglichkeit, Nachfragen zu stellen.
Das Erste, was ich gesagt habe, ist, ich glaube nicht, dass das Grundproblem von Qualität ist, dass man sagt, ich habe hier eine Entscheidung und ich nehme jetzt die Abkürzung und ich weiß, dass diese Abkürzung folgenden Vor- und folgenden Nachteil hat, sondern meine Behauptung ist, dass in den meisten Fällen das einfach durch Zeitdruck entsteht.
Das heißt also, wenn ich in der Situation bin, dass ich sage, ich habe hier zwei Möglichkeiten und ich schätze die objektiv ab und mache mir über die Konsequenzen aktiv Gedanken, dann sind wir meiner Ansicht nach schon nahe beim Ergebnis.
Das heißt, ich würde behaupten, wenn ich schon früh die Kosten und die möglichen Effekte mir überlege und eine aktive Entscheidung treffe, ist das Problem vielleicht schon gelöst.
Und das andere ist, Schätzen als Basis von Entscheidungen ist ja tagtägliches Geschäft.
Das machen wir ja irgendwie dauernd.
Agiles Schätzen ist genau diese Basis und ich glaube, was dabei halt wichtig ist, ist, das soll ja nur eine Entscheidung ermöglichen.
Also es ist ja nicht so, dass ich daraus eine Deadline ableite und jetzt sage, also in genau zehn Monaten haben wir das und das geschafft oder in zwei Wochen oder so, sondern es geht darum zu sagen, ich habe diese beiden Alternativen.
Diese Alternative ist aufwendiger als die andere, hat aber dafür den Vorteil, dass wir langfristig leichter das System modifizieren können, während die andere eben genau das Gegenteil hat.
Es ist halt kurzfristig leicht realisierbar, hat aber langfristig dann zu Schwierigkeiten und da muss ich abschätzen, welche von den beiden mit dem, was ich im Moment weiß, wahrscheinlich die bessere Alternative ist.
Und dafür brauche ich aber jetzt nicht zu sagen, das eine sind zehn oder das andere sind fünf Tage oder zehn oder fünf Wochen, Monate, was auch immer, sondern ich muss halt nur sagen, das ist halt wahrscheinlich die Sache, die halt weniger aufwendig ist in Summe, nicht also eben auch über die längere Laufzeit und das bedeutet, ich muss nur eine grobgranulare Abschätzung haben.
## Das Spannungsfeld zwischen Qualität und Zeitdruck

Gut, was bedeutet das jetzt?
Das ist so ein bisschen mein Problem, also das, was ich mir jetzt eigentlich wünschen würde, wäre, dass wir eben genau diese Diskussion, von daher passt die Frage von DIN Hamburg gerade sehr gut da rein, dass wir die halt jetzt treffen, diskutieren würden.
Also wir würden jetzt irgendwie dem Team sagen, hört mal zu, wir haben ja zwei Möglichkeiten, entweder wir machen es halt so oder wir machen es halt so, welche ist denn die bessere Möglichkeit?
Und dazu muss jetzt irgendwie Management sagen, also wahrscheinlich werden wir dieses Stück Code nie wieder anfassen oder am 24.12. ist das Ding sowieso obsolet und wir werfen es weg.
Das muss irgendwie glaubwürdig sein oder nicht.
Vielleicht sagt das Management auch, naja, wenn wir es halt am 1.12. nicht geliefert haben, ist es sowieso sinnlos, weil dann ist halt der Business Case weg, das muss also auf jeden Fall da sein.
Also wir müssen halt Informationen über eine harte Deadline, über eine weiche Deadline, über den Trade-Off, über die Dinge, die halt in Zukunft da in Änderung kommen und so weiter, die müssten wir halt alle bekommen und gleichzeitig müsste dann halt die Technik dazu willentlich und in der Lage sein, das Zeug irgendwie abzuschätzen, wie die in Hamburg halt sagt und irgendwie auch sozusagen dem Management zu vertrauen, dass das, was die sagen, also wenn die sagen, da ist halt diese Deadline oder wenn die sagen nicht, das fassen wir nie wieder an oder wir werfen es weg, das eben auch tatsächlich zu glauben.
So und das würde dann zu einer offenen Kommunikation führen und dann würden wir halt irgendeine Entscheidung treffen.
So und das Problem bei der Sache ist, dass das glaube ich in den allermeisten Fällen oder lass mich anders sagen, ich würde behaupten, das wünsche ich mir, aber das kriege ich halt in der Realität in dem Projekt meistens nicht hin, was dazu führt, dass halt man andere Maßnahmen ergreifen kann, die irgendwie funktionieren.
Also zum Beispiel Maßnahmen, dass man sagt, von dem 14-Tage-Sprint oder 10-Tage-Sprint nehmen wir uns jetzt zwei Tage und die investieren wir halt in die Verbesserung des Systems.
So und das ist etwas, was klar sagt, es ist eingehalten oder nicht.
Wir können es halt am Ende uns angucken und wir können halt sagen, von den zehn Tagen Sprint sind halt zwei Tage tatsächlich in Verbesserung gelaufen, geflossen.
Jetzt können wir halt anschließend ein Checkmark setzen und können halt sagen, das ist tatsächlich passiert.
Das ist also easy und diese Zeit können wir halt auch sozusagen leicht schützen.
Wir tun halt so, als hätte dieses Team eben nur eine Kapazität von acht Tagen, nicht von zehn und diese zwei Tage sind eben tatsächlich zur Verbesserung der Qualität da.
Wir können also dadurch dafür sorgen, dass eben dieser Zeitdruck sozusagen gemanagt wird und eben nicht zu stark wird und wir können irgendwie dadurch versuchen, dieses System zu sanieren.
Das Problem bei der Sache ist, dass man dadurch auch eben diese Entscheidung so ein bisschen entkoppelt von dem, was das Management benötigt.
Also was da halt im Worst-Case rauskommen kann, ist, dass man sagt, wir machen halt diesen Teil des Systems total super und leicht wartbar und dann kommt halt irgendwie jemand und sagt, hier ist ein Requirement und dann stellt man halt fest, dieses Requirement ist irgendwo anders und das, was man gerade so schön poliert hat an Code, das wird halt nie wieder angefasst.
Das würde aber oder umgekehrt oder nicht, wir bauen halt hochoptimierten Code, schönen Code für Dinge, die halt mit Perspektive überhaupt nicht weiter genutzt werden und so weiter.
Dafür, um sowas zu vermeiden, müsste man jetzt diese Kommunikation haben, die ist aber schwierig.
Was wir außerdem dadurch ausschließen, ist eben, dass wir jetzt das Budget vielleicht erweitern können.
Vielleicht ist es ja gerade sinnvoll, noch mehr Zeit in Qualität zu investieren und weniger Zeit darin, neue Features zu schruppen.
Das würde aber bedeuten, dass wir fundamental was anders machen müssen, also das Budget ändern müssen.
Und das könnten wir nur, wenn jemand sagt, im Moment ist vielleicht die Qualität wichtiger als die Weiterentwicklung.
Und insgesamt, um es nochmal klar zu sagen, die Größe des Problems kann man gar nicht unterschätzen.
Es gab da vor einiger Zeit, ich verlinke das noch, einen Artikel auf Mastodon, der war sehr, sehr schön, wo jemand gesagt hat, okay, bis Ende des Jahres halte ich das hier noch durch, aber dann gehe ich halt und hat sich dann in die Arbeit begeben mit irgendjemandem zusammen und hat dann im Rahmen dessen an dem Tag noch gesagt, okay, ich halte das hier nicht mehr aus, ich gehe jetzt.
Und zwar eben wegen dieser Schmerzen, die tatsächlich dort in der Wartung sozusagen drin sind.
Und das ist halt, wie soll ich sagen, etwas, was zutiefst beeindruckend ist und zwar nicht in einer positiven Art und Weise.
Und nicht Projekte können halt in diesen völligen Stillstand kommen, wo sie de facto nicht mehr dazu in der Lage sind, überhaupt noch irgendwas zu ändern.
Und das kann irgendwie dann eben zu einem ganz, ganz krassen Problem führen.
Gleichzeitig muss man halt sagen, und das ist etwas, was ich eben genau auf dieser Keynote von den XP Days gesagt habe, die technische Exzellenz im Umkehrschluss führt nicht unbedingt zu einem Geschäftsvorteil.
Also man kann halt auch mit anderen Mechanismen eben sich ein Geschäftsvorteil erreichen.
Man kann Menschen ausbeuten, man kann das System betrügen.
Es gibt auch Consultancies, die halt neue Menschen frisch von der Uni halt jedes Jahr anstellen und nicht in die Dauerhafte investieren, sondern man erwartet, dass sie nach zwei oder drei Jahren, wenn sie keinen Bock mehr haben, weil sie halt unter hohem Druck Software entwickeln müssen, dann irgendwo anders hingehen.
Das funktioniert also auch in unserer Branche mit dieser Ausbeutung.
Wir sind da sicherlich privilegiert.
Das ist eine andere Ebene von Ausbeutung, als wenn irgendjemand im Akkord irgendwo am Fließband arbeitet.
Aber es gibt eben auch bei uns Ausbeutung.
Es gibt bei uns auch Unternehmen, die halt das System betrügen, also nicht die Fossilindustrie wird halt gepäppelt von der öffentlichen Hand und muss sich eben dem Wettbewerb nicht stellen.
Und das bedeutet, die sind irgendwie entkoppelt davon, dass sie halt irgendwie jetzt technisch exzellente Software bauen müssen oder überhaupt irgendwas dort exzellent bauen müssen, sondern die haben eben andere Mechanismen gefunden, um im Wettbewerb zu bestehen.
Anders gesagt, nur Softwaremenschen glauben, dass sich alles um Software dreht und kümmert.
Was also bedeutet, dass Wettbewerb vielfältiger stattfindet und Softwarequalität eben nur ein Faktor ist, der dazu führt, dass Unternehmen kompetitiv sind.
Jetzt kommt noch ein weiterer Punkt, der, glaube ich, total wichtig ist.
Und also ein Punkt, den ich halt machen wollte, ist, ich glaube, diese Kommunikation hat ein Problem und das ist etwas, was wir wirklich verbessern können und wo ich halt auch einige Dinge wirklich schwierig finde.
Also mir ist zum Beispiel überhaupt nicht klar, warum Menschen halt einfach ohne Feedback zu geben halt ertragen, dass die Systeme, die sie bauen, ganz, ganz schrecklich sind und dass sie halt irgendwie sozusagen jeden Tag Schmerzen erleiden.
Da würde ich mir halt wünschen und halt auch glauben, dass man da mal Feedback geben kann.
Und das ist so einer der Punkte und das ist dann eben nicht ein Management-Problem, sondern Management entscheidet nach bestem Wissen und Gewissen und bekommt eben nicht die richtigen Informationen oder nicht ausreichend Informationen oder nicht aus Informationen so kommuniziert, wie es eigentlich notwendig wäre.
Der andere Punkt ist und das finde ich eigentlich auch nochmal wichtig darauf hinzuweisen, also es ist nicht so, dass nur wir als Techniker darunter leiden, dass die Qualität der Systeme halt irgendwie suboptimal ist, sondern da ist halt noch auch Management und Business leidet darunter.
Also eigentlich macht dieser wahrgenommene Gegensatz gar keinen Sinn und daher finde ich eben auch Kommunikation wichtig.
Und Hintergrund ist einfach der, wenn ich mir halt angucke, was ich irgendwie so tue, Sanierung alter Systeme, Architekturrenovierung, solche Geschichten, das ist ein Schwerpunkt meiner Arbeit.
Und das ist etwas, also nicht Migration weg vom Monolithen, ich möchte irgendwie das System wartbarer bekommen und das sind Projekte, die aus dem Management kommen.
Einmal deswegen, weil sie halt wahnsinnig teuer sind.
Also ich sage halt, ich will das System perspektivisch wegwerfen und neu machen.
Das ist wahnsinnig teuer.
Das ist nichts, wo jetzt ein Techniker sich hinstellen kann und sagen kann, ich bin frustriert, ich würde es irgendwie besser bauen, sondern es ist etwas, wo irgendwie sich Euros draus sozusagen versprochen werden.
Was eben bedeutet, dass das alte System sozusagen nicht abgeschrieben beziehungsweise tot ist und ich muss es eben komplett neu nochmal aufbauen.
Was also bedeutet, ich habe eine massive Investition.
Und ich glaube nicht, dass darüber Menschen, die so betriebswirtschaftlich denken, glücklich sind, wenn sie sagen, wir haben da eine Software, die funktioniert ja im Prinzip auch, wir müssen sie leider wegwerfen, weil wir können sie leider nicht mehr weiter betreiben und nicht mehr weiter warten.
Das heißt also, da ist halt auch ein Problem und das ist auch etwas, was manchmal so passiert, dass so ein Management wechselt, wo dann gesagt wird, okay, wir haben hier die alte Software-Landschaft und jetzt haben wir eben jemanden, der da neu rangehen will, der vielleicht in irgendeiner Weise Zukunft, Progress, Fortschritt haben möchte und die Person kümmert sich jetzt darum, dieses System tatsächlich irgendwie sozusagen wegzuwerfen und neu zu machen.
Und das bedeutet halt, dass auch aus dieser Perspektive Wartbarkeit eigentlich wichtig ist, denn das sind teure Projekte, die oft ihre Ziele auch nicht erreichen und damit leiden sie halt sozusagen unter der eigenen Entscheidung.
Und dahinter steckt, glaube ich, auch die Art und Weise, wie man Management betreibt oder wie man arbeiten will.
Wenn ich sage, ich bin Firmeninhaber, dann möchte ich ein nachhaltiges Geschäftsmodell haben, was sich nachhaltig lohnt.
Wenn ich so etwas habe, dass ich an Quartalszahlen gemessen werde, in irgendeiner Art und Weise ist vielleicht meine Inzentivierung für eine nachhaltige Entwicklung deutlich geringer.
Es gibt börsennotierte Unternehmen, die irgendwie Quartalszahlen publizieren und langfristige Strategie verfolgen.
Das muss man sich aber leisten können.
Es gibt sicher, wenn man Quartalszahlen abliefern muss, liegt der Drang nahe, kurzfristige Vorteile zu generieren und dann kann man nicht in diese Nachhaltigkeit investieren.
Wir reden eigentlich darüber, will ich Software nachhaltig dauerhaft implementieren oder kurzfristig?
Das ist eigentlich eine Businessfrage und das zeigt sich dann auch an anderen ständig.
Es gibt Unternehmen, mir würde da zum Beispiel ein großer Betreiber von Bahninfrastruktur in Europa einfallen, wo man sagen muss, die sind jetzt dabei und schauen, dass sie ihr komplettes Schienennetz neu machen müssen.
Das ist dann eben etwas, wo nicht Software, sondern was anderes komplett saniert werden muss.
Da sind aber auch überraschende Schwierigkeiten.
Warum mache ich dieses massive Investment?
Weil ich unter Druck stehe, weil ich neue Produkte launchen will.
Welche Produkte willst du launchen?
Da kommt manchmal keine Antwort oder es ist nicht klar, wie dieses Ziel, ich will neue Produkte launchen, vielleicht kann man ja konkrete nennen, wie das jetzt zusammenpasst mit der Grundsanierung der Software.
Da ist halt auch eine Optimierung, die dann darauf hinausläuft, dass man sich dann überlegen muss, wenn wir jetzt sagen, wir wollen ein neues Produkt launchen, irgendein Finanzprodukt, eine Cyber-Versicherung, mir fällt gerade nichts Sinnvolles ein, dann sollten wir im Rahmen der Software-Sanierung die Frage beantworten, wie kann ich denn diese Cyber-Versicherung tatsächlich launchen.
Da hilft es mir wahrscheinlich nichts, wenn ich mein Lebensversicherungszeug modernisiere.
Und da könnte man jetzt sagen, okay, cool, du erzählst gerade offensichtliche Dinge.
Ja, aber ich befürchte, dass in vielen Situationen genau diese Frage, also was ist denn das, was am Markt eigentlich passieren soll, wie passt das zur Renovierung, oft nicht zusammenpasst.
Und ich glaube, das hat auch wieder diese Geschichte mit, wir wollen ja ein technisch gutes System entwickeln und das soll irgendwie abstrakt gut sein, aber es ist daneben nicht abgestimmt auf das, was tatsächlich im Markt passiert.
Der Christian Trutz schreibt, ich erlebe diesen Schmerz auf Entwickler- und Managementseite, oft ist aber das Problem, dass Technikerinnen und Management aneinander vorbeireden.
Danke, das ist das, was ich eigentlich versuche zu sagen und insbesondere ist halt mein Feedback, da müssen wir daran arbeiten, unsere Kommunikation zu verbessern, weil wir können nicht erwarten, dass die Kommunikation des Managements besser wird.
Eigentlich sollte es diesen Graben nicht geben, aber wenn es den gibt, können wir an unserer Seite arbeiten, aber weniger an der anderen Seite und das bedeutet eben, dass meine Empfehlung wäre, sich in diese Welt zu versuchen hineinzuversetzen oder sich tatsächlich mal jemanden zu nehmen und zu schauen, was diese Person denn so als Themen sieht und wie die überhaupt typischerweise redet und agiert.
Wir haben da auch eine Episode gemacht zum Thema Firmenpolitik mit dem Michael Ahrens zusammen, der eben ein definierter Nicht-Techniker ist und da kann man auch nochmal was darüber sehen, wie man dort kommunizieren kann.
Ein Gedanke, den ich noch sozusagen reinwerfen wollte.
Ich habe halt oft dieses Totschlag-Beispiel, also nehmen wir mal an, ich bin ein Start-Up.
Ich habe also jetzt eine Million Euro.
Ich kann mit der Million Euro sagen wir mal ein Jahr überleben und jetzt fange ich an und baue eine Software für meinen Business Case und jetzt bin ich nach einem Jahr fertig.
Ein Szenario, ich habe halt eine dreckige, schreckliche Software, die aber das Business Problem löst und ich habe dadurch Kunden.
Das ist super, weil dann kann ich mehr Geld besorgen oder ich habe vielleicht sogar Umsatz und Gewinn und kann aus diesem Geld meine weitere Entwicklung finanzieren, die dann möglicherweise bedeutet, dass ich diese Software wegwerfen muss und neu implementieren muss.
Das ist btw. das, wenn man sich das in mir anschaut, was viele von den großen Unternehmen tatsächlich gemacht haben.
Die erste Iteration der Amazon Software zum Beispiel ist irgendwie genau so eine.
Die Alternative wäre, oder das andere Szenario wäre, dass ich dort eine Software habe, die ist halt wartbar, saubere Code-Qualität, langfristig weiterentwickelbar, aber leider habe ich keine Leute, die die Software benutzen und ich habe dadurch eben nicht die Möglichkeit, Geld aufzutreiben.
Dann habe ich halt einen Fehler, also dann bin ich eigentlich tot.
Das heißt, die Software-Qualität im Sinne von Wartbarkeit nützt mir ja nichts.
Ich brauche halt andere Software-Qualität, ich brauche halt Software-Qualität im Sinne von Benutzerfreundlichkeit und diese Dinge, die damit zusammenhängen.
Da ist eben tatsächlich eine nachhaltige Entwicklung viel am Platze.
Das ist so ein bisschen ein auf die Spitze getriebenes Beispiel.
Das ist aber etwas, was tatsächlich ein typisches Pattern ist.
Viele von den erfolgreichen Start-ups, die ich so kenne, haben irgendwie genau dieses Thema, dass sie sagen, wir haben so einen schrecklichen alten Monolithen, von dem müssen wir halt irgendwie weg und der ist halt irgendwie auch schrecklich und unwartbar.
Das ist wahrscheinlich genau das Überblöpsel hiervon und das sind die Unternehmen, die es überlebt haben und die jetzt sagen, dieser schreckliche Monolith muss weg.
Die anderen Unternehmen, die es nicht überlebt haben, haben wahrscheinlich schreckliche Monolithen, die heute niemanden mehr interessieren, weil sie halt einfach tote Software sind, weil es diese Unternehmen nicht mehr gibt.
Ich bin nicht sicher, was das für etablierte Unternehmen bedeutet.
Wenn ich eine Versicherung bin, habe ich da dasselbe, dass ich jetzt sage, ich will etwas aufbauen und ich will diesen Business Case erschließen und das muss ich halt erst mal tun, weiß ich nicht.
Und da kommt wieder diese Frage nach dem Zeitdruck, also ist der Zeitdruck real oder ist der irreal?
Kann man dann überhaupt nachhaltig arbeiten?
Wenn jetzt die Aussage ist, auch bei etablierten Unternehmen gibt es halt genau dieses Thema.
Ich habe an einem System gearbeitet, das die Grundannahme hatte, dass Bestellungen über Nacht irgendwie an Lager zugeteilt werden können und das ist heute offensichtlich nicht mehr so.
Wenn ich heute irgendwo online was bestelle, dann will ich vielleicht, dass es morgen da ist.
Das heißt, wenn morgen erst das Lager anfängt, das zu kommissionieren, ist das halt doof.
Das sollten Sie jetzt schon kurzfristig machen, idealerweise sofort.
Dann ist die Frage, wann baue ich das System so um?
Das heißt, ich baue es um von Batch-Verarbeitung hin zu irgendwas anderem, also mehr Batches, die laufen, nicht nur einer pro Nacht, sondern im Stundentakt laufen, vielleicht auch so was, dass ich eventbasiert arbeite, dass ich sage, da kommt jetzt eine Bestellung rein und dann läuft halt perspektivisch jemand im Lager los und holt sich das, keine Ahnung.
Da ist die Frage, kann ich das vorher antizipieren?
Also kann ich vorher antizipieren, dass diese Entscheidungsgrund seines Batches eine Entscheidung ist, die ich perspektivisch irgendwann revidieren will?
Ich würde behaupten, wahrscheinlich nicht und das ist auch etwas, was nicht so unwahrscheinlich ist oder jetzt so ein Ausreißer ist.
Mit Überweisung haben wir dasselbe Thema.
Die sind halt früher über Nacht gekommen und sind am nächsten Tag gewesen.
Jetzt kommen sie mittlerweile untertäglich, das heißt also, die Überweisungssysteme müssen sich auch entsprechend modifizieren und dieses gesamte Thema, auch Monolithen und Module sind eben auch im Management-Mitarbeiter-Thema, also auch da ist diese Wartbarkeit ein Thema.
Vielleicht noch ein Hinweis.
Ich verspreche mir einiges von dieser Idee, die wir diskutiert haben bei der Tidy First Episode mit dem Ken Beck, weil der ein gutes Modell gefunden hat, dieses Problem zu illustrieren.
Also der sagt halt, es gibt zwei Möglichkeiten, ich kann jetzt Geld investieren für Dinge, die unmittelbar Geld bringen oder ich kann irgendwie Optionen kaufen.
Also ich kann jetzt zum Beispiel eine Option kaufen, die sagt, nächstes Jahr kriegst du Öl, Stahl oder irgendwas geliefert und das ist wertvoll, weil damit kann ich jetzt eine Planung eintreten.
Also ich kann jetzt für nächstes Jahr sagen, ich will Rennräder bauen, die will ich aus Stahlrohren bauen, ich kaufe mir jetzt eine Option, dass mir jemand Stahlrohre liefert und dadurch kann ich jetzt anfangen und kann sagen, also wenn nächstes Jahr im Sommergeschäft meine teuren Rennräder kaufen wollt, die werden halt so und so viel kosten und das habe ich halt irgendwie abgesichert, weil ich eben jemanden habe, der mir zu einem bestimmten Preis Stahlrohre liefern kann und dann habe ich eben dort genau diese Option, die zu kaufen.
Und das Schöne ist halt, wenn der Marktpreis zu dem Zeitpunkt niedriger ist, dann kriege ich sie sogar noch billiger, aber ich kann mein Risiko managen.
Und das habe ich in der Softwareentwicklung genauso.
Ich kann jetzt der Entwicklerin sagen, setze ich halt hin und baue ein Feature, dann verdiene ich sofort Geld oder ich sage halt, setze ich hin und investiere darin, dass ich in einem Jahr noch mehr Geld verdienen kann, weil ich dann ein Systemteil habe, das gut änderbar ist.
Ich glaube, das ist als Erklärmodell hilfreich.
Ich finde das besser als das Erklärmodell für TechnicAdapt, aber ich bin nicht sicher, ob es hilft, weil dieses Thema mit der Nachhaltigkeit fällt uns ja generell schwer.
Also ein nachhaltiges Geschäftsmodell, wo ich halt nicht kurzfristig gierig bin, das ist eben ein generelles Problem und vielleicht muss ich das eben auch nicht sein.
Also vielleicht muss ich auch nicht nachhaltig sein.
Vielleicht ist in der Wirtschaft eben sowas kurzfristiges auch oft eine gute Idee.
So, was bedeutet das?
Zeitdruck ist eben, glaube ich, einer der wichtigen Auslöser für das, was wir hier beobachten.
Ich sollte halt diese Abwägung Zeitdruck gegen die Option, das System zu verbessern, irgendwie treffen.
Ich glaube, dieses Modell von Ken Beck ist da gut.
Ob es in der Praxis funktioniert, weiß ich nicht.
Was eben dazu führt, das glaube ich, die Möglichkeit, Systeme dauerhaft qualitativ hochwertig zu halten, in der Praxis diese Budgets sind.
Aber für die Budgets muss ich halt, da schränke ich sozusagen das Qualitätsstreben der EntwicklerInnen ein, indem ich eben sage, hier ist die Zeit, die ihr dafür habt, eure Qualität zu verbessern.
Das bedeutet halt, dieses maximale Qualitätsziel, was wir EntwicklerInnen an vielen Stellen haben und was ich in den Keynote kritisiert habe, ist irgendwie schwierig.
Reiner Zeitdruck aus Management ist schwierig.
Ich würde mir eigentlich eine Kommunikation darüber wünschen.
Und das ist, glaube ich, ein echt schwieriges Thema.
Das ist, glaube ich, sehr schwer, das zu erreichen.
Und da ist wieder dieses Thema mit der Kommunikation, was wir in den letzten Episoden, da haben wir ganz viel über Kommunikation gemacht, wie man das konkret hinbekommt.
Das ist dann eigentlich das Werkzeug, was dort entscheidend ist, was eben wiederum bedeutet, auch im Vergleich zu dem, was jetzt irgendwie so an Fragen am Anfang kam und auch im Vorfeld an Anfragen kam.
Ich glaube gar nicht so sehr, dass das Problem ist, dass wir nicht wissen, wie wir qualitativ hochwertige Software bauen.
Ich glaube, das Problem ist, wir kommen sozusagen nicht dazu.
Und das kann man natürlich auch wieder in Abrede stellen.
Man kann sagen, naja, aber bestimmte Maßnahmen, bestimmte Architektur-Patterns, vielleicht sind die halt nicht allgemein bekannt.
Grundlagen von Modularisierung sind zum Beispiel so etwas, wo ich selber das Gefühl habe, die sind nicht allgemein bekannt, aber sollten es sein.
Ich glaube trotzdem, dass eigentlich dieses andere Thema Kommunikation, dieser Trade-Off, dass das der entscheidende Punkt ist.
Gut, ich schaue nochmal, ob ich irgendwelche Themen irgendwo übersehen habe, irgendwelche Fragen, die halt noch da sind.
Das scheint nicht der Fall zu sein.
Dann haben wir eigentlich, also ich weise noch mal kurz hin auf den Spreadshirt-Shop, den man hier sieht, wo man ganz viele ganz tolle Dinge einkaufen kann.
Also wir verdienen daran nichts.
Das war nicht die Idee.
Sprich, wir, genau, die sind halt Kostendecken, beziehungsweise wenn wir da tatsächlich was verdienen, wenn wir das irgendwie einem guten Zweck zur Verfügung stellen.
Und die nächste Episode ist dann am 7.
Das ist also tatsächlich Freitag in der Woche mit der Diana Montaljon, zusammen mit Lisa, die dann über System Thinking redet.
Die hatten wir auch schon mal im Stream, war sehr spannend.
Und genau, vielleicht schaltet ihr euch da wieder ein.
Das wird dann in Englisch sein.
Dann würde ich sagen, vielen Dank.
Genau, heute am Mittwoch aufgrund der Feiertage morgen und übermorgen.
Und nächste Woche sehen wir uns dann irgendwie nicht, weil Lisa da das übernimmt.
Aber vielleicht an einer anderen Stelle.
Vielen Dank.
Und so, nee, stimmt gar nicht.
Das ist nämlich komplizierter.
Also am 8. am Freitag ist Cosima Laube zum Thema Coaching mit Lisa da.
Und der Termin am Donnerstag am 7. den macht Lisa auch mit der Diana zusammen.
Dann würde ich sagen, vielen Dank.
Schönes Wochenende schon mal.
Schöne Feiertage und bis dahin.
Und danke für die Fragen, für den vielen Input.