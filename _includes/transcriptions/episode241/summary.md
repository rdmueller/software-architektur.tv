# Folge 241 - Domain-Driven Design - Ein vollständiges Beispiel 2/2

## Taktisches Design im Domain-Driven Design

In dieser Episode wird das Konzept des taktischen Designs innerhalb des Domain-Driven Design (DDD) vertieft. Es wird erklärt, wie ein System sinnvoll in Kontexte aufgeteilt werden kann und welche objektorientierten Konzepte dabei eine Rolle spielen. Wichtig sind hierbei Entities, Value Objects, Aggregate, Repositories, Factories und Services. 

### Schlüsselkomponenten im DDD

- **Entities**: Objekte mit einer eindeutigen Identität, die über ihren Zustand hinaus differenziert werden, z. B. eine Person oder ein Produkt.
- **Value Objects**: Objekte, die durch ihre Werte definiert sind und im Normalfall unveränderlich sind, wie z. B. Geldbeträge oder Maße.
- **Aggregate**: Eine Gruppe von Entities und Value Objects, die als einheitliche Einheit betrachtet wird. Der Aggregate Root sorgt für internal Konsistenz.
- **Repositories**: Abstraktionen, die eine Sammlung von Aggregates repräsentieren und den Zugriff auf diese steuern.
- **Factories**: Zuständig für die Erzeugung komplexer oder aggregierter Objekte, um einen klaren und verständlichen Konstruktionsprozess anzubieten.
- **Services**: Dienen der Implementierung von Geschäftslogik, die nicht zu einer bestimmten Entity oder einem Aggregate gehört.

## Normen der DDD-Architektur

Diskussionen über Alternativen zu DDD und Möglichkeiten zur Implementierung von funktionalen Programmiersprachen werden erwähnt. Die Relevanz der Aufteilung von Logik in die verschiedenen Schichten des Systems wird betont, und conclusively die Anwendung von Schichten im Design, wie die Trennung zwischen Command- und Query-semantik, wird verdeutlicht.

### Design Level Event Storming

Es wird darauf eingegangen, wie Event Storming genutzt wird, um die Geschäftslogik und Abläufe innerhalb der Domain zu verstehen. Der Prozess wird in zwei Hauptstufen eingeteilt: Big Picture Event Storming, das einen Überblick über die Events bietet, und Design Level Event Storming, das detaillierter in die Geschäftslogik einsteigt.

### Event Sourcing und CQRS

Event Sourcing wird als Persistenzstrategie definiert, bei der Ereignisse gespeichert werden, die den Zustand eines Objekts beeinflussen. CQRS (Command Query Responsibility Segregation) trennt Lese- und Schreiboperationen und ermöglicht damit eine verbesserte Skalierbarkeit und Wartbarkeit.

### Schicht-Architektur vs. Hexagonale Architektur

Es wird ein Vergleich zwischen einer traditionellen Schichtenarchitektur und der hexagonalen Architektur innerhalb von DDD angeboten. Letztere bietet mehr Flexibilität in der Integration von Technologien und ist leichter testbar, da die Abhängigkeiten umgekehrt sind.

## Key Takeaways

1. Taktisches Design ist essenziell für die Strukturierung objektorientierter Systeme in DDD.
2. Die klare Trennung zwischen Aggregates, Entities, Value Objects, Repositories, Factories und Services ist fundamental für ein wirksames DDD.
3. Event Storming ist ein effektives Werkzeug zur Visualisierung und Analyse von Geschäftsabläufen in DDD-Systemen.
4. Event Sourcing und CQRS sind fortgeschrittene Strategien, die je nach Architekturanforderungen verwendet werden.
5. Hexagonale Architektur bietet eine bessere Testbarkeit und Flexibilität als traditionelle Schichtenarchitektur.

## Wichtige Fragen in der Folge

1. Was sind die Unterschiede zwischen Entities und Value Objects in DDD?
2. Wie definiert man ein Aggregate und welchen Zweck erfüllt der Aggregate Root?
3. Was sind die Vorteile von Event Sourcing im Vergleich zur direkten Speicherung des Zustands?
4. Wie kann CQRS die Skalierbarkeit eines DDD-Systems erhöhen?
5. Warum sollte man hexagonale Architektur der traditionellen Schichtenarchitektur vorziehen?

## Glossar

- **Entities**: Objekte, die eine eindeutige Identität besitzen, und deren Gleichheit auf ihrer Identität basiert.
- **Value Objects**: Objekte, die durch ihre Werte definiert sind und unveränderlich sind.
- **Aggregate**: Eine Einheit aus Entities und Value Objects, die durch einen Aggregate Root verwaltet wird.
- **Aggregate Root**: Die Hauptentität eines Aggregates, die für die Konsistenz der inneren Objekte verantwortlich ist.
- **Repositories**: Schichten, die den Zugriff auf Aggregates und deren Persistenz abstrahieren.
- **Factories**: Muster zur Erzeugung komplexer Objekte.
- **Services**: Klassen, die Geschäftslogik darstellen, die nicht an eine bestimmte Entity oder ein Aggregate gebunden ist.
- **Event Sourcing**: Muster, bei dem Änderungen durch Ereignisse erfasst werden, die den Zustand eines Systems beeinflussen.
- **CQRS (Command Query Responsibility Segregation)**: Muster, das Lese- und Schreiboperationen trennt, um eine bessere Skalierbarkeit und Performance zu erreichen.