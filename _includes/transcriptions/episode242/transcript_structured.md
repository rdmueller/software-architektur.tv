# Folge 242 - Generative AI Meets Software Architecture mit Ralf D.
Müller Hallo, ich bin Eberhard Wolff.
Freitags mache ich oder Lisa Moritz ein Livestream zum Thema Software-Architektur, oft zusammen mit Gästen.
Dieser Podcast ist das Audio des Streams.
Weitere Folgen, Sketchnotes und vieles mehr findet ihr unter software-architektur.tv.
## Einführung in das Thema Generative AI

Ja, herzlich willkommen zu unserer heutigen Folge von Software-Architektur im Stream.
Lars Holbeckamp ist leider kurzfristig verhindert.
Deswegen ist Eberhard Wolff eingesprungen.
Wir werden die Rollen etwas umdrehen, weil eigentlich hatte ich vor, Lars als Experten zu interviewen, zu dem Thema Gen AI meets Architektur.
Und, Moment.
Sorry.
Sorry, ich habe gerade Probleme gekriegt hier mit meinem Audio-Setup.
## Experiment mit einem LLM

Also, wir werden die Rollen umdrehen.
Ich werde nicht Lars Holbeckamp als Experten interviewen, sondern ich werde jetzt über meine Erfahrungen mit Gen AI und der Software-Architektur sprechen und Eberhard Wolff wird hoffentlich seine Expertenmeinung dazu einbringen.
Und starten wollten wir jetzt mit einem Experiment, was ich gemacht habe.
Das heißt, ich habe die Maschine benutzt, also ein LLM, um ein komplettes Projekt zu erstellen.
In einem Channel hat sich ein User beklagt, dass es für ASCII-Doc immer noch keinen Linter gibt seit mehreren Jahren.
### Ziel des Experiments

Und ich habe mir gedacht, ach Mensch, das ist doch eigentlich ein schönes Real-World-Problem, um jetzt mal ein Projekt mit der KI zu starten.
Genau, vielleicht kurz dazu, also ## Überblick über ASCII-Doc und Linter

ASCII-Doc ist eben ein System, mit dem man Dokumentation schreiben kann.
Ich glaube, nicht nur Architektur-Dokumentation, sondern im Allgemeinen.
### Was ist ein Linter?

Und ein Linter ist so ein Ding, was irgendwie sagt, okay, das Zeug, was du irgendwie eingibst, ist sinnvoll oder weniger sinnvoll.
Und das war eben das Missing-Feature.
Und wir hatten dich auch mehrmals im Stream zu genau diesem Thema mit Architektur-Dokumentation.
### Was ist ASCII-Doc?

ASCII-Doc ist so eins der Projekte, wo du ein paar Sachen machst.
Und das ist so ein bisschen der Hintergrund.
Genau, exakt.
Also ASCII-Doc, das Markdown für technische Dokumentation, sage ich mal so.
Und der Linter soll eben überprüfen, ob so ein paar Styles eingehalten worden sind, dass keine Überschriftenlevel übersprungen werden oder sowas.
Und ich habe mir gedacht, das wäre jetzt mal wirklich ein gutes Real-World-Projekt, um zu gucken, ob ich das mit der KI programmieren kann.
Ich habe mein eigenes Chatbot-Frontend, was so ein Agentic-Workflow entwickelt hat.
Das heißt, es hat Function-Calls, die es aufrufen kann.
Zu diesen Function-Calls gehören zum Beispiel dazu, dass es Dbash nutzen kann, dass es Python-Code ausführen kann.
Und ich habe ein System-Comp geschrieben, der es angewiesen hat.
Sorry, was ist ein Agentic-Workflow? Über dieses Thema allein kann ich eine Stunde füllen.
### Agentic Workflow

Ein Agentic-Workflow ist ein selbst ablaufender, eigenständig ablaufender Workflow.
Meistens spricht man auch von einem Workflow mit Agenten.
Das heißt, ich habe nicht nur einen Chat-Partner, einen LLM, sondern ich habe mehrere LLMs in unterschiedlichen Rollen.
Bei mir sind es nicht mehrere LLMs in unterschiedlichen Rollen, sondern es ist ein LLM.
Und wenn es ein Tool aufruft, wie zum Beispiel bei Chat.JPG, kann Chat.JPG einen Python-Interpreter aufrufen oder kann ein Bild generieren.
Und nach dem Aufruf geht eigentlich die Kontrolle zurück an den User.
Das heißt, es läuft nicht eigenständig weiter.
Manchmal kriege ich auch Chat.JPG zu dem Eigenständigen.
Ich habe das jetzt so gemacht, dass der Control-Flow bei dem LLM bleibt.
Und das hat den interessanten Nebeneffekt, dass wenn das LLM Code ausführt und es kommt vom Compiler ein Syntax-Error oder so, dann sagt das LLM, Moment, ich glaube, ich weiß, woran es liegt.
Ich schreibe den Code nochmal neu, probiere es nochmal aus.
Ich habe auch, weil ich in Richtung Architekturarbeit mit der GenAI gehen will, habe ich ein Plug-In, einen Function Call aufgebaut, der ein Plant-URL-Diagramm rendern kann.
Das heißt, Chat.JPG selbst erzeugt Plant-URL-Code, zeigt den Code an, da sehe ich noch kein Diagramm.
Wenn ich dann zum Beispiel über den Coki-Server, Coki.io gehe, dann kann der das Diagramm über eine Library rendern, gibt manchmal Syntax-Errors zurück.
Da reagiert das LLM dann selbstständig drauf, korrigiert den Code, bis dann eben vom Coki-Server das Diagramm kommt und er zeigt dann das Diagramm an.
Das ist total cool.
Also er kann sich über diesen Agentic-Workflow selbst korrigieren.
Und bei diesem Linter habe ich mir gedacht, das ist so eine einfache Architektur.
Es ist ein Programm, was irgendwie über den ASCII-Doc-Source-Code gehen muss und verschiedene Regeln anwendet.
Regeln, die eben bestimmte Eigenschaften überprüfen.
## Implementierung des Linters

Das heißt, diese Regeln sind einzelne Module, die so ein LLM einzeln implementieren kann.
### Testgetriebene Entwicklung

Und ich habe das Modell halt angewiesen, dass es testgetrieben arbeiten soll.
Und dadurch hat es erstmal Tests geschrieben, hat dann Code geschrieben und die Tests sind fehlgeschlagen und es ging in die Iteration rein.
Und es hat tatsächlich ein komplettes Projekt erzeugt.
Und das ist ja jetzt erstmal Software-Entwicklung.
Aber zum Schluss habe ich, als er die ersten Regeln implementiert hat, habe ich mich daran erinnert, dass ich ihm auch schon beigebracht habe, mit dem Architecture Communication Canvas zu arbeiten.
Also das ist so ein One-Pager, der eine Architektur beschreibt.
Und ich habe es gebeten, diesen One-Pager zu erstellen.
Es hat es gemacht.
Und dann habe ich nochmal nach den Sternen gegriffen und habe gesagt, du kennst auch Arc42, das Template für Architekturdokumentation.
Erstelle doch mal bitte eine komplette Architekturdokumentation.
Und auch das hat er gemacht.
Und das Spannende ist, wir hatten ja schon eine Folge über einen ähnlichen Ansatz, wo wir versucht haben, die ISAQB-Aufgabe zu lösen.
Da kannte das Modell aber nicht den vollen Umfang meiner Lösungen, weil ich vieles im Kopf hatte.
Es konnte mir Fragen stellen, aber trotzdem blieb für das Modell einiges im Verborgenen.
Hier hat es jetzt selbst die Architekturentscheidungen getroffen und dokumentiert.
Und dadurch hat es überhaupt die Möglichkeit gehabt, diese Entscheidungen zu dokumentieren.
Mal für mich, was hast du jetzt diesem System gesagt?
Also wenn du dem sagst, wir brauchen einen ASCII-Doc-Linter.
Du musst ja jetzt ein Set von Regeln haben.
Woher kommt dieses Set von Regeln, das sagt, okay, das ist das, was wir mit diesem Linter überprüfen wollen.
Du hattest jetzt gesagt, dass zum Beispiel nicht eine Überschrift-Hierarchie übersprungen wird.
Ich nehme an, dass du damit meinst, es ist nicht 1.1.1 gleich nach 1, sondern es ist eben 1.1.1 und dann 1.1.1.
Und da müsstest du jetzt sagen, okay, das ist eine Regel, die ist sinnvoll aus irgendwelchen Gründen.
Und du müsstest halt irgendwie definieren, wie diese Regel aussieht.
Wie ist das alles zustande gekommen?
Auch da habe ich dem Modell das meiste selbst überlassen.
Ich habe natürlich sprachlich drei Regeln mitgegeben, so nach dem Motto, die Überschriftenreihenfolge oder die Überschriften-Hierarchie.
Ich weiß gar nicht mehr, was die anderen beiden waren.
Und habe dem Modell dann gesagt, dass es bitte weitere Regeln sich ausdenken soll.
Und da kommt dieses Weltwissen ins Spiel von dem Modell.
Es kennt andere Linter, es kennt zum Beispiel den Markdown-Linter.
Und es hat sich ganz gut Regeln ausgedacht.
Und jetzt gucke ich mal rein.
Also Überschriften, da hat es jetzt drei Regeln.
Zum Beispiel darf man bei ASCII-Doc, der oberste Überschriften-Level ist den Buchtitel vorbehalten.
Ein Buch kann nicht mehrere Buchtitel haben.
Deswegen darf es diesen Level nur einmal geben.
Dann gibt es noch Blockregeln, da hat er sich zwei ausgedacht.
Ich habe bestimmte Blöcke, zum Beispiel eine Tabelle oder einen Codeblock.
Und wenn ich die am Ende nicht schließe, dann fällt es unter Umständen nicht auf, wenn ich ein modulares Dokument habe, weil das Dokument einfach am Ende ist, wo der Codeblock zu Ende ist, wird alles automatisch geschlossen.
Wenn ich dieses Dokument aber in ein größeres Dokument inkludiere, dann kriege ich da Probleme, also das überprüft er auch.
Er überprüft Whitespaces in bestimmten Situationen.
Genau, da hat er Whitespace-Regeln.
Und noch Images, dass die bestimmte Attribute haben.
Das hat er jetzt nicht so ausgedacht, hat es implementiert.
Hat auch schon dazu geschrieben, wir haben hier noch ein paar Regeln in petto, die wir in Zukunft implementieren wollen, zum Beispiel Broken Links.
Und das hat das Modell jetzt erstmal so selbstständig gemacht.
Das heißt, es hat in unsere Arbeit als Architekt eingegriffen und hat diese Arbeit übernommen.
Wie ist denn das angekommen?
Hast du dir dasselbe mal angeschaut?
Haben irgendwelche Leute was dazu gesagt?
Wie ist sozusagen das Community- oder das Benutz-Fan-Feedback an der Stelle?
### Feedback der Community

Also bislang ist es noch nicht großartig veröffentlicht worden.
Das heißt, wir sprechen jetzt hier eigentlich das erste Mal in größerer Runde darüber.
## Ergebnisse des Experiments

Ich habe es mir angeguckt und ich muss sagen, das Ergebnis sieht eigentlich ziemlich gut aus.
Ich bin recht zufrieden damit.
Er hat in der Dokumentation Diagramme verwendet.
Und das ist zum Verständnis, trägt extrem dazu bei.
Die Diagramme sehen gut aus.
Da waren frühere Ergebnisse schlechter.
Manche Diagramme, da hat er es, finde ich, übertrieben.
Die sind überflüssig, die würde ich einfach auslöschen.
Aber er hat durch diesen Plat-UML-Ansatz eben tatsächlich die Chance, Diagramme zu erzeugen.
Und jetzt, wo ich über die Dokumentation drüber gucke, da ist noch ein zweiter Effekt dabei.
Denn in dem ASCII-Doc sind die Diagramme textuell beschrieben als Plant-UML.
Sie werden erst beim Rendering zu Diagrammen, die wir eben visuell erfassen können.
Meine Erfahrung mit den Modellen ist, dass sie weiterhin mit Diagrammen visuell nicht so gut umgehen können.
Aber wenn ich jetzt wieder auf diesem Projekt aufsetze und sich das Modell, die Dokumentation anguckt, wird es den Source-Code sehen, der Diagramm.
Und kann sie somit verstehen.
Wobei man dann ja, glaube ich, vor allem im anderen Punkt ist, nämlich wenn man das Ding sozusagen weiterentwickelt.
Kurz sozusagen, ich habe jetzt im Chat gesehen, also Teal George hatte geschrieben, die Spannung wird immer größer.
Okay, keine Ahnung.
Und Marco Wessemann hat geschrieben, ich bin sehr gespannt, vor allem auf die ASCII, die dabei herauskommt.
Ich weiß nicht genau, was eine ASCII ist.
Architecture Communication Canvas.
Achso, genau, der Architecture Communication Canvas.
Genau, den erwähntest du.
Ich gebe das jetzt mal hier in den Chat rein.
Ich habe selbst tatsächlich noch gar nicht großartig drüber geguckt.
Aber das Feedback, das interessiert mich natürlich auch.
Und deswegen gebe ich das jetzt mal hier rein.
Ich glaube, eine der Erinnerungen von dem, was wir ja vorher gemacht haben, mit dieser erste Kopie Advanced-Level-Beispiel-Aufgabe, und ich wollte da, also korrigiere mich, aber ich habe so eine Erinnerung, dass wir halt irgendwann festgestellt haben, dass eben tatsächlich die Aufgabe gar nicht mehr so in dem Fenster drin war, was das System noch angeguckt hat.
Trotzdem hat man das Gefühl, dass die Dokumentation ganz gut ist.
Also man muss da, glaube ich, vorsichtig sein, weil man, also wie soll ich sagen, GPT und diese ganzen AI-Lösungen sind nach meinem Empfinden darauf optimiert, den Eindruck zu erwecken, dass sie halt ganz was Tolles produzieren, indem sie halt so Fragen überbeantworten.
Also ich beantworte nicht eine Frage mit Ja, Nein, sondern ich sage, hier ist halt ganz viel Information.
Und man denkt so, wow, da ist halt ganz viel Information und das ist ja auf jeden Fall richtig.
Und ich glaube, da haben wir uns, also ich habe mich damals, glaube ich, ein bisschen davon einwickeln lassen.
Und da wäre jetzt, glaube ich, der Hinweis, oder so verstehe ich jedenfalls das, was du sagst, dass sozusagen die kritische Betrachtung noch nicht da ist.
Aber es gibt Funktionen, also das wäre jetzt die nächste Frage.
Woher weißt du, dass der Code jetzt tatsächlich so funktioniert, wie er funktionieren sollte, oder dass das System das tut, was es soll?
Einmal hat es ja, sage ich mal, Requirements erfunden.
Das heißt, also ein Problem könnte halt sein, dass Dinge, die halt so ein Linter eigentlich machen sollte, da gar nicht drin sind.
Wobei du sagst, naja, es gibt halt einen Markdown-Linter.
Markdown und LSDocs sind ja relativ ähnlich.
Das heißt, da ist sozusagen ein Vorbild, was man kopieren kann.
Woher weiß man, dass das jetzt sinnvoll ist, was der tut?
Im Sinne von, dann sind ja tatsächlich eigentlich Anforderungen erfunden worden, oder?
Ja, natürlich sind Anforderungen erfunden worden.
Ich hätte mehr Zeit investieren können und mit ihm in den Dialog gehen können.
Dass ich hätte sagen können, stelle mir Fragen bezüglich der Antworten.
Ich wollte aber, dass er loslegt.
Und ich habe gedacht, ein Linter ist jetzt nicht so ein schwieriges Problem.
Da findet man selbst die Anforderungen.
Das machen wir ja auch teilweise, dass wir eben bei so einem Projekt Vorschläge für Anforderungen machen.
Also, nur um es kurz zu ergänzen.
Also, wie soll ich sagen?
Ich finde es gar nicht so absurd, sich hier hinzustellen und zu sagen, okay, es gibt halt einen Linter für Markdown.
Ich brauche halt das LSDoc, was soll's?
Also, finde ich, das ist ein ganz normales manches Vorgehen.
Und von daher bin ich mir eben, also, ich meinte das gar nicht abqualifizierend, sondern ich habe eher das Gefühl oder ich hätte die Vermutung, dass halt dadurch es tatsächlich möglich ist, für so ein automatisiertes System halt irgendetwas zu bauen, was eben tatsächlich sinnvoll ist, weil es ist eben nur eine Kopie.
Das gehört eben zu der Frage, ob wir als Menschen nicht auch nur eine Kopie gebaut hätten.
Ja, definitiv.
### Vertrauen in AI-generierten Code

Also, ich habe hier auch keine Kreativität von ihm erwartet, aber ich fand es sehr spannend, dass er tatsächlich das mit dem Test getrieben gemacht hat, dass er ein Unit-Test-Framework genommen hat.
Und bis gerade eben hätte ich jetzt nicht gewusst, ob er dann vielleicht die Tests gelöst hat, indem er einfach sagt, es wird true.
Jetzt habe ich gerade einen Blick reingeworfen.
Nein, er macht da tatsächlich was.
Und ich habe auch gesehen, in seinem Dialog, wie die Tests immer wieder fehlgeschlagen sind, er sie korrigiert hat, er ein neues Feature implementiert hat, dabei ein alter Test fehlgeschlagen ist, und er dann den wieder verbessert hat.
Also, da scheint wirklich Logik dahinter zu sein.
Er hat auch an einem gewissen Punkt interessanterweise gesagt, ihm reichen jetzt die einfachen Tests nicht aus, er möchte auch Test-Coverage machen, hat eben entsprechend Test-Coverage aktiviert, hat gemerkt, ich glaube, wir sind bei 29 Prozent, und hat dann mal so zwischengefragt, soll ich das nächste Feature implementieren, oder erst mal den Test-Coverage erhöhen?
Ich fände das super spooky, was da abgeht.
Vielleicht in dem Kontext noch eine Frage.
Danke.
Also, wenn ich einen Unitest habe, der hat sagt, zwei und zwei ist fünf, und ich habe eine Implementierung, die hat sagt, zwei und zwei ist fünf, dann ist das in sich konsistent, aber objektiv falsch.
Woher weißt du, dass dieses System jetzt das tut, was es eigentlich tun sollte?
Also, im Sinne von, dass es etwas tut, was fachlich tatsächlich korrekt ist, nicht?
Also, zwei und zwei ist halt eben vier.
Wenn ich halt in dem System im Test und auch in der Implementierung sage, zwei und zwei ist fünf, dann habe ich halt eine hundertprozentige Testabdeckung, aber auch lauter grüne Tests, aber am Ende habe ich halt Quatsch.
Also, woher weiß ich, dass das nicht der Fall ist?
## Herausforderungen und Bedenken

Das ist tatsächlich eine für mich momentan schwierig zu beantwortende Frage.
Ich sehe das gerade so, dass, für mich ist gerade die Situation, als nie, wenn ich einem Kollegen gesagt hätte, du kannst du das mal implementieren, und er kommt zurück und sagt, guck mal, folgende Features sind implementiert, die Checks sind grün, und ich würde mich darauf verlassen.
Jetzt würde dann der nächste Schritt kommen, dass ich den fertigen Linter ausprobiere und dann merken würde, ob der Kollege geschummelt hat oder nicht.
Momentan sehe ich noch keine Anzeichen, dass das System geschummelt hat.
Ich sehe, dass der Linter in den Tests aufgerufen wird, dass eben überprüft wird, wie viele Findings er gefunden hat zu dieser Regel, und das scheint tatsächlich gut zu sein.
Ja, also der Grund, warum ich frage, ist einmal eben unsere gemeinsame Erfahrung, die wir ja gemacht haben, wo ich irgendwie das Gefühl hatte, dass uns letztendlich halt Chachipiti so ein bisschen durch hübschen Text beeindruckt hat.
Und ehrlich gesagt ist das so eine von den letzten Learned aus unserer damaligen gemeinsamen Episode, das für mich auch so bei Strukturdokumentation eine Rolle spielt, dass man halt vorsichtig sein muss, wie sehr man sich sozusagen einwickeln lässt.
Und das ist für mich auch etwas, ist auch so ein bisschen, wenn ich jetzt zynisch sein sollte, so eine Beraterskill.
Ich meine, man kann irgendwie etwas überzeugend darzustellen, was aber in sich eigentlich unsinnig ist.
Und deswegen frage ich halt, der andere Punkt, weswegen ich frage, also ich habe ja vor einiger Zeit diesen Blogpost geschrieben zum Thema, dass eben KI überbewertet ist.
Und da hatte ich halt diese wissenschaftliche Studie herausgesucht.
Die bin ich dann irgendwann gestoßen.
Ich habe das nicht exzessiv sozusagen nochmal nachgeschaut.
Und da ist es halt so, dass man gesagt hat, okay, wir nehmen halt zwei Gruppen.
Die eine Gruppe baut halt Code und baut den Code halt mit AI-Tool-Unterstützung.
Die andere Gruppe baut halt den Code und macht es halt irgendwie klassisch, was halt für uns bedeutet, typischerweise bedeutet Stack-Overflow.
Und das müssten solche Aufgaben gewesen sein, wie Verschluss meine Datei.
Und dann ist halt rausgekommen, dass die Gruppe, die als Stack-Overflow benutzt hat, die sichere Lösung gebaut hat und glaubte, die weniger sichere Lösung zu haben.
Das heißt also, die Gruppe, die AI-Tools benutzt hat, hatte ein hohes Vertrauen in ihren eigenen Code, der bedauerlicherweise aber falsch war.
Also im Sinne von, er war weniger sicher.
Und das sind halt offensichtliche Aufgaben gewesen.
Die Verschlüsseln der Datei, da ist halt Sicherheit das Feature.
Wenn ich es halt nicht richtig hinbekomme, ist es halt sinnlos, die Datei zu verschlüsseln.
Das ist also nichts, was man ignorieren kann.
Und das führt irgendwie genau zu der Frage, wenn ich jetzt also sage, okay, cool, dieses System hat mich jetzt irgendwie sozusagen, hat mir halt diesen Linter beschert.
Woher weiß ich, dass das, was da mir passiert, auch irgendwie sinnvoll ist und dass das eben tatsächlich funktioniert.
Und das ist etwas anderes als bei einem menschlichen Kollegen.
Also da würde ich halt erwarten, dass der eben ein besseres Verständnis, der wirklich im Weltrat und sich halt irgendwie bemüht hat.
Aber keine Ahnung.
Es gibt ganz viele, ach so, sorry.
Also kurzer Hinweis, es gibt ganz viele im Chat, aber sonst bring deinen Gedanken erst mal, glaube ich, zu Ende.
Das ist, glaube ich, wichtiger.
Wobei ich ihn gerade verloren habe.
Diese Sache mit dem, wir hatten diese Erfahrung gemacht, dass wir das Gefühl hatten, er erzählt viel, aber da ist wenig Inhalt dahinter.
Wenn wir rein von textuellen Aufgaben, sprachlichen Aufgaben reden, dann kann man uns recht gut blenden, sage ich mal.
Wir haben aber in der IT den Vorteil, dass, wenn es um Code geht, wir den Code verifizieren können.
Natürlich, wenn er selbst die Tests schreibt, dann kann er wieder mogeln.
Meine Erfahrung ist von kleinen Experimenten, dass er nicht mogelt.
Gut, kann trotzdem passieren.
Aber meine Experimente waren immer wieder, habe ich gesagt, schreibt mir mal ein Merge Sort, hier ist ein Test und führe den Test aus und überprüfe das.
Und die Tests habe ich etwas trickreich gemacht.
Ich habe z.B. ihm mehrere Obstsorten gegeben und die Sortierung in dem Test war nicht alphabetisch, sondern nach der Länge der Wörter.
Oder ich gebe ihm Zahlen und die Sortierung in meinem Test ist wieder nicht nach den Zahlen, sondern alphabetisch nach den Zahlwörtern.
Da experimentiert er rum.
Manchmal mogelt er, dass er sagt, es ist nur ein Test.
Das heißt, ich kann in meinem Merge Sort tatsächlich ein Ergebnis zurückgeben und das funktioniert.
### Fehler in den Tests

Da kann man dann sagen, ich habe hier noch mehr Tests.
Er versucht das auf jeden Fall erst mal mit Code.
Und einmal hatte ich sogar den Fall, dass ich einen Fehler hatte in dem Test.
Er rumprobiert hat und zum Schluss gesagt hat, du hast da einen Fehler in deinem Test, das kann ich gar nicht sortieren.
Ich habe auch das Gefühl, und da bin ich jetzt nicht Experte genug, vielleicht haben wir im Chat jemanden, wir sind mit dem Weltwissen noch auf einem relativ alten Stand vom letzten Jahr bei den meisten Modellen.
Da hat sich also wenig getan.
Aber ich habe das Gefühl, dass das Interface, also das, wie das System lernt, mit Frage-Antwort-Pan umzugehen, dass sich das über die Zeit verbessert hat.
Das sehen wir ja auch bei OpenAI mit dem Reasoning-Modell, was länger braucht, um zu antworten, aber eben tatsächlich diesen Chain of Sort durchführt und dass wir dadurch bessere Modelle bekommen haben, die eben diese Aufgaben besser lösen können.
Was ist ein Chain of Sort?
Meistens sagen wir dem Modell, mach mir dies und jenes.
Gib mir eine Detailgliederung für meinen Vortrag nächste Woche.
Und da ist das Modell dann schlecht.
Wenn ich ihm aber eine Gedankenkette vorgebe und vielleicht sogar iterativ erarbeite, dass ich ihm sage, mach mir erstmal eine Grobgliederung.
Wenn du die Grobgliederung hast, geh in die Detailgliederung.
Wenn du das hast, erarbeite mir Sprechtexte vielleicht.
Das ist diese Gedankenkette, mit der er besser umgehen kann.
Und so machen das die neuen Modelle auch intern schon selbst, dass sie sich erstmal überlegen, was muss ich machen, um diese Lösung zu erzeugen.
In dem Fall erstmal Tests schreiben oder erstmal sich Regeln überlegen, dann Tests dafür schreiben, dann implementieren.
Der Chat quillt rüber.
Ja, genau.
Lass uns da mal durchgehen.
Also die Tutor hat geschrieben, Ralf hat so viel erzählt, was am Ende die AI realisiert hat und ich bin sehr gespannt auf das Endergebnis.
Das ist noch nicht Release.
Ich habe den Link hier reingepastet, vorlesen.
Okay, gut.
Das heißt also, das ist sogar in diesem Internet jetzt schon verfügbar.
Ich finde es spannend, dass der AI sich selbst korrigiert bis zum komponierbaren Artefakt, weil ich halt hinzufügen muss, aus meiner Perspektive, also komponierbar ist das vergeblicherweise, was daraus fällt.
Du sagst schon, dass es die Tests nicht erfüllt hat.
Es ist teilweise auch so, es kommt auf die Sprache drauf an und auf die Aufgabe, wie gut er es kann.
Plat.uml findet er zum Beispiel sehr viele Beispiele im Netz, hat es also in seinen Trainingsdaten.
Trotzdem hat er manchmal einen Syntax Error, dass er nicht daran denkt, dass ein Name in Anführungszeichen gesetzt werden muss, wenn Space enthalten ist.
Da korrigiert er sich dann auch selbst.
Andere Sachen, nicht so bekannte Sprachen oder so, da hat er größere Probleme.
Dann hat Jörg Möller geschrieben zu der Frage, woher weiß ich, dass kein Quatsch entstanden ist, wie Ralf schon sagt, eventuell so vorgeben, wie wenn ein Mensch die Lösung geschrieben hätte, glaube ich, steht da.
Peer-Reviews, das Code geben halt sogar Peer-Review-Agenten über den generierten Code in der Verwendung von beschriftlichen Requirements.
Und das ist wiederum ein interessanter Punkt.
Du hast jetzt gesagt, es gab dieses Stack Overflow-Experiment mit der Security.
Wie sicher ist der Code?
Mein Frontend hat tatsächlich noch ein Tool, das heißt innerer Dialog.
Da kann es selbst eine LLM aufrufen.
Es muss einen System Prompt mitgeben und dann eine Aufgabe.
Und wenn man ihm sagt, es soll nochmal den Code aus der Perspektive eines Security-Experten und aus der Security der Wartbarkeit sich angucken, dann geht er tatsächlich in diesen inneren Dialog.
Und gerade bei der Wartbarkeit finde ich es faszinierend, da sagt er, oh mit den variablen Namen, da halten wir uns jetzt mal bitte an die Standards.
Hier bitte Kommentare noch in den Code reinsetzen.
Und übrigens, diese eine Methode, die sollte man modularisieren und aufsplitten in zwei.
Ja, also für mich scheint er jetzt gerade, ich weiß gar nicht, ob ich das, ich glaube, ich lese das aber eher in die Frage.
Nein, für mich scheint da eine Geschichte von, wie soll ich sagen, Aufgabe von Kontrollierbarkeit dahinter zu stecken.
Also entweder könnte ich jetzt tatsächlich den Code halt komplett reviewen, dann würde es halt bedeuten, dass ich mich auf diese Ebene runterbegebe.
Und das, was ich jetzt an deinem Beispiel so spannend fand und an dem, was du damit gemacht hast, ist ja, dass man im Prinzip sagt, naja, lösen, bau mal.
Und dann kommt halt irgendwas raus.
Und du hast, also tatsächlich ist es dann eben so, wie wenn ich mein Gefühl, wie wenn ich jetzt eben irgendeinem Team oder irgendeinem Menschen gesagt hätte, bau mal.
Und da will ich ja jetzt nicht auf der Ebene eigentlich das Zeug halt irgendwie reviewen.
Aber ja, also du kannst natürlich irgendwie nochmal jemanden drüber gucken lassen.
Das führt aber trotzdem nicht dazu, dass es meiner Ansicht nach beherrschbarer ist.
Das Ergebnis wird halt nur besser.
Also ich weiß immer noch nicht, was da drin passiert.
Genau, dann hat Crazy P hier geschrieben, Linter sind doch dafür gedacht, einen automatisierten Check durchzuführen.
Für den Check wäre doch der Linter verantwortlich.
Also wir sprechen über ein Linter für EskiDoc.
Das ist eine Dokumentationssprache und nicht über ein Linter für die primäre Sprache selber.
Das sind also zwei unterschiedliche Dinge.
Dann schrieb auf Twitch der Darth Kali, ich finde die Tests sollten schon immer von Menschen geschrieben werden, also vielleicht nicht im Code, aber der fachliche Inhalt.
Es kann ja sein, dass 2 plus 2 5 in einem gewissen fachlichen Kontext korrekt ist.
Haben wir glaube ich schon diskutiert.
Also da ist halt einmal diese Geschichte mit, dann würde man irgendwie runtergreifen auf diese Code-Ebene.
Und die andere Sache ist, ich muss gerade an die Episode denken, die wir ja gemacht hatten über Code-Retreats.
Du hast es ja selber auch gesagt, ich kann dafür sorgen, dass ein Test grün ist und ich kann exakt nur dieses Beispiel, was der Test abtestet, implementieren.
Also es gibt eine Übung in diesem Programming-Code-Review-Ding, dass man versucht möglichst böse zu sein.
Und wenn jemand von mir möchte, dass ich jetzt eine Addition implementiere und 2 plus 2 soll irgendwie 4 ergeben, dann sage ich, meine Addition gibt immer 4 zurück.
Und dann ist der Test grün und er macht keine Addition.
Dann kommt der nächste Fall und er sagt, 2 plus 3 ist aber 5.
Dann gucke ich mir den zweiten Additionsfaktor an.
Bei 2 sage ich, das Ergebnis ist 4.
Bei 3 sage ich, das Ergebnis ist 5.
Den ersten Faktor ignoriere ich.
Habe ich wieder zwei grünen Tests und so weiter.
Und das ist ein prinzipielles Problem von Tests, dass die Tests Beispiele geben.
Und der Sinn von dieser Übung hört sich ein bisschen bizarr an, aber der Sinn von dieser Übung ist, glaube ich, auch darauf hinzuweisen, dass man, wenn man gute Tests schreiben will, sehr viel machen muss.
Weil man muss dann eben tatsächlich so viel machen, dass die andere Person dazu gezwungen ist, sinnvollen Code zu implementieren.
Und das kann ganz schön aufwendig werden, das zu tun.
Und das will ich ja eigentlich nicht.
Ja, du sprichst da ein Thema an, das gilt nicht nur für die Tests, sondern auch für Dokumentation.
Ich war immer skeptisch gegenüber automatisch generierten Tests, weil ich gebe der Maschine eine Funktion, schreibe mir Tests dafür und sie weiß nicht, was eigentlich dahinter steckt, was diese Funktion machen soll.
Sie sieht nur, was sie macht.
Das heißt, wenn die Maschine exakt testet, dann testet sie auch die Bugs mit. Ähnlich ist es bei der Dokumentation.
Ich habe immer gesagt, automatisch generierte Dokumentation macht wenig Sinn, weil wenn die Maschine den Code sieht, kann sie erklären, was der Code macht.
Sie kann nicht erklären, warum dieser Code so aufgesetzt worden ist, warum ich einen Merge Sort und keinen Quick Sort genommen habe, zum Beispiel.
Diese Information ist verloren zu dem Zeitpunkt, wo ich einfach nur den Test oder den Code für die Dokumentation der Maschine gebe.
Hier haben wir jetzt den interessanten Punkt, dass die Maschine selbst Entscheidungen getroffen hat, die sie dokumentieren kann.
Die Maschine hat selbst beschlossen, was dieser Code, wie er sich verhalten soll und konnte dadurch hoffentlich verhaltensbasierte Tests schreiben.
Und das ist jetzt eine Annahme von mir, die jetzt erst noch mehr verifiziert werden muss.
Aber das macht halt dieses Experiment so interessant, dass es eben der komplette Block an die Maschine gegeben worden ist.
Ja, und ich glaube, ich sage da nochmal dasselbe.
Ich wäre immer vorsichtig, weil das eben darauf hinauslaufen kann, dass man möglicherweise so einer Illusion hinterherläuft.
Also sprich, das wirkt so, als wäre es eben sinnvoll, aber in Wirklichkeit ist es das eben nicht.
Also man hat das Gefühl, dass die Maschine etwas tut, weil der Verdacht nahelegt, dass da sozusagen Reasoning hinter steckt.
Du hattest mir netterweise vorhin die Architekturdokumentation gegeben und in der Architekturdokumentation, also nur mal random irgendwas rauszugreifen, sind halt Quality Requirements und da steht halt irgendwie als erstes Performance-Szenarios und das steht als erstes, das Prozessieren eines 1000-Zeilen-Dokuments soll weniger als eine Sekunde dauern.
Das ist hohe Priorität.
Dann steht als nächstes, viele Dateien bearbeiten, also wenn es 100 Dokumente sein sollte, sollen weniger als 10 Sekunden sein.
Das ist Medium.
Dann steht Speicherbedarf, wenn ich ein großes Dokument, zum Beispiel 10 Megabyte, bearbeite, dann sollte ich weniger als 100 Megabyte Rahmen benutzen.
Ist das Ding in Java?
Nein, das ist in Python.
Das ist eben auch high.
Dann steht halt die Startup-Time von dem Linter ist weniger als 0,5 Sekunden und das ist Medium.
Ich weiß nicht, wie du es siehst, aber das hört sich für mich, also die eine Frage wäre halt, woher zum Teufel kommt das?
Und die andere Frage ist halt, hält die Software diese Bedingungen irgendwie ein?
Und ich wäre bei beiden überrascht, wenn es dafür sozusagen eine vernünftige Antwort gebe.
Denn ich halte es für, das Prozessieren eines 1000-Zeilen-Dokuments jetzt eine Sekunde oder zwei Sekunden dauert, das glaube ich irgendwie egal.
Warum das High-Priority ist, ist mir irgendwie nicht klar.
Und 100 Dokumente in weniger als 10 Sekunden, also ich benutze SGDoc.
Ich weiß nicht, hast du ein Projekt gesehen, wo es 100 SGDoc-Dokumente gibt?
Es kann sich leicht was ansammeln.
Vor allem, wenn man mehrere Module hat, die man jeweils mit A42 dokumentiert zu einem großen Projekt zusammenfügt, dann kann das schon mal passieren.
Aber ich glaube, wichtig ist hier, dass die Maschine, vielleicht interpretiere ich auch zu viel rein, aber so ein Linter soll schnell laufen.
Er soll den Bildprozess nicht aufhalten.
Vielleicht interpretiere ich zu viel rein.
Ja, also es ist nur random.
Ehrlich gesagt, bin ich da nochmal durchgescrollt und da hat irgendwie sozusagen rübergestolpert.
Und ich bin so ein bisschen, ich finde das bei den Qualitätsszenarien immer schwierig und insbesondere bei den Qualitätsszenarien finde ich es wichtig, die Dinge herauszusuchen, die tatsächlich wirklich wirklich relevant sind und nicht irgendwie random irgendwelche Dinge.
Und das hier ist für mich ein Beispiel von, ich kann mir vorstellen, dass das Mensch genauso schreiben würde, aber den Menschen würde ich jetzt irgendwie fragen, okay, woher kommt das?
Warum ist das so?
Und irgendwie versuchen herauszufinden, was das sozusagen soll.
Weil wenn ich so ein Ding aufschreibe, sage ich damit, das ist wichtig.
Performance von dem Ding ist wichtig und insbesondere da steht ja hohe Priorität.
Und ich finde das nicht nachvollziehbar.
Also nicht genau diese Frage mit der einen Sekunde wäre jetzt die Frage.
Und die nächste Frage, die sich ja anschließt, ist, okay, woher weißt du, dass das Ding eine Sekunde braucht?
Hast du einen Test?
Zeig mal.
Und es steht ja auch, dass das Ding innerhalb von weniger als 0,5 Sekunden starten soll.
Gut ist das?
Weiß ich nicht, wie preist denn wahrscheinlich?
Und das ist halt etwas, was ich meine.
Also ich glaube, man muss halt immer kritisch bleiben.
Die Requirements kann ich sozusagen auch kurz mal aufschreiben und mir ausdenken.
Und dann sieht man halt, wow, krass, Qualitätsszenarien, sehr, sehr schön.
Und dann ist aber irgendwie genau die Gefahr, dass man, wenn man sozusagen Worte herausfindet, die haben halt keinen Inhalt.
Und das ist, glaube ich, hier etwas, vor dem ich halt sozusagen warnen möchte.
Absolut.
Ich muss aber auch sagen, ich bin schon mal erst mal erstaunt, dass er eben die Qualitätsszenarien tatsächlich auch nochmal aufgegliedert hat in Performance, Reliability, Usability und dann auch ein Quality Tree gebaut hat.
Aber dein Feedback jetzt, das finde ich total klasse, weil das würde ich jetzt in den System mit aufnehmen, dass ich ihm sage, immer wenn er Qualitätsszenarien erstellt, er bitte auch begründen soll, warum das eben wichtig oder weniger wichtig ist.
Und dann liefert er eine Scheinbegründung.
Ja, tatsächlich.
Aber dann werde ich es besser überprüfen können und werde nachfragen können.
Wenn ich mir mehr Zeit nehme, dann könnte ich auch viel interaktiver mit ihm arbeiten und ihn auch in die richtige Richtung bewegen.
Ob das jetzt wirklich so ist, dass das so schnell läuft, ich könnte ihm als nächstes die Aufgabe geben, zu versuchen, Tests für die Qualitätsszenarien zu schreiben.
Genau, was dann aber bedeutet, dass du tatsächlich sozusagen einen Architekturberater brauchst.
Zwar niemanden, der es jetzt selber macht, aber du brauchst einen Architekturberater.
Ich glaube, das ist noch ein anderer Punkt.
Wenn man das jetzt jemandem vorlegen würde und sagen würde, okay, fällt dir irgendwas auf?
Also so eine Art Turing-Test.
Kann man etwas unterscheiden, was ein Mensch gebaut hat?
Also Turing-Test ist ja dieser Test, wo man sagt, ich habe es vergessen, wie es ganz exakt läuft.
Man hat ein vordefiniertes Gespräch mit einem Gegenüber über ein bestimmtes Thema oder man kann es auch frei wählen.
Man muss am Ende entscheiden, ob es eine Maschine ist oder eben ein Mensch, mit dem man da spricht.
Und sowas Ähnliches könnte man hier jetzt auch machen.
Man könnte also sagen, okay, cool, diese Architekturdokumentation, kommt die von einem Menschen oder kommt die von einer Maschine?
Das ist eine andere Frage, als ist die gut oder schlecht.
Ich bin mir nicht sicher, was das Ergebnis ist.
Denn wenn ich mir das jetzt irgendwie rausziehe, das kann auch ohne Weiteres ein Mensch geschrieben haben.
Also das ist, glaube ich, unser allertäglich Brot, dass man sagt, okay, das ist ein Qualitätsszenario.
Erklär mir mal, warum zum Teufel gibt es dieses Qualitätsszenario?
Warum ist das wichtig?
Und dann stimmt man halt irgendwie gemeinsam fest, so wichtig ist das vielleicht gar nicht.
Gerade bei Performance sind solche vom Himmel gefallenen Anforderungen, glaube ich, gar nicht ungewöhnlich.
Das ist auch etwas, was ich aus unseren letzten Episoden mitgenommen habe.
Wir können durchaus als Menschen auch noch da besser werden in diesem ganzen Bereich.
Das ist auch klar.
Du sprichst hier ein Thema an, ich merke das auch immer wieder, wenn man das A42 tatsächlich als Formular benutzt.
Und dann ist da ein Feld, fünf Qualitätskriterien.
Ich habe gerade überhaupt keins.
Ich saug mir was aus den Fingern.
Dann würde man sich tatsächlich teilweise auch so verhalten.
Und weil du den Turing-Test ansprichst, das ist faszinierend.
Also ich würde jetzt zum Beispiel aufgrund der Grafiken, die erzeugt worden sind, der Diagramme sagen, okay, bei manchen Diagrammen, bei der Risikomatrix, unter Technical Risks und Technical Debt, die ist, da merkt man, da hat keiner visuell drüber geguckt und die macht überhaupt keinen Sinn.
Das ist sicher die Maschine gewesen.
Bei anderen Sachen muss ich sagen, der Turing-Test, ich habe irgendwann mal angefangen zu sagen, die Maschine besteht den Turing-Test nicht mehr, weil sie zu perfekt ist.
Soweit ich weiß, ist das Setting so, man hat zwei Chats und man muss sagen, welcher der Chat-Partner Maschine ist und welcher Mensch.
Und man merkt halt schnell, dass das Wissen sehr breit ist, sehr detailliert und solche Geschichten.
Und die Maschine hat trotzdem den Turing-Test mal bestanden in einem Experiment.
Und der System-Prompt war so nach dem Motto, naja, antworte wie ein 15-jähriger Teenager und baue auch Rechtschreibfehler ein und solche Geschichten, um diesen Perfektionismus rauszunehmen.
Und dadurch hat die Maschine, glaube ich, in 51 Prozent oder so der Fälle tatsächlich den Status Mensch bekommen.
Was aber wiederum bedeutet, dass es um Scheinelemente geht nicht, also wie zum Beispiel um korrekte Rechtschreibung oder sowas und weniger um Inhalte möglicherweise.
Genau, der Marco Wesselmann hat noch geschrieben, das Outcome sollte in jedem Fall natürlich am Review-Prozess unterlaufen, wie der jeweils gestaltet ist.
Es ist sicherlich unternehmensabhängig, Abnahme gegen Qualitäten und so weiter, war, glaube ich, diskutiert. Ähnliche Ansätze gibt es auch bei anderen Text-Artifakten, die über LLMS entstehen, also nicht Code.
Und der Jörg, glaube, das geht halt auch um dieses Review-Thema.
Und der Jörg hat noch weiter geschrieben, für diese Sache, dass das halt gereviewt werden.
Aber dabei kann man sich eben auch unterstützen lassen, wenn man das will, indem die Agentenrolle Review einbaut.
Führt aber, glaube ich, nicht darauf.
Also dann hat man ein System, was halt in sich aber irgendwie Unsinn produzieren kann.
Keine Ahnung.
Führt man ein paar Reviews anders durch, wenn man weiß, es wurde durch eine LLMS entsteht, wurde gerade besprochen.
Okay.
Wo wurde der Link gepostet?
Der Link ist nicht in diesem Chat.
Ich habe ihn dann nochmal gepostet.
Okay, alles klar.
Das größte Problem ist, dass AI-Code nicht in größerem Kontext einordnen kann.
Insbesondere indirekte Abhängigkeiten werden in der Regel nicht erkannt, auch semantisch oft problematisch, schreibt Malitius von YouTube.
Genau, das ist tatsächlich ein interessantes Problem, wo ich mir teilweise überlegt habe, wir schreiben Code für den Menschen.
Die Maschine braucht vielleicht anderen Code.
Gerade in Java, wenn wir eine Interface-Definition haben, eine Implementierung, dann die Usage und die Dokumentation, dann haben wir vier Dokumente, unter Umständen viel mehr, in denen eigentlich das Modell nachgucken muss.
So ein Copilot, GitHub Copilot, da hatte ich bislang immer Probleme, dass er, ja, er hat immer nur drei Dokumente maximal genommen.
Und dann reicht der Kontext nicht aus.
In eigenen Experimenten kann ich den vollen Kontext nutzen, 128.000 Token, das ist schon ein Büchlein, was ich nutzen kann.
Und auch der Copilot und andere Systeme gehen dazu über, dass sie jetzt das komplette Repository in einer Vektordatenbank indizieren.
Das heißt, ich glaube, dieses Problem haben wir ganz gut gelöst.
Ja, und das führt, glaube ich, zu so einer interessanten Geschichte.
Das war nämlich auch das, was ich dachte, als du mir gesagt hast, hier ist die Architektur-Dokumentation, da haben wir nur so einen Gedankenblitz.
Was soll das eigentlich, weil das ist ja etwas von menschlicher Kommunikation und ich bin nicht sicher, ob das eigentlich das ist, was man will.
Also eigentlich dreht sich jetzt die Diskussion, die wir zumindest irgendwie führen, eher um so eine Verifikation.
Klassisches Architektur-Documentation, meiner Ansicht nach so, aber du bist ja eher der größere Experte.
Das ist der Mechanismus, mit dem ich jetzt sage, ich habe mir übrigens Folgendes dabei gedacht.
Das sind so die wesentlichen Eigenschaften der Software und das will ich halt jemandem anders erklären.
Und das ist also eigentlich so zwischenmenschliche Kommunikation.
Das, was wir jetzt hier gerade diskutieren, ist glaube ich was anderes.
Das ist irgendwie sowas wie, kannst du mir sagen, welche Eigenschaften diese Software tatsächlich hat und kann ich irgendwie das Ergebnis verifizieren und ist es für mich nachvollziehbar, was da passiert ist.
Vielleicht brauche ich dafür halt auch eine andere Art von Dokumentation und eine andere Art von Darstellung.
Ich fand es halt irgendwie, das war glaube ich der Gedankenblitz, ich fand es halt irgendwie absurd, dass halt eine Maschine ein Dokument erstellt, was eigentlich für menschliche Kommunikation gedacht ist.
Wenn ich eine Architektur-Dokumentation schreibe, damit du dann später irgendwie das System übernehmen kannst und dann bist du verstanden, was ich mir dabei überlegt habe.
Aber ist das etwas, was jetzt bei Menschen eine Rolle spielt?
Wahrscheinlich wird dieser Linter, wie du es auch gerade gesagt hast, jetzt irgendwie weiterhin von irgendeinem AI-System weiterentwickelt, oder?
Würde ich jetzt mal annehmen.
Das wäre mein Ziel, dass ich das AI-System bitte, das weiterzuentwickeln, ja.
Aber du sprichst einen interessanten Punkt an.
Es gibt so verschiedene Faktoren, wo wir uns überlegen müssen, wie es weitergeht mit der KI, die wir nicht mehr einfangen können, wie sie unsere Arbeit beeinflusst.
Du sagst jetzt, die Architektur-Dokumentation ist für uns Menschen geschaffen.
Ja, wir haben sie für uns Menschen geschaffen, weil wir als Menschen die Architektur erstellt haben.
Wichtig ist aber, dass in dieser Architektur-Dokumentation Informationen drin sind, die auch die Maschine braucht, aus meiner Sicht.
Wenn wir qualitätsgetriebene Architektur machen, dann basieren die Entscheidungen, die wir für die Software treffen, auf den Qualitätskriterien.
Und die Maschine kann die Entscheidung nur treffen, wenn sie die Qualitätskriterien kennt.
Gerade wenn ich jetzt in etwas Spezielles reingehe, wenn ich sage, das ist ein Linter und du weißt schon, wie ein Linter funktioniert.
Okay, aber wenn ich jetzt den Linter für ganz riesige Projekte habe, dann habe ich ein anderes Qualitätskriterium, was die Maschine kennen muss, behaupte ich.
Ja, was ich mir jetzt eigentlich wünschen würde, wäre, dass mir das System sagt, okay, hör mal zu, Performance, keine Ahnung, habe ich mir nicht angeguckt, ist auch nicht getestet, ist halt so, ist halt so, wie es ist.
Und ich meine, probiere es halt aus, ob es schnell genug ist oder nicht.
Und das wäre eigentlich die Information, die ich brauche.
Weil ich dann wüsste, das ist sozusagen ein Blindspot und das hat keine zugesicherte Sache.
Das, was ich bekomme, ist Illusion.
Also ist eben das, was ich auch sonst bei Architekturdokumentationen häufig bekomme.
Irgendwelche random Aussagen, die mit der Realität nichts zu tun haben.
Also das System sagt im Prinzip, so ein Linter könnte halt vielleicht schnell sein müssen.
Deswegen habe ich mal aufgeschrieben, wie schnell das ungefähr sein könnte.
Mit der jetzigen Implementierung hat das eigentlich nichts zu tun.
Aber das sieht ja aus wie Qualitätsszenarien.
Also ich übertreibe jetzt und kann nur nochmal hinzufügen, das wäre jetzt auch etwas, was durchaus ein menschlicher Architekt möglicherweise geliefert hätte.
Und das ist aber eigentlich nicht das, was sie mir, für mich wäre es hilfreicher.
Ich weiß nicht, wie es bei dir aussieht.
Wenn das System jetzt sagen würde, ich habe mir das nicht angeguckt.
Punkt.
Diese Lösung ist eben dort.
Das ist halt ein offenes Thema.
Und genau das kriege ich möglicherweise nicht raus.
Das wäre aber hilfreich für die, oder irgendwie sowas wie, meine Entscheidungen zugunsten von irgendwas basieren hier drauf.
Also nicht, dass ich Vertrauen bekomme, dass es stärker nachvollziehbar ist, was das System überhaupt tut und so weiter.
Und stattdessen kriege ich jetzt eigentlich ein Dokument voller Nebelkerzen.
Ja, aber genau diese Überlegungen, die du jetzt anstellst, ich würde dir als nächstes in den Sitzungspunkt reinnehmen.
Wir hatten ja schon, dass er begründen soll, warum er dieses Qualitätskriterium gewählt hat.
Ja, das wird eine Scheinbegründung erstmal sein.
Aber jetzt sagst du, du willst da wissen, ob das wirklich verifiziert ist oder nicht.
Das heißt, er könnte reinschreiben, ob es ja durch den Test verifiziert worden ist.
Am besten noch, ob der Test grün oder rot ist.
Oder was hat die Herausforderung des Systems denn nicht?
Also im Moment oder auf einem Punkt oder irgendwie sowas.
Vielleicht, weiß ich nicht.
Also das wäre eigentlich die nächste Frage, womit wir jetzt implizieren, dass das System dazu in der Lage ist, logische Schlüsse zu ziehen.
Das kann das doch gar nicht, oder?
Ich weiß es nicht.
Ich weiß es nicht.
Also es macht den Eindruck, als könne es logische Schlüsse ziehen.
Es überrascht mich immer wieder.
Ich habe es mal gefragt, wie ich erkennen kann, ob es ein LLM ist oder ein Mensch.
Ich habe gesagt, naja, ein LLM hat kein Weltbild.
Es weiß nicht, wie die Welt aussieht.
Das heißt, es kann dieses Wissen nicht einsetzen.
Ich habe es dann gefragt, wenn ich einen Elefanten und ein Eichhörnchen in der Streichholzschachtel sperre, wie schwer ist die Streichholzschachtel?
Ich habe erwartet, da kommen zwei Tonnen Neue so raus.
Er hat gesagt, also Elefant passt nicht rein, Eichhörnchen wirst du nicht einfangen können.
Das ist eine Scherzfrage, oder?
Auch wenn es nur vorgespielt ist.
Dieses Verhalten ist der Hammer.
Aber das ist so ein bisschen das Problem dabei, nicht?
Also genau diese Geschichte, dass es eben sehr gut Nebelkerzen zünden kann und halt sagen kann, es wirkt so, aber in Wirklichkeit ist es halt eben nicht so.
Lass uns kurz irgendwie, genau, das ist eine sehr interessante Diskussion.
Wir kommen ein bisschen weg von den Sachen, die wir im Chat hatten.
Marco Wessemann hat geschrieben, die Interpretation welcher Tests in welcher Form nötig ist, ist meiner Meinung nach etwas, was aktuell durch KI nur schwer abbildbar ist.
Durch viel Code wird man schnell abgelegt, ich nehme an, abgehängt und geblendet.
Das ist genau der Punkt.
Da fängt es wieder an mit Beherrschbarkeit.
Und der Martin Axiomeyer hat geschrieben, schreibt man Architekturdokumentationen in der Idee, macht zum Beispiel GitHub Copilot Vorschläge zur Vervollständigung der Zeile nicht immer korrekt und das, was man möchte, aber manchmal mit tiefreichenden Hinweisen.
Ich weiß nicht, wie deine Einstellung ist.
Ich würde unterstellen, dass das Thema GitHub Copilot, ja, weiß ich eigentlich gar nicht genau.
Das wäre noch die Frage, ob das eben eines von diesen AI-Werkzeugen ist, was in dieser zitierten Studie untersucht worden ist.
Aber eigentlich ist die Idee Code Completion und da hat irgendwie sozusagen schlau sein in Bezug auf das, was bereits genutzt worden ist draußen im Internet.
Das finde ich jetzt nicht verwerflich.
Wir reden hier über etwas anderes.
Im Prinzip reden wir hier darüber, dass eigentlich ein Entwickler in einem Team so emuliert wird.
Das ist ja eigentlich das, was da passiert.
Also vielleicht nicht ein Team, aber jemand, der jetzt sagt, ich brauche mal den Code und ich mache halt irgendwie alles.
Also die Dokumentation, dieses ganze Graffel.
Also eben das, was so ein cross-funktionaler Techniker letztendlich ist da ausgekommen.
Wobei diese Referenz auf den GitHub Copilot, da kommt auch noch etwas anderes durch.
### Veränderung der Entwicklungsmethoden

Ich glaube, wir werden unsere Art, wie wir entwickeln, verändern.
Wer schon den Source Code von meinem Projekt gefunden hat, der wird ganz viele Meta-Files finden.
Und da habe ich das Modell gebeten, immer wenn eine Datei angelegt wird, reinzuschreiben, was diese Datei macht.
Weil dadurch kann sie schnell einen Überblick bekommen.
Sie hat ein List-Files-Befehl.
Der gibt den kompletten Baum aus mit der Beschreibung des Files, sodass der Kontext nicht großartig gefüllt wird.
Ansonsten, wenn der Kontext fehlt, dann muss das LLM aufgrund des Dateinamens raten.
Wir wissen, in der und der Datei war das und das.
In dem Folder liegt dies und jenes.
Das hilft.
Auch beim GitHub Copilot.
Wenn ich erst einen Kommentar schreibe, was die Funktion machen soll, dann ist die Auto-Vervollständigung viel besser.
Ich habe es von manchen Entwicklern schon mitbekommen, dass sie anfangen, einen Header in jedes File für die KI zu setzen.
In dem drin steht quasi nochmal so ein System-Prompt.
Was soll in dieser Datei drin sein, was nicht?
Wie soll es dort drinnen stehen?
So werden wir die Art und Weise, wie wir programmieren, der KI anpassen.
Während die Hersteller versuchen, die KI unserer Programmierweise anzupassen.
Wobei ich jetzt sagen würde, dass man sagt, ich habe da so ein komisches Ding.
Ich weiß nicht genau, was da drin vorgeht.
Aber ich beschreibe es mal abstrakt.
Das ist Modularisierung.
Wenn wir mithilfe von AI-Technikern dazu bekommen, Sachen zu modularisieren, indem sie hinschreiben, was das Ding tun soll, und dass es von draußen erkennbar ist und nicht in den Tiefen des Codes implizit klar wird, finde ich das nicht ablehnenswert.
Das war freundlich zu sagen.
Absolut.
Interessant ist aber jetzt der Aufwand-Nutzen.
Wir haben hier von dem Entwerfen des Codes und dem Review gesprochen.
Jetzt überlegt ihr mal, wenn die Maschine, sie wird immer schneller, wenn sie den Code, den Stand, den wir jetzt gerade haben, mit was sind das, acht Regeln oder so, in einer Stunde implementiert.
Dann will ich ein Review haben.
Und wie lange braucht der Mensch, um diesen Code zu reviewen?
Die Maschine kann ich gleich wieder darauf ansetzen und sagen, mach du mal ein Review.
Und dann baue ich irgendwo Vertrauen auf.
Genauso wie wenn ich ein Entwicklungsteam habe und ich weiß am Anfang gar nicht, wie gut sind die, was können die.
Und durch die ersten Ergebnisse baue ich Vertrauen auf.
Da bin ich jetzt gespannt, welches Vertrauen ich in die Maschine aufbauen kann.
Und wenn ich über das automatisierte Review ein Vertrauen aufbaue, dass ich sage, eigentlich ist das okay, dann laufe ich Gefahr, dass ich das menschliche Review ausfallen lasse.
Du hattest das selber mal gesagt, wir sind in der besonderen Rolle, dass wir Software entwickeln und Software läuft auf im Wesentlichen deterministischen Maschinen, auch wenn es manchmal nicht so aussieht.
Das bedeutet, wir können sagen, dieses Stück Software tut das und das ist objektiv in einer automatisierten, von einer AI zugreifbaren Umgebung verifizierbar.
Was was anderes ist, als wenn wir sagen würden, baue mal ein Fahrrad.
Ein Fahrrad ist etwas, wo ich diese Zyklen nicht machen kann.
Ich kriege kein Feedback.
Da kann theoretisch etwas Komisches herauskommen.
Ich könnte das noch simulieren, aber wir sind da deutlich näher dran.
Ich bin mir nicht sicher, das ist ein Gedanke, der in meinem Hinterkopf die ganze Zeit existiert.
Wir haben diesen Schritt damals gehabt, von Assembler- und Maschinensprachen zu Gruppensprachen, wo diese Geschichte passiert ist.
Ganz früher war es tatsächlich so, dass man einzelne Nullen und eins in den Speicher geschrieben hat, also 40er oder 50er.
Man musste die Befehle per Hand tatsächlich überlegen, welche Nullen und Eins das sind.
Dann hat man diese Assembler-Mnemonics gehabt, um zu sagen, diese Maschinenbefehle, da habe ich etwas, was menschenähnlicher ist.
Dann konnte man diese Assembler-Mnemonics automatisch in einen Binärcode umschreiben.
Dann haben wir angefangen, Hochsprachen zu bauen.
Die sind auf einer höheren Abstraktionsebene.
Im Extremfall mache ich diese Dinge und dann läuft es parallel oder sequenziell oder was auch immer.
Es gibt auch unterschiedliche Ausführungsmöglichkeiten, gerade bei funktionalen Programmiersprachen.
Aber auch sonst ist es so, dass wir komplexere Konstrukte haben, die vielen Maschinensprachbefehlen entsprechen.
Wir sind hier vielleicht an einer ähnlichen Stelle.
Man sagt, ich beschreibe, was ich haben will.
Dann kommt das Ding in der nächsten niedrigeren Sprache raus.
So wie ein Compiler Assembler macht.
Wenn du sagst, wir bauen einen Linter, dann kommt ein Linter raus.
Du musst noch spezifizieren, was das tut.
Das ist eine höhere Abstraktionsebene analog zu diesen höheren Programmiersprachen.
Ich bin mir nicht sicher, ob die Analogie stimmt.
Aber wenn sie stimmen sollte, würde das in letzter Konsequenz bedeuten, dass dieser Kontrollverlust bis zu einem gewissen Maße fein ist.
Ich gucke mir nicht den Bytecode von einem Java-Compiler an.
Man guckt sich auch nicht den Assembler-Code von einem C-Compiler an.
Auf diesen Ebenen arbeitet man typischerweise nicht mehr.
Vielleicht wäre das etwas, wo wir hinkommen.
Wobei hier das Problem ist, dass diese Sachen nicht offensichtlich deterministisch sind.
Die sind deterministisch, weil sie auf Software und Computer laufen.
Aber es ist etwas anderes, einen Compiler zu haben, der so richtig deterministisch ist und trivial deterministisch.
Hier reden wir schon über Dinge, die ein bisschen komplizierter und anders sind.
Es spricht an mir die Frage, will ich überhaupt noch diese Tests verstehen?
Will ich das überhaupt tun?
Eigentlich will ich dahin kommen, dass ich das nicht mehr will.
Dieses Misstrauen will ich eliminieren.
Aber das ist eine visionäre Geschichte.
Wir sind am Ende der Zeit.
Will ich die Tests noch verstehen?
Will ich den Code noch verstehen?
Reicht mir das Ergebnis?
Ich sage, wir haben auch so ein Problem, wenn die kognitive Leistung der Maschinen besser wird als unsere menschliche kognitive Leistung.
Wenn die Maschine Code erzeugt, der zwar funktioniert, aber so komplex ist, dass wir nicht mehr drüber gucken können, wird es auch sehr spannend.
Auch das ist etwas, wo wir Lösungen brauchen werden in Zukunft.
Das ist aber krasse Zukunftsmusik.
Da möchte ich noch mal erinnern, die Geschichte, die man durch dieses Paper angucken kann, ist, dass, blöd gesagt, es bedeutet, wenn ich einer Entwicklerin eine AI-Unterstützung gebe, wird es schlimmer mit ihr.
Ich habe mir heute Vormittag noch ein Prüfsthing gelesen, auf Mastodon, wo eine Person, die offensichtlich an der Universität arbeitete, genau diese Sachen hat mit, okay, erklär mir mal, wie du diese Aufgabe gelöst hast.
Da kommt dann zurück, keine Ahnung, musst du Chez Cheepity fragen.
Das ist halt trivialerweise im hohen Maße schwierig.
Das bedeutet, dass ich dem Ding ausgeliefert bin.
Sie hatte zumindest ein Beispiel, auch wenn man das gepostet hat, wo, so sagte sie, ein im hohen Maße falscher Aussage kam.
Sie hat gesagt, okay, das kann so nicht sein.
Dann haben wir zurückgekommen, doch, hier, guck mal, da ist der Screenshot.
Was mich dabei beeindruckt, ist, es gibt dieses Buch, die Macht der Computer und die Ohnmacht der Vernunft von dem Weizenbaum, das ist aus den 70ern.
Da beschreibt er diese Geschichte von Elisa.
Da hat Elisa gebaut, diese neue Technologie, und dann hat Elisa gesagt, diese Psychiater-Emulation, wie auch immer man es nennen will, eigentlich ist das etwas, was relativ trivial, die Fragen wieder zurückwirft.
Du sagst, du hast Probleme mit deiner Familie, und dann kommt da zurück, erzähl mir mehr über deine Familie oder über deine Mutter.
Das ist ein relativ einfacher Algorithmus.
Ich habe in den 80ern mal 100-Zeilen-Basic-Ding abgetippt, was das tut.
Was er beobachtet hat, war, dass seine Sekretärin angefangen hat, mit diesem Ding zu reden, und gesagt hat, guck dir bitte nicht an, was ich mit dem Ding berede.
Das bedeutet, dass diese Sekretärin damals offensichtlich dieses System für voll genommen hat, und dem Dinge anvertraut hat, die eben privat sind.
Das ist genau das Problem.
Was mich dabei fasziniert ist, das ist 50 Jahre her, das ist genau das Problem, was wir jetzt auch haben.
Du fängst an und sagst, ich mache irgendetwas mit so einem AI-System, es kommt etwas zurück, und man nimmt das für voll.
Dabei ist sehr fraglich, ob es an allen Stellen vernünftige Lösungen baut.
Ich will trotzdem noch eine Abschlussfrage stellen.
Was ist denn dein Tipp?
Was man heute jetzt anders machen könnte, oder wo du sehen würdest, wo du diese Sachen jetzt produktiv einsetzen kannst?
Würdest du empfehlen, anderen Leuten ein Linter jetzt auch mit Chats GPT oder einem AI-System zu bauen?
Nein.
## Fazit und Empfehlungen

Wir haben die Systeme, wie GitHub Copilot, die unsere Fähigkeiten unterstützen, verstärken.
Das funktioniert ganz gut.
Das, was ich jetzt gemacht habe, ist ein Experiment, was aufzeigt, was in Zukunft sein könnte.
Ich finde es sehr wichtig, dass wir uns damit beschäftigen, um uns Gedanken zu machen.
Wie werden in Zukunft Reviews laufen?
Wie werden wir in Zukunft entwickeln?
Was von der Dokumentation ist in Zukunft wichtig?
Was ist weniger wichtig, weil die Maschine aus dem Code erklären kann?
Ich glaube, das war es noch.
Martin Axelmeier hat noch geschrieben, ein LLM muss nicht 100% fehlerfrei sein, um hilfreich zu sein.
Zum Beispiel zur Selbstreflektion.
Vielleicht kann man auch sagen, man muss damit leben können, dass das so ist.
Das ist vielleicht auch das, was sich durch die Stunden durchgezogen hat.
Dieser Hinweis auf dieses Misstrauen, Gut.
Dann würde ich sagen, vielen Dank.
Hat Spaß gemacht.
Ich fand es auch super spannend.
Die Episode mit Lars wirst du, nicht wir, zu einem geeigneten Zeitpunkt nachholen.
Das ist noch offen.
Wir haben ansonsten, ich gucke mal kurz in den Plan.
Wir haben am 6.12. tatsächlich nächste Woche Prozessorchestration BPMN und Workflows mit Bernd Rücker.
Dann haben wir am 10.12. sind wir live bei den IT-Tagen.
Der 6.12. ist ein Freitag.
Der 10.12. ist ein Dienstag, wenn ich mich recht entsinne.
Da geht es um diese Frage IT 2034.
Da werden wir die Sachen von den IT-Tagen abholen.
Wir haben dann noch am 20.12. dieses KI under oder overhyped mit Stefan Schmidt, dem André Neubauer und uns beiden und Lisa in der Moderation.
Achso.
Und heute ist der Trailer für den Adventskalender live gegangen.
Wo wir jetzt tatsächlich im Dezember jeden Tag einen Buchtipp haben werden.
Das ist also das nächste, was passiert, kann man sich auch anschauen.
Genau, dann würde ich sagen, nochmal vielen Dank.
Schönes Wochenende und bis dahin.
Genau, schönes Wochenende.
Tschüss.