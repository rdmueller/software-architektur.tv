# Folge 237: Warum ist Software(-Architektur) eigentlich immer so schlecht?

In der heutigen Episode von Software-Architektur im Stream befassen wir uns mit einer Frage, die viele Softwareentwickler und Architekten beschäftigt: Warum ist die Qualität der Software-Architektur oft so schlecht? Dieses Thema anzusprechen, ist nicht nur wichtig, sondern auch herausfordernd, denn die Ursachen sind vielschichtig und gehen tief in die Strukturen und Verfahren der Softwareentwicklung hinein.

## Ein persönlicher Blick auf schlechte Softwarequalität

Als Berater sehe ich häufig suboptimale Softwarelösungen, was für mich eine tägliche Herausforderung darstellt. Es ist nicht nur frustrierend, sondern wirft auch die wichtige Frage auf: Was müsste sich ändern, damit ich arbeitslos werde? In meinen Gesprächen und Beobachtungen ist mir aufgefallen, dass viele Teams und Unternehmen durchaus ein Bewusstsein für die Qualität ihrer Software haben. Dennoch investieren sie oft nicht in die notwendigen Verbesserungen. 

Ein zentraler Punkt, den ich hier ansprechen möchte, ist, dass viele Systeme keine vernünftige Struktur haben. Die Geschäftslogik ist verteilt, nicht sinnvoll organisiert und das erschwert die Wartbarkeit erheblich. Natürlich hat Softwarequalität viele Dimensionen wie Performance, Zuverlässigkeit und Sicherheit, doch in dieser Folge möchte ich mich auf den Aspekt der Wartbarkeit und Struktur konzentrieren.

## Die Frage der architektonischen Qualität

Eine interessante Frage, die in einem LinkedIn-Post von Martin Egli gestellt wurde, lautet: "Wann ist die Softwarearchitektur gut genug?" Diese Frage trifft den Kern des Problems. Oft sagen wir, wir wollen Software entwickeln, die spezifische, nicht-funktionale Anforderungen erfüllt. Dennoch, in der Realität sehe ich oft das Gegenteil – die Architektur ist einfach schlecht strukturiert. Besonders schockierend ist, dass viele derjenigen, die an diesen Systemen arbeiten, zwar wissen, dass die Qualität nicht stimmt, jedoch aus verschiedenen Gründen nicht in der Lage sind, dies zu ändern.

In einem weiteren Austausch mit Kollegen kam die Vermutung auf, dass die Qualitätssicherung schuld an unserer schlechten Softwarequalität sei. Dabei ist es nicht nur eine Frage der Tests – es geht viel tiefer. Der Druck, schnell und billig zu produzieren, führt dazu, dass Techniker und Entwickler zahlreiche „Abkürzungen“ nehmen. Das heißt, sie treffen Entscheidungen, die kurzfristig vielleicht Sinn machen, langfristig aber katastrophale Folgen haben können.

## Der Schatten des Zeitdrucks

Zeitdruck ist ein zentrales Thema in der Softwareentwicklung. Oft entscheiden sich Teams aufgrund von Deadlines für eine schnelle Lösung anstatt für nachhaltige. In meiner Erfahrung ist dieser Zeitdruck häufig nicht durch tatsächliche Geschäftsanforderungen motiviert, sondern entsteht durch eine Art von künstlichen Deadlines, die nicht wirklich sinnvoll sind.

Diese künstlichen Zeitvorgaben stehen oft im Widerspruch zu einem nachhaltigen Ansatz zur Softwareentwicklung. Sie führen dazu, dass Entwickler unter enormem Druck arbeiten müssen, was die Qualität der Software negativ beeinflusst. Zudem kann das Management oft nicht nachvollziehen, warum scheinbar einfache Aufgaben länger dauern als geplant. Der Grund: Technische Komplexität und das Streben nach einer soliden Softwarearchitektur sind schwer zu kommunizierende Themen.

## Der Einfluss des Managements

Ein oft übersehener Aspekt ist die Rolle des Managements bei der Softwarequalität. Entscheidungen, die auf der Managementebene getroffen werden, beeinflussen direkt die Architektur und die Qualität der Software. Die Entscheidung für Technologien oder Architekturansätze, wie z.B. Microservices, kann ohne ein tiefes technisches Verständnis getroffen werden. Oft führt das dazu, dass Teams in ein architektonisches Chaos geraten.

Das muss nicht zwangsläufig schlecht sein, ist jedoch problematisch, wenn es auf mangelndes Verständnis oder unzureichende Kommunikation zurückzuführen ist. Teams müssen die Fähigkeit entwickeln, technische Herausforderungen zu kommunizieren und sicherzustellen, dass das Management die Auswirkungen ihrer Entscheidungen versteht. Wenn der Druck zu groß und die Kommunikation unzureichend ist, wird es schwierig, qualitativ hochwertige Software zu entwickeln.

## Die Illusion von technischer Exzellenz

Im digitalen Zeitalter gibt es die illusionäre Vorstellung, dass technische Exzellenz automatisch die Softwarequalität verbessert. In meiner letzten Keynote habe ich festgestellt, dass das Streben nach reiner technischer Exzellenz manchmal auch problematisch ist. Wir müssen den Kompromiss finden, wo Qualität sinnvollerweise am nachhaltigen Erfolg eines Produkts ausgerichtet ist.

Es ist wichtig zu erkennen, dass nicht alle Teile eines Systems ständig in höchster Qualität gehalten werden können – das steigert die Komplexität und führt oft zu Überforderung der Teams. Hier kommt das Konzept der „Core Domain“ ins Spiel, das darauf hinweist, dass wir uns auf wesentliche Funktionen konzentrieren und dort die Qualität hochhalten sollten, während wir bei anderen weniger kritischen Aspekten Abstriche machen können.

## Kommunikation ist der Schlüssel

Die Herausforderung, vor der wir stehen, besteht darin, eine konstruktive und effektive Kommunikation aufzubauen. Techniker und Management müssen gemeinsame Grundsätze entwickeln. Es sollte Raum für Diskussionen geben, um Missverständnisse auszuräumen und gemeinsam an Lösungen zu arbeiten. Wenn alle Beteiligten verstehen, welche Auswirkungen Entscheidungen auf die Qualität der Software haben, können wir nachhaltige Verbesserungen erreichen.

Zusätzlich können wir Techniken und Werkzeuge implementieren, die uns helfen, die architektonischen Standards ein- und durchzusetzen. Statische Code-Analysen, Peer-Reviews oder Code-Qualitätswerkzeuge können dabei nützlich sein, um sicherzustellen, dass wir konstant auf ein hohes Qualität- und Wartbarkeitsniveau hinarbeiten.

## Fazit: Ein verlorenes Rennen?

Die Frage, warum Software(-Architektur) oft schlecht ist, ist komplex und erfordert ein Umdenken in der Denkweise vieler Teams und Unternehmen. Wir müssen verstehen, dass hohe Qualität nicht nur technisches Handwerk ist, sondern auch die praktische Umsetzung in einem geschäftlichen Kontext verlangt. Schnell, billig und einfach zu produzieren bedeutet oft, in die Falle der schlechten Qualität zu tappen. Letztlich müssen wir die Balance finden zwischen technischer Exzellenz, nachhaltigen Entscheidungen und dem Bewusstsein für die geschäftlichen Rahmenbedingungen.

Die Herausforderungen, vor denen wir stehen, sind nicht unlösbar, doch sie erfordern eine proaktive Herangehensweise, sowohl von technischen als auch von managementseitigen Perspektiven. Nur durch klare Worte, offene Fragen und eine kontinuierliche Zusammenarbeit können wir die Weichen für eine bessere Softwarearchitektur und -qualität stellen – zum Wohle aller.