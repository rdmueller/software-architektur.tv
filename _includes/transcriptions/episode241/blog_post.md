# Folge 241 - Domain-Driven Design: Ein vollständiges Beispiel (Teil 2 von 2)

Willkommen zur zweiten Episode über Domain-Driven Design (DDD)! In diesem Blog-Beitrag setzen wir unsere Diskussion über den praktischen Einsatz von DDD fort und vertiefen uns in das taktische Design, ein essenzieller Aspekt für den Aufbau robuster Software-Systeme. Insbesondere werden wir die verschiedenen Patterns von DDD kennenlernen und deren praktische Anwendung in einem Beispiel diskutieren.

## Taktisches Design

Im letzten Teil haben wir die Grundlagen von DDD behandelt, wie die Identifizierung von bounded contexts und die Definierung von Team-Verantwortlichkeiten. Nun wenden wir uns dem taktischen Design zu – dem Bereich, der sich mit der konkreten Implementierung innerhalb dieser delimitierten Kontexte beschäftigt.

### Entities und Value Objects

Der erste Grundstein im taktischen Design sind **Entities**: Objekte, die durch ihre Identität definiert sind. Zum Beispiel hat jeder Kunde in einem System eine eindeutige Identität, auch wenn es eine zweite Instanz mit denselben Attributen gibt. Das bedeutet, dass jede Entity individualisierbar und unterscheidbar ist.

Im Gegensatz dazu stehen **Value Objects**: Diese Objekte repräsentieren Mengen oder Werte, die identisch sind, solange die Werte übereinstimmen. So können etwa „2 Euro“ und „2 Meter“ unabhängig von ihrer Repräsentation als Value Object betrachtet werden. Sie sind unveränderlich und können nur durch neue Instanzen mit unterschiedlichen Werten ersetzt werden.

### Domain Events

Ein weiteres wichtiges Konzept im DDD sind **Domain Events**, die bedeutende Ereignisse innerhalb des Systems darstellen. Sie sind entscheidend für die Kommunikation zwischen verschiedenen Komponenten und helfen, die Historie von Zustandsänderungen festzuhalten. Hierbei spielt Event Storming eine zentrale Rolle, um diese Ereignisse zu identifizieren und zu modellieren.

### Aggregates und Aggregate Roots

Auf einer weiteren Schicht finden wir **Aggregates** – Gruppen von Entities und Value Objects, die zusammen eine konsistente Einheit bilden. Jedes Aggregate hat eine **Aggregate Root**, die die Kontrolle über die inneren Mitglieder des Aggregates hat und sicherstellt, dass Integritätsbedingungen gewahrt bleiben.

Das Aggregate hat die Aufgabe, sicherzustellen, dass alle Änderungen innerhalb des Aggregates atomar sind. Wenn beispielsweise eine Bestellung erstellt wird, muss sowohl das Hinzufügen eines Artikels zur Bestellung als auch die Aktualisierung des Gesamtbetrags erfolgen. Diese Änderungen sollten zusammen umgesetzt werden, um Konsistenz zu gewährleisten.

### Repositories

*Repositories* bieten eine Abstraktionsebene, um Aggregates zu verwalten. Sie stellen sicher, dass die zugrunde liegenden Speichermechanismen vom Rest der Anwendung verborgen bleiben. So können wir ein Repository für Kunden haben, das nur spezifische Abfragen ermöglicht, die für die Fachdomäne relevant sind, zum Beispiel nach der Kundennummer oder dem Namen. Dies fördert ein fachlich konsistentes Design.

### Factories und Services

Bei der Erstellung komplexer Objekte kommen **Factories** ins Spiel. Sie sind dafür verantwortlich, Aggregate oder Value Objects zu initialisieren, wenn die Konstruktion zu komplex ist, um sie direkt im Code zu erstellen. 

**Services** schließlich sind Klassen, die Geschäftslogik enthalten, die nicht sinnvoll in Entities oder Aggregates untergebracht werden kann. Sie ermöglichen es uns, Logik zu kapseln, die mehrere Aggregates betrifft oder nicht direkt einem bestimmten Aggregate zugeordnet werden kann.

### Alternativen zum taktischen DDD

Während taktisches DDD für komplexe Systeme hervorragend geeignet ist, gibt es Situationen, in denen es sinnvoll sein kann, weniger komplexe Ansätze zu wählen. Hier sind einige Überlegungen:

1. **Funktionale Programmierung:** Eine alternative Denkweise ist die funktionale Programmierung, bei der Zustände vermieden werden. Stattdessen berechnet man neue Werte ohne Seiteneffekte. Hier könnten wir beispielsweise aus einem Zinssatz den neuen Kontostand berechnen, aber der Kontostand selbst wird extern verwaltet, was eine andere, funktionale Architektur impliziert.

2. **Transaction Script:** Bei weniger komplexen Geschäftslogiken kann es sinnvoll sein, einen **Transaction Script**-Ansatz zu verwenden. Hierbei bearbeiten wir HTTP-Requests direkt und nehmen einfache Datenbankoperationen vor, ohne tiefgehende abstrahierte Strukturen zu benötigen. Das reduziert den initialen Entwicklungsaufwand, kann aber schnell unübersichtlich werden, wenn die Logik komplexer wird.

### Beispiel: E-Commerce-System

Um die Theorie in die Praxis umzusetzen, betrachten wir ein E-Commerce-System. Hier könnten wir einen bounded context für die Lieferung haben. Wir definieren:

- **Entities:** Lieferungen, Pakete
- **Value Objects:** Adressen
- **Aggregates:** Die Lieferung als Aggregate Root, die mehrere Pakete und Adressen verwaltet.

Für die Zustellung könnten wir über ein Delivery Repository die Funktionalität implementieren, um alle Pakete für einen bestimmten Kunden abzufragen. 

Wir können auch einen Service definieren, der die Logik für die Schätzung von Lieferzeiten übernimmt und basierend auf verschiedenen Faktoren eine Auslieferung plant. Zudem generieren wir bei jeder Zustellung ein Domain Event, das als Ereignis den Status innerhalb des Systems aktualisiert.

### Event Storming und Design-Level

Ein effektives Event Storming kann die weitere Gestaltung der Business Logik und die Interaktionen zwischen den verschiedenen Komponenten klären. Es gibt verschiedene Granularitätsstufen, von Big-Picture-Event-Storming, bei dem wir die Gesamtarchitektur betrachten, bis hin zu Design-Level-Event-Storming, bei dem es um feingranulare Details geht.

### CQRS und Event Sourcing

Zwei weitere interessante Muster sind **CQRS (Command Query Responsibility Segregation)** und **Event Sourcing**. CQRS fördert die Trennung von Lese- und Schreiboperationen, was uns erlaubt, spezialisierte Modelle für Abfragen und Änderungen zu erstellen. Event Sourcing hingegen legt Wert darauf, alle Änderungen als Ereignisse zu speichern, wodurch wir den gesamten Zustand des Systems aus der Historie rekonstruieren können.

### Abstraktion und Architekturmuster

Letztendlich geht es darum, die passende Abstraktionsebene zu finden und die richtigen Architekturmuster auszuwählen. Während Layering eine klare Trennung der logischen Schichten betont, bietet die hexagonale Architektur eine flexiblere und testbare Struktur, in der die Geschäftslogik von externen Komponenten nicht beeinflusst wird. 

### Fazit

Domain-Driven Design ist eine kraftvolle Methodik, die es uns ermöglicht, komplexe Systeme zu verstehen und sie strukturiert abzubilden. Indem wir die verschiedenen Konzepte und Muster richtig einsetzen, können wir robuste, wartbare und skalierbare Systeme schaffen. In der nächsten Folge werden wir uns auf das Thema der Generativen KI in der Softwarearchitektur konzentrieren und dessen Einfluss auf moderne Entwicklungsansätze untersuchen. Ich hoffe, diese Episode war hilfreich und aufschlussreich für euer Verständnis von DDD!

Vielen Dank für's Zuhören! Ich wünsche euch ein produktives Wochenende!