---
description: Best Practices für die Staging-Zuordnung - [!DNL Marketo Measure]
title: Best Practices für die Phasenzuordnung
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 4%

---

# Best Practices für die Phasenzuordnung {#best-practices-for-stage-mapping}

## Überblick {#overview}

Im Abschnitt &quot;Staging-Zuordnung&quot;Ihres [!DNL Marketo Measure]-Kontos werden die Phasen beschrieben, die [!DNL Marketo Measure] automatisch aus Ihrem CRM-System abruft, sowie alle benutzerdefinierten Phasen, die Sie bei Verwendung des benutzerdefinierten Attributionsmodells definiert haben. Die Gültigkeit Ihrer [!DNL Marketo Measure] -Daten hängt davon ab, dass diese Schritte korrekt sortiert werden, damit [!DNL Marketo Measure] Ihren Trichter und den Verlauf der Datensätze im gesamten Trichter genau verstehen kann.

Im Abschnitt &quot;Staging-Zuordnung&quot;Ihrer [!DNL Marketo Measure]-Instanz werden sowohl aktive als auch inaktive Phasen aus Ihrem CRM-System angezeigt. Ordnen Sie alle Bühnen nach bestem Wissen und Gewissen an, wie Ihr Trichter heute ist.

Eine zusätzliche Funktion, die in diesem Abschnitt verwaltet wird, sind Trichterschritte, mit denen Sie Bühnen zum Trichter hinzufügen können, ohne eine Attribution anzuwenden. Trichterphasen werden als Touchpoints verfolgt und im Feld Touchpoint-Positionen in Ihrem CRM-System ausgefüllt. Diese Trichterphasen werden auch in verschiedenen Journey-Pinnwänden in [!DNL Marketo Measure] Discover dargestellt.

## Bewährte Methoden {#best-practices}

Unabhängig davon, ob Sie Ihre Staging-Zuordnung zum ersten Mal bewerten oder Ihre Trichterreihenfolge überprüfen, sollten Sie die folgenden Best Practices beachten.

* Ordnung ist alles!
   * Prüfen Sie unter Berücksichtigung von [!DNL Marketo Measure] , ob aktive und inaktive Phasen aus Ihrem CRM-System in allen Phasen, die auf Lead/Kontakt oder Opportunity verwendet werden können, gruppiert und entsprechend geordnet sind.
* Stellen Sie beim Definieren einer benutzerdefinierten Phase sicher, dass das Verfolgen des Feldverlaufs für alle Felder aktiviert ist, die zum Definieren der Phase verwendet werden
* Verwenden Sie kein Formelfeld, um eine benutzerdefinierte Phase zu definieren
   * Ein boolesches Feld ist die Best Practice-Empfehlung
* Beachten Sie, dass der Abschnitt Lead- oder Kontaktphase in Verloren, Offen und Konvertiert unterteilt ist. Überprüfen Sie, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden.
   * Eine Bühne im falschen Abschnitt &quot;Bühne&quot;kann zu hochgradig falschen [!DNL Marketo Measure]-Daten führen
   * Wenn Sie Marketo Measure Ultimate-Kunde sind und Ihr standardmäßiges Dashboard-Objekt als &quot;Kontakt&quot;festgelegt haben, verwenden Sie nicht die folgenden beiden für &quot;Lead&quot;spezifischen Felder ([Weitere Informationen](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Beachten Sie, dass der Abschnitt &quot;Opportunity stage&quot;in Lost, Open und Won unterteilt ist. Überprüfen Sie, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden.
   * Wenn sich eine Phase im falschen Abschnitt befindet, kann dies zu sehr falschen [!DNL Marketo Measure] Umsatz- oder Pipeline-Umsatzdaten führen
* Vermeiden Sie die Verwendung doppelter Staging-Namen (unser System erkennt sie und entfernt sie automatisch).
* Wenn Sie eine Regel festlegen möchten, die nach NULL-Werten sucht, lassen Sie das Textfeld &quot;Wert&quot;leer.

## Best Practices für Wartung {#best-practices-for-maintenance}

Wenn Sie Ihre Staging-Zuordnung einmal jährlich überprüfen, stellen Sie sicher, dass Ihre Opportunity-Daten in [!DNL Marketo Measure] korrekt und aktuell sind.

Andere Gründe, die eine Überprüfung Ihrer Staging-Zuordnung Trigger haben könnten, sind ...

* Wechsel in Ihrem Marketing-Team
* Alle Änderungen an Ihren CRM-Phasen
* Aktualisierungen am Trichter Ihrer Organisation
* Anzeige falscher Umsatzdaten in Ihren [!DNL Marketo Measure] Berichten

>[!MORELIKETHIS]
>
>[Der Unterschied zwischen Trichterphasen und benutzerdefinierten Modellphasen](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
