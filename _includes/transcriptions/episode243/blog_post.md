# Folge 243 - Process Orchestration, BPMN und Workflows mit Bernd Rücker

In dieser Episode sprechen wir über ein sehr spannendes, aber oft missverstandenes Thema: Process Orchestration, BPMN (Business Process Model and Notation) und Workflows. Diese Konzepte sind von entscheidender Bedeutung für die Automatisierung von Geschäftsprozessen und die Effizienz moderner Softwarearchitekturen. Ich habe Bernd Rücker eingeladen, einen Experten auf diesem Gebiet, der uns durch die verschiedenen Aspekte dieser Themen führen wird.

## Unser Gast: Bernd Rücker

Bernd hat einen Ingenieurs-Hintergrund und ist ein leidenschaftlicher Enthusiast im Bereich Prozessautomatisierung. Vor vielen Jahren gründete er Camunda, ein Unternehmen, das sich auf BPM und Process Automation spezialisiert hat. Durch seine Arbeit hat er viele wertvolle Erkenntnisse darüber gewonnen, was in der Praxis funktioniert – und was nicht. Mit seiner Expertise in BPMN und Prozessautomatisierung werden wir darüber sprechen, wie sich diese Konzepte in die Software-Architektur integrieren lassen.

## Die Begriffswelt von BPMN und Process Orchestration

Um zu verstehen, wie BPMN und Prozessorchestrierung funktionieren, ist es wichtig, einige grundlegende Begriffe zu klären. Viele Menschen verwenden Begriffe wie Workflow Engine, Business Process Management (BPM) und Process Orchestration synonym, aber es gibt feine Unterschiede.

1. **Workflow Engine**: Dies bezieht sich oft auf eine Softwarekomponente, die die Durchführung und Automatisierung von Workflows unterstützt. Häufig wird dieser Begriff mit menschlichen Aufgaben und To-Do-Listen assoziiert.

2. **Business Process Management (BPM)**: BPM ist ein umfassender Begriff, der sich auf die Disziplin bezieht, die Geschäftsprozesse strukturiert, analysiert, verbessert und automatisiert.

3. **Process Orchestration**: Orchestrierung bezeichnet die Koordination verschiedener Schritte in einem Prozess. Es geht darum, die richtigen Aufgaben in der richtigen Reihenfolge auszuführen, unabhängig davon, ob diese Aufgaben von einem Menschen oder einem System ausgeführt werden. 

4. **BPMN (Business Process Model and Notation)**: BPMN ist eine standardisierte grafische Sprache für die Modellierung von Geschäftsprozessen. Es erlaubt uns, Prozesse visuell darzustellen und sie anschließend automatisiert auszuführen.

## Warum ist Process Orchestration so wichtig?

Um die Bedeutung von Process Orchestration zu verdeutlichen, ziehen wir ein Beispiel aus der Bankenbranche heran: Den Kontoeröffnungsprozess. Bei der Eröffnung eines neuen Kontos müssen verschiedene Schritte eingehalten und an unterschiedlichen Systemen ausgeführt werden – von der Website der Bank über interne Prüfungen bis hin zur Erstellung von Kontodaten. 

Um diesen Prozess zu automatisieren, sind zwei Hauptaspekte erforderlich:
- **Orchestrierung**: Die Koordination der Schritte und Aktivitäten im Prozess.
- **Automatisierung von Aufgaben**: Hierbei werden Aufgaben, die in der Vergangenheit manuell ausgeführt wurden, durch Systemaufrufe oder durch Benachrichtigungen und Aufgaben an Menschen ersetzt.

Die Orchestrierung sorgt zudem dafür, dass langlaufende Prozesse unterstützt werden, die oft auf Antworten von Dritten warten müssen. Hierzu wird Wartung und Persistenz in der Orchestrations-Engine benötigt.

## Der Platz von BPMN in der Software-Architektur

BPMN ist nicht nur eine visuelle Modellierungssprache; sie ermöglicht auch eine tiefere Integration in den Softwareentwicklungszyklus. Wenn wir eine BPMN-Notation verwenden, können wir sowohl den Prozess visualisieren als auch direkt die Logik hinter den einzelnen Schritten (Tasks) programmieren. Der Vorteil dieser Herangehensweise ist, dass wir Geschäftslogik direkt in den Prozess implementieren können, was wiederum die Trennung zwischen technischem und fachlichem Verständnis fördert.

## Die Grenze zwischen Integrations- und Geschäftsprozessen

Es gibt verschiedene Anwendungsfälle für Process Orchestration. Ein klassisches Beispiel sind Integrationsprozesse, bei denen wir verschiedene Systeme nahtlos miteinander verbinden. Hier spielt BPMN als Teil der Infrastruktur eine zentrale Rolle, da es eine grafische Darstellung bietet, die es einfacher macht, die Schritte und Logik zu verstehen.

Andererseits stehen Geschäftsprozesse, wie beispielsweise die vollständige Kontoeröffnung oder die Bearbeitung von Versicherungsanträgen, im Vordergrund. Hier ist die Prozessbeschreibung nicht nur ein technisches Artefakt, sondern auch ein wichtiges Werkzeug für das Management, das Monitoring und die Optimierung dieser Prozesse.

## Geschäftslogik: Wo gehört sie hin?

Bei der Diskussion über Process Orchestration erreichen wir oft die Frage, wie viel Geschäftslogik in den Prozess integriert werden sollte. Bernd erläutert, dass in Integrationsprozessen oft nur technische Logik vorherrscht, während Geschäftsprozesse tatsächlich auf Geschäftslogik basieren. Es ist wichtig, die richtige Balance zu finden: Zu viel Geschäftslogik kann die Flexibilität und Wartbarkeit des Prozesses beeinträchtigen.

Eine der Stärken von BPMN ist seine Fähigkeit, Geschäftsanforderungen visuell darzustellen – eine Funktion, die sowohl Entwicklern als auch Fachabteilungen zugutekommt. Wir können Prozesse so gestalten, dass sie effektiv sind, aber auch anpassbar bleiben, wenn sich die geschäftlichen Anforderungen verändern.

## Choreografie vs. Orchestrierung: Eine wichtige Unterscheidung

Ein wichtiges Konzept, das im Rahmen dieser Diskussion immer wieder auftaucht, ist der Unterschied zwischen Choreografie und Orchestrierung. Choreografie bezieht sich auf ein integratives, dezentrales Modell, bei dem Teile in einem Prozess auf Ereignisse reagieren, während Orchestrierung eine zentrale Steuerung und Koordination mehrerer Systembereiche impliziert.

Beide Ansätze haben ihre Vor- und Nachteile. Orchestrierung gibt uns die Kontrolle und Transparenz, während Choreografie Flexibilität und Unabhängigkeit zwischen den verschiedenen Komponenten bietet. Oft werden für verschiedene Anwendungsfälle kombiniert.

## Vorschläge zur Implementierung und Nutzung von Camunda

Bernd gibt abschließend einige praktische Hinweise für die Implementierung und Nutzung von Camunda und ähnlichen Tools. Es ist wichtig, die richtigen Schritte zu unternehmen, um ein erfolgreiches Projekt aufzubauen. Dazu gehört unter anderem:

- Die Schulung von Teams, um BPMN effektiv zu modellieren und zu nutzen.
- Die Definition klarer Rollen und Verantwortlichkeiten für die Prozessberatung und -modellierung.
- Die kontinuierliche Diskussion und Feedback mit Stakeholdern, um die Relevanz und Nützlichkeit der Prozesse sicherzustellen.

## Fazit und Ausblick

Die Themen Process Orchestration, BPMN und Workflows sind entscheidend für die Automatisierung und Effizienz moderner Geschäftsprozesse. Diese Konzepte ermöglichen es Unternehmen, flexibel auf Veränderungen im Markt zu reagieren und gleichzeitig die Qualität ihrer Dienstleistungen aufrechtzuerhalten. 

Mit Experten wie Bernd Rücker können wir ein tieferes Verständnis für die Integration dieser Konzepte in die Software-Architektur gewinnen. Der Austausch zwischen Fachabteilungen und der IT wird immer wichtiger, um die Geschäftsprozesse erfolgreich zu gestalten. 

Wir freuen uns auf weitere Diskussionen und würden uns freuen, Ihre Gedanken zu diesen Themen zu hören. Fühlen Sie sich frei, den Kontakt zu Bernd aufzunehmen oder unsere nächste Episode zu verfolgen!