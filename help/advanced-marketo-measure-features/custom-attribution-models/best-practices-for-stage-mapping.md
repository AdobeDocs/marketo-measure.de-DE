---
description: Best Practices für die Staging-Zuordnung - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für die Staging-Zuordnung
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Best Practices für die Staging-Zuordnung {#best-practices-for-stage-mapping}

## Überblick {#overview}

Der Abschnitt &quot;Staging-Zuordnung&quot;Ihrer [!DNL Marketo Measure] -Konto beschreibt die Schritte, die [!DNL Marketo Measure] ruft automatisch aus Ihrem CRM-System und allen benutzerdefinierten Phasen ab, die Sie bei Verwendung des benutzerdefinierten Attributionsmodells definiert haben. Die Gültigkeit Ihrer [!DNL Marketo Measure] Daten beruhen darauf, dass diese Bühnen korrekt angeordnet werden, sodass [!DNL Marketo Measure] kann Ihren Trichter und das Fortschreiten der Datensätze im gesamten Trichter genau verstehen.

Im Abschnitt &quot;Staging-Zuordnung&quot;Ihrer [!DNL Marketo Measure] -Instanz werden sowohl aktive als auch inaktive Phasen aus Ihrem CRM-System angezeigt. Ordnen Sie alle Bühnen nach bestem Wissen und Gewissen an, wie Ihr Trichter heute ist.

Eine zusätzliche Funktion, die in diesem Abschnitt verwaltet wird, sind Trichterschritte, mit denen Sie Bühnen zum Trichter hinzufügen können, ohne eine Attribution anzuwenden. Trichterphasen werden als Touchpoints verfolgt und im Feld Touchpoint-Positionen in Ihrem CRM-System ausgefüllt. Diese Trichterphasen werden auch in verschiedenen Journey-Pinnwänden in [!DNL Marketo Measure] Entdecken Sie.

## Bewährte Methoden {#best-practices}

Unabhängig davon, ob Sie Ihre Staging-Zuordnung zum ersten Mal bewerten oder Ihre Trichterreihenfolge lediglich überprüfen, sollten Sie die folgenden Best Practices beachten.

* Ordnung ist alles!
   * Überlegungen [!DNL Marketo Measure] ruft aktive und inaktive Phasen aus Ihrem CRM ab, bestätigen Sie, dass alle Phasen, die für Lead/Kontakt oder Chancen verwendet werden können, gruppiert und entsprechend geordnet sind.
* Stellen Sie beim Definieren einer benutzerdefinierten Phase sicher, dass das Verfolgen des Feldverlaufs für alle Felder aktiviert ist, die zum Definieren der Phase verwendet werden
* Verwenden Sie kein Formelfeld, um eine benutzerdefinierte Phase zu definieren
   * Ein boolesches Feld ist die Best Practice-Empfehlung
* Beachten Sie, dass der Abschnitt &quot;Lead- oder Kontaktphase&quot;in &quot;Verloren&quot;, &quot;Offen&quot;und &quot;Konvertiert&quot;unterteilt ist. überprüfen, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden
   * Das Vorhandensein einer Phase im falschen Abschnitt kann zu einer hochgradig falschen [!DNL Marketo Measure] data
* Beachten Sie, dass der Abschnitt &quot;Opportunity stage&quot;in &quot;Lost&quot;, &quot;Open&quot;und &quot;Won&quot;unterteilt ist. überprüfen, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden
   * Das Vorhandensein einer Phase im falschen Abschnitt kann zu einer hochgradig falschen [!DNL Marketo Measure] Umsatz- oder Pipeline-Umsatzdaten
* Vermeiden Sie die Verwendung doppelter Staging-Namen (unser System erkennt sie und entfernt sie automatisch).

## Best Practices für Wartung {#best-practices-for-maintenance}

Wenn Sie Ihre Staging-Zuordnung einmal jährlich überprüfen, stellen Sie sicher, dass Ihre Opportunity-Daten in [!DNL Marketo Measure] genau und auf dem neuesten Stand ist.

Andere Gründe, die eine Überprüfung Ihrer Staging-Zuordnung Trigger haben könnten, sind ...

* Umsatz in Ihrem Marketing-Team
* Alle Änderungen an Ihren CRM-Phasen
* Aktualisierungen am Trichter Ihrer Organisation
* Anzeigen falscher Umsatzdaten in Ihrer [!DNL Marketo Measure] Berichterstellung

>[!MORELIKETHIS]
>
>[Der Unterschied zwischen Trichterphasen und benutzerdefinierten Modellphasen](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
