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

Im Abschnitt Stadienzuordnung Ihres [!DNL Marketo Measure] Kontos werden die Stadien, die [!DNL Marketo Measure] automatisch aus Ihrem CRM abruft, und alle benutzerdefinierten Stadien, die Sie bei Verwendung des benutzerdefinierten Attributionsmodells definiert haben, beschrieben. Die Gültigkeit Ihrer [!DNL Marketo Measure]-Daten hängt davon ab, dass diese Phasen korrekt sortiert werden, damit [!DNL Marketo Measure] Ihren Trichter und das Fortschreiten der Datensätze im gesamten Trichter genau verstehen können.

Im Abschnitt Staging-Zuordnung Ihrer [!DNL Marketo Measure]-Instanz sehen Sie sowohl aktive als auch inaktive Phasen in Ihrem CRM. Sortieren Sie alle Stadien nach bestem Wissen und Gewissen in Übereinstimmung mit dem heutigen Trichter.

Eine zusätzliche Funktion, die in diesem Abschnitt verwaltet wird, sind Trichterphasen, mit denen Sie dem Trichter Stadien hinzufügen können, ohne Attribution anzuwenden. Die Trichterphasen werden als Touchpoints verfolgt und im Feld Touchpoint-Positionen in Ihrem CRM aufgefüllt. Diese Trichterstufen werden auch auf verschiedenen Journey-Boards in [!DNL Marketo Measure] Discover vertreten sein.

## Bewährte Methoden {#best-practices}

Unabhängig davon, ob Sie Ihr Staging-Mapping zum ersten Mal bewerten oder nur Ihre Trichterreihenfolge überprüfen, ist es wichtig, die folgenden Best Practices zu beachten.

* Bestellung ist alles!
   * Wenn Sie [!DNL Marketo Measure] aktive und inaktive Phase aus Ihrem CRM abrufen, bestätigen Sie, dass alle Phasen, die für einen Lead/Kontakt oder eine Opportunity verwendet werden könnten, gruppiert und entsprechend sortiert werden.
* Stellen Sie bei der Definition eines benutzerdefinierten Schritts sicher, dass die Feldverlaufsverfolgung für alle Felder aktiviert ist, die zum Definieren des Schritts verwendet werden
* Verwenden Sie kein Formelfeld, um einen benutzerdefinierten Schritt zu definieren
   * Ein boolesches Feld ist die Best-Practice-Empfehlung
* Beachten Sie, dass der Abschnitt Lead- oder Kontaktphase in Verloren, Offen und Konvertiert unterteilt ist. Überprüfen Sie, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden
   * Eine Stufe im falschen Abschnitt der Stufe kann zu stark falschen [!DNL Marketo Measure] führen
   * Wenn Sie Marketo Measure Ultimate-Kunde sind und Ihr standardmäßiges Dashboard-Objekt als Kontakt festgelegt haben, verwenden Sie nicht die beiden folgenden Lead-spezifischen Felder ([ mehr dazu](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Beachten Sie, dass der Abschnitt „Opportunity-Phase“ in „Verloren“, „Offen“ und „Gewonnen“ unterteilt ist. Überprüfen Sie, ob sich die Phasen in ihrem entsprechenden Abschnitt befinden
   * Eine Phase im falschen Stadienabschnitt kann zu stark falschen [!DNL Marketo Measure] Umsatz- oder Pipeline-Umsatzdaten führen
* Vermeiden Sie die Verwendung doppelter Phasennamen (unser System erkennt sie und entfernt sie automatisch).
* Um eine Regel festzulegen, die auf NULL-Werte prüft, lassen Sie das Textfeld „Wert“ leer.

## Best Practices für die Wartung {#best-practices-for-maintenance}

Wenn Sie Ihr Staging-Mapping einmal jährlich überprüfen, wird sichergestellt, dass Ihre Opportunity-Daten in [!DNL Marketo Measure] korrekt und auf dem neuesten Stand sind.

Andere Gründe, die Trigger für eine Überprüfung Ihres Staging-Mappings sein könnten, sind…

* Wechsel in Ihrem Marketing-Team
* Alle Änderungen an Ihren CRM-Phasen
* Aktualisierungen des Trichters Ihrer Organisation
* Anzeige falscher Umsatzdaten in Ihren [!DNL Marketo Measure]

>[!MORELIKETHIS]
>
>[Der Unterschied zwischen Trichterstufen und benutzerdefinierten Modellstadien](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
