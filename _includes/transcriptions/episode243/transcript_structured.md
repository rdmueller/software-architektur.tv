# Folge 243 - Process Orchestration, BPMN und Workflows mit Bernd Rücker Hallo, ich bin Eberhard Wolff.
Freitags mache ich oder Lisa Moritz einen Livestream zum Thema Software-Architektur, oft zusammen mit Gästen.
Dieser Podcast ist das Audio des Streams.
Weitere Folgen, Sketchnotes und vieles mehr findet ihr unter software-architektur.tv.
## Einführung in den Podcast

So, herzlich willkommen zu einer weiteren Episode von Software-Architektur im Stream.
## Hinweise und Ankündigungen

Bevor wir inhaltlich loslegen, so ein paar Hinweise.
### Adventskalender

Der eine Hinweis ist, wir haben den Adventskalender, offensichtlich noch bis Weihnachten, wo es jeden Tag einen Buchtipp gibt von irgendeiner Person.
Sehr vielfältig und sehr spannend.
Guckt da gerne rein.
Ich habe die Links auch in den Chat getan.
### Nächste Episode

Und bei Mastodon kann man dem sogar folgen.
Da gibt es also dann einen Account, wo die neuen Videos dann irgendwie kommen.
Dank Feediverse kann man eben auch neue Videos abonnieren.
Und der zweite Hinweis, nächste Woche gibt es eine Episode von den IT-Tagen, das ist am Dienstag.
Und zwar abends, ich meine um 19 Uhr, da kann ich aber gleich nochmal nachgucken.
Und da sprechen wir darüber, wie denn eigentlich so IT in 2034 aussieht.
Genau, das dazu.
## Einführung in das Thema

Heute geht es um ein ganz anderes Thema.
### Prozessautomatisierung

Heute geht es irgendwie so um dieses Thema rund um Process Orchestration und die verschiedenen Sachen, die es da so gibt.
### Gäste im Stream

Und dazu habe ich Bernd eingeladen.
Bernd, schön, dass du da bist und schön, dass du die Zeit gefunden hast.
Willst du kurz zwei Worte über dich sagen?
Zwei Worte?
Das sind wenige.
### Berufsweg

Ja, überhaupt danke, dass du mich eingeladen hast.
Freut mich, dass das Thema hier rauskommt.
Genau, mein Background ist, ich habe eigentlich einen Engineering-Background.
Ich würde mal fast behaupten, wir haben uns vor bestimmt auch schon über zehn Jahren mit Spring mal kennengelernt.
So in dieser ganzen Java-Enterprise-Ecke.
Habe mich aber dann schon ganz, ganz früh diesem Thema Prozessautomatisierung im weitesten Sinne verschrieben und habe auch zu BPMN viel gemacht.
Alles Themen, wo wir gleich, glaube ich, nochmal ein bisschen einsteigen wollen.
### Gründung von Camunda

Habe dann früh die Camunda gegründet, zusammen mit dem Jakob Frey, das eigentlich Beratungshaus rund um dieses Thema BPM, Prozessautomatisierung.
Und dann hat mich das Thema nie mehr losgelassen.
Und wir haben selber als Camunda dann pivotiert, wie man so schön sagt, 2013 vom Beratungshaus zu einem Software-Hersteller.
Also wir hatten einfach ganz, ganz viel gesehen über die Trainings und die Workshops, die wir so gemacht haben, was bei den Kunden, bei den Unternehmen funktioniert hat in Richtung Prozessautomatisierung.
Oder vor allem auch, was nicht funktioniert hat, auch im Sinne von Software.
Damals war ja ganz viel sowas wie, keine Ahnung, IBM Processor oder irgendwelche Software-AG-Sachen.
Und das hat alles nicht so wahnsinnig gut funktioniert.
Wir waren viel mit Open Source zum Beispiel dann unterwegs.
Da gab es aber auch einfach gewisse Probleme, sage ich mal.
Und dann haben wir irgendwann gesagt, hey, eigentlich wissen wir, wie das Produkt aussehen sollte, was man da bräuchte.
Und dann haben wir irgendwann quasi uns den Mut genommen und haben gesagt, okay, dann machen wir das.
### Monetarisierung

Und seitdem sind wir seit 2013 einfach Software-Hersteller und wachsen ganz, ganz fröhlich vor uns hin.
Sind jetzt gerade ungefähr 500 Leute und haben gerade diesen, wie ich gelernt habe, Zentaurin-Status erreicht, den man bei 100 Millionen Jahresumsatz bekommt.
Also wo man quasi schon bewiesen hat, dass die Software offensichtlich auch tatsächlich irgendwie hilfreich ist.
## Wirtschaftlicher Erfolg von Camunda

Genau, also von dem her in zwei Worten würde ich sagen, so Process Orchestration, das ist ein Wort für mich, Enthusiast.
Genau, super.
Vielen Dank und auch herzlichen Glückwunsch zu dem wirtschaftlichen Erfolg an der Stelle.
Damit ist eigentlich gar nicht, also das gibt halt diese Beziehung zu Camon.
Und dann vielleicht kurz einen Hinweis dazu, wie die Episode zustande gekommen ist.
Die ist halt dadurch zustande gekommen, dass ich einen Vortrag und einen Workshop gehalten habe.
Und irgendwie kamen da halt so Fragen rund um, wie passt denn eigentlich diese Geschichte Business Process Management zusammen so mit klassischer Architektur, Domain-Domain-Design, Baune-Kontexte, Modularisierung.
Und das fand ich war eine gute Frage.
Und nachdem das halt irgendwie zweimal innerhalb von, ich weiß gar nicht, so 14 Tagen irgendwie aufgetaucht ist, habe ich gedacht, machen wir mal eine Episode und holen uns halt mal jemanden dazu, der es sozusagen so wirklich versteht.
Und genau, da bin ich dann auf die Band gekommen.
Und das führt so ein bisschen gleich zu der ersten Frage.
## Begriffsklärung

Wie heißt denn jetzt dieser Bereich eigentlich?
Also Workflow Engine, Process Orchestration, BPMN, BPM.
Was ist der richtige Begriff oder wie ist diese Begriffsverwirrung so ein bisschen zu erklären?
Ja, also lass uns vielleicht versuchen, die Begriffsverwirrung zu untangeln, also auseinanderzuholen.
### Workflow Engine

Ich würde sogar behaupten, einiges sind synonyme Begriffe und werden auch teilweise einfach sehr unterschiedlich benutzt.
Also aus der Historie heraus benutze ich persönlich immer noch gerne den Begriff Workflow Engine, weil der ganz arg diese, das ist klar, ich habe eine Softwarekomponente, eine Engine, die macht dann auch irgendwas und die soll eben so in dem Fall Workflows, also letztendlich ja auch Prozesse, abarbeiten.
Das Problem dieses Begriff Workflow Engines ist dann ganz oft, dass er mit so menschlichen To-Do-Listen und Tasks eher, ich steuere Aufgaben zu Menschen, assoziiert wird und damit jetzt nicht unbedingt in so, ich sage mal, eher IT-nahen Themen wie, keine Ahnung, Microservices Orchestration oder ich baue jetzt eine Zahlungsplattform, dann denkt man meist nicht an Workflow Engine.
Aber das dahinterstehende Konzept ist ja einfach zu sagen, okay, ich baue ein Stück Software, dem kann ich eine Beschreibung meines Prozesses geben.
Das sind immer irgendwie Schritte, irgendwie Kästchen und Peile dazwischen, was passiert in welcher Reihenfolge und dann kann die Maschine das für mich steuern.
Und das ist eben dieses Steuerung, dann sind wir eben bei Orchestrierung, deswegen eher dieser, ich sage mal, neuer Begriff der Prozessorchestrierung, Process Orchestration und dann gibt es eben auch einen Process Orchestration Engine, aber letztendlich meint es eigentlich was sehr, sehr Gleiches an der Stelle.
Und ich komme gleich, BPM und BPMN würde ich gleich mal noch machen, aber lass mich mal ein Beispiel machen.
Ich mache immer gerne Beispiele und da würde ich gerne ein, zwei Dinge auch noch entwirren, die ganz oft in einen Topf geworfen werden.
Wir haben auch schon Prozessautomatisierung gesagt, mindestens ich habe es, glaube ich, in der Intro mal gesagt.
Unter Prozessautomatisierung verstehen jetzt auch ganz viele Leute verschiedene Dinge.
Ich gucke jetzt mal auf Geschäftsprozesse.
Ich mache ein Beispiel, Kontoeröffnungsprozess.
Also das ist jetzt einfach aus der Bankenwelt.
Ich will ein neues, keine Ahnung, Shiro-Konto aufmachen.
So, dann geht ja auf der Seite der Bank ein gewisser Prozess los.
Also ich gehe vielleicht auf die Webseite, tippe meine Daten ab, klicke auf den Button und dann geht dort ein Prozess los, sodass er sagt, im ersten Schritt muss vielleicht irgendwelche Prüfungen gemacht werden, Adressprüfungen, irgendwelche Scoring-Sachen, also hier so Schufa-Einträge.
Dann muss irgendwie heutzutage Know-Your-Customer oder Compliance-Check, bla, dann gehen so Sachen los.
Dann muss die Bank vielleicht noch entscheiden, wollen sie das?
Und dann passieren gewisse Schritte in der Reihenfolge, mein Konto, wir haben vielleicht eine IBAN zu vergeben, wirklich das Konto in den richtigen System, Backend-System anzulegen und so weiter und so fort.
Und das ist ein Prozess, verschiedene Schritte abfolgen.
### Modellierung von Prozessen

Um diesen Prozess zu automatisieren, brauche ich eigentlich so zwei Ingredients.
Das eine ist eben dieses Thema Orchestrierung, also wie sorge ich dafür, dass die richtigen Dinge in der richtigen Reihenfolge passieren?
Und das zweite ist auch ein Stück weit automatisieren der Aufgaben, die in diesem Prozess zu tun sind.
Also es könnte sein, dass da irgendwie ich soll einen Schufa-Score prüfen als Beispiel, hat man früher wahrscheinlich einfach irgendjemand per Hand irgendwo in ein System geguckt, macht man heute nicht mehr, ruft man einfach ein System auf, eine Schnittstelle.
Und so ist das auch zu sehen.
Jeder Schritt ist dann entweder ein Systemaufruf, API-Aufruf, was auch immer das ist.
Oder eben den Menschen aufrufen, also eine Aufgabe in die Liste zu legen oder auch, keine Ahnung, heutzutage ihn anzuslacken oder eine Teams-Message zu schicken.
Also wie genau dann die Maschine mit den Menschen in Kontakt tritt, sei immer dahingestellt.
### Prozessautomatisierung

Also von dem her Process Automation ist für mich immer Process Orchestration und Task Automation.
Und so kommt das dann alles auch so ein bisschen zusammen.
Lass mich noch einen Begriff erklären und dann gebe ich dir auch mal wieder kurz Zeit, da reinzuhaken.
Nämlich den BPMN hast du mal kurz erwähnt.
Das steht für Business Process Model and Notation.
Das ist ein ISO, also inzwischen ISO-Standard für diese Prozessbeschreibungssprache letztendlich.
Also wenn man so will, ein XML-Dialekt, in dem ich dann diese Prozesse aufmalen kann auf der einen Seite, also wirklich grafisch, aber eben unter der Haube auch wirklich eine Bedeutung dahinter steckt, was diese Kästchen jetzt sind und wie ich da jetzt Logik dahinter hänge und was die eigentlich zur Ausführungszeit so bedeuten.
Ob der Pfad jetzt nach oben oder nach unten geht, ob ich da was parallel mache.
Also da kann ich auch so Timeouts machen.
Also BPMN ist sehr, sehr mächtig darin, so typische Probleme auszudrücken, die ich eben in solchen Prozessen habe.
Und das kann ich direkt zu einer, also zumindest einer guten Orchestration Engine geben und sagen, hier ist mein Prozessmodell und dann kann ich mir das auf der einen Seite grafisch angucken, aber eben auch direkt ausführen.
Genau, super.
Was also bedeutet, dass wir, wenn man das zusammenfassen sollte, oder das wäre die Frage, hört sich das für mich so an wie, das ist so ein Ding, was irgendwie atomare Sachen koordiniert.
Passt das so weit?
Ja, aus Sicht des Prozesses atomar.
Also ich habe einzelne Schritte, die sind aus der Sicht des Prozesses atomar.
Da kann ja nochmal ganz viel drinstecken.
Ja, genau.
Also da könnte drinstecken, jetzt mach hier eine Prüfung.
Das ist vielleicht ja sogar ein komplett eigener Prozess, der drei Wochen dauert.
Aber eben eine Koordination und Integration, das ist so ein bisschen die Idee.
Und das führt dann eigentlich zu der nächsten Frage.
Also bedeutet das, dass man da jetzt keine Geschäftslogik drin haben sollte?
Also dass man sagt, das ist eben so eine Integrationsschicht oder bestimmte Teile sind ja vielleicht dann tatsächlich Geschäftslogik, weil ich mir auch in dieser Integration dann irgendwelche Entscheidungen treffen muss.
Also ist das gut oder schlecht, wenn da halt irgendwie Geschäftslogik drin ist?
Oder sollte da nur bestimmte Geschäftslogik drin sein?
Oder wie ist da die Idee?
Lass uns mal vielleicht versuchen, ich versuche mal noch was anderes so ein bisschen auseinander zu ziehen.
Und das ist so, also jetzt habe ich diese Maschine, diese Orchestration Engine.
Oder man nennt sie auch gerne Workflow Engine.
Meine Erfahrung ist, dass die Leute das im Kopf immer noch besser klarkriegen.
So, jetzt habe ich diese Engine.
Und erst mal aus einer rein technischen Sicht ist das ja irgendwie so, sie stellt mir so eine Capability quasi bereit.
Das geht hauptsächlich darum, ich habe ein grafisches Modell, das kann ich ausführen.
Und ich kann langlaufende Sachen unterstützen.
Und dieses Thema Long Running, nämlich weil ich ganz oft warten muss auf Fremdsysteme, die brauchen ein bisschen mir eine Antwort geben, auf den Menschen, der auch nicht jeden Millisekunden antwortet, auf irgendwelche Events, die halt erst in zwei Wochen sind oder keine Ahnung.
Also ich muss warten und daraus resultieren Anforderungen an Persistenz, an Operating, an Monitoring, so, so, so.
Aber das ist erst mal so diese technische Komponente.
Jetzt kann ich die natürlich für unterschiedliche Anwendungsszenarien irgendwie brauchen.
Das eine, du hast es gerade schon gesagt, sind integrationsnahe Sachen.
Also wir haben durchaus so Use Cases.
Ich würde es jetzt mal Integrationsprozesse nennen, wo es eigentlich darum geht.
Ich will ja, keine Ahnung, ich will irgendwas über AI, über irgend so ein AWS-AI-Service rausfinden.
Aber dafür brauche ich vielleicht zwei, drei, vier Schritte, die nacheinander folgen.
Muss die Daten kurz transformieren, damit ich sie richtig irgendwie dahin schicken kann.
Oder du kannst das ganz simpel machen.
Auch ich will eine GMS-Nachricht schicken und auf die Antwort warten.
Und wenn die nicht kommt, will ich noch was anderes machen.
Also es gibt manchmal so Anforderungen, wo ich sage, ich muss halt drei, vier, fünf, sechs Sachen machen, um eigentlich fachlich gesehen so eine technische Schnittstelle aufzurufen.
Das wäre für mich so ein Integrationsprozess.
Dafür kann ich natürlich BPMN benutzen.
Dafür benutzen auch Leute Camunda oder andere Frameworks.
Ist aber ein ganz anderer Anwendungsfall, als wenn ich tatsächlich so, was wir Ende-zu-Ende-Geschäftsprozesse nennen, anschaue.
Also was ich gerade meinte, Kontoeröffnung oder was weiß ich.
Du willst eine Versicherungspolizei, du willst einen Schaden abwickeln, du willst neue Mobilverträge auf deinem Handy haben, du willst umziehen.
Das sind so typische Prozesse, die wir da eben auch bei den Kunden sehen.
Und das ist ja eine ganz andere Flughöhe.
Also da habe ich dann so einen Schritt, der heißt dann eben, ich muss das in mein Kernsystem schneiden, in mein Kernbankensystem.
Und vielleicht ist das unter der Haube dann ein Integrationsprozess mit 20 Schritten, weil das halt irgendwie kompliziert ist.
Und auf beiden Systeme spielt Process Orchestration Prinzipiell eine Rolle.
Theoretisch sind natürlich die Anforderungen ein bisschen anders, auch an die Tools.
Du hast eigentlich gefragt nach Geschäftslogik.
Jetzt fange ich langsam an, zu deiner Frage zurückzukommen.
Wenn ich mir diese Integrationsprozesse angucke, dann ist das typischerweise eben genau eigentlich keine echte Geschäftslogik, weil ich sage, da muss ich halt irgendwelchen technischen Kram machen, der ganz oft mit Long Running, mit Langlaufen zu tun hat, was mir eben schwer macht, es in Java oder in Python zu programmieren.
Deswegen will ich vielleicht irgendwie ein Framework on top.
Aber das sollte idealerweise natürlich nicht wirklich Geschäftslogik sein.
Wenn ich mir jetzt Geschäftsprozesse angucke, dann bestehen die ja ganz essentiell aus Geschäftslogik.
Das ist ja eigentlich die Geschäftslogik, dass ich sage, hey, ich nehme nur Kunden in meine Bank auf, wo ich halt vorher diese fünf Prüfungen gemacht habe.
Und vielleicht ist das ja sogar eine gesetzliche Anforderung.
Also das ist essentiell Geschäftslogik.
Und ich will genau, dass die in diesem Prozess landet.
Dafür mache ich ihn eigentlich.
Das ist ja einer der großen Vorteile.
Also Langlaufen spielt dort auch eine Rolle.
Aber das andere, was dann schnell auch eine Rolle spielt, ist eben dieses Thema Sichtbarkeit.
Ich kann das jetzt mit verschiedenen Stakeholdern besprechen.
Ich kann das bei Banken der internen Revision zeigen, wenn das denn sein muss.
Ich bekomme so Process Intelligence Tooling, wo ich sehe, welche Pfade werden oft durchlaufen.
Wo dauert das lange?
Unter welchen Datenkonstellationen geht das oft nicht weiter?
Oder was auch immer.
Also da kann man ganz, ganz tolle Sachen eigentlich machen.
Und das basiert immer auf diesen grafischen Modellen.
Also da habe ich, wenn man so will, ein bisschen andere, was in der Plattform bringt mir eigentlich wie viel.
Macht das noch Sinn gerade?
Ja, also wenn ich es sozusagen zusammenfassen würde, hört sich das so an wie, ich habe eben bestimmte Dinge, du hast eben gesagt, Long-Running-Prozesse, die ich halt eben auch Persistenz halten kann.
Und das können Sachen sein, die andere Dinge integrieren oder eben die ich halt sozusagen selber dann für mich entwerfe.
Und davon abhänge ich, ob es jetzt sozusagen meine eigenen Prozesse sind oder nur Integration, will ich halt Geschäftslogik in dem Prozess drin haben oder eben auch nicht.
So habe ich das jetzt sozusagen für mich verstanden.
Ja.
Vielleicht darf ich noch eine Sache dann on top da her, die ich wichtig finde.
Du musst dann natürlich auch immer gucken, welche Granularität von Logik willst du eigentlich in diesen Prozess packen.
Und das ist dann auch unterschiedlich.
Also bei einem Integrationsprozess bin ich ja in einer tiefen Granularität.
Der sieht vielleicht ein bisschen aus wie in Anführungszeichen grafisches Programmieren manchmal.
Aber jeder Schritt kann halt sozusagen stehenbleiben, Long-Running sein.
Und so ein Geschäftsprozess ist natürlich auf einer Abstraktionsebene, wo ich sage, jetzt mach das aus einer fachlichen Sicht.
Du hast es ja vorhin schon gesagt.
Was sind denn atomare Tasks sozusagen?
Also was will ich hier tun?
Ganz häufig dann ja sogar unabhängig von der Implementierung gedacht.
Also sozusagen abstrakt von der Technologie.
Also bis hin zu eigentlich ist das egal, ob diesen Task jetzt ein Mensch macht, der dann sich durch 15 Oberflächenmasken klickt oder ob das ein Systemaufruf ist oder ob das morgen ein AI-Agent ist, der das irgendwie übernimmt.
Sollte egal sein, solange diese Granularität eigentlich irgendwie passt.
Also da fange ich dann genau nicht an, jeden kleinen Kran sozusagen da rein zu modellieren, sondern will dann eine Granularität finden, wo ich sage, okay, dieser Geschäftsprozess ist sauber, dann habe ich einen Task und der ist irgendwie implementiert.
Vielleicht ist das sogar nochmal ein Prozess in der Ebene drunter, weil das eben Sinn macht.
Vielleicht ist das auch einfach nur ein Serviceaufruf.
Vielleicht ist das aber auch Programmierung, dann eben doch ein bisschen Java-Code hintendran.
Also in dem Sinne, das ist einfach, wenn man so will, ein zusätzliches Werkzeug im Stack, was ja auch gar nichts ersetzen soll in dem Sinne, was einfach diese Prozessebene bildet.
Heißt das, ich kann jetzt mit sowas wie Camunda beispielsweise BPMN benutzen und gleichzeitig das auch als Programmierframework benutzen?
Also habe ich beide Möglichkeiten?
Also du kannst das zusammenstecken.
Also der Weg, wie die Engine funktioniert, ist letztendlich einfach auch über API.
Also in dem Sinne kannst du das auch komplett headless fahren, wenn du das möchtest.
Du kannst ja dann auch Unit Tests schreiben.
Das wollte ich gerade sagen, im einfachsten Fall.
Das stimmt, glaube ich.
Ich weiß gar nicht, ob es der einfachste Fall ist.
Aber wenn ich jetzt aus einer Java-Entwicklerbrille denke und überhaupt keine Ahnung habe von Workflow-Engines und BPMN, dann kann ich mir schon auch so vorstellen, dass ich sage, na ja, ich habe jetzt halt noch so ein grafisches Bild und an jedem Knoten, der ist einfach verknüpft mit einer Methode in meinem Java-Code.
Und wenn ich quasi die Prozessinstanz, sagt man, also wenn ich einen neuen Prozess antriggere, sage ich über API, hey, starte eine neue Prozessinstanz und nimm bitte die paar Daten mit.
Das ist typischerweise ganz wenig, so eine kleine Map von Sachen.
Dann guckt die Workflow-Engine in dieses Prozessmodell.
Was muss ich machen, wenn ich den starte?
Ah, ich laufe mal hier lang und dann kommt dieser Knoten da.
Und was bedeutet dieser Knoten?
Ah, das heißt eigentlich, dass dieser Code da unten in Java aufgerufen wird.
Und dann stellt sie eben sicher, dass das passiert sozusagen.
Und zwischendrin könnte sie auch warten und persistieren und so.
Aber das heißt, ich kann das schon mit meiner Programmierung zusammenbauen.
Ich kann mir auch ganz normal Unitests dafür schreiben.
Also ich kann auch sagen, ich will gewisse Szenarien bauen, wo ich sage, wenn diese Kontoeröffnung mit genau diesen Daten da vorne reingesteckt losläuft, erwarte ich, dass sie dann, keine Ahnung, diese Prüfung dieser API aufruft mit diesen Parametern, die ich dann irgendwie so rausmocke und solche Geschichten.
Also das ist nicht zwangsläufig weit weg von der Programmierung.
Das ist, wenn man genau hinguckt, eigentlich mit der Grund, warum wir damals auch Camunda als Produkt gestartet haben, weil die Tools, die wir damals gesehen haben, also wie gesagt 2012, 2013, lange her, die konnten genau das nicht.
Da waren es dann ganz oft, okay, ich nehme jetzt hier dieses BPM-Produkt und dann muss ich auch alles da drin machen.
Und dann war es echt hakelig, noch echte Software-Engineering dazu zu packen und das zusammenzukriegen.
Das war eigentlich immer so ein bisschen das Ding.
Genau.
Da ist jetzt gerade im Chat so ein bisschen eine Diskussion, die ich auch schon im Hinterkopf hatte.
Also was du ja sagst, ist, okay, ich habe ja diese grafische Notation und es gibt ja jetzt insbesondere diese Geschichten rund um kollaborative Modellierung, sowas wie Events-Storming, wo man eigentlich versucht, mit so Low-Tech-Produkten, also so Post-Its, dafür zu sorgen, dass man diese wahrgenommenen Barrieren hat, reduziert und hat gesagt, okay, wenn du halt ein Post-It schreibst, kannst du halt Events-Storming machen.
Das kann halt nicht so schwierig sein.
Und demgegenüber stehen halt solche formalen, also das ist ja offensichtlich informell nicht, also ein Post-It ist halt irgendwie was, was nicht Formales wäre.
Ein BPMN, sei es fair gesagt, ist halt ein ISO-Standard und hat irgendwie auch dann irgendwelchen Formalitäten entsprechen müssen.
Der Darth Kali hat jetzt gerade im Chat geschrieben, wir benutzen Camunda.
Wir können mit den Entwicklern näher zusammenkommen.
Und da hat jetzt Ralf Müller geschrieben, kommen die 5-Tech-Experten mit BPMN gut zurecht.
Ich habe die Erfahrung, dass die Decorator teilweise als zutanisch angesehen werden.
Und dann kommt halt irgendwie Darth Kali und sagt, wir entwickeln das gemeinsam, da funktioniert es sehr gut.
Also führt ja zu der Frage, wie ist denn dein Eindruck?
Also der Darth Kali sagt halt irgendwie, vielleicht ist das sogar das, was beide sagen, nur Menschen wie wir, also TechnikerInnen, können das wirklich verstehen.
Und für PHI-ExpertInnen ist das zu formal.
Also es steht da nicht ganz, aber das höre ich so ein bisschen raus.
Ist da eine Erwartungshaltung, dass Menschen, also normale Menschen, nicht TechnikerInnen, BPMN verstehen und das modellieren sollten?
Oder ist das tatsächlich etwas so für Leute wie uns, die ja mit so formalen Systemen Erfahrung haben?
Schade, wir können jetzt eine halbe Stunde lang erstmal rollen und was ein normaler Mensch ist definieren.
Aber das lassen wir mal.
Ich würde eigentlich das ziemlich unterstützen, wie es da im Jet, glaube ich, passiert ist.
Also das eine ist, meine Erwartungshaltung wäre nicht, dass jetzt zum Beispiel Fachabteilungen direkt BPMN modellieren.
Das glaube ich auch nicht.
Das ist aber eigentlich auch nicht der Weg.
Also dann die Frage ist tatsächlich, wie baue ich mein Vorgehen auf?
Und andersrum gesagt, was ich auch schon sehr oft gesehen habe, was gut funktioniert, ist, wenn du eine Rolle hast, die tatsächlich diese BPMNs modelliert.
Ob das jetzt ein Business-Analyst ist, das habe ich schon gesehen, wenn die gut sind, ja.
Manchmal ist denen das auch ein bisschen zu formal.
Warum auch immer dann PowerPoint so viel cooler ist, aber ist ja egal erst mal.
Dann ist es vielleicht auch tatsächlich jemand auf der IT-Seite, in der Entwicklungsseite.
Aber wenn es irgendjemanden gibt, der diese BPMNs modelliert, ist ja das Zweite, diese BPMNs sozusagen zu verstehen, wenn ich sie sehe.
Und das funktioniert dann in der Breite doch wieder eigentlich ganz gut.
Und da muss ja auch nicht jeder Fachanwender sozusagen jedes Detail immer im Modell verstehen.
Man muss ja auch dazu sagen, dass es ja den großen Bonuspunkt gibt, dass dieses Modell, dieses grafische Modell, was ich habe, ja dann nicht sozusagen nur für irgendwie eine Doku erzeugt wird, die dann keinem was bringt, sondern es ist ja laufende Software.
Das heißt, ich kann da wirklich jederzeit reingucken, auch wieder mit dem Fachanwender zusammen sagen, okay, ihr braucht diese Änderung jetzt, lasst uns mal gucken, wo eigentlich.
Und vielleicht versteht ihr das Modell nicht alleine komplett.
Aber trotzdem habe ich diese Basis, auf der ich dann einfach kommunizieren kann.
Und die Erfahrung zeigt dann auch, wenn die Reife im Unternehmen steigt, je mehr man damit arbeitet, desto mehr wird das auch dann verstanden.
Und dann wäre einfach mein Anspruch nicht, dass jeder 100 Prozent BPMN verstehen muss, das ist Quatsch.
Aber es muss halt mal mindestens, ich sage mal, ein, zwei Leute im Unternehmen geben, die das wirklich so ein bisschen treiben können.
Also wir haben bei größeren Kunden, die das einfach auch wirklich in der Breite einsetzen, ganz oft irgendwie so ein zentrales Team, was einfach die anderen unterstützt, enabelt, ein bisschen supportet.
Und dann funktioniert das eigentlich ganz gut.
Und jetzt kommen ja, glaube ich, die nächsten Jahre da eh noch viel, was so dieses ganze Thema Co-Piloting angeht.
Also wir können heute schon BPMN Co-Pilot, wo ich also theoretisch, das habe ich noch nicht probiert, das wäre mal spannend, so ein Event-Storming, also Event-Storming geht ja sogar von der Sache her gut zusammen mit BPMN.
Also Event-Storming wäre dann sozusagen die Kreativ-Technik, auch irgendwo hinzukommen.
Und BPMN wäre eher das, okay, und jetzt mache ich was draus.
Was aber dann noch sehr gut zu den Events passt, die ich da eigentlich gestormt habe quasi.
Und du kannst so einem Co-Pilot heute ja schon sowas hinwerfen.
Also wenn ich das als Tabelle habe, dann werfe ich dem das hin und er macht mir ein BPMN-Modell draus.
Das wird nicht sofort cool sein, aber da komme ich recht schnell sozusagen in so ein Rädchen rein.
Und darum geht es ja am Ende des Tages.
Genau, also vielleicht noch kurz, im Chat hat Dav gerade noch geschrieben, somit entsteht ein guter Wissensaustausch.
Also durch dieses, dass EntwicklerInnen und Domain-Experten gemeinsam was machen.
Wir EntwicklerInnen lernen mehr über den Fachprozess und die FachexpertInnen haben mehr Verständnis für die technischen Hürden.
Das hört sich also soweit sozusagen gut an.
Und bei Twitch hat der Java-Hippie gesagt, ich habe auch sehr gute Erfahrungen mit der Leistbarkeit von BPMN gemacht.
Wir haben einen sehr langen Konteröffnungsprozess anhand des BPMN-Modells mit der Rechtsabteilung einer Bank diskutieren können.
Gut, ich glaube, damit haben wir sowieso ein bisschen dieses BPMN-Grafische Modellierung usw.
Beziehungsweise, das wäre halt noch die andere Frage, die mich so ein bisschen beschäftigt.
Also grafische Notationen, wenn sie halt formal sind, haben halt manchmal dieses Problem, dass es halt einfacher ist, Dinge halt einfach als Code hinzuschreiben.
Und nun sagst du ja, das ist auch ein XML-Dialekt, aber in XML ist es halt auch nicht so richtig schön.
Gerade so diese URL-Geschichten sind halt häufig so, wenn man das halt wirklich formal richtig irgendwie alles hinschreibt, wird es halt wahnsinnig kompliziert, unübersichtlich.
Und man wünscht sich halt eine Programmiersprache.
Ist das irgendwie auch ein Problem, was es so im BPMN und diesem Workflow-Bereich gibt?
Also ich sehe es eigentlich nicht als Problem.
Also du siehst ja, wenn du mal ein Weilchen da draußen unterwegs bist, alles Mögliche.
Also ich habe auch schon echt Projekte gesehen, die auch BPMN in der Granularitätsstufe verwendet haben, wo ich sagen würde, das hat keinen Sinn.
Also da wurde grafisch programmiert.
Das ist schon Verstand quasi, weil jetzt haben wir das Tool, jetzt benutzen wir es auch.
Und dann kommen natürlich Modelle raus, wo man sich sagt, okay, das bringt mir jetzt eigentlich nichts.
Also weil dann habe ich nur Overhead und nichts gewonnen.
Das hätte ich lieber programmiert.
Aber wenn ich diese Granularitätsstufe richtig treffe, muss man ja sehen, gerade bei Ende-zu-Ende-Geschäftsprozessen, wenn ich mir die angucke, ist der Aufwand selten sozusagen jetzt diese, und lass das mal 50 Knoten sein.
Aber die aufzumalen und zu verdrahten ist nicht der Aufwand im Projekt.
Der Aufwand im Projekt ist zu verstehen, welche Knoten ich haben muss, in welcher Reihenfolge die eigentlich stattfinden, wie der Datenfluss dazwischen ist, warum das da hinten eigentlich weiß, was da vorne irgendwie passiert ist und wie ich das jetzt verändern kann.
Und da passiert der eigentliche Aufwand.
Und da hilft mir dieses Modell einfach so unglaublich viel, weil ich dann mit ganz vielen Menschen kommunizieren kann, mit denen ich halt nicht auf Code gucken könnte.
Da kann man jetzt lange diskutieren, kann ich so ein Fach anwenden.
Da ist aber auch noch hier Bullet-Point-Liste an Statements.
Dann schreibe ich eine schöne DSL.
Ich glaube nicht, dass es funktioniert.
Spätestens, wenn man mal so einen Loop drin hat, dann hat man noch so einen Timer oder haben wir noch 15 andere Sachen.
Also da machen wir ja gute Erfahrungen.
Ich habe da überhaupt kein Problem damit.
Und dann kommt typischerweise das nächste Jahr, aber da machen wir doch so Änderungen.
Da muss ich ja so Diffing machen und bis jetzt XML-Diffs machen.
Das ist ja total Banane.
Also zwei Punkte dazu.
In der Praxis war diese XML-Diffs nie so ein großes Problem, weil man jetzt selten den kompletten Prozess verändert.
Und das muss ja nicht jeder das Kästchen jetzt einen Millimeter weiter nach links schieben, nur weil er es schöner findet.
Also wenn man da so ein bisschen quasi Funkdisziplin an den Tag legt, funktioniert das mit XML ziemlich gut.
Das zweite Ding ist, dass ja inzwischen die Tools, auch wie unseres, kann man ein grafisches Diffing machen.
Also daran scheitert es heutzutage sozusagen nicht mehr.
Und dann kannst du schon auch einfach ziemlich coole Sachen machen.
Also noch zwei Sachen aus dem Chat.
Der Ralf D.
Müller hat geschrieben, ich warte ja immer noch auf einen Text für Diagram Library à la PlantUML für BPMN.
Weiß ich nicht, ob du dazu sagen willst.
Ich kenne das konkrete Tool nicht.
Aber was ich glaube, womit sich das auflösen wird, ist diese Copilot-Sache.
Also dass man einfach die AI nutzt, die kann das Modell erstellen.
Und das funktioniert schon ziemlich gut.
Und was ich dem dann reinwerfe, da kann ich mir meine eigene Zündung, das checkt die AI ja erstaunlich gut.
Und dann hat der Grumio eine Frage, also auch bei YouTube, die uns so ein bisschen vom ursprünglichen Plan ablenkt.
Aber das muss ja nicht negativ sein.
Er hat geschrieben, gibt es typische Stolpersteine bei der Einführung von Tools wie Cramunda, die man vermeiden sollte?
Gerade mit Hinblick, wenn schon eine Art Eigenentwicklung im Unternehmen existiert.
Ja, also da gibt es immer viele.
### Granularität verstehen

Also da muss man ja, it depends, da muss man jetzt ein bisschen hingucken, wie die Situation genau da ist.
Also ich sage mal, Stolpersteine jetzt einfach mal generell bei der Einführung sind ganz oft das, was wir jetzt eh schon besprochen haben.
So Granularität verstehen, verstehen, was mir das Tool eigentlich bringt und dann eben nicht grafisch programmieren.
Das ist so das eine.
Klar, wenn ich schon eine eigene, selbstgebaute Workflow-Engine im Haus habe, das sehen wir ganz, ganz oft.
Also die lösen wir auch oft ab.
Dann muss man sich einfach fast eher die politische Lage oft mal angucken.
Was haben wir da schon und wer mag das oder wer mag das nicht?
Und wie wird das intern gesehen?
Ich sehe es eigentlich meistens super positiv, weil das zumindest bedeutet, dass im Unternehmen schon diese Denke verstanden ist.
Was ist eigentlich eine Workflow-Engine?
Was bringt mir das?
Wie kann ich das machen?
Und das ist super hilfreich.
Und meistens ist die Situation auch so, dass das gemocht wird, nur dass dann halt meistens zu wenig Kapazität intern da ist, diese Workflow-Engine anständig weiterzuentwickeln.
Und dann fehlen Features oder das nicht oder hier ein Bug oder das kann man nicht machen.
Und dann ist das meistens auch eine ziemlich schöne Situation zu sagen, okay, dann kommen wir mit einem anderen Tool rein.
Das kann das und ansonsten macht ihr das ähnlich weiter.
Ich würde noch eine Sache sagen, weil die ist jetzt vielleicht immer so ein bisschen egoistisch gedacht, aber das darf ich ja hier.
Nein, die treibt mich gerade so arg um.
Ich habe ja zwei Dinge.
Also einmal sind wir als Camunda quasi von der Unternehmens-Lifecycle her inzwischen schon ein Wallchen am Markt und haben recht viele Kunden, die auch tatsächlich auf großer Scale das einsetzen.
Also nicht nur einen Prozess, sondern viele Prozesse.
Das heißt, sie haben mich die letzten Jahre viel damit beschäftigt.
Dazu hat sie auch nochmal ein Buch geschrieben, wie, was muss ich da eigentlich tun, das so ins Enterprise zu bringen, in die Breite zu bringen, auch intern quasi zu skalieren.
Und dabei habe ich viel gelernt und eins der Learnings, und das fand ich total interessant, war Vollness.
Und das war bei einem, ich würde mal sagen, das war mein Auslöser, wo ich es verstanden habe, bei einem Versicherer, die tatsächlich Camunda in einer großen Breite einsetzen, die auch RPA in einer großen Breite einsetzen. Übrigens sowas wie Robotic Process Automation.
Wahrscheinlich kennen das hier ganz so viele, aber das ist so diese Idee.
Also wir kennen das unter Selenium und Testautomatisierung, aber die gleichen Tools werden ja auch verwendet, um Oberflächen zu steuern.
Ganz oft, wenn man eben keine Schnittstelle hat, keine anständige.
Dann wird für Task-Automatisierung eben eine Oberfläche angesteuert.
Und Folgendes ist passiert in dem Unternehmen jetzt eher, also gar nicht so aus einer technischen Sicht, sondern aus einer Management-Sicht.
RPA hat folgenden Vorteil, wenn man so will.
RPA-Projekte können immer sofort so ein Return-on-Invest rechnen.
Weil sie ersetzen typischerweise Menschen, die stupide Daten von A nach B hacken.
Dann kann man sagen, okay, dieses RPA-Projekt hat mich gekostet X, damit spare ich jetzt so und so viele Leute, die können jetzt was anderes machen.
Damit habe ich einen Return Y und damit habe ich ein cooles Projekt.
Und das machen die auch.
Und dann führte das irgendwann zu dieser Wahrnehmung, RPA ist ja voll cool, damit sparen wir voll das Geld und Camunda kostet ja hier irgendwie ganz viel.
Obwohl dann Kernprozesse dort automatisiert waren und zwar gar nicht wenige.
Also es war auf so einem Niveau, wo man sagt, okay, aber wenn man Camunda morgen abstellt, läuft halt die Versicherung nicht mehr.
Und diese Wahl, ich halte das für wichtig, das habe ich, wenn man darauf achtet, jetzt schon oft erlebt.
Diesen Wert sozusagen, was auch die Workflow-Engine bringt und warum ich das tue und welchen strategischen Wert das hat.
Also das, was ich vorhin sagte, ich verstehe jetzt die richtige Granularität der Tasks, führt dazu, dass ich zum Beispiel mir auf einmal überlegen kann, wo ich AI überhaupt einsetzen will, wo ich AI überhaupt einsetzen kann.
Das ist momentan die Riesen-Diskussion überall.
Und dieses Thema Business Agility dann hinzukriegen, ist massiv wichtig, aber ist schwer in Zahlen zu drücken.
Und IT hat sowieso, also ich glaube, wir kennen das alle, wir haben dann immer so eine Zurückhaltung da drin.
Und dann so, ja, aber das ist doch klar, dass das irgendwie, das macht doch total Sinn, das ist doch auch eine schöne Architektur oder so.
Aber das auf der richtigen Ebene zu überzeugen, halte ich nochmal für extrem wichtig.
Und gerade wenn man aus einer IT heraus, das kennen wir oft, Camunda-Projekte initiiert, man sieht die technischen Vorteile, man spart sozusagen in dem Projekt schon Aufwand, super.
Aber darüber hinaus noch sich diese Ebene auch mit anzugucken, weil sonst habe ich es einfach über die Zeit inzwischen erlebt, dass Projekte abgesägt werden aus politischer Großwetterlage und gar nicht aus einer technischen Sicht.
Also das ist ja ähnlich wie auch bei Microsoft.
Jetzt muss man ja auch irgendwie diese ganze Business-Entscheider-Ebene irgendwie so ein bisschen mitdenken.
Sorry, das war lange, aber das ist mir irgendwie so gerade wichtig, weil, also gerade das auch der Architekten-Community ein bisschen mehr ins Buch zu schreiben, sich das einfach anzugucken.
Ja, also ich bin ehrlich gesagt voll bei dir.
Also ich bin halt auch der Meinung, dass wir technische Maßnahmen ergreifen, uns nahezu in der Pflicht befinden, nachzuweisen, dass die halt irgendwie betriebswirtschaftlich Sinn machen.
Und also einmal aus politisch motiviert, aber auch einfach deswegen, weil wenn wir es halt sozusagen nicht begründen können, dass das halt irgendwie dabei hilft, noch mehr Geld zu verdienen, dann sind das vielleicht auch keine guten Maßnahmen.
Und von daher hilft diese Brille halt auch da nochmal Prioritäten zu setzen.
Das Buch, was du genannt hast, worauf du angespielt hast, ist wahrscheinlich dieses Enterprise Process Orchestration.
Das verlinke ich auch nochmal.
Achso, du hast es schon?
Nein, das ist ein Early Access, von mir selber gedruckt, wie man das so heutzutage machen kann.
Aber das kommt in Wiley, das ist gerade im Prozess, das sollte im April da sein.
Genau.
So, jetzt kommt das nächste Thema und das ist halt diese Geschichte mit Orchestration und Choreography.
Und du hattest beim Vorgespräch gesagt, da gibt es keine klare Definition, aber du hast ja Bücher geschrieben und da steht offensichtlich eine Definition drin.
Das andere, genau.
Ja, genau, das Practical Process Automation.
Was ist das denn überhaupt?
## Unterschied zwischen Orchestrierung und Choreografie

Also was ist Choreography, was ist Orchestration?
Ja, lass mich auch noch einen Satz vielleicht ausholen zu dem Thema, weil tatsächlich, das hat mich, lass mich lügen, ich würde sagen 2017, 2018 rum echt viel beschäftigt.
Also dieser ganze Microservices-Event-Driven-Architecture-Hype rüberschwappte und jetzt nicht jeder, aber echt viele zu mir kamen und sagten, ach, guck mal, dann brauchen wir doch euer Zugang.
Wir machen doch jetzt alle Choreographie, wir machen doch jetzt alles eventgetrieben.
Da wird doch nichts zentral gesteuert über so eine BPM-Maschine da.
Das ist doch jetzt Quatsch, da seid ihr doch irgendwie jetzt raus.
Und darüber habe ich dann echt viel nachgedacht.
Also einmal, sozusagen kann man jetzt natürlich so aus dem Filmhut aufsetzen und sagen, oh nein, das darf ja nicht passieren.
Aber tatsächlich war es so ein inhaltlicher, nein, das halte ich für Blödsinn.
Aber ich wollte es wirklich verstehen und dann bin ich da so relativ tief abgetaucht.
Und das erste genau, was du gesagt hast, fand ich total interessant, wenn man ein bisschen googelt, im Internet sucht, man findet keine sauberen Definitionen für weder Choreografie noch für Orchestrierung.
Und da findet man sehr widersprüchliche Sachen und zwar auch auf den echt viel zitierten Sachen.
Also ich glaube, das viel zitierteste war eine Stack-Overflow-Diskussion, die sogar dann relativ saubere Diagramme da reingepackt hat, die meiner Ansicht nach aber falsch sind oder sich teilweise sogar auch ein bisschen widersprechen.
Na ja, und da hat sich das dann so ein bisschen alles gefüttert.
Deswegen habe ich versucht, das aufzuräumen.
Und ich habe eine Definition dann ins Buch geschrieben, die ich für mich stimmig finde.
Ich glaube nicht, dass sie, ich würde jetzt nicht behaupten, dass sie im Internet total adaptiert ist.
Aber ich verstehe es.
Für mich ist Choreografie immer, wenn es um eventgetriebene Kopplung eigentlich geht.
So Choreografie heißt für mich, wenn ich Komponenten habe, die einfach auf Ereignisse reagieren, die andere Komponenten irgendwie in die Welt geworfen haben.
Und dann weiß typischerweise, das hat dann eben so Charakteristiken.
Das ist letztendlich eine Kommunikation zwischen zwei Komponenten, aber die, die das Event emittiert, die weiß nicht, wer was mit diesem Event machen will.
Und die, die dieses Event dann verarbeitet, die weiß, dass sie das Event verarbeiten will.
Aber im Zweifel auch gar nicht, wo es herkommt.
Und das ist für mich dann Choreografie.
Weil ich kann jetzt Systeme bauen, die dann einfach, jeder schmeißt so Events.
Hey, hier will ein Kunde ein neues Konto.
Hey, ich habe einen Kunden übrigens hier geprüft.
Hey, ich habe jetzt hier irgendwie ein Konto angelegt.
Und dann können andere Komponenten darauf reagieren und was machen.
Das war eine Zeit lang so die Idee, so bauen wir jetzt Systeme.
Weil dann immer mit diesem Argument niedrige Kopplung, dann können ja einfach diese, entscheide ich einfach in meinen Microservices, auf welche Events sie reagieren.
Alles ist schick.
Kann ich das ja auch schnell ändern oder so, war glaube ich oft die Idee.
So, was ist jetzt für mich Orchestrierung?
Orchestrierung definiere ich für mich, wenn zwei Komponenten miteinander interagieren über nicht Events, sondern über Commands.
Oder wenn man Sam Newman liest oder Mark, der macht ja viel zu Microservices, er nennt es lieber Request.
Er findet Command zu, suggeriert zu arg, das muss man jetzt tun.
Das kann man nicht ablehnen.
Aber ich nenne sie Commands.
Ich finde es trotzdem einfacher.
Und das heißt, bei dieser Kommunikationsbeziehung, es ist jetzt einfach andersrum.
Nämlich der Sender weiß, hier da drüben, du machst jetzt mal bitte für mich die Prüfung.
Und dann schickt ein Request und wartet, bis er zurückkommt.
Der Empfänger, der diese Prüfung macht, in dem Fall, stellt einfach nur, wenn man so will, eine API bereit.
Der weiß gar nicht, von wem er aufgerufen hat.
Für mich, also das ist erstmal für mich diese zwei Seiten der Medaille, wenn das halbwegs Sinn macht.
Das wäre eigentlich gleich etwas, wo ich so ein paar Fragen hätte.
Du hattest es ja vorhin so ein bisschen kurz gesagt.
Orchestration, Choreography, ich würde auch sagen, von der Begriffsbildung her, für mich schwingt da mindestens mit, dass es halt um eine zentrale Kontrolle geht oder eben auch nicht.
Also Orchestration impliziert für mich, zumindest vom Begriff her, eine zentrale Kontrolle.
Also irgendwo ein Ding gibt, was eben sagt, genau nicht.
Also das macht jetzt irgendwie das.
Das heißt also, im Rahmen der Kontoeröffnung würde ich jetzt erwarten, dass es da halt eine Entität, irgendetwas gibt, was eben sagt, das sind die Schritte, die halt irgendwie aufeinander abfolgen.
Was eben dann zum Beispiel in so einer Workflow-Engine halt liegt.
Und dann habe ich halt einzelne, diese atomaren Teile, die darüber halt koordiniert werden.
Während bei Choreography hätte ich jetzt gedacht, aber das scheint eine andere Definition zu sein.
Da weiß ich ja zum Beispiel dieses Schufa-Scoring, dass es halt die Schufa-Score irgendjemanden gibt, der irgendwas damit weitermacht.
Das heißt also, dieses eine Ding weiß, was der nächste Schritt ist.
Und so wie eben das Schufa-Score-Ding dann aufgerufen worden ist von irgendwas anderem.
Das heißt, jeder Schritt weiß, welches die nächsten Schritte sind.
Und ich habe es halt dezentral.
Das, was du jetzt vorschlägst als Definition, scheint damit nicht viel zu tun zu haben.
Oder täusche ich mich da irgendwie?
Nein, das ist nicht ganz weit weg.
Vielleicht das allerletzte, was du gesagt hast, war vielleicht nochmal ein bisschen was anderes.
Diese Komponente weiß, wie es da weitergeht.
Also für mich ist tatsächlich Event getrieben, also wenn ich Event und Choreographie angucke, wenn ich ein Event erzeuge, weiß ich nicht, wie es weitergeht.
Das ist für mich einfach Event getrieben.
Weil das ist nicht meine Verantwortung.
Also da geht es auch viel um Verantwortung, wie ich jetzt meine Komponente schneide.
Und wenn ich ein Event erzeuge, sollte ich nicht davon ausgehen, dass jetzt was passiert.
Was aber bedeutet, dass Choreography, so wie ich es jetzt gerade eben versucht habe zu definieren, würde ja bedeuten, der Schufa-Schritt weiß, was der nächste Schritt ist, weil ich eine dezentrale Kontrolle habe.
Das wäre für mich tatsächlich nicht in dem Sinne Choreografie, sondern das wäre eigentlich, wenn du so willst, eine verteilte Orchestrierung, weil die Schufa ja dann quasi das steuert.
Diese Schufa-Komponente steuert ja jetzt eine andere Komponente, was zu tun.
Warum sollte sie das tun?
Jetzt kann man sich überlegen, wie man sozusagen Orchestrierung implementiert.
Also man könnte theoretisch ja sagen, es gibt dieses Routing-Slip-Pattern als Beispiel, dieser, wie heißt es auf Deutsch, dieser Laufzettel.
Also ich könnte quasi in so eine Message reinschreiben und wenn du fertig bist, schick das da weiter.
Dann wüsste diese Komponente, die jetzt das Schufa-Scoring macht, kann den Routing-Slip lesen und weiß, da schicke ich es jetzt hin, ohne zu wissen, warum eigentlich.
Damit hätte ich quasi auch Orchestrierung gebaut, dezentraler.
Ich glaube nur nicht daran, dass das besser funktioniert.
Also nur, dass wir es sauber bekommen, das heißt, das, was du jetzt bei Choreografie sozusagen voraussetzt, ist, ich habe eine anonyme Menge an Dingen, die irgendwie reagieren, während du sagst, bei Orchestrierung weiß ich, mit wem ich spreche.
Das ist die Definition, die du jetzt mit Commands und Events sozusagen siehst.
Ja genau, im Prinzip ist das so, ja.
Okay, und dann sagst du halt, wenn ich ein Ding habe, also dieser Schufa-Schritt weiß, was die nächsten Schritte sind, dann ist das bei Orchestrierung aber dezentral.
Genau, ein anderer Weg, das hinzukriegen sozusagen.
Genau, und irgendwie scheinst du jetzt zu implizieren aus dem, was du gesagt hast, dass so eine dezentrale Orchestrierung irgendwie keinen Sinn macht oder deutliche Nachteile hat.
Also zwei Dinge.
Erstens, ich störe mich immer ein bisschen an diesem Wort zentral und dezentral, weil das, glaube ich, auch häufig ganz unterschiedlich verstanden wird.
Also wenn Leute schon ein bisschen länger dabei sind und gerade mit BPM-Systemen und ich sage zentral, dann denken die immer an, oh, wir haben hier diesen einen dicken BPM-Server im Unternehmen, der wird noch von diesem Team gemanagt und wenn ich da irgendwas mache, ist das ein Riesen-Bottleneck, das ist irgendwie alles blöd und so wollen wir das ja nicht.
Passt auch nicht mit Microservices zusammen.
Und das Team ist ja nicht so, also so sieht ja Technologie heute nicht mehr aus, sondern ich kann ja auch sagen, ich fahre allein schon die Orchestrierungslogik dezentral.
Also ich hätte meinen einen zum Beispiel Kontoeröffnungsservice, wenn ich so denke, und dieser Kontoeröffnungsservice, der ownt quasi gewisse Geschäftslogik, wie das Konto zu öffnen ist, der Herr der Name.
Und da gibt es ja dann auch irgendwie einen Verantwortlichen und ein Team vielleicht, das das baut und weil eben dieser Kontoeröffnungsprozess davon profitieren kann, eine Orchestration-Engine zu nehmen, werden sie das vermutlich, hoffentlich tun und sagen dann auf dem Weg anderen Services, die sie als Zulieferer brauchen, eben Bescheid.
Natürlich könnte ich jetzt sagen, nee, ich nehme keine Orchestration-Engine, weil will ich nicht und könnte irgendwie einen Routing-Slip ausdenken und den rumreichen.
Das würde schon technisch funktionieren.
Ich kenne jetzt einfach zumindest keine Out-of-the-Box, wie sagt man, Framework oder Vorgehen, wo ich das echt gesehen habe, dass das gut funktioniert.
Rein vom Pattern her würde das schon funktionieren.
Ich frage mich dann, welchen Vorteil ich da mit habe, weil dann hätte ich ja diese Komponente, wenn wir bei dem Beispiel bleiben, die mein Schufa-Score macht, die muss ja auf einmal einen Routing-Slip verstehen und wissen, wie es weitergeht.
Versus in der anderen Variante habe ich halt meinen Kontoeröffnung-Service und der weiß, erstmal mache ich Schufa-Scoring und wenn das fertig ist, mache ich was anderes und dann muss ich Schufa-Scoring gar nicht anfassen.
Und dann kann das sogar morgen ein SaaS-Dienst sein, wenn das geht.
Das ist mir völlig egal, hat überhaupt keinen Einfluss.
Also im Sinne der Kopplung stört es mich dann so darüber nachzudenken, dass man sagt, dieser Routing-Slip wäre jetzt bald dezentral weniger gekoppelt.
Aber man kann es tun.
Das wäre für mich immer noch, aber trotzdem Orchestrierung, wäre eine andere Art, das zu implementieren.
Damit du aber implizit jetzt sagst, also eigentlich sagst, ich brauche sowieso einen Prozess als Gesamtprozess, eben die Kontoeröffnung.
Und so die Aussage, ich habe eigentlich nur die Wahl, entweder das als Routing-Slip mitzuschicken oder ich muss es halt zentral koordinieren in einer Workflow-Engine.
Was du damit in Abrede stellst, ist, dass man den Prozess so modellieren kann, dass er eben nur aus den Einzelschritten besteht und die Gesamtsicht halt einfach dann sozusagen verschwindet.
Also nicht, dass ich sage, okay, ich bin halt Schufa, ich kenne den nächsten Schritt und ich weiß nicht, was sonst noch irgendwie passiert.
Muss ich auch nicht wissen, muss ich auch nicht einen Routing-Slip haben, sondern ich habe irgendwie nur mich und den nächsten Schritt und der Schritt, von dem ich irgendwie aufgerufen werde.
Also eben sozusagen inherente Dezentralisierung, weil ich fachlich halt dieses Gesamtmodell nicht brauche, über den gesamten Kontoeröffnungsprozess.
Also ich würde das an sich, also zumindest am Anfang, den Satz, den du gesagt hast, fast unterschreiben.
Ich würde sagen, man will diesen Prozess halt haben und man braucht ihn nicht zwingend.
Ich kann das anders implementieren.
Ich glaube, man will ihn eigentlich haben.
Warum?
Weil ich bei solchen Ende-zu-Ende-Prozessen halt tatsächlich auch die Verantwortung zum Beispiel klar haben will.
Also auch rein organisatorisch, weil ich möchte da einen Owner haben.
Vielleicht ist unsere Brille ganz oft ein Process-Owner, aber du kannst das ja auch im Domain-Driven-Design.
Also du brauchst eine Ownership für diese Komponente.
Die hat eine gewisse Verantwortung.
Was muss sie denn eigentlich hinkriegen?
Und dann sage ich dir, du musst Kontoeröffnungen hinkriegen und die müssen übrigens morgen drei Tage schneller sein, weil die Competition ist auch drei Tage schneller.
Und die müssen irgendwie so und so eine Quote haben.
Die brauchen irgendwelche Absprungquoten.
Wo gehen die Leute eigentlich verloren?
Wie oft können wir nachfragen?
So etwas kommt ja auf diesen Owner zu.
Und um das quasi sauber auch ownen zu können, will ich an dieser Stelle diesen Gesamtprozess auch verstehen, will ich ihn auch modellieren, will ich ihn auch monitoren können, will ich ihn auch überwachen können, will ich auch eingreifen können, will ich auch im Operating sozusagen den wiedersehen und sagen, hier laufen gerade 100 Prozesse wild.
Also die laufen da alle auf und dann sehe ich das und dann sehe ich auch, was ist vorher passiert, warum sind die Daten krude und das sind nicht irgendwelche Dead Messages, die sich irgendwo auftun und keiner weiß, wo die herkommen.
Also ich sage nicht, dass man das so bauen muss, aber ich glaube, man will es eigentlich so bauen, weil man genau diese Ownership dann auch machen kann sozusagen.
Und mein Punkt war dann immer oder ist noch der, das widerspricht sich dann überhaupt nicht mit so Domain Driven Design Modularisierung oder Microservices oder auch Entkopplung, wenn man das glaube ich einfach sauber schneidet und die Granularitäten auch sauber schneidet.
Und dann lasse ich gleich wieder zu Wort kommen, eine Sache noch.
Ich fand das Beispiel schön, wenn wir beim Account Opening oder Kontoeröffnung bleiben, weil Sam Newman hatte das in einem Buch, habe ich auch länger mal mit ihm diskutiert.
Er hat da auch eventgetriebene Teile drin.
So was wie sein Beispiel ist hier so ein Bonusprogramm, Loyalty Points Bank.
Da soll ich noch eingetragen werden, wenn ein Kunde neu aufgenommen wurde.
Und das will ich doch jetzt nicht jedes Mal den Kundenservice anpacken, wenn ich mir irgendwie ein neues Programm ausdenke, wo ich diesen Kunden eben eintrage.
Und da zum Beispiel bin ich ja hundertprozentig dabei.
Also ich würde zum Beispiel in so einem Kunden-Onboarding-Prozess unterscheiden zwischen dieser Phase, für die ich als Komponente Kunden-Onboarding halt auch wirklich zuständig bin.
Und das sind typischerweise die Prüfungen.
Das sind dann auch wirklich die Anlage in den Kernsystemen und so ein, zwei Dinge.
Und dann bin ich auch fertig.
Und dann darf ich gerne Events erzeugen und darf gerne sagen, hier wurde ein neuer Kunde angelegt.
Und dann können andere auch losgehen ohne meine Kontrolle, ohne dass ich davon weiß und was daraus machen.
Was so ein bisschen impliziert, dass Events grobgranularer sozusagen sind als Prozesse.
Also ein Prozess würde dann eben in diesem Ansatz am Ende vielleicht mal ein Event losschicken.
Muss nicht so sein.
Also typischerweise schicken, ich würde mal sagen, eine Handvoll Events schickt so einen Prozess schon.
Der kann ja auch zwischendurch so meilensteinmäßig, jetzt ist irgendwas passiert, so ein bisschen was will ich halt die Umwelt auch wissen lassen.
Weil das ist so das andere Ding, was ich nämlich auch glaube, sobald ich Events erzeuge, die sind ja auch eine Schnittstelle, die schmeiße ich irgendwo hin und dann darf jemand darauf reagieren.
Und das habe ich ja eben genau nicht mehr unter Kontrolle.
Das heißt, aus einer Wartungsperspektive, wenn ich mir dieses System in zwei, drei, vier Jahren angucke und will dieses Event halt wegnehmen, verändern, was auch immer, da muss ich ja erst mal verstehen, was da eigentlich passiert.
Und das ist gar nicht so trivial.
Und deswegen will ich wahrscheinlich im ersten Schritt sparsam sein mit Events, die ich, das ist ja Public API, ist immer schlecht zu ändern.
Aber typischerweise habe ich schon so eine Handvoll, die ich dann eben auch ausfülle.
So was aber eigentlich bedeutet, dass du im Kern sagst, ich will halt diese fachliche Entität, diesen Prozess halt irgendwie haben, weil du sagst, es gibt halt jemanden, der dafür zuständig ist.
Und ich glaube, ein ganz wichtiger Punkt, den du halt nennst, ist sozusagen auch diese Transparenz.
Also dass man halt irgendwie sagt, okay, was passiert denn innerhalb dieses Prozesses und dieses ganze Monitoring-Geraffe, was halt irgendwie nochmal eine andere Dimension ist.
Also das ist ja nicht Modellierung und Systementwurf, sondern tatsächlich irgendwie sehen, was macht das System eigentlich.
Genau, aber auch auf einem grafischen Modell.
Das ist einfach sehr wichtig.
Genau, also, wie soll ich sagen, die Frage, und du hattest ja vorhin irgendwie gesagt, und das war ja auch so ein bisschen so ein Auslöser für diese Episode, dass es halt sozusagen vollständig kompatibel mit Domain-Driven-Design ist.
Da liegt jetzt so ein bisschen die Frage in der Luft, naja, aber also nicht Domain-Driven-Design, da gibt es ja immer nur Kontexte.
Dann gibt es halt diese Kontexte, diese ganzen Geschichten rund um Strategic Design.
Dann gibt es irgendwie taktisches Design.
Und also meines Wissens nach gibt es halt kein Pattern, was halt sagt, der Business-Prozess.
Und es gibt auch, ich wüsste auch nicht, wo es sozusagen reingehören würde.
Also wir würden ja jetzt über eine Koordination innerhalb, als wenn es eine Koordination innerhalb eines Bauern und Kontextes wäre, müsste es halt eben im taktischen Design sein.
Da gibt es sowas nicht.
Wenn es halt übergreifend wäre, hört sich ein bisschen danach an, als wäre es halt eher nicht so.
Also vielleicht ist das zu grobgranular.
Dann müsste es halt im Strategic Design sein.
Ist da irgendwie eine Lücke oder wie erklärst du dir das?
Oder nehme ich was falsch wahr?
Ich würde zwei Sachen dazu sagen wollen.
Also das eine, also eben auch das Domain-Driven-Design kennt eigentlich dieses Process-Manager-Pattern.
Ich freue mich nicht, wo das genau verankert ist, da ich jetzt zu lange nicht mehr in die DDD-Bücher reingeguckt habe.
Aber der Process-Manager ist eigentlich was, was vielleicht nicht in dem DDD-Buch hier von Eric Evans drinsteht.
Das weiß ich jetzt ehrlich gesagt nicht, aber in der Community dort auf jeden Fall viel diskutiert wird.
Aus einer reinen DDD-Brille, ja, das passiert eigentlich innerhalb eines Bauern und Kontextes in einer Domäne.
Also wenn du dir diese hexagonale Architektur anguckst, wäre dann einfach quasi die Workflow-Engine nochmal so eine Capability, die ich habe, sodass ich meine Domain-Logik innerhalb dieses Dings auch mit BPMN ausdrücken kann, statt mit anderem Code.
So würde ich sagen, passt das in DDD.
Und wenn ich dann quasi integrieren muss, weil ich eben andere Services brauche, dann ist das einfach, ja, ich rede halt mit anderen Kontexten.
Das kann ich ja tun, so oder so.
Zum Beispiel eben über Events, wie du sagtest.
Zum Beispiel.
Oder einfach über Request-Response, also Commands.
Warum nicht?
Geht ja auch.
Ja, ich überlege gerade.
Also damit haben wir eigentlich irgendwie, glaube ich, dieses Thema mit der zentralen und dezentralen Kontrolle diskutiert.
Das war, glaube ich, irgendwie sehr hilfreich.
Darf ich noch eine Sache sagen?
Ja, sehr gerne.
In der Praxis tatsächlich erlebe ich es aber echt selten, dass das auf dieser Ebene wirklich dann gelebt wird.
Also tatsächlich, weil du sagtest, oder es ist nochmal extra, passiert es außerhalb.
Also wir haben nicht wenige Kunden, die tatsächlich diesen Praxis-Layer als eigenen Praxis-Layer sehen und etablieren.
Das kommt jetzt, würde ich sagen, nicht unbedingt aus einer Solution-Architecture oder aus einer Architektenbrille raus.
Das kommt fast eher aus einer Business-Architecture-Brille raus.
Und da ist es einfach so ein plakativ schöner Layer.
Und dann sind Prozesse, gerade so Ende-zu-Ende-Geschäftsprozesse schon so ein bisschen was Eigenes in dieser Welt.
Das funktioniert schon auch sehr gut.
Also ich will mich dem nicht wehren.
Meine It-Depends-Brille ist immer so ein bisschen zu gucken, wo man so steht im Unternehmen.
Also auch so gedankenmäßig.
Und dann geht das meiner Ansicht nach sehr, sehr gut mit DDD zusammen.
Aber es geht tatsächlich auch gut als eigener Layer zusammen.
Also das halte ich beides für einen total gangbaren Weg.
Mit gewissen Unterschieden dann.
Ja, also fair.
Und ich meine der Hinweis, dass sozusagen Geschäftsprozesse Geschäftsprozesse sind und dass die halt irgendwie da draußen in der Realität existieren und dass es so eine gute Idee ist, die halt irgendwie als solcher zu modellieren, ist ja total nachvollziehbar.
Insbesondere, wie du gesagt hast, weil es eben etwas ist, wo ich halt Menschen habe, die halt dafür verantwortlich sind, die dann halt dieses Artefakt haben und eben auch sehen können, wie dieses Artefakt in der IT-Welt funktioniert und wie gut das halt funktioniert.
Und das ist, finde ich, total nachvollziehbar.
Und wie gesagt, das ist so etwas, was so ein bisschen vielleicht im, also mindestens halt im blauen Buch nicht vorkommt.
Aber also deswegen ist es ja eben gut, vielleicht darüber zu reden, dass es halt eine Ergänzung sein kann.
Damit ist halt auch so ein bisschen, habe ich das Gefühl, diese Frage beantwortet, die wir hier aufgeschrieben haben.
Von wegen, die Abfolge der Aktivitäten ändert sich doch nicht.
Das heißt also, ich muss vielleicht diesen Prozess, es ist sozusagen nicht so spannend, diesen Prozess hinzumalen, damit man ihn irgendwie ändern kann.
Weil du, also du hast damit ja irgendwie gesagt, naja, es ist eine Transparenz, es ist ein Artefakt, was irgendwie eher so Anforderungen erfüllt und vielleicht ist die Änderbarkeit gar nicht dann der wichtigste Punkt.
Wobei, ja doch, also nicht der einzige.
Also natürlich ist Monitoring und Sichtbarkeit, also auch Monitoring extrem wichtig.
Aber diese Änderbarkeit, also auch diese Diskussion habe ich halt sehr häufig.
Ich glaube, dass es nicht so ist, dass Prozesse, auch Geschäftsprozesse sind nicht mehr stabil.
Vielleicht ist es so am besten ausgedrückt.
Also wir haben so viel Veränderung heute.
Von einmal technischen Möglichkeiten, also AI vorneweg, aber auch was ich alles, an digitaler Transformation, an IT-Modernisierung.
Also man kann ja diverse Programme raussuchen, wo alle Unternehmen gerade fahren, die alle darauf abzielen, eigentlich auch wirklich Geschäftsprozesse in ihren Grundfesten mal sauber zu rütteln.
Noch dazu kommen ja auch, dass Geschäftsmodelle gar nicht mehr so stabil sind.
Also selbst auch in etablierten Branchen schneidet sich das um.
Ich mache irgendwie neue Zulieferer, baue mir da andere Sachen zusammen, Open Banking, weiß ich nicht was.
Also sprich, ich glaube nicht daran, dass Geschäftsprozesse so stabil sind, wie wir irgendwie das vor 10 oder 20 Jahren einfach, wie sie da wahrscheinlich auch waren, wo wir dann sagten, naja, aber der Prozess, der ist doch stabil, und wir machen immer noch das Gleiche.
Da glaube ich nicht mehr so dran.
Also von dem her finde ich das trotzdem wichtig, dieser Änderbarkeit.
Ja, okay.
Also das ist ja eine Aussage über die Änderung der Fachlichkeit.
Man könnte jetzt noch eine Frage stellen, die ja damit sozusagen im Zusammenhang steht.
Also das Ziel von Softwarearchitektur und Modellisierung ist ja eigentlich, irgendwie Änderungen zu begrenzen.
Und was du jetzt irgendwie sagst, ist, naja, wir müssen halt auf dieser eher grobgranularen Ebene dann tatsächlich irgendwie Änderungen vollziehen, eben auf dieser Business-Prozess-Ebene.
Ist das eine Niederlage von Modellisierung sozusagen, nicht?
Nein, nein, aber wir müssen das ja anders ausdrücken.
Ziel von Softwarearchitektur ist ja eigentlich, die nötigen Änderungen zu minimieren, um die notwendigen fachlichen Änderungen zu ermöglichen.
Und ich muss halt einfach fachliche Änderungen zulassen.
Und dann muss ich Änderungen im System machen.
Also das geht einfach nicht ohne.
Das wäre schön, vielleicht macht das irgendwann der Co-Pilot, aber da sind wir noch lange nicht.
### Politische Aspekte

Und das heißt, ich muss diese Änderungen ermöglichen und das zu wenig Aufwand.
Und da hilft eben, glaube ich, genau dieser Prozess, weil ich sage, wenn ich auf der Prozessebene, klar, wenn ich meinen Datenband tausche, hilft mir das nichts, aber wenn ich auf der Prozessebene Änderungen machen will, fachlich, dann hilft mir das, dass ich das an dieser Stelle machen kann und dann eben auch nicht fünf Systeme angucken muss, die alle irgendwie mal diese Nachrichten in die Hand nehmen.
Sondern ich kann vielleicht das auf dieser einen Stelle begrenzen.
Also immer wenn ich Prozessänderungen habe, wird das genau einfacher.
Also das macht diese Architektur dann sozusagen.
Genau, also der Florian hat bei YouTube geschrieben, ich würde sagen, es gibt in Capital Letters ja den Geschäftsprozess, in der Regel fachlich sowieso, BPM, BPMN hilft mir erstmal nur, diesen leicht zu modellieren und zu verstehen.
Ich glaube, das ist eine gute Zusammenfassung mit dem, was du gesagt hast.
Dann schreibt er weiter, bei BPM bekommt man, meiner Meinung nach, die Orchestration, das Treiben des Prozesses sowieso, sowie die Geschäftstransparenz zur Laufzeit und im Business Activity Monitoring praktisch geschenkt.
Passt, glaube ich, auch zu dem, was du gesagt hast.
Und dann schreibt er weiter, bei Choreography, zum Beispiel Venture in Architecture ohne Orchestrator, muss die Steuerung und Prozesstransparenz anderweitig sichergestellt hergestellt werden.
Was, glaube ich, auch zu dem passt, was du gesagt hast.
Genau, dann passt das sozusagen soweit.
Wir sind so ein bisschen am Ende der Zeit.
Wie probiere ich es aus, wäre so die letzte Frage sozusagen.
## Probe und Implementierung

Machen.
Nein, also ich empfehle es immer einfach tatsächlich, auch wirklich mal auszuprobieren, mal ein bisschen damit spielen.
Das ist ja wieder das Schöne als Techie, das macht ja dann auch ein bisschen Spaß.
### Erste Schritte

Ihr könnt einfach bei uns, commoner.com, dann könnt ihr das zum Beispiel einfach runterladen.
Und dann haben wir so Get Started Guides, je nachdem, wo ihr steht.
Wenn ihr programmieren wollt, gerne mit Spring.
Einfach mal ein bisschen was machen.
Also ihr könnt auch SARS machen, wenn ihr gar nicht runterladen wollt, dann solltet ihr eigentlich in einer halben Stunde da was am Laufen haben und ein bisschen spielen.
Perfekt.
Dann würde ich sagen, haben wir es soweit?
Oder hast du noch Themen, die du sprechen wollen würdest?
Also viele, aber da haben wir ja keine Zeit mehr.
Nein, ansonsten, wen noch was interessiert, auch immer gerne auf mich zukommen.
Tatsächlich interessieren mich die Themen alle im Herzen sehr, von dem her freue ich mich immer über gute Diskussionen.
Genau, ich packe deinen Link zu deinem Mastodon Account, deinem Blue Sky Account und zu deinem LinkedIn nochmal in die Notes.
Und da kann man dich dann ja auch ansprechen.
So ist es.
Genau, perfekt.
Dann würde ich sagen, vielen Dank.
Schönes Wochenende.
Und wie gesagt, Dienstagabend um 19 Uhr, ich hätte nochmal nachgeguckt, haben wir dann eben IT in 2034.
Und wir haben tatsächlich einen längeren Planungshorizont.
Das heißt, am 20. geht es dann mit Ralf, dem Stefan und André zum Thema und mit der Moderation von Lisa zum Thema, was denn nun eigentlich AI für uns bedeutet und was wir damit irgendwie so anfangen können, wenn wir da so einen netten Launchable haben.
Der Auslöser war, dass Stefan und André einen Kommentar losgeschickt hatten, wo sie dann gesagt haben, AI ist eigentlich underhyped und ich hatte ja gesagt, es sei overhyped und das werden wir jetzt endgültig ausdiskutieren.
Gut, dann, wie gesagt, vielen Dank.
Ja, danke, dass ich da sein durfte.
Bis dann.
Tschüss.
So, und damit sind wir raus.
Lass mich kurz nochmal...