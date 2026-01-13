---
description: Best Practices für Touchpoint-Einstellungen - [!DNL Marketo Measure]
title: Best Practices für Touchpoint-Einstellungen
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 6%

---


# Best Practices für Touchpoint-Einstellungen {#best-practices-for-touchpoint-settings}

## Überblick {#overview}

Im [!UICONTROL Touchpoint]Einstellungen Ihrer [!DNL Marketo Measure] App können Sie Regeln festlegen, mit denen Touchpoints aus Ihren [!DNL Marketo Measure] und verwandten Systemen unterdrückt oder entfernt werden. Diese Regeln können Ihnen dabei helfen, bestimmte Datensätze zu isolieren, die nicht in Ihren Kunden-Touchpoint-Daten dargestellt werden müssen oder die Sie nicht als Attribution erhalten möchten, ohne Ihre Nachverfolgung und Datenerfassung zu stören.

**Touchpoint-Entfernung** bedeutet, dass [!DNL Marketo Measure] alle Touchpoints, die den Regelkriterien entsprechen, aus Ihrem CRM bereinigen (d. h. entfernen). Die Daten können im Dashboard [!DNL Marketo Measure] ROI (Discover) gemeldet werden, erscheinen jedoch nicht im CRM. Wird häufig verwendet, um die Belastung der Datenspeicherungsbeschränkungen in Ihrem CRM zu verringern

**Touchpoint-Unterdrückung** ähnelt der Touchpoint-Entfernung, aber die Daten können NICHT im ROI-Dashboard gemeldet werden. Alle unterdrückten Touchpoints sind im CRM oder Discover nicht zugänglich. Die Unterdrückung stellt sicher, dass Ihre CRM-Daten und Ihre Discover-Daten übereinstimmen. Wird häufig verwendet, um eine Feinabstimmung vorzunehmen und genauer anzugeben, welche Touchpoint-Daten Sie als Attribution erhalten möchten.

In Ihrer [!DNL Marketo Measure] App ist der Abschnitt [!UICONTROL Touchpoint]Einstellungen“ in vier wichtige Abschnitte unterteilt. Jeder Abschnitt unterdrückt oder entfernt einen anderen Datensatz. Verwenden Sie die unten stehende Taste, um sicherzustellen, dass Ihre Regeln die gewünschten Touchpoints unterdrücken oder entfernen.

* Entfernen Sie Buyer Touchpoints aus dem CRM
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, mit der **Buyer Touchpoint-Daten** (die Touchpoints, die der Person zugeordnet sind, nicht der Opportunity) aus Ihrem **CRM entfernt werden**
* Buyer Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Touchpoint-Daten** (die Touchpoints, die der Person zugeordnet sind, nicht der Opportunity) aus Ihrem **CRM** und **Entdecken** entfernt
* Buyer Attribution Touchpoints aus dem CRM entfernen
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, mit der **Buyer Attribution Touchpoint**-Daten (die Touchpoints, die mit der Opportunity und dem Umsatz verknüpft sind) aus Ihrem **CRM entfernt werden**
* Buyer Attribution Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Attribution Touchpoint**-Daten (die Touchpoints, die mit der Opportunity und dem Umsatz verknüpft sind) aus Ihrem **CRM** und **Discover**

## Best Practices {#best-practice}

Unabhängig davon, ob Sie zum ersten Mal Touchpoint-Einstellungsregeln festlegen oder diese nur überprüfen, um ihre Genauigkeit zu überprüfen, sollten Sie die folgenden Best Practices beachten.

* Erstellen Sie vor dem Erstellen der Regeln die Liste der Daten, die Sie unterdrücken oder entfernen möchten
* Ermitteln Sie genau, welche Felder die von Ihnen eingerichteten Regeln klar kennzeichnen.
* Stellen Sie sicher, dass Sie den richtigen Operator für die Regel angegeben haben
* Vergewissern Sie sich mithilfe des obigen Schlüssels, dass Ihre Regel im richtigen Abschnitt der Touchpoint-Einstellungen angegeben ist
* Testen Sie Ihre Regeln, bevor Sie sie implementieren, indem Sie die Regellogik in einem Touchpoint-Bericht für Käufer in CRM replizieren, um sicherzustellen, dass die gewünschten Daten unterdrückt oder entfernt werden

## Best Practices für die Wartung {#best-practice-for-maintenance}

Die Überprüfung Ihrer [!UICONTROL Touchpoint-Einstellungen] ist wichtig, da sie Ihre Daten drastisch ändern können, wenn sie nicht richtig definiert sind. Als Best Practice empfehlen wir, Ihre Touchpoint-Einstellungen mindestens zweimal jährlich zu überprüfen. Dies ist eine einfache visuelle Überprüfung der Regeln, die im Abschnitt Touchpoint-Einstellungen Ihrer [!DNL Marketo Measure] App eingerichtet sind. Bei dieser Überprüfung können Sie sicher sein, dass Ihre Touchpoint-Einstellungen auf dem neuesten Stand sind und dass alle Änderungen entsprechend vorgenommen werden können.

Gründe für die Überprüfung Ihrer [!UICONTROL Touchpoint]-Einstellungen sind…

* Wechsel in Ihrem Marketing-Team
* Wichtige Aktualisierungen Ihrer Website-Struktur
* Identifizierung von Touchpoint-Daten, die nicht mehr nützlich sind
   * Jedes Mal, wenn Sie auf Touchpoint-Daten stoßen, bei denen Sie der Meinung sind, dass sie keine Attribution-Credits erhalten sollten, stellen [!DNL touchpoint suppression] Regeln die Funktionalität dar, Ihre Daten so sauber und genau wie möglich zu gestalten.
* Änderungen an den Feldern, die zur Definition der Unterdrückungs- oder Entfernungsregeln verwendet werden

>[!MORELIKETHIS]
> [Touchpoint-Entfernung und Unterdrückung - Übersicht](/help/advanced-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
> [Warum Touchpoints niemals gelöscht werden sollten](/help/advanced-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
> [Käufer-Touchpoints (BT) vs. Käufer-Attribution-Touchpoints (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-differences.md)

