# Folge 242 - Generative AI Meets Software Architecture mit Ralf D. Müller

## Zusammenfassung

### Generative KI für Software-Projekte
In der Episode diskutiert Ralf D. Müller, wie er ein reales Software-Projekt mit Hilfe eines generativen KI-Modells (LLM) erstellt hat. Das Projekt fokussiert sich auf die Entwicklung eines Linters für ASCII-Doc, ein Tool zur Überprüfung der Dokumentationssyntax.

### Agentic-Workflow
Ein zentrales Konzept des Projekts ist der Agentic-Workflow, bei dem das LLM eine Reihe von Funktionen (Function Calls) aufrufen kann, um Code zu generieren, Tests auszuführen und Diagramme zu erstellen. Außerdem erklärt Ralf die einerseits spannende, andererseits potenziell verwirrende Selbstkorrekturfähigkeiten des LLMs.

### Automatische Regelgenerierung
Das LLM generierte nicht nur Regeln für den Linter, sondern half auch beim Testen und der architektonischen Dokumentation. Dies geschah durch ein Test-getriebenes Vorgehen, bei dem das LLM Iterationen durchführte, um fehlerfreien Code zu produzieren.

### Herausforderungen bei der Qualitätssicherung
Es wurden Bedenken hinsichtlich der Qualität der automatisch generierten Anforderungen, Tests und Regeln geäußert. Obwohl das LLM in vielen Fällen zu erstellen schien, was sinnvoll war, bleibt die Herausforderung, den generierten Code und die annähernde Logik dahinter vollständig zu verstehen.

### Doc- und Code-Generierung
Die Ergebnisse des Projekts, darunter auch Diagramme und Architekturdokumentation, zeigten eine Mischung aus brauchbarem und verwirrendem Inhalt. Ralf und Eberhard besprechen die Auswirkungen solcher Dokumentationen auf die menschliche Kommunikation in Entwicklungsprozessen.

### Zukünftige Möglichkeiten
Abschließend wird betont, dass trotz der beeindruckenden Ergebnisse, ein Mensch immer noch eine wichtige Rolle im Überprüfungsprozess spielt, um Missverständnisse und Fehlausgaben zu vermeiden. 

## Key Takeaways
1. Ralf D. Müller hat ein Projekt zur Entwicklung eines Linters für ASCII-Doc mittels generativer KI (LLM) implementiert.
2. Der Agentic-Workflow ermöglicht es dem LLM, diverse Funktionen auszuführen und dabei iterativ zu lernen und sich selbst zu korrigieren.
3. Die Qualität der generierten Anforderungen und Tests war sowohl beeindruckend als auch fraglich; das LLM musste mehrfach überprüft werden.
4. Es bestehen Herausforderungen hinsichtlich des Verständnisses von generiertem Code und der Aufrechterhaltung der Qualität in der Generierung von Anforderungen.
5. Generierte Architekturdokumentationen können für menschliche Benutzer sowohl nützlich als auch verwirrend sein.
6. Die Rolle des Menschen bleibt entscheidend im Überprüfungsprozess, auch wenn generative KI beachtliche Ergebnisse liefert.

## Wichtige Fragen
1. Wie funktioniert der Agentic-Workflow bei der Interaktion mit dem LLM?
2. Welche Regeln wurden für den ASCII-Doc-Linter generiert, und wie kam es zu diesen Regeln?
3. Wie lässt sich die Qualität des generierten Codes und der Dokumentation verifizieren?
4. Welche Rolle spielt menschliches Feedback im Prozess der Entwicklung mit generativer KI?
5. Inwiefern kann die generative KI die Art der Softwareentwicklung und Dokumentation in Zukunft beeinflussen?
6. Ist es sinnvoll, sich auf generierte Tests zu verlassen, und wie können die Tests verifiziert werden?

## Glossar
- **ASCII-Doc**: Eine Dokumentationssprache, die verwendet wird, um technische Dokumentationen zu schreiben.
- **Linter**: Ein Tool, das den Quellcode auf stilistische und syntaktische Fehler überprüft.
- **LLM (Language Model)**: Ein KI-Modell, das Text versteht und generiert, basierend auf vorhergehenden Daten und Konversationen.
- **Agentic-Workflow**: Ein Workflow, bei dem ein Agent (z.B. ein KI-Modell) Aktionen autonom ausführt und selbst Entscheidungen trifft.
- **PlantUML**: Eine Open-Source-Tool, das es ermöglicht, UML-Diagramme aus textueller Beschreibung zu erstellen.