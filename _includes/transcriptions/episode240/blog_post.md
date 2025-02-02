# Domain-Driven Design: Ein vollständiges Beispiel (Teil 1)

Herzlich willkommen zu unserer heutigen Episode, in der wir uns intensiv mit Domain-Driven Design (DDD) beschäftigen werden. In diesem ersten Teil steigen wir tief in die strategischen Aspekte von DDD ein und erkunden, wie wir dieses Modell effektiv in der Softwareentwicklung einsetzen können. Domain-Driven Design ist ein wertvolles Werkzeug, das uns helfen kann, komplexe Softwareprojekte zu strukturieren und effizient umzusetzen. 

## Warum ist Domain-Driven Design wichtig?

Die Bedeutung von DDD liegt in der Tatsache, dass es uns ermöglicht, unsere Softwareentwicklung eng an den geschäftlichen Anforderungen und der realen Domäne auszurichten. Dabei stehen meist zwei zentrale Rollen im Vordergrund: die Domain-ExpertInnen, die das Fachwissen über die konkrete Domäne besitzen, und die Software-EntwicklerInnen, die wissen, wie man aus diesem Wissen funktionierende Software baut. Um den Herausforderungen, die diese beiden Gruppen mit sich bringen, gerecht zu werden, ist eine enge Zusammenarbeit nötig. 

Ein zentrales Ziel von DDD ist es, diese Zusammenarbeit zu fördern, indem wir ein gemeinsames Verständnis der Domäne entwickeln. Hierbei eignen sich verschiedene Techniken, die es uns ermöglichen, die Herausforderung der Kommunikation zwischen Domain-ExpertInnen und Software-EntwicklerInnen zu meistern. 

## Event-Storming: Der erste Schritt in die Zusammenarbeit

Eine der effektivsten Methoden, die sich in der Praxis als hilfreich erwiesen hat, ist Event-Storming. Dabei geht es darum, relevante Ereignisse – also die Dinge, die in der Domäne geschehen – zu identifizieren und visuell darzustellen. Ein zentraler Aspekt des Event-Stormings ist, dass es ein relativ einfacher, "low-tech" Ansatz ist: Man benötigt lediglich etwas Material wie Post-its oder digitale Tools, um die Ideen festzuhalten.

In der ersten Phase, die wir Chaotic Exploration nennen, sollten die Teilnehmer dazu ermutigt werden, möglichst viele Ereignisse auf Post-its zu schreiben. Diese Ereignisse sind oft in der Vergangenheitsform gehalten und geben uns einen klaren Eindruck davon, was in der Domäne passiert ist. 

Ein Beispiel könnte das Ereignis „Bestellung akzeptiert“ sein. Indem wir solche Ereignisse erfassen und strukturieren, können wir anschließend den zeitlichen Ablauf und die Abhängigkeiten der verschiedenen Prozesse klären. Es ist wichtig, dass wir uns währenddessen nicht nur auf die richtige Reihenfolge konzentrieren, sondern auch darauf, welche Vorbedingungen für die verschiedenen Ereignisse notwendig sind.

## Swimlanes und Pivotal Events

Im weiteren Verlauf nutzen wir Swimlanes, um parallele Prozesse sichtbar zu machen. Das hilft uns, die verschiedenen Aktivitäten, die gleichzeitig stattfinden, zu organisieren. So haben wir in einem E-Commerce-System möglicherweise swimlanes für die Bestellung, die Rechnungsstellung und die Lieferung. Jedes dieser Elemente hat seine eigene Logik, weist jedoch auch Berührungspunkte mit den anderen Prozessen auf.

Ein weiterer wichtiger Schritt ist die Identifizierung von Pivotal Events oder Schlüsselmomente. Diese sind entscheidende Punkte im Prozess, an denen sich die zuständige Domäne grundlegend verändert. Ein Beispiel für ein solches Ereignis könnte sein, wenn eine Bestellung akzeptiert wird und die Ware somit nicht mehr storniert, sondern schließlich ausgeliefert wird. Diese Pivotal Events helfen uns nicht nur zu verstehen, was in der Domäne passiert, sondern auch, wie verschiedene Prozesse zusammenarbeiten.

## Die Herausforderung der richtigen Ressourcen

Die Herausforderung beim Event-Storming besteht häufig darin, die richtigen Menschen an einen Tisch zu bringen. Domain-ExpertInnen, die jeden Tag mit dem System arbeiten, sind häufig nicht in der Lage, die Zukunft des Systems zu gestalten. Auf der anderen Seite können die Software-EntwicklerInnen oft nicht die Entscheidungen und Prioritäten treffen, die für die Weiterentwicklung des Systems entscheidend sind.

Um die Herausforderungen zu überwinden, brauchen wir eine gründliche und offene Kommunikation. Es ist entscheidend, dass sowohl die Innovatoren als auch die Praktiker zusammenarbeiten, damit ein gemeinsames Modell entstehen kann, das aus den Intuitionen und dem Wissen beider Gruppen entsteht.

## Alternativen zu Event-Storming

Neben Event-Storming gibt es weitere Methoden, die in ähnlicher Weise genutzt werden können, um ein gemeinsames Verständnis der Domäne zu erlangen. Eine prominent genannte Methode ist das Domain Storytelling. Hierbei wird der Ablauf eines Prozesses in Form einer Geschichte erzählt, wodurch die Dynamik der verschiedenen Schritte besser erfasst wird. Eine andere Technik ist Context Mapping, bei der wir die verschiedenen Kontextgrenzen innerhalb unserer Softwarearchitektur identifizieren und aufzeichnen.

## Strategisches Design und Kern-Domäne

Nachdem wir nun die Grundlagen gelegt haben, wollen wir auf strategische Designüberlegungen eingehen. Ein zentraler Aspekt von DDD ist die Identifizierung der Kern-Domäne. Diese ist der Bereich, der für den Erfolg und die Differenzierung des Unternehmens von entscheidender Bedeutung ist. Es ist wichtig, sich darauf zu konzentrieren, wo man die besondere Expertise hat und wie diese Expertise den Unternehmenserfolg beeinflussen kann.

Um den Fokus auf die Kern-Domäne zu legen, ist es entscheidend, die Struktur der Software so anzupassen, dass sie diese Prioritäten widerspiegelt. Im Kontext von DDD bringt die Modellierung der Kern-Domäne sowohl eine technische als auch eine geschäftliche Perspektive in Einklang.

## Fazit und Ausblick

In dieser ersten Episode haben wir wichtige Grundlagen und Strategien des Domain-Driven Designs erkundet. Wir haben gesehen, wie Event-Storming als Werkzeug genutzt werden kann, um die Komplexität der Zusammenarbeit zwischen Domain-ExpertInnen und Software-EntwicklerInnen zu reduzieren.

Im nächsten Teil werden wir uns dann mit den taktischen Aspekten von DDD beschäftigen. Dazu gehört, wie die strategischen Entscheidungen konkret in die Architektur und in die Implementierung übersetzt werden können. Insbesondere werden wir uns mit den Themen der modularen Strukturierung, der Schichtarchitektur sowie der Implementierung von Ubiquitous Language auseinander setzen.

Ich freue mich auf die nächste Episode, in der wir tiefer in die technischen Details eintauchen und aufzeigen, wie wir die Strategien, die wir heute besprochen haben, in der Praxis umsetzen können. Bleibt dran!