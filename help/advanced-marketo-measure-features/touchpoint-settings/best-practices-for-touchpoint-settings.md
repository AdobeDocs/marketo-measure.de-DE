---
description: Best Practices für Touchpoint-Einstellungen - [!DNL Marketo Measure]
title: Best Practices für Touchpoint-Einstellungen
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 6%

---

# Best Practices für Touchpoint-Einstellungen {#best-practices-for-touchpoint-settings}

## Überblick {#overview}

Die [!UICONTROL Touchpoint-Einstellungen] -Abschnitt Ihres [!DNL Marketo Measure] Mit der -App können Sie Regeln festlegen, die Touchpoints unterdrücken oder aus Ihrem [!DNL Marketo Measure] Daten und verwandten Systemen. Diese Regeln können Ihnen dabei helfen, bestimmte Datensätze zu isolieren, die nicht in Ihren Kunden-Touchpoint-Daten dargestellt werden müssen oder die Sie nicht ohne Störung des Trackings und der Datenerfassung Attributionszuschüsse erhalten möchten.

**Touchpoint-Entfernung** bedeutet [!DNL Marketo Measure] löscht (d. h. entfernt) alle Touchpoints aus Ihrem CRM-System, die den Regelkriterien entsprechen. Die Daten können in der Variablen [!DNL Marketo Measure] ROI-Dashboard (Discover), jedoch nicht im CRM angezeigt. Wird häufig verwendet, um Stress bei Ihren Datenspeicherbeschränkungen in Ihrem CRM-System zu verringern.

**Touchpoint-Unterdrückung** ähnelt der Entfernung von Touchpoints, die Daten können jedoch NICHT im ROI-Dashboard gemeldet werden. Auf unterdrückte Touchpoints kann im CRM oder Discover nicht zugegriffen werden. Durch die Unterdrückung wird sichergestellt, dass Ihre CRM-Daten und Ihre Discover-Daten übereinstimmen. Wird häufig verwendet, um festzulegen, welche Touchpoint-Daten Sie Attributionsgutschriften erhalten möchten.

In der [!DNL Marketo Measure] App, die [!UICONTROL Touchpoint-Einstellungen] wird in vier Schlüsselabschnitte unterteilt. Jeder Abschnitt unterdrückt oder entfernt einen anderen Datensatz. Verwenden Sie den unten stehenden Schlüssel, um sicherzustellen, dass Ihre Regeln die gewünschten Touchpoints unterdrücken oder entfernen.

* Entfernen Sie Buyer Touchpoints aus dem CRM
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Touchpoint-Daten des Käufers** (die Touchpoints, die mit der Person verknüpft sind, nicht die Gelegenheit) aus Ihrem **CRM**
* Buyer Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Touchpoint-Daten des Käufers** (die Touchpoints, die mit der Person verknüpft sind, nicht die Gelegenheit) aus Ihrem **CRM** und **Discover**
* Buyer Attribution Touchpoints aus dem CRM entfernen
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Touchpoint der Käuferzuordnung** Daten (die Touchpoints, die mit der Gelegenheit und dem Umsatz verknüpft sind) aus Ihrem **CRM**
* Buyer Attribution Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Touchpoint der Käuferzuordnung** Daten (die Touchpoints, die mit der Gelegenheit und dem Umsatz verknüpft sind) aus Ihrem **CRM** und **Discover**

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie zum ersten Mal Touchpoint-Einstellungsregeln erstellen oder diese nur überprüfen, um die Genauigkeit zu überprüfen.

* Erstellen Sie die Liste der Daten, die Sie unterdrücken oder entfernen möchten, bevor Sie die Regeln erstellen
* Identifizieren Sie genau, welche Felder die von Ihnen eingerichteten Regeln eindeutig kennzeichnen.
* Stellen Sie sicher, dass Sie den richtigen Operator für die Regel angegeben haben
* Stellen Sie mithilfe des oben stehenden Schlüssels sicher, dass Ihre Regel im richtigen Abschnitt der Touchpoint-Einstellungen angegeben ist.
* Testen Sie Ihre Regeln, bevor Sie sie implementieren, indem Sie die Regellogik in einem Käufer-Touchpoint-Bericht in CRM replizieren, um sicherzustellen, dass die gewünschten Daten unterdrückt oder entfernt werden.

## Best Practice für die Wartung {#best-practice-for-maintenance}

Überprüfen Sie Ihre [!UICONTROL Touchpoint-Einstellungen] ist wichtig, da sie Ihre Daten drastisch ändern können, wenn sie nicht richtig definiert sind. Als Best Practice empfehlen wir, Ihre Touchpoint-Einstellungen mindestens zweimal jährlich zu überprüfen. Dies ist eine einfache visuelle Überprüfung der Regeln, die im Abschnitt &quot;Touchpoint-Einstellungen&quot;Ihres [!DNL Marketo Measure] App. Diese Überprüfung gibt Ihnen die Gewissheit, dass Ihre Touchpoint-Einstellungen aktuell sind und dass alle Änderungen entsprechend vorgenommen werden können.

Gründe für die Überprüfung Ihrer [!UICONTROL Touchpoint] Zu den Einstellungen gehören ...

* Wechsel in Ihrem Marketing-Team
* Wesentliche Aktualisierungen der Website-Struktur
* Identifizierung von Touchpoint-Daten, die nicht mehr nützlich sind
   * Jedes Mal, wenn Sie auf Touchpoint-Daten treffen, von denen Sie denken, dass sie keine Attribution erhalten sollten, [!DNL touchpoint suppression] -Regeln dienen dazu, sicherzustellen, dass Ihre Daten so sauber und genau wie möglich sind.
* Änderungen an den Feldern, mit denen Sie Unterdrückungs- oder Löschregeln definieren

>[!MORELIKETHIS]
>
>* [Entfernung und Unterdrückung von Touchpoints - Übersicht](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [Warum Touchpoints nie gelöscht werden sollten](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [Käufer-Touchpoints (BT) vs. Buyer Attribution Touchpoints (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

