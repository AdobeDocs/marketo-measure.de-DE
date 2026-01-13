---
description: Häufig gestellte Fragen zum Modell für maschinelles Lernen - [!DNL Marketo Measure]
title: Modell für maschinelles Lernen – FAQ
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
feature: Custom Models
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---


# Modell für maschinelles Lernen – FAQ {#machine-learning-model-faq}

Das Modell des [!DNL Marketo Measure] maschinellen Lernens verwendet Ihre Touchpoint-Daten, um zu berechnen, wie viel Attributionsgewichtung den einzelnen Stadien zugewiesen werden soll. Das hängt davon ab, wie wichtig die einzelnen Phasen für den Abschluss von Verträgen waren.

Was sagen mir die Prozentsätze der Zuordnung aus dem Modell des maschinellen Lernens über die einzelnen Phasen?

Die Prozentsätze der Zuordnungen jedes Schritts spiegeln die potenziellen Auswirkungen Ihrer Marketing-Maßnahmen wider. Ein höherer Prozentsatz bedeutet, dass das Marketing die Bewegung der funnel zu diesem Zeitpunkt direkt beeinflussen kann. Ein niedrigerer Attributionsprozentsatz bedeutet, dass Stadien für Ihr Team weniger wichtig sind.

Wie wird das Modell für maschinelles Lernen berechnet?

[!DNL Marketo Measure] berechnet die Wichtigkeit jedes benutzerdefinierten Schritts anhand der Touchpoint-Daten in Ihrem Konto. Die Kriterien, nach denen die Bedeutung der einzelnen Phasen bestimmt wird, sind:

* Modellgenauigkeit: Wie genau wird das Modell sein, wenn wir ein prädiktives Modell mit den Touchpoint-Daten erstellen, um vorherzusagen, ob wir letztendlich einen Deal gewinnen werden? Eine höhere Prognosegenauigkeit bedeutet, dass die Details dieser Phase mehr damit korrelieren, ob ein Geschäft abgeschlossen wird
* Konversionsrate: Wenn Leads oder Vertriebschancen in diesem bestimmten Stadium mit einer hohen Rate in das nächste Stadium konvertieren, deutet dies darauf hin, dass die Marketing-Aktivitäten, die in diesem Stadium stattfanden, nicht sehr wichtig waren. Wenn hingegen eine bestimmte Phase mit einer niedrigen Rate in die nächste Phase konvertiert, kann dies darauf hindeuten, dass die Marketing-Aktivitäten, die in dieser Phase stattfanden, die Konversion angetrieben haben.
* Gewichtung der Touchpoint-Eindeutigkeit: Wenn eine Phase als eigenständige Transition auftritt, d. h. es gab keine anderen Phasenübergänge, die gleichzeitig stattfanden, könnte diese Phase eine höhere Attributionsgewichtung erhalten. Wenn dagegen ein Touchpoint für ein Stadium mit anderen Stadien geteilt wird (z. B. der Touchpoint teilt die Stadien Erster Kontakt, Lead-Konversion und Opportunity-Konversion), könnte dieses Stadium eine niedrigere Attributionsgewichtung erhalten.

Die endgültige Gewichtung für ein benutzerdefiniertes Stadium wird wie folgt berechnet:

**_Modellprozentsatz = Modellgenauigkeit x Konversionsrate x Gewichtung der Touchpoint-Eindeutigkeit_**

Am Ende werden alle benutzerdefinierten Stufengewichte normalisiert und in % konvertiert, wie unten dargestellt.

Warum werden in der Spalte für maschinelles Lernen keine Zahlen angezeigt?

Wenn das benutzerdefinierte Attributionsmodell für Ihr Konto aktiviert ist, dauert es in der Regel zwischen 3 und 7 Tage, bis unser Modell ausgeführt und diese Zahlen auf der Grundlage Ihrer historischen Daten erstellt wird.

Wie oft wird das Modell für maschinelles Lernen aktualisiert?

Wir führen das Modell alle 7 Tage erneut aus.

Warum setzt das Modell Middle Touches immer auf 10 %?

Die Zuweisung von 10 % Attributionsguthaben zu Middle Touches ist eine Standardeinstellung für alle unsere Attributionsmodelle.

Wann sollte ich meine Attributionsverteilung ändern?

Wenden Sie sich an Ihren Account Manager, um die Auswirkungen einer Änderung Ihrer Attributionsprozentsätze zu besprechen und zu erfahren, welche Stadien Sie in Ihr benutzerdefiniertes Modell aufnehmen sollen. Jeder [!DNL Salesforce]- und Verkaufsprozess ist einzigartig, und wir möchten sicherstellen, dass Ihr benutzerdefiniertes Modell genau modelliert wird.

Dennoch haben wir einige allgemeine Trends bei unseren Kunden erkannt:

Ein Trend, der uns aufgefallen ist, ist, dass es nicht immer von Vorteil ist, weitere Stadien in Ihr Modell aufzunehmen. Wenn Kundinnen und Kunden beispielsweise am Ende der funnel mehrere Opportunity-Stadien hinzugefügt haben, erhalten diese Stadien in der Regel sehr niedrige Prozentwerte für die Attribution. Niedrige Prozentwerte zeigen eine hohe Konversionsrate an, was normalerweise bedeutet, dass diese Stadien beim Schließen von Abschlüssen nicht so wirkungsvoll sind. Einige Kunden entscheiden sich letztendlich dafür, diese Stadien nicht in die funnel aufzunehmen. Wenn Sie eine Stufe aus Ihrem Attributionsmodell entfernen, berechnet das Maschinenmodell die Prozentsätze neu und verteilt sie neu.

Wir haben auch festgestellt, dass es eine hohe Konversionsrate von der Lead-Erstellung zu Marketing-qualifizierten Phasen gibt, sodass die Phase Marketing-qualifiziert eine niedrigere prozentuale Attributionsgewichtung erhalten könnte. Je nach Geschäfts- und Verkaufszyklus kann es von Vorteil sein, diesen Schritt aus dem benutzerdefinierten Modell zu entfernen.

Denken Sie daran, dass Sie Marketing-Aktivitäten über einen bestimmten Stadienübergang verfolgen möchten, diesen Stadium jedoch nicht als Attribution-Credits erhalten soll. Sie können diesen Schritt in Ihr Modell einbeziehen und diesem Stadium 0 % Attribution-Credits zuweisen.
