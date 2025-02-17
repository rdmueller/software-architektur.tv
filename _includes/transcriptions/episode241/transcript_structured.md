# Folge 241 - Domain-Driven Design - Ein vollständiges Beispiel 2/2 Hallo, ich bin Eberhard Wolff.
Freitags mache ich oder Lisa Moritz einen Livestream zum Thema Software-Architektur, oft zusammen mit Gästen.
Dieser Podcast ist das Audio des Streams.
Weitere Folgen, Sketchnotes und vieles mehr findet ihr unter software-architektur.tv.
## Einleitung zum Thema Domain-Driven Design

So, dann herzlich willkommen zu einer weiteren Episode zum Thema Domain-Driven Design, ein durchgängiges Beispiel.
## Hinweis auf Training zu Domain-Driven Design

Ich habe noch einen Hinweis.
Es gibt dieses Training Domain-Driven Design saniert Legacy.
Das ist ein Nachmittag am 16.12. über Socratoria.
Das ist auch nicht besonders teuer.
Wenn euch also dieses Thema mit Domain-Driven Design interessiert, insbesondere der Umgang mit Legacy, das ist eine Möglichkeit, darüber nochmal was mit bei mir tatsächlich ganz praktisch zu erfahren.
Also wir machen da praktische Übungen und reden halt nicht nur darüber, sondern machen es eben auch.
Und das ist nochmal eine gute Ergänzung für das, was wir hier sehen.
Weil wie gesagt, hier sehen wir eben nicht, wie man mit Legacy umgeht.
## Taktisches Design im Domain-Driven Design

Gut, das Erste, worüber ich tatsächlich sprechen möchte, ist das Thema mit dem taktischen Design.
Das ist auch so ein bisschen so die Bruchstelle zum letzten Mal.
Wir haben letztes Mal sehr grob über das Ganze gesprochen.
Also, wie teile ich ein System auf in bauende Kontexte, wie baue ich, welche Zuständigkeiten haben Teams und so weiter und so fort.
Und das ist hier jetzt eine ganz andere Ebene.
Das ist die Ebene von so tatsächlich Klassen und warum jetzt taktisches Design.
Also taktisches Design sind ein paar objektorientierte Konzepte.
Und es macht total viel Sinn, gute objektorientierte Systeme zu bauen.
Dafür hilft genau taktisches Design.
So, und die Patterns können wir jetzt durchgehen.
### Definition von Entities

Das erste Pattern ist eine Entity.
Das ist irgendetwas, was eine Identität hat.
Also eine Person hat eine Identität.
Das heißt, wenn es jetzt den Eberhard Wolf nochmal gäbe, also da gibt es jetzt eine vollständig identische Kopie, die also so aussieht, wie ich, die da wohnt, wo ich wohne und nicht so weit identisch ist.
Das ist trotzdem eine andere Person.
### Unterscheidung zwischen Entities und Value Objects

Die kann ich irgendwie unterscheiden.
Und das bedeutet, dass hier eben tatsächlich die Dinger eine Identität haben.
Eine Person hat eine Identität, ein Produkt hat eine Identität, solche Geschichten halt.
Und davon grenzen sich ab sowas wie Value Objects, also zum Beispiel einen Wert wie zwei Euro oder zwei Meter.
Zwei Meter sind halt zwei Meter und es ist relativ egal, ob diese zwei, also zwei Euro sind zwei Euro.
Das heißt also, das sind tatsächlich Dinge, die eben nur sich durch den Wert unterscheiden.
## Domäne Events im Domain-Driven Design

So, dann gibt es Domäne Events.
### Bedeutung von Domäne Events

Das sind nämlich Sachen, die halt bei Domänen ExpertInnen, für die halt irgendwie relevant sind.
Also irgendwas hat, ist passiert in der Vergangenheit.
Darüber hatten wir ja letztes Mal schon gesprochen.
Das ist auch etwas, was bei Event Storming beispielsweise eine Rolle spielt.
Das sind also Dinge, die ich da jetzt irgendwie auch als Klassen umsetzen kann.
So, vielleicht noch zwei generelle Dinge.
Der eine generelle Hinweis ist, das, was wir hier sehen, ist jetzt so, dass wir im Wesentlichen Abhängigkeiten von oben nach unten haben.
Das heißt, das hier sind tatsächlich Basisdinge, die halt auf nichts anderes, von nichts anderem abhängen.
Und die andere Sache ist, wir reden halt über ein richtiges objektorientiertes Konzept.
Das heißt, die Dinge, die wir hier sehen, haben Logik.
Also wenn ich jetzt irgendwie sage, ich kann irgendwie mit, ich habe zum Beispiel zwei Euro, ich kann irgendwie Geldbeträge zum Beispiel summieren und ich kann die versuchen zu runden und was auch immer ich da sonst noch machen kann.
Das sind halt Dinge, die ich jetzt an diesem Value Object beispielsweise modellieren würde.
Das sind also Dinge, die tatsächlich Logik enthalten.
## Aggregates und Aggregate Roots

So, darauf aufbauend gibt es dann auf der nächsten Schicht diese Aggregates.
Die sind so, dass sie aus mehreren verschiedenen Dingen zusammengesetzt sind.
Deswegen sind sie auch etwas höher.
Das heißt also, es gibt Entities und Value Objects, die sind halt in Aggregates zusammengefasst und da gibt es so eine Aggregate Route, das jetzt dafür zuständig ist, dort die Konsistenz zu gewährleisten.
Das heißt, wenn ich jetzt zum Beispiel eine Bestellung habe und ich füge in diese Bestellung irgendetwas ein, was ich gerne bestellen möchte, dann wird das zum einen eingefügt und zum anderen wird dafür gesorgt, dass eben der Gesamtbetrag der Bestellung entsprechend angepasst wird.
Dann ist das Ding halt in sich konsistent und das Aggregate Route sorgt dann eben dafür, dass genau diese Änderung sozusagen automatisch stattfindet.
### Konsistenz innerhalb von Aggregates

Was eben bedeutet, dass innerhalb von Aggregates Konsistenzbedingungen synchron durchgesetzt werden. Über Aggregate Grenzen hinweg nicht unbedingt synchron und ich kann Aggregates auch benutzen, um sie halt im Netzwerk zu replizieren.
Dann habe ich da auch Eventual Consistency, das heißt also alle Kopien des Aggregates werden dann schlussendlich, Eventual bedeutet schlussendlich, nicht eventuell, sondern schlussendlich werden die halt irgendwie konsistent werden.
Das ist deswegen interessant, weil eine Überweisung beispielsweise ändert halt zwei Konten und jetzt könnte man denken, na das will ich jetzt irgendwie konsistent haben und was Domain-Germany-Design sagt ist, nee, das Konto in sich ist konsistent.
Da wäre also jetzt zum einen eben der Betrag richtig, ich habe irgendwie nach der Überweisung 240 Euro und zum anderen ist die Überweisung da tatsächlich auch verbucht oder nichts von beiden.
Aber die Konten, die können irgendwie dann inkonsistent sein, was übrigens auch genauso ist, wie die Realität irgendwie aussieht.
Also wenn ich jetzt Geld überweise, ist das für einige Zeit irgendwo zwischen diesen beiden Konten, also das Geld ist einige Zeit verloren, so nehme ich zumindest an, das ist also das, was hier irgendwie sozusagen eine Rolle spielt.
Was eben auch bedeutet, dass Bonn und Kontexte, die ja grobgranularer sind, nicht etwa in sich gesamt konsistent sind, sondern eben Aggregates konsistent sind.
Genau, das besteht eben aus Entities, also meine einzelnen Buchungen wären eben beispielsweise irgendwelche Entities und Wertobjekten, der Kontostand beispielsweise wäre so ein Wertobjekt.
Dann habe ich Repositories, die geben mir die Illusion einer Kollektion von Aggregates, die dann halt im Speicher scheinbar steht, aber in Wirklichkeit in der Datenbank ist.
Das ist halt auch ein konzeptionelles Ding und was ich da besonders spannend finde, ist, dass Repositories eben auch die richtigen, fachlich richtigen Anfragen implementieren.
Das heißt also, ein Repository wird nicht sagen, ich gebe dir Zugriff auf irgendwelche beliebigen Objekte, sondern das Repository wird sagen, okay, ich habe jetzt eben die Möglichkeit, ein Konto nach zum Beispiel Kontonummer zu finden, vielleicht auch nach dem Namen des Kontoinhabers und dem Geburtsdatum, aber nicht anhand des Kontostandes, weil das irgendwie fachlich überhaupt keinen Sinn macht.
Das würde jetzt bedeuten, dass das Repository nur die fachlichen Anfragen exponiert, was, glaube ich, ein ganz interessantes Designkonzept ist, weil eben so etwas wie zum Beispiel GraphQL sagt, ich kann beliebige Anfragen stellen, Repository sagt, das macht eigentlich keinen Sinn, wir wollen nur die fachlich korrekten Anforderungen.
Dann gibt es Factories.
## Factories im Domain-Driven Design

Factories erzeugen komplexe Value-Objects oder Aggregates.
Sehr umgegangen auf For-Pattern braucht man, glaube ich, nicht viel drüber zu sagen.
Wenn ein Konstruktor nicht reich ist, benutze ich eine Factory.
## Services und Geschäftslogik im Domain-Driven Design

Und darüber sind dann Services.
Services sind die Dinge, wo ich Geschäftslogik nicht sinnvollerweise in einem Aggregate oder Entities unterbringen kann.
Es gibt Geschäftslogik, die übergreifend ist, über verschiedene Aggregates.
Die Überweisung beispielsweise ist etwas, wo ich zwei Aggregates habe.
Jetzt kann ich schlecht einem Konto zuordnen, also baue ich das wahrscheinlich in ein Service.
Damit ist hier auch klar, wie das funktioniert.
Ich sage, ich habe Logik, die bringe ich in einer dieser Klassen unter.
Es ist nicht so, dass Entities beispielsweise logikfrei sein sollten.
## Alternativen zu taktischem Domain-Driven Design

Jetzt ist die Frage, das ist etwas, was sich insgesamt durch diesen Talk so zieht.
Ich finde es immer wichtig, Alternativen zu benennen.
Wir haben jetzt taktisches Domain-Domain-Design.
Jetzt ist die Frage, kann ich auch nicht taktisches Domain-Domain-Design umsetzen?
### Funktional Programmierung als Alternative

Eine Möglichkeit ist es, das funktional zu machen.
Das ist ein seiteneffektfreier, funktionaler Kern.
Das heißt, ich habe keine Entities, keine Aggregates.
Wenn ich ein Entity ändere, dann hat das einen Seiteneffekt.
Das Ding hat ja einen Zustand.
Das Konto hat einen Kontostand beispielsweise.
Das bedeutet, dieser Zustand ändert sich.
Das ist offensichtlich ein Seiteneffekt oder eine Wirkung.
Bei funktioneller Programmierung kann ich so etwas nicht haben.
Bei funktionaler Programmierung hätte ich einen Kern, der sagt, ich berechne aus einem Zinssatz den neuen Kontostand.
Aber es ist dann die Aufgabe des Systems rundherum, dafür zu sorgen, dass dieser Seiteneffekt erzeugt wird.
Dass dieser Information gespeichert wird.
Ich hätte einen Kern, der sagt, das ist der neue Kontostand.
Dann hätte ich irgendwo um diesen Kern herum etwas, was dafür sorgt, dass das System in die Datenbank gespeichert wird. Über das Thema habe ich vor einiger Zeit mit Mike Sperber gesprochen.
Tatsächlich ist das schon mehr als ein Jahr her.
Da haben wir darüber diskutiert, wie eine funktionelle Architektur aussehen soll.
Mike ist jemand, der sich sehr stark damit beschäftigt hat.
Da haben wir uns die ESR-KUBI-Beispielaufgabe angeguckt.
Da kann man über dieses Thema genau reden.
Was es noch an Alternativen gibt, ist, wenn ich weniger komplexe Systeme habe.
Die Prämisse für dieses Set von Patterns ist, ich habe komplexe Geschäftslogik.
### Transaction Script als einfaches Konzept

Wenn ich ein System habe, das Daten von A nach B kopiert, und ich baue jetzt ein Repository, Aggregates, Entities, Value Objects usw.
Dann ist die Frage, ob das wirklich schlau ist.
Ich investiere viel Aufwand, diese Sachen zu bauen.
Aber den Vorteil, dass ich dort objektorientierte Möglichkeiten habe, meine Logik zu strukturieren, davon habe ich wenig, weil ich keine Logik habe.
Dafür ist eine Alternative so etwas wie ein Transaction Script.
Ein Transaction Script sagt, ich bearbeite einen Request aus der Präsentationsschicht direkt und habe da Datenbank-Code drin.
Ich habe einen HTTP-Request, der in mein System reinkommt.
Dann sage ich, insert into meine tolle Datenbank-Tabelle irgendeinen Wert.
So etwas ähnliches ist ein Table Model, wo ich sage, es gibt ein Objekt, was eine Datenbank-Tabelle repräsentiert.
Das hat den Vorteil, dass ich all diese Schichten nicht habe und relativ problemlos sagen kann, wenn das von der HTTP-Schicht kommt, dann ändere ich genau das in der Datenbank.
Das sehe ich auf einen Blick.
Das geht dann natürlich massiv schief, wenn ich dort eine komplexe Logik habe, weil die müsste ich da reinfriemeln.
Das macht wenig Sinn.
Hier habe ich auch den Vorteil, dass ich die Datenbank-Anfragen optimieren kann.
Ich kann handoptimierte Queries da reinbauen und irgendwelche tollen Dinge konstruieren, ohne dass ich da viel Aufwand habe.
## Beispiel eines E-Commerce-Systems

Gehen wir mal das Beispiel durch.
Das Beispiel, das wir hier hatten, war ein E-Commerce-System.
Das heißt, wir würden uns jetzt irgendeinen von diesem Bauen in Kontexten herausnehmen.
Ich habe mir jetzt den Bauen in Kontexten herausgenommen mit der Delivery.
Das ist das Ding, was sagt, ich möchte den Klicker verschicken.
Wie verschicke ich denn nun tatsächlich diesen Klicker?
Oder wenn ich etwas billig finde, das iPhone.
Das ist sogar noch teurer.
Das will ich vielleicht noch mal anders versichert verschicken.
Das ist das, was ich hier jetzt entscheiden möchte.
Das heißt, ich habe irgendwelche Logik und fange jetzt an und sage, ich habe hier eine Entity.
Also ich habe ein Paket.
Ich habe eine Adresse.
Das ist ein Wertobjekt.
Die Simon von Utrechtstraße, wo die Swaglab GmbH sitzt.
Das ist eben ein Wert.
Das ist keine Identität in diesem Fall.
Und das zusammen habe ich in so einer Lieferung.
Das heißt, in dieser Lieferung steht jetzt drin, dieses Paket geht an diese Adresse.
Vielleicht sind da auch noch solche Informationen drin, wie welche Waren sind denn eigentlich in dem jeweiligen Paket drin.
Das ist so, nehme ich jetzt an, kompliziert zu bauen, dass ich dafür eine Factory brauche.
Und ich habe auch so ein Delivery Repository, wo ich jetzt sagen kann, gib mir mal alle Pakete für diesen Kunden.
Das wäre etwas, was ich vielleicht fachlich motivieren kann, die ich gerne in diesem Wagen haben möchte.
Das wäre auch etwas, was mich fachlich motivieren kann und so weiter und so weiter.
## Wichtigkeit der Logic und Geschäftsprozesse

Alexander schreibt gerade, ich bin ein großer Fan von DDD und ich finde, dass viel zu wenig darüber gesprochen wird, wo man DDD nicht einsetzen sollte.
Gut, dass es hier erwähnt wurde.
Vielen Dank.
Andere Sacrifices, was ich jetzt haben kann, ist zum Beispiel ein Kunde.
Und da hätte ich jetzt auch irgendwelche Informationen.
Vielleicht hat er mir ein Set von Adressen, wo er typischerweise Sachen hinschickt oder was auch immer.
Sondern dann hätte ich hier ein Service, der jetzt sagt, okay, ich schätze eben eine Lieferung.
Also ich sage, für diesen Kunden möchte ich gerne diese Lieferung haben.
Und das bedeutet, dieses Ding sorgt dann dafür, dass diese Lieferungen entstehen, braucht Zugriff auf den Kunden.
Das kann ich also schwer jetzt dem Kunden oder der Lieferung geben.
Die Lieferung hätte jetzt solche Sachen wie, sag mir mal, wie dein Wert ist.
Sag mir mal, ob du versichert bist, solche Geschichten.
Und diese übergreifende Logik wäre jetzt eben in so einem Service.
Und ich habe hier dennoch so ein Event.
Die Lieferung ist irgendwie geschedult worden.
Das heißt, ich habe jetzt gesagt, das und das soll dann und dann geliefert werden.
Und darauf kann jetzt irgendjemand reagieren, wenn diese Person Lust dazu hat.
Ich habe darüber eine ganze Folge gehabt, wo ich das nochmal ausdiskutiert habe.
Die ist jetzt tatsächlich von diesem Jahr.
Und da spreche ich tatsächlich eine ganze Stunde über diese ganzen Konzepte.
Und gehe da nochmal tiefer drauf ein.
Die Frage ist, wie ich das umsetze.
Und in gewisser Weise ist das, was wir jetzt hier diskutieren, so plain old Java Objects.
Also das ist eigentlich nur ein objektorientiertes Konstrukt, um irgendwie Logik aufzuteilen.
Und deswegen könnte das halt genug sein.
Was das bedeutet ist, ich habe hier keine besonderen technischen Anforderungen.
Also Entities will ich vielleicht noch speichern.
Das heißt, da habe ich vielleicht so etwas, dass ich eine Persistenzlösung haben möchte.
Vielleicht ist in den Repositories irgendwie auch eine Persistenzlösung drin, die das konkret umsetzt.
Aber im Wesentlichen habe ich hier eigentlich einfach nur ein objektorientiertes System.
Und es gibt sowas wie zum Beispiel X-Molecules, was für verschiedene Programmiersprachen die, die die Konzepte sozusagen direkt unterstützt.
Und das hat der gute Oliver Rothbaum auch beschrieben in einem Blogpost.
Und darüber haben wir dann irgendwie auch gesprochen.
Das heißt also, ich kann mit sowas wie J-Molecules jetzt sehr schön so ein System aufbauen.
Und dabei geht es halt zum Beispiel auch um Abhängigkeiten.
Also ich möchte jetzt gerne zum Beispiel, dass ein Service Aggregates nutzen kann.
Aber Aggregates sollten halt keine Services nutzen.
Das heißt, es gibt halt so Beziehungen, die sich halt aus diesen Patterns halt ziemlich direkt ergeben.
Bedeutet also, dass ich da eigentlich eben diese Abhängigkeiten habe.
Wie zum Beispiel, dass Services Aggregates benutzen dürfen.
Und da kann ich so Architekturmanagement-Werkzeuge verwenden.
Also die Architekturmanagement-Werkzeuge, darüber habe ich halt tatsächlich mehrere Episoden gehabt.
Ich verlinke das übrigens auch alles noch in den Shownotes.
Das sind so Werkzeuge, mit denen ich irgendwie sagen kann, okay, Services dürfen auf Aggregates zugreifen.
Aggregates dürfen auf Entities und Value Objects zugreifen und so weiter und so weiter.
Und dann werden eben diese Abhängigkeiten sozusagen durchgesetzt.
Das heißt also, ich habe halt einen Checker, der da drüber läuft und sagt, nee, das darfst du nicht.
Und da gibt es ganz unterschiedliche Werkzeuge.
Es gibt sowas wie Structure 101 oder so eine Graph, die das eher grafisch darstellen, die ich auch in den Bildprozess mit reinbekommen kann.
Es gibt zum Beispiel sowas wie ArcUnit, wo ich das als Teil des Unit-Tests habe.
Und wie gesagt, da gibt es halt eine große Auswahl und man kann sich da diese ganzen Werkzeuge sozusagen anschauen.
So, in dem Kontext möchte ich nochmal sprechen über das Thema Design-Level-Event-Storming.
Wir haben halt gesprochen über Big-Picture-Event-Storming bei der letzten Session.
Und Big-Picture-Event-Storming ist letztendlich sowas, dass ich eben Domäne-Events habe.
Domäne-Events habe und diese Domäne-Events, die schreibe ich halt irgendwie auf und kriege dadurch halt eine Information darüber, wie meine Domäne so im Wesentlichen funktioniert.
Und ich kann das benutzen, um zum Beispiel Bauern und Kontexte zu identifizieren.
Das heißt, ich habe solche Geschichten dort typischerweise wie, ich habe eine Bestellung entgegengenommen, das Ding ist jetzt irgendwie ausgeliefert, solche Sachen.
Und dann kann ich halt irgendwie sagen, bestimmte Funktionalitäten, also das Ausliefern und das Rechnungsschreiben ist vielleicht in unterschiedlichen Bauern und Kontexten.
Darüber haben wir letztes Mal gesprochen.
So, JudeRude schreibt, sollten die Value-Objects eigentlich nicht immutable sein und damit keine Logik haben?
Genau, die repräsentieren Werte und Werte sind unveränderlich.
Zwei Euro sind halt zwei Euro.
Ich kann nicht sagen, zwei Euro sind plötzlich zwei Euro und zehn Cent, sondern das ist eben ein Wert.
Was halt bedeutet, wenn ich jetzt zum Beispiel den Wert meiner Bestellung ändere, erzeuge ich dort ein neues Value Object.
Das bedeutet aber nicht, dass die Dinger keine Logik haben dürfen.
Also ich könnte jetzt zum Beispiel ja auch, wenn ich etwas runden möchte, einen Betrag runden möchte, kann ich zum Beispiel sagen, das ist halt eine Methode und die gibt ein neues Value Object zurück.
Und das alte Value Object ist dann eben auch noch da.
Sprich, die sind dann eben unänderbar.
Also sie haben halt irgendwie Wertsemantik.
Und auch sonst, also wie soll ich sagen, solche Sachen wie Vergleiche sind da vielleicht auch ein Thema.
Also wenn ich jetzt Meter vergleiche oder mich Geldbeträge vergleiche, vielleicht ist das irgendwie etwas, was ich da auch drin habe als Logik.
Von daher haben die halt auch Logik.
Das ist genau die Idee.
Christian Trutz schreibt, verwendest du zum Beispiel Spring Modulus, um Packages zu strukturieren?
Genau, sowas kann man beispielsweise dann verwenden, um so ein System halt auf dieser Package-Ebene zu strukturieren.
Gut, ich glaube, dann haben wir das Thema so ein bisschen erledigt.
Ich schaue noch mal kurz, ob hier noch was reinkommt.
Denn sonst würde ich halt tatsächlich mit diesem Design Level Event Storming weitermachen.
## Design-Level-Event-Storming

Wichtig ist bei dem Design Level Event Storming, sich noch mal zu vergegenwärtigen, worum es eigentlich geht.
Ich möchte gerne verstehen, wie die Geschäftslogik ist.
Und das will ich halt bei diesem Big Picture Event Storming, was wir beim letzten Mal diskutiert haben, grobgranular verstehen.
Und hier möchte ich es jetzt feingranular verstehen.
### Detail-Level im Design-Level-Event-Storming

Das heißt also, ich habe zum Beispiel ein Read-Modell.
Und ein Read-Modell ist etwas, wo ich jetzt zum Beispiel eine UI rankleben kann und sagen kann, okay, die zeigt halt irgendetwas an.
Dann habe ich irgendwelche Aktoren, also Menschen, die irgendwas machen und zum Beispiel ein Command rausgeben können.
Und entweder durch ein externes System oder durch mein eigenes System entstehen dann irgendwelche Events.
Also ich könnte zum Beispiel sagen, ich bin ein Kunde, ich bin also hier in Ekta.
Ich gebe das Command, ich will es jetzt gerne haben.
Also ich möchte gerne diese Bestellung abgeben.
Das geht an mein System.
Event, was rauskommt, ist Bestellung akzeptiert.
Dann könnte es sein, dass ich daraus eine Bestellung generiert habe, die ich mir anschließend anzeigen kann.
Und hier wäre jetzt vielleicht so eine Policy, die jetzt sagt, es entsteht irgendwie das nächste Command.
Also das ist so ein Automatismus.
Das heißt, wenn hier die Bestellung akzeptiert worden ist, könnte ich eine Policy haben, die jetzt sagt, okay, alles klar.
Dann werde ich jetzt irgendwie dafür sorgen, schreibt bitte eine Rechnung und sorge bitte dafür, dass irgendwie das Ding auch ausgeliefert wird.
So, das ist so die Idee.
Und dadurch komme ich jetzt in ein feingranulares Modell.
Also ich hätte halt in dem Big Picture Event Storming, was wir letztes Mal diskutiert haben, hätte ich halt nur das hier.
Also die Domain Events.
Hier habe ich jetzt noch viele, viele zusätzliche Informationen, die mir jetzt ein tieferes, besseres Verständnis darüber geben, was hier eigentlich passiert.
Und ich erinnere nochmal daran, das ist eben etwas, was wir jetzt mit Domänen-Experten zusammen erstellen wollen.
Und das Ziel ist also, die Domäne jetzt auf diesem Detail-Level, das ich halt für ein taktisches Domain-Domain-Design benötige, dass ich das eben auf dieser Ebene verstehe.
Und da ist jetzt kein, also ich würde sagen, offensichtlich gibt es kein triviales Mapping auf taktisches Domain-Domain-Design.
Sprich, das, was wir hier jetzt sehen, ist eine ganz andere Begriffswelt.
Also wir reden über Systeme, wir reden über Read Models, wir reden über UI.
Das sind alles Dinge, die in diesem taktischen Domain-Domain-Design nicht vorkommen.
Deswegen ist es vielleicht ganz spannend, nochmal zu schauen, wie ich das jetzt eigentlich mappe.
Und ich würde ein Command in taktischem Domain-Domain-Design erwarten, ist ein Methoden-Aufruf auf einem Aggregate oder auf einem Service.
Wenn ich also jetzt sage, ich möchte das gerne bestellen, dann würde ich halt erwarten, es gibt irgendwo eine Methode oder vielleicht auch mehrere Methoden.
Eine Methode würde ich sogar sagen, die jetzt irgendwie sagt, okay, ich bestelle jetzt dieses ganze Graffel für dich.
Und die ist jetzt in dem Fall wahrscheinlich in einem Service, weil ich im Rahmen dessen eine Bestellung erzeugen muss und verschiedene andere Dinge erzeugen muss.
Könnte aber für einfache Fälle auch in einem Aggregate sein.
So, dann habe ich eben das System.
Das wäre also jetzt mein Aggregate oder mein Service, wenn ich das Frank Granada sehe.
Da kommt jetzt ein Domänen-Event raus.
Das könnte ich direkt als Domänen-Event auch im taktischen Domain-Domain-Design umsetzen.
Das ist also etwas, wo tatsächlich diese Begrifflichkeit letztendlich identisch ist.
Dann habe ich ein Read-Modell und das ist letztendlich wieder ein Aggregate.
Das heißt, das Ding, wo ich hier das Command aufrufe und das Ding, was ich hier anzeige, kann aus meiner Sicht dasselbe Objekt sein.
In dem einen Fall benutze ich eben die Lese-Geschichten und in dem anderen Fall die Schreib-Geschichten.
Das ist, glaube ich, eine gute Praxis, die Methoden, die Zustand ändern, zu trennen von den Methoden, die mir eine Information über den Zustand geben.
Also ich habe entweder Methoden, die sagen, ich sage dir irgendwas über die Lieferung.
Was ist da drin an Produkten oder so?
Oder ich habe Methoden, die dafür sorgen, dass irgendetwas mit dieser Lieferung passiert.
Und dieses Read-Modell wäre dann der Teil des Aggregates, der tatsächlich diese Auskunft über diesen Zustand gibt.
Wir sprechen gleich noch über solche Sachen wie CQS.
Da würden wir tatsächlich jetzt das Read-Modell auch trennen und eben sagen, das sind andere Klassen, vielleicht sogar ein anderer Microservice.
Das ist eine Option.
Ich halte das persönlich nicht für zwingend.
Und hier sieht man eben genau eine der Möglichkeiten, die ich jetzt habe.
Ich kann mich jetzt als Architekt hinsetzen und kann sagen, wir haben einen relativ einfachen Fall.
Wir packen eben die Commands und das Read-Modell zusammen.
Oder ich kann sagen, aus irgendwelchen Gründen ist das kompliziert und ich will das eher trennen.
Vielleicht will ich die getrennt skalieren.
Dann mache ich ja CQS.
Das ist aber nicht zwingend.
Ich will hier ja nur verstehen, was die Menschen wollen.
Und dafür ist es vielleicht ganz interessant zu sehen, was ich hier eigentlich lesen möchte.
Und genau die Information bekomme ich aus dem Design Level Events Tomic raus.
Eine Policy wäre jetzt auch wieder etwas, wo auf ein Domain-Event reagiert wird.
Also irgendwelche Geschäftslogik, die dafür sorgt, dass zum Beispiel eben diese Rechnung geschrieben wird.
Das ist etwas, was eben auch wieder vielleicht in einem Aggregate oder in einem Service dann passiert.
Da, wo eben Geschäftslogik typischerweise ist.
Und damit bin ich eigentlich mit dem Thema sozusagen soweit erstmal durch und kann weitermachen mit dem nächsten Thema.
Das ist diese Geschichte mit dem Events Sourcing.
Mal kurz sehen, dass ich die nächste Tabelle...
Genau, hier ist es. Ähm...
Hier ist ein bisschen...
Genau, wir haben noch so ungefähr Halbzeit.
Hier ist so ein bisschen jetzt...
Wie soll ich sagen?
Das ist ein weiteres Thema.
Events Sourcing und CQS sind irgendwie Möglichkeiten, wie ich bestimmte Dinge einfach umsetze.
Und die sind unabhängig von taktischem Domain-Design.
Ich werde, glaube ich, auch gleich nochmal sagen, wie ich dieses Thema insgesamt bewerte.
Ob das zwingend ist oder wie auch immer.
### Definition von Events Sourcing

Events Sourcing bedeutet, dass ich die Events, die zu einem bestimmten Zustand geführt haben, auch speichere.
Ich kann auch den Zustand selber speichern.
Offensichtlich muss ich das nicht unbedingt, weil ich kann aus den Events diesen Zustand ermitteln.
Und ich kann jetzt als System of Record, also das System, das tatsächlich jetzt das Verlässliche sein soll, da kann ich entweder sagen, das ist der Zustand oder die Events.
Das bleibt mir dann überlassen.
Das heißt, was ich jetzt machen kann, zum Beispiel mit irgendwelchen Bestellungen, ist, ich habe hier einen Event Store.
Und ich habe hier den Zustand.
Und jetzt habe ich hier eine Schnittstelle und irgendwelche Aufrufe, irgendwelche Nachrichten passen hier auf mich ein.
Ich rede also jetzt über ein System, was sich damit beschäftigt, irgendwas mit Bestellungen zu machen.
Hier kommt ein Aufruf rein, der sagt, diese Bestellung 42 soll jetzt ausgeliefert werden.
Das heißt, ich merke mir in dem Event Store, dass diese Bestellung 42 tatsächlich ausgeliefert werden soll und akzeptiert ist.
Und dann habe ich hier den Zustand, der jetzt sagt, die Bestellung 42 gibt es.
Dann kommt der nächste Aufruf, der sagt, okay, Bestellung 23 ist irgendwie da.
Und dann habe ich hier als Zustand eben auch die Bestellung 23.
Dann sage ich als nächstes, die Bestellung 42 ist gecancelt.
Das ist wieder ein Event.
Das merke ich mir jetzt wieder im Zustand.
Und dann sage ich, die andere ist ausgeliefert und das merke ich mir auch wieder im Zustand.
Das heißt also, ich habe hier jetzt ein System, was den Zustand speichert und außerdem die Events, die zu diesem Zustand geführt haben.
Bei einer Bestellung bin ich nicht sicher, ob das so wirklich, wirklich notwendig ist.
Bei einem Konto bin ich mir relativ sicher, dass das wirklich unbedingt notwendig ist.
Denn mich interessiert nicht nur, wie viel Geld ich gerade auf dem Konto habe, sondern auch, ob die letzten Überweisungen mir eingegangen sind.
Und das führt dazu, dass wir hier eben Systeme unterscheiden können.
Wir haben Systeme, die nur den Zustand abspeichern.
Ich könnte jetzt ein System haben, was sagt, die Bestellung 42 ist ausgeliefert, Punkt.
Und ich könnte den Zustand on the fly errechnen.
Ich könnte z.B. den Kontostand ermitteln aus den Überweisungen und Transaktionen, die es bisher gab.
Oder ich kann den Kontostand speichern und außerdem die Events, die dazu geführt haben.
Und wenn ich diese Events speichere, dann ist es eben Events Hossing.
Da gibt es noch einen Hinweis, der mir wichtig ist.
Das ist eigentlich im Kern eine Persistenzstrategie.
Das heißt, die Frage ist, wie speichere ich mein Konto bzw. meine Bestellung?
Und ich kann jetzt sagen, ich speichere den Zustand und außerdem die Events, die dazu geführt haben.
Eine Persistenzstrategie sollte intern sein.
Das heißt also, wer auch immer jetzt zuständig ist für sowas wie Konten oder was auch immer ich da habe, sollte eben wählen, ob sie Events Hossing machen oder nicht.
Das bedeutet insbesondere, dass es nicht so sein sollte, dass die extern beobachtbaren Events dazu führen, dass ich meinen lokalen Zustand habe.
Und da gibt es tatsächlich, ich packe das nochmal in die Show Notes, da gibt es ein Video, wo ich gesagt habe, wenn ich in Kafka alle Events ablege und dann sage, okay, ich kann den lokalen Zustand von der Microsoft Services aus diesen zentralen Events im Kafka auch für die Kommunikation genutzt werden, ich kann diesen Zustand der Microsoft Services rekonstruieren, dann habe ich eigentlich einen Datenbankmonolithen.
Die Microsoft Services haben keine unabhängigen Datenmodelle, sondern die haben nur einen Cache für das, was eben in Kafka drin liegt.
Ich kann denen halt irgendwie ihre Datenbank wegziehen, dann sagen die, kein Problem, ich lese nochmal alle Events, ich habe das halt rekonstruiert.
Und das muss dazu führen, dass ich dort irgendwie eine hohe Abhängigkeit habe.
Und das ist ja etwas, was ich eigentlich gerne vermeiden möchte.
Deswegen finde ich das schwierig.
Ich verlinke da nochmal das Video.
Und es gibt da noch eine andere Geschichte.
Da muss ich nochmal den Artikel rausfinden.
Christian Städtler hat da mal einen Artikel drüber geschrieben, dass eben diese internen Events möglicherweise feingranularer sind, als das, was ich halt extern bekannt geben möchte.
Also wenn ich jetzt irgendwie sage, okay, ich bin halt dafür zuständig, dass sich ein Kunde, eine Kundin registriert, dann habe ich da halt solche Geschichten wie, hey, deine E-Mail-Adresse war nicht valide, hey, dein Personalausweis-Check hat nicht funktioniert.
Und das sind alles Dinge, die mich extern nicht interessieren.
Da will ich halt nur sagen, dieser Mensch ist jetzt irgendwie sozusagen validiert.
Und da ist auch wieder die Geschichte, die internen Events sind was anderes als die externen Events, deswegen will ich das eben trennen.
So, was bedeutet das jetzt?
Kann ich sowas wie eine, also ich habe ja so eine Lieferung, die Lieferung ist aus dem Lager rausgenommen worden, ist dann halt in einen Lastwagen reingepackt worden, ist dann ausgeliefert worden und die Kundin hat irgendwie gesagt, habe ich auch bekommen.
Jetzt ist halt irgendwie die Frage, kann ich diese Lieferung oder so einen Event-Store überhaupt modellieren?
Wahrscheinlich nicht, weil das interessiert mich genau.
Mich interessiert, wer wann was damit gemacht hat, weil ich dann später sagen kann, okay, du hast aber gesagt, das ist angekommen oder das ist halt bei dir im Lastwagen gewesen, wo ist denn das hinbekommen?
Umgekehrt ist es aber eben so, dass ich mir bei dieser Lieferung nicht sicher bin, ob ich eigentlich den Zustand der Lieferung berechnen möchte.
Also was habe ich jetzt davon, wenn ich den Zustand nicht speichere?
Ich würde hier also jetzt neben dem Event-Store noch reinschreiben, ja, diese Lieferung ist halt angekommen und Kundin hat gesagt, ist alles fein.
Also ich habe einen Zustand, der hat gesagt, ist halt abgeschlossen, erfolgreich abgeschlossen, fertig.
Und ich kann dann halt auf der anderen Seite, wenn jemand sich dafür interessiert, wie es dazu gekommen ist, irgendwie diese Events rausziehen und kann die halt sozusagen anzeigen.
Das ist eine fachliche Diskussion.
Eigentlich sage ich, das ist die Art und Weise, wie ich sowas fachlich typischerweise modellieren möchte.
Und das ist etwas, wo ich eben gerade nicht den Zustand rekonstruieren möchte, was halt häufig so ein bisschen so als Vorteil eigentlich verkauft wird von Events raus.
CQRS, das ist so der andere Ansatz.
Das ist diese Command Query Responsibility Separation, wo ich also lesen und schreiben irgendwie separiere.
Und das würde jetzt so funktionieren, dass ich eine Command Queue habe.
Da sind also irgendwelche Commands, z.B. eine Rechnung.
Dann habe ich einen Command Händler, der z.B. vielleicht dafür sorgt, dass wenn eine Rechnung erzeugt wird, auch gleich bezahlt wird.
Dann ist da eine Datenbank, da werden die Rechnungen z.B. hinterlegt.
Und dann gibt es einen Query Händler, und der ist irgendwie getrennt.
Und da kann ich z.B.
Rechnungen lesen.
Die Commands habe ich vielleicht noch in einem Command Store liegen.
Und das wäre jetzt so insgesamt mein Modell.
Hier also tatsächlich dieses Read Modell.
Das wäre das hier, was der Query Händler benutzen würde.
Und hier hätte ich das Modell, wo ich tatsächlich Dinge halt ändere oder diesen Teil, was irgendwie nicht das System ist, was eben Commands entgegennimmt aus dem Design Level Event Storming.
Wenn ich das so baue, bedeutet das, dass das Modell zum Schreiben hier durch die Commands und das von den Queries eigentlich dasselbe ist, weil das ist ja eine gemeinsame Datenbank.
Habe ich dann überhaupt was davon?
Ja, ich habe etwas davon, weil diese Query Händler z.B. ein Read Replica benutzen können.
Ich kann jetzt irgendwie sagen, ich baue das System so, wie es hier steht.
Ich habe jetzt die Query Händler.
Die Query Händler benutzen ein Read Replica der Datenbank.
Ich kann das Lesen stärker skalieren.
Das ist so ein bisschen glaube ich der Vorteil, der hier im Wesentlichen entsteht.
Diese beiden Teile sind eben z.B. unabhängig skalierbar.
Ich kann jetzt eben den Command Händler und den Query Händler in zwei unterschiedlichen Microservices ausführen.
Und das führt eben auch dazu, dass ich bei diesem Pattern nicht so sicher bin, wie oft ich es eigentlich benutzen wollen würde.
Denn es macht nur dann Sinn, wenn ich etwas für Skalierung zumindest, nur dann Sinn, wenn ich sage, ich will diesen Query Händler Bereich unabhängig vom Schreiben skalieren.
Und da glaube ich, muss ich schon in signifikante Skalierungshöhen kommen, damit ich da sozusagen Gewinn habe.
Ich kann auch etwas anderes machen.
Ich kann sagen, der Query Händler hat einen Snapshot.
Und diesen Snapshot baue ich durch Eventsourcing-Geschichten zusammen.
Das würde jetzt also bedeuten, dass ich hier diese Commands habe.
Hier wird irgendwas an Logik gebaut.
Also ich sage z.B., dass halt eben die Bezahlung stattfindet.
Und dann habe ich hier so ein Eventsourcing hin zu der Datenbank für den Snapshot.
Und dort würde ich jetzt jedes Mal, wenn eine Rechnung erstellt wird, wird dort dann eben dementsprechend ein neuer Eintrag in diese Datenbank gemacht.
Das wird noch stärker dadurch entkoppelt.
Das könnte z.B. sinnvoll sein für so etwas wie Statistiken.
Also für Statistiken will ich jetzt vielleicht wirklich ein getrenntes Lesemodell haben.
Da will ich auch andere Informationen haben, irgendwie eher Summen.
Und das ist etwas, wo ich dann vielleicht wirklich ein SQS-Ding bauen will.
Da habe ich einmal sozusagen die Daten, die halt sowieso Bewegungsdaten sind.
Und dann habe ich die Daten eher für die Statistik.
Das würde jetzt wahrscheinlich auch bedeuten, dass Statistiken vielleicht sogar ein anderer Bonded Context sind, mit einem eben komplett anderen Datenmodell.
Also vielleicht muss ich eben Statistiken anders modellieren und für den Rest CQS zu benutzen.
Also wenn ich hier sage, ich will halt nur ganz normal sozusagen Rechnungen lesen, da bin ich mir nicht so sicher, ob das sinnvoll ist, wobei man bei Rechnungen noch argumentieren kann.
Es ist vielleicht gar nicht so schlecht, wenn ich sozusagen ein Nur-Lese-Modell habe, weil Rechnung kann ich eben nur einmal schreiben und erstellen und danach kann ich sie nur noch lesen.
Das ist eben tatsächlich ja fachlich korrekt.
Also ich kann nicht sagen, ups, ich habe mich bei dieser Rechnung vertan, lass mich sie mal kurz ändern, sondern ich muss dann sagen, ich habe mich bei der Rechnung vertan, lass mich die Rechnung stornieren, ich schreibe eine neue.
Das ist so ein Modell, was irgendwie sagt, okay, nicht Queries erlauben, sind halt getrennt, arbeiten auf dem Read-Replika und ich habe das andere Ding, was diese Rechnung erzeugt, das ist vielleicht gar nicht schlecht, um genau diese Policy halt auch strikt durchzusetzen.
Also vielleicht ist es aus so einer fachlichen Idee nicht so schlecht.
So, Typhonix schreibt, das Wording in Snapshot ist eigentlich im Events-Hosting-Kontext was anderes, damit die Daten beim Aufbauen einzigartiger zwischengespeichert werden.
Eigentlich sind doch eher Projektionen gemeint, oder?
Ja, kann gut sein, dass ich mich da sozusagen in der Benahmung vertan habe.
Guter Punkt, danke für den Hinweis.
Also genau, Snapshot bezieht sich vielleicht eben tatsächlich eher auf ein Aggregate, guter Punkt.
Ich habe zu dem Thema auch eine ganze Episode gemacht, da diskutiere ich das Thema auch nochmal tiefer.
Da kann man sich das eben anschauen.
## Layering im Domain-Driven Design

Und damit kommen wir jetzt zu diesem Thema, wo es beim letzten Mal schon Interesse gab.
Und ich bin etwas schneller sozusagen geplant und das ist die Geschichte mit den Layern.
### Entwicklung von Layering-Architekturen

Da ist erstmal der Hinweis, das ist tatsächlich ein Pattern aus dem ursprünglichen blauen Domain-Domain-Design-Buch.
Also es gibt Layering als Pattern in diesem blauen Domain-Domain-Design-Buch und damit ist eben gemeint, dass ich sage, ich habe hier die UI, die Logik und die Persistenz.
Und solche Schichten haben halt immer Abhängigkeiten von oben nach unten.
Das heißt, ich sage, die UI benutzt die Logik, die Logik benutzt die Persistenz und das ist eben genau diese Geschichte mit der Schichtung.
Für mich ist das prototypische Modell für eine Schichtung eigentlich sowas wie dieser Netzwerk-Stack, wo ich eben unten ein physisches Layer habe, also Ethernet oder Wi-Fi.
Dann habe ich eben IP darüber, dann habe ich TCP darüber und dann irgendwelche Protokolle wie FTP oder HTTP.
Und das ist genau eben auch so eine Schichtung.
Also HTTP benutzt TCP oder UDP mittlerweile.
TCP und UDP benutzen IP.
IP benutzt dann eben, was auch immer ich hier gerade verwende, Ethernet oder Wi-Fi.
Und es gibt eben nur die Abhängigkeit in dieser Richtung.
Ich erwähne das deswegen, weil diese Schichtung, glaube ich, aus einer technischen Perspektive oft Sinn macht.
Hier reden wir ja aber darüber, wie wir Fachlichkeit strukturieren.
Jetzt ist eben die Frage, also beim Netzwerk-Layering ist es beispielsweise so, dass dadurch, dass ich diese physische Schicht habe, kann ich jetzt relativ trivial von Ethernet auf Wi-Fi wechseln oder von Wi-Fi auf Mobilfunk.
Dadrüber ist das eben genau verborgen.
Das heißt also, ich kann diese untere Schicht genau austauschen und der Rest des Systems bleibt davon unberührt.
Hier würde ich argumentieren, ist das nicht so richtig ein guter Grund, weil die Persistenz werde ich wahrscheinlich seltener austauschen.
Also ist dann die Frage, warum wir dieses Pattern doch sind.
Und was Eric da eben gesagt hat, ist, naja, ich separiere halt die Logik und habe die Persistenz halt an genau einer Stelle und dadurch baue ich das System so, dass es einfach zu verstehen ist.
Und tatsächlich ist es so, dass Domain-Domain-Design jetzt gar nichts über die UI sagt.
Also was Domain-Domain-Design halt sagt, ist, okay, wir haben Services, wir haben Aggregates, solche Geschichten, dass wir eine UI haben, die das benutzt.
Das ist irgendwie klar, aber wir sagen nicht, wie die strukturiert sein sollte.
Da gibt es ja auch Möglichkeiten, sowas halt irgendwie zu strukturieren.
Und bei der Persistenz, naja, es gibt ein Repository als Pattern, aber das sagt auch noch nicht so wahnsinnig viel darüber aus, wie man das jetzt machen, genau so umsetzen möchte.
Und da gibt es eben, also wir haben eben zum Beispiel dieses Transaction Script gesehen, da gibt es halt durchaus auch andere Möglichkeiten.
Und das bedeutet, dass eigentlich der Kern dieses Patterns nur sagt, wir haben die Logik separiert.
Die Logik ist auch tatsächlich der Bereich, wo Domain-Domain-Design ganz viel darüber sagt.
Also Entity, Aggregates und so weiter, das sind alles Dinge, die in dieser Logik-Geschicht drin sind.
Und wir separieren das von der Persistenz, damit ich nicht, wenn ich über die Logik nachdenke und nachschaue, was da eigentlich gerade passiert, irgendwie genervt werde von SQL-Statements, die halt damit erstmal nichts zu tun haben oder JPA-Geschichten, die halt damit erstmal nichts zu tun haben, sondern das habe ich halt irgendwo anders und analog.
Es ist eben auch so, dass ich die UI davon getrennt habe.
Und auf diesem Abstraktions-Layer oder auf dieser Abstraktionsebene ist hexagonale Architektur eigentlich auch eine Lösung für dasselbe Problem.
Also hexagonale, sprich Eric hätte halt in seinem Buch auch sagen können, wir sprechen ja nicht über Layer, sondern wir sprechen über hexagonal.
Dass er das nicht gemacht hat, hängt damit zusammen, dass eben Domain Driven Design, wenn ich mich nicht irre, etwas älter ist als hexagonale Architektur.
Also sprich, damals war irgendwie diese Dreischicht-Architektur mit UI-Logik und Persistenz das, was man typischerweise gemacht hat.
So, was ist jetzt bei hexagonaler Architektur anders?
Clean Architecture ist da zum Beispiel auch sehr ähnlich.
Da sage ich halt, die Geschäftslogik exportiert irgendwelche Ports.
Also ich habe die Geschäftslogik, die hat jetzt hier zum Beispiel einen Port, um Notifications rauszuschicken und dann habe ich Adapter, die diese Ports implementieren.
Also ich habe zum Beispiel einen E-Mail Adapter.
Das heißt also, ich sage hier in der Business-Logik, ich habe eine Notification-Schnittstelle und der E-Mail Adapter kann die jetzt implementieren.
Und hier sind zum Beispiel irgendwelche Business-Events, die ich jetzt an die UI rausgebe.
Hier ist irgendwie ein Admin-Ding, was ich an die Admin-UI rausgebe und hier ist die Persistenz.
Und da habe ich einen Datenbanken-Adapter, der diese Persistenz umsetzt.
So, was ich dadurch erreicht habe, ist, dass in allen Fällen die Abhängigkeit von außen, von dem Datenbanken-Adapter beispielsweise zur Persistenz geht.
Der implementiert also das, was hier die Persistenz gerne haben möchte oder hier von der Admin-UI hin zur Admin oder vom E-Mail Adapter hin zur Notification.
Das ist bei Layering ja gerade nicht so.
Bei Layering ist es eben so, dass die Logik die Persistenz benutzt.
Das heißt also, Logik hängt von Persistenz ab.
Hier hängt alles von der Logik ab, auch die Implementierung der Persistenz der Datenbanken-Adapter.
Für mich ist das relativ ähnlich zu diesem Dependency-Immersion-Prinzip, wo ich also sage, wenn ich etwas benutze, dann kann ich halt auch die Schnittstelle hier irgendwie definieren und dann ist die Abhängigkeit genau umgekehrt.
Also die Business-Logik verwendet den Datenbanken-Adapter, ist aber softwaretechnisch nicht davon abhängig, sondern gibt ihm die Schnittstelle vor, die der Datenbanken-Adapter implementieren muss.
Das heißt also, Datenbanken-Adapter implementiert Persistenz-Port.
Dadurch ist die Abhängigkeit von draußen von diesen Adaptern hin zu den Ports.
Und das führt zum Beispiel, also erstmal erreiche ich damit dasselbe Ziel wie die Slayering.
Also nicht, was Eric ja sagt, ist, ich möchte halt gerne die Logik separieren von einem anderen.
Das erreiche ich hiermit auch, vielleicht sogar noch ein Tick besser, weil ich eben nicht diese Abhängigkeit zur Persistenz habe.
Und ich habe außerdem den Vorteil, dass ich das Zeug besser testen kann, weil der Geschäfts-Logik-Kern von jeder Art von Technologie frei ist.
Also das heißt, wenn ich die Schichtung habe, dann ist es in der Logik so, dass ich tatsächlich irgendwie von der Persistenz abhänge.
Vielleicht muss ich irgendwelche Exceptions fangen, die die Persistenz wirft.
Hier ist es so, dass eben der Datenbanken-Adapter von der Business-Logik abhängig ist.
Der definiert, was sozusagen zu erwarten ist und wie die Schnittstelle aussehen soll.
Und dann wird der Datenbanken-Adapter das implementieren.
Das heißt also, die Persistenz weiß nichts davon.
Die Business-Logik weiß nichts davon, was hier genau passiert.
Und das führt zu einer besseren Testbarkeit, weil ich kann jetzt den Datenbanken-Adapter und alle anderen Adapteuren durch irgendwas im Test ersetzen.
Ich kann jetzt sagen, da gibt es ein Ding, was sich so verhält wie eine Datenbank.
Oder ich kann irgendetwas haben, was jetzt zum Beispiel die Notifications abfragt.
Die hat sonst, wenn wir jetzt E-Mails rausgehen.
Das heißt, ich kann mit dem Geschäfts-Logik-Kern getrennt in Isolation testen.
Und das ist, glaube ich, auch ein signifikanter Vorteil.
Ich habe eine Episode mit dem Warren Vernon gemacht.
Warren hat auch das Buch geschrieben, Domain-Domain-Design-Kompakt.
Eigentlich hatte ich erwartet, wir reden jetzt über Domain-Domain-Design.
Aber er hat dann ganz viel gesprochen über Ports and Adapters beziehungsweise hexagonale Architektur.
Und eine Sache, die dabei, glaube ich, total spannend war, war, dass Warren im Prinzip gesagt hat, na ja, ist das jetzt wirklich so viel komplizierter, eine hexagonale Architektur zu bauen?
Und das ist tatsächlich ein guter Punkt.
Also Layering sagt, ich habe diese drei Sachen separiert.
Und hexagonale Architektur sagt, ich habe diese, also nicht, bei Layering habe ich isoliert UI, Logik und Persistenz.
Und hexagonale Architektur sagt jetzt, ich habe diese drei Sachen isoliert und die Persistenz hängt von der Logik ab.
Also hier bei, sorry, hier bei, also wenn ich hier bin bei Layering, da wäre es halt so, dass die Logik die Persistenz verwendet und davon abhängig ist.
Hier ist es genau umgekehrt.
Hier sage ich also, die Logik kennt die Persistenz nicht, sondern umgekehrt, der Datenbank-Adapter implementiert diese Schnittstelle, die der Logik-Kern vorgibt.
In Bezug auf die UI ist es sowieso identisch, weil da ist es eben so, dass die UI die Logik verwendet.
Hier von oben nach unten gehen die Abhängigkeiten.
Das ist hier genauso.
Das heißt also, die UI kommt jetzt irgendwie und benutzt hier diesen Port.
Das heißt, da ist der Abhängigkeitsfall genauso.
Das heißt also, das Einzige, was sich tatsächlich ändert, ist halt dieser andere Abhängigkeitsfall bei dem Datenbank-Adapter.
Und relativ dumm gesagt, das kann ich halt erreichen, indem ich halt in der Geschäftslogik irgendwie diese Schnittstellen definiere.
Und ja, ich muss dann darauf aufpassen, dass es eben technologieunabhängig ist.
Aber das ist es dann eben auch.
Das heißt, eigentlich ist ein Punkt, wenn ich halt das separiere, ist der große Aufwand, ist da nicht mehr so ein großer Unterschied in Bezug auf Aufwand zwischen hexagonaler Architektur und Layering.
Und das fand ich einen ganz spannenden Gedanken, weil ja eben hexagonale Architektur so ein bisschen vielleicht den Ruf hat, kompliziert zu sein.
Und da ist, glaube ich, genau dieser Input halt interessant.
Und wie gesagt, die Alternative dazu wäre dann eben sowas wie ein Transaction Script, wo ich eben diese Schichtung nicht mache, wo ich also eben die Geschäftslogik nicht mehr so stark isoliere, einfach weil es halt zu wenig davon gibt oder gar keine.
Und da sollte ich vielleicht noch eine Sache hinzufügen.
Wenn ich dazu gezwungen bin, als Entwickler in ein System zu bauen, das keine Geschäftslogik hat, bedeutet das, dass ich auch nicht wahnsinnig viel Wert generiere, würde ich behaupten.
Und es kann sein, dass ich tatsächlich ein System dann baue, was nicht wirklich das Geschäftslogikproblem löst.
Also Kundin kommt und sagt, ich möchte gerne, dass ich folgende Daten sehe.
Okay, ist da Geschäftslogik?
Nein, ich will nur die Daten anzeigen.
Aber das ist wahrscheinlich nicht das, was diese Person wirklich will.
Was sie in Wirklichkeit will, ist, sie möchte jetzt entscheiden, wenn ich mir den Kunden angucke, kann ich halt entscheiden, ob das ein guter oder ein schlechter Kunde ist.
Dann ist es aber eigentlich so, dass es halt eine Geschäftslogik hinter steckt, die ich jetzt versuchen kann zu implementieren.
Also ich kann jetzt sagen, hey, das ist halt nach unserer Policy ein guter Kunde, weil der hat viele Sachen bestellt und wenig zurückgegeben.
Das bedeutet, wenn ich ein System baue, was nur Daten von A nach B transportiert oder nur Daten anzeigt, ist das möglicherweise eine vertane Chance, ein System mit mehr Geschäftslogik zu bauen.
Das heißt, das Thema mit dem Transaction Script ist die richtige Lösung, wenn ich wenig Logik habe.
Aber Vorsicht, vielleicht ist es halt nur so, dass die Logik vor mir versteckt worden ist.
Das bedeutet in der Zusammenfassung, ich habe das hier nochmal versucht aufzumalen und die ganzen Sachen in so einen Überblick zu bringen.
Und zwar von links nach rechts kommen immer mehr Details.
Das war etwas, was ich auch beim letzten Mal gesagt habe.
Also die Idee ist hier nicht, dass das ein Wasserfall ist, wo ich einmal durchlaufe, sondern ich arbeite auf unterschiedlichen Detailebenen.
Das Grobgranularste, was ich habe, ist Big Picture Event Storming.
Da kriege ich einen Überblick über das Gesamtsystem, über die Events, die da laufen.
Und ich kann dann darüber zum Beispiel entscheiden oder ein nächster Detailierungsschritt wäre zu sagen, was ist eigentlich meine Core Domain, was ist also das, worauf es ankommt.
Ich kann Strategic Design benutzen als Alternative zu Team Topologies.
Da sage ich, welche Teams verantwortlich sind und wer was wo macht.
Das ist etwas, ich weiß gar nicht, ob das detaillierter ist.
Also hier rede ich eigentlich über die Geschäftslogik bei dem Big Picture Event Storming.
Und hier sage ich, bei so etwas wie Strategic Design oder Team Topologies oder Core Domain, sage ich eigentlich, wie ich das aufteilen möchte auf Ebene von Teams.
Und die arbeiten dann eben an einem oder mehr umbauenden Kontexten.
Und dann kommen diese ganz konkreten Techniken, über die wir gesprochen haben, also Tactical Design, um eben einen bauernden Kontext tatsächlich zu implementieren und halt zu sagen, wie der umgesetzt wird.
Design Level Event Storming, um zu verstehen, was auf dieser Ebene die Anforderungen sind.
Ich kann so etwas benutzen wie Event Sourcing oder CQRS.
Wenn ich die dafür notwendigen Voraussetzungen habe, in dem Sinne, dass ich halt einen Vorteil davon generiere, wenn ich eben im Fall von Event Sourcing die Events speichere, beziehungsweise im Fall von CQRS, wenn ich den Schreib- und den Leseteil tatsächlich voneinander trennen kann.
Und dann gibt es eben Layers oder hexagonale Architektur.
Da habe ich jetzt auch ein Fragezeichen hintergesetzt.
Bei Event Sourcing und CQRS würde ich halt irgendwie behaupten, okay, das benutze ich halt dann, wenn es sozusagen passt.
Bei Layers oder hexagonal würde ich sagen, eins von den beiden Patterns sollte ich halt irgendwie anwenden, weil ich sonst eben am Ende die Logik und die anderen Sachen so sehr vermischt habe.
Judy Ruth schreibt noch, zusätzlich besteht Warn auf die Benennung Ports und Adapters anstatt hexagonale Architektur oder hexagonale Architektur.
Guter Punkt, ich erinnere das gar nicht.
Und tatsächlich ist das vielleicht auch ein Punkt, der hier ein bisschen unglücklich ist.
Also die hexagonale Architektur heißt eben hexagonal, weil der Business-Logik-Kern und das Drumherum sozusagen zufällig als Hexagon gemalt werden.
Und es ist tatsächlich so, dass Ports und Adapter die bessere Bezeichnung ist, weil das drückt glaube ich besser aus, worum es eigentlich geht.
Nämlich darum, diese Ports zu exponieren vom Geschäfts-Logik-Kern und dann Adapteuren zu haben drumherum, die das halt irgendwie entsprechend umsetzen.
Gut, dann haben wir es glaube ich tatsächlich soweit.
Ein Hinweis, nächste Woche, also wie gesagt, es gibt dieses Training rund um das Thema Domain-Design-Saniert-Legacy, das ist am 16.12.
Nachmittags, könnt ihr gerne dazukommen.
Ist glaube ich auch preislich moderat und ist eine gute Möglichkeit nochmal darüber zu reden, wie man Legacy mit DDD aufbaut.
Das andere ist, nächste Woche wird der Ralf mit dem Lars Röwekamp sprechen über das Thema Generative AI meets Software Architecture.
Und das wird um 15 Uhr sein, also Freitag 15 Uhr.
Das ist ein bisschen später als sonst üblich.
Und vielleicht wollt ihr da sozusagen wieder einschalten.
Ansonsten vielen Dank für die Aufmerksamkeit.
Vielen Dank auch für die Fragen und für die Kommentare.
Und dann würde ich sagen, wünsche ich schon mal allseits ein angenehmes und schönes Wochenende.
Bis dahin, vielen Dank.