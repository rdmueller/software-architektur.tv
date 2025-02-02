# Generative KI trifft auf Software-Architektur: Ein Praktischer Ansatz

In der modernen Software-Entwicklung gewinnt die Nutzung von Künstlicher Intelligenz (KI), besonders in Form von Generative AI, zunehmend an Bedeutung. In der neuesten Episode meines Podcasts habe ich mit Ralf D. Müller über seine Erfahrungen gesprochen, in denen er die Möglichkeiten von Generativer KI in einem realen Software-Projekt erkundet hat. Diese Episode befasst sich damit, wie KI zur Verbesserung der Software-Architektur eingesetzt werden kann und welche Herausforderungen und Chancen sich daraus ergeben.

## Der Ausgangspunkt: Ein Linter für ASCII-Doc

Ralf beschloss, ein Projekt zu starten, das auf einer realen Problematik basierte: Die Community beklagte sich, dass es seit Jahren keinen Linter für ASCII-Doc gab. ASCII-Doc, ein System zur Erstellung technischer Dokumentationen, benötigt Mechanismen, um sicherzustellen, dass die Erstellung von Dokumenten den gewissen Standards entspricht. Ein Linter, der Code auf Übereinstimmung mit vordefinierten Regeln überprüft, stellt genau diese notwendige Funktionalität zur Verfügung. Ralf erkannte die Möglichkeit, Generative AI zu nutzen, um diesen Linter zu erstellen.

### Der Agentic-Workflow

Ein wichtiger Bestandteil seiner Umsetzung war die Verwendung eines sogenannten „Agentic-Workflows“. Aber was ist das genau? Es handelt sich um einen selbstablaufenden Workflow, der es ermöglicht, verschiedene Rollen innerhalb des Prozesses zu definieren. In Ralfs Fall arbeitete er mit multifunktionalen LLMs (Large Language Models). Der LLM agierte nicht nur als Textgenerator, sondern konnte auch Programmcode ausführen und auf verschiedene Tools zugreifen. Diese Fähigkeit zur Interaktion mit externen Systemen erlaubte es der KI, auf Fehler zu reagieren und die generierten Lösungen iterativ zu verbessern.

## Der Entwicklungsprozess

Bei der Entwicklung des Linters gab es mehrere Schritte, die Ralf mit dem LLM umsetzte. Er gab dem Modell einige grundlegende Regeln zur Erstellung des Linters, wie zum Beispiel die Überprüfung der Überschrifts-Hierarchie. Das LLM erhielt dann die Anweisung, weitere Regeln zu entwickeln, was auf dessen Vorwissen zurückgriff. Es brachte die Intelligenz ein, die es hatte. Auf diese Weise konnte Ralf beobachten, wie die KI in der Lage war, die Regeln selbstständig zu erweitern und zu dokumentieren.

### Qualitätsanforderungen

Ein weiterer bemerkenswerter Moment war, als Ralf das LLM bat, Qualitätsaufstellungen für den Linter zu erstellen. Die KI entwickelte Szenarien, die sich nach den Anforderungen der Software richteten, wie etwa Performanz und Effizienz. Diese Qualitätsanforderungen waren jedoch auch eine Herausforderung, da die KI letztendlich keine Daten zur tatsächlichen Leistung des Linters hatte. Ralf merkte an, dass diese Situationen uns in der Software-Entwicklung immer begleiten werden, unabhängig davon, ob wir mit Menschen oder Maschinen arbeiten.

## Die Herausforderungen

Obwohl Ralfs Experiment vielversprechend war, gibt es mehrere Herausforderungen, die es zu bewältigen gilt. Die Qualität und Verlässlichkeit der von der KI generierten Dokumentation ist nicht immer gegeben. So stellte Ralf fest, dass die Anzahl und die Art der Qualitätsanforderungen, die die KI generierte, fragmentiert und oft nicht nachvollziehbar waren. Der Linter könnte beispielsweise verlangen, dass ein 1000-Zeilen-Dokument in weniger als einer Sekunde verarbeitet wird – eine Anforderung, die nach menschlichem Ermessen zumindest hinterfragt werden sollte.

### Verwechslung mit menschlicher Intelligenz

Ein zentrales Problem ist das Potenzial, generierte Anforderungen und Dokumentationen als gültig und verbindlich zu akzeptieren. Dies verursacht die Gefahr, dass wir uns bei der Entscheidungsfindung und Qualitätssicherung zunehmend auf die von der Maschine generierten Inhalte verlassen und nicht kritisch hinterfragen, wie wir es bei menschlicher Arbeit tun würden. Es ist entscheidend, dass wir bewusst mit diese Illusion umgehen, die Generative KI erzeugen kann.

## Die Zukunft der Software-Entwicklung

Trotz der Herausforderungen gibt es viele Chancen, die KI in unsere Software-Entwicklungsprozesse zu integrieren. Der Schlüssel liegt in der kritischen Betrachtung und der Kombination von menschlicher und maschineller Intelligenz. Ralf sieht die Zukunft der Software-Entwicklung in einer symbiotischen Beziehung zwischen Mensch und KI, in der wir beide voneinander lernen und uns gegenseitig unterstützen können.

### Fazit

Generative KI hat das Potenzial, die Art und Weise, wie wir Software entwickeln, grundlegend zu verändern. Der Versuch, einen Linter für ASCII-Doc mithilfe von KI zu erstellen, ist ein großes Experiment, das uns viele wertvolle Einblicke in die Möglichkeiten und Herausforderungen bringt, die mit der Einführung dieser neuen Technologie verbunden sind. Die Ergebnisse überzeugen, und obwohl wir auf viele Fragen, insbesondere zur Verlässlichkeit, noch keine endgültigen Antworten haben, sind wir auf einem vielversprechenden Weg. 

Insgesamt zeigt Ralfs Projekt, dass die Integration von Generativer KI in Software-Architektur nicht nur machbar, sondern auch äußerst spannend ist. Wir müssen jedoch wachsam bleiben und sicherstellen, dass wir die Qualität und Integrität unserer Produkte für die Zukunft aufrechterhalten.