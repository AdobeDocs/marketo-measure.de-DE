---
unique-page-id: 18874775
description: FAQ zum Modell für maschinelles Lernen - [!DNL Marketo Measure] - Produktdokumentation
title: Modell für maschinelles Lernen – FAQ
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
feature: Custom Models
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# Modell für maschinelles Lernen – FAQ {#machine-learning-model-faq}

Die [!DNL Marketo Measure] Das Modell für maschinelles Lernen verwendet Ihre Touchpoint-Daten, um zu berechnen, wie viel Zuordnungsgewichtung jeder Phase zugewiesen werden soll. Dies wird dadurch bestimmt, wie wichtig jede Etappe beim Abschluss von Fahrverträgen war.

Was sagen mir die Attributionsprozentsätze des Modells für maschinelles Lernen über jede Phase?

Die Zuordnungsprozentsätze jeder Phase spiegeln die potenziellen Auswirkungen Ihrer Marketing-Maßnahmen wider. Ein höherer Prozentsatz bedeutet, dass Marketing die Bewegung des Trichters an diesem Punkt direkt beeinflussen kann. Ein geringerer Attributionsprozentsatz bedeutet, dass Phasen für Ihr Team weniger wichtig sind.

Wie wird das Modell für maschinelles Lernen berechnet?

[!DNL Marketo Measure] berechnet die Wichtigkeit jeder benutzerdefinierten Phase mithilfe der Touchpoint-Daten aus Ihrem Konto. Die Kriterien, anhand derer die Bedeutung jeder Phase bestimmt wird, sind:

* Modellgenauigkeit: Wenn wir ein prädiktives Modell mit den Touchpoint-Daten erstellen, um vorherzusagen, ob wir irgendwann ein Geschäft gewinnen werden, wie genau wird das Modell sein? Höhere Vorhersagegenauigkeit bedeutet, dass die Details dieser Phase eher mit der Frage korrelieren, ob ein Geschäft abgeschlossen wird
* Konversionsrate: Wenn sich Interessenten oder Chancen in dieser Phase in einer hohen Rate in die nächste Stufe umwandeln, hat dies den Eindruck, dass die in dieser Phase erfolgten Marketingaktivitäten nicht sehr wichtig waren. Umgekehrt kann dies darauf hindeuten, dass die in dieser Phase aufgetretenen Marketingaktivitäten zur Konversion beitragen, wenn eine bestimmte Phase in eine niedrige Rate in die nächste Phase konvertiert wird.
* Eindeutige Touchpoint-Gewichtung: Wenn eine Phase als eigenständige Transition auftritt, d. h. keine anderen Phasenübergänge gleichzeitig aufgetreten sind, kann diese Phase eine höhere Attributionsgewichtung erhalten. Umgekehrt könnte diese Phase eine niedrigere Attributionsgewichtung erhalten, wenn ein Touchpoint für eine Phase mit anderen Phasen geteilt wird (z. B. der Touchpoint die Schritte Erstkontakt, Lead-Konversion und Opportunity Conversion teilt).

Die endgültige Gewichtung für eine benutzerdefinierte Phase wird wie folgt berechnet:

**_Modellprozentsatz = Modellgenauigkeit x Konversionsrate x Touchpoint-Eindeutigkeitsgewicht_**

Am Ende werden alle benutzerdefinierten Staging-Gewichtungen normalisiert und in % konvertiert, wie unten dargestellt.

Warum werden in der Spalte &quot;Machine Learning&quot;keine Zahlen angezeigt?

Wenn das benutzerdefinierte Attributionsmodell für Ihr Konto aktiviert ist, dauert es in der Regel 3-7 Tage, bis unser Modell ausgeführt und diese Zahlen basierend auf Ihren historischen Daten erstellt wird.

Wie oft wird das Modell für maschinelles Lernen aktualisiert?

Wir führen das Modell alle sieben Tage erneut aus.

Warum setzt das Modell &quot;Middle Touches&quot;immer auf 10 %?

Die Zuweisung von 10 % Zuordnungsguthaben zu &quot;Middle Touches&quot;ist eine Standardeinstellung für alle unsere Attributionsmodelle.

Wann sollte ich meine Attributionsverteilung ändern?

Wenden Sie sich an Ihren Kundenbetreuer, um zu besprechen, welche Auswirkungen die Änderung Ihrer Attributionsprozentsätze hat und welche Phasen in Ihr benutzerdefiniertes Modell aufgenommen werden sollen. Jeder [!DNL Salesforce] und der Verkaufsprozess einzigartig ist, und wir möchten sicherstellen, dass Ihr benutzerdefiniertes Modell korrekt modelliert wird.

Dennoch haben wir einige allgemeine Trends für unsere Kunden ermittelt:

Ein Trend, den wir bemerkt haben, ist, dass es nicht immer von Vorteil ist, mehr Phasen in Ihr Modell aufzunehmen. Wenn Kunden beispielsweise mehrere Opportunity-Phasen am Ende des Trichters hinzugefügt haben, erhalten diese Phasen meist sehr niedrige Attributionsprozentwerte. Niedrige Prozentwerte weisen auf eine hohe Konversionsrate hin, was normalerweise bedeutet, dass diese Phasen nicht so wirkungsvoll sind, wenn es darum geht, Angebote zu schließen. Einige Kunden entscheiden sich letztendlich dafür, diese Phasen nicht in den Trichter aufzunehmen. Wenn Sie eine Phase aus Ihrem Attributionsmodell entfernen, berechnet das maschinelle Modell die Prozentsätze neu und verteilt sie neu.

Wir haben auch festgestellt, dass es eine hohe Konversionsrate von Lead-Erstellung zu Marketing-Qualifizierten Bühnen gibt. Daher könnte die Stufe Marketing-Qualifiziert eine niedrigere Prozentattributionsgewichtung erhalten. Je nach Ihrem Geschäfts- und Verkaufszyklus kann es von Vorteil sein, diese Phase aus dem benutzerdefinierten Modell zu entfernen.

Beachten Sie Folgendes: Wenn Sie Marketingaktivitäten über einen bestimmten Übergang in der Phase verfolgen möchten, aber nicht möchten, dass diese Phase eine Attribution-Gutschrift erhält, können Sie diese Phase in Ihr Modell aufnehmen und dieser Phase eine 0-%-Attribution zuweisen.
