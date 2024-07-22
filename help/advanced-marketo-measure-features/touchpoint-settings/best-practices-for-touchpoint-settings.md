---
description: Best Practices für Touchpoint-Einstellungen - [!DNL Marketo Measure]
title: Best Practices für Touchpoint-Einstellungen
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 6%

---

# Best Practices für Touchpoint-Einstellungen {#best-practices-for-touchpoint-settings}

## Überblick {#overview}

Im Abschnitt [!UICONTROL Touchpoint-Einstellungen] Ihrer [!DNL Marketo Measure]-App können Sie Regeln festlegen, die Touchpoints unterdrücken oder aus Ihren [!DNL Marketo Measure] -Daten und verwandten Systemen entfernen. Diese Regeln können Ihnen dabei helfen, bestimmte Datensätze zu isolieren, die nicht in Ihren Kunden-Touchpoint-Daten dargestellt werden müssen oder die Sie nicht ohne Störung des Trackings und der Datenerfassung Attributionszuschüsse erhalten möchten.

**Touchpoint-Entfernung** bedeutet, dass [!DNL Marketo Measure] alle Touchpoints aus Ihrem CRM-System bereinigt (d. h. entfernt), die den Regelkriterien entsprechen. Die Daten können im [!DNL Marketo Measure] ROI-Dashboard (Discover) gemeldet, aber nicht im CRM angezeigt werden. Wird häufig verwendet, um Stress bei Ihren Datenspeicherbeschränkungen in Ihrem CRM-System zu verringern.

**Touchpoint-Unterdrückung** ähnelt der Touchpoint-Entfernung, die Daten können jedoch NICHT im ROI-Dashboard gemeldet werden. Auf unterdrückte Touchpoints kann im CRM oder Discover nicht zugegriffen werden. Durch die Unterdrückung wird sichergestellt, dass Ihre CRM-Daten und Ihre Discover-Daten übereinstimmen. Wird häufig verwendet, um festzulegen, welche Touchpoint-Daten Sie Attributionsgutschriften erhalten möchten.

In Ihrer [!DNL Marketo Measure]-App wird der Abschnitt [!UICONTROL Touchpoint-Einstellungen] in vier wichtige Abschnitte unterteilt. Jeder Abschnitt unterdrückt oder entfernt einen anderen Datensatz. Verwenden Sie den unten stehenden Schlüssel, um sicherzustellen, dass Ihre Regeln die gewünschten Touchpoints unterdrücken oder entfernen.

* Entfernen Sie Buyer Touchpoints aus dem CRM
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Touchpoint-Daten** (die Touchpoints, die mit der Person verknüpft sind, nicht die Gelegenheit) aus Ihrem **CRM** entfernt
* Buyer Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Touchpoint-Daten** (die Touchpoints, die mit der Person verknüpft sind, nicht die Gelegenheit) aus Ihrem **CRM** und **Discover** entfernt
* Buyer Attribution Touchpoints aus dem CRM entfernen
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Attribution Touchpoint**-Daten (die Touchpoints, die mit der Gelegenheit und dem Umsatz verknüpft sind) aus Ihrem **CRM** entfernt
* Buyer Attribution Touchpoints aus dem CRM unterdrücken
   * Verwenden Sie diesen Abschnitt, wenn Sie eine Regel erstellen möchten, die **Buyer Attribution Touchpoint**-Daten (die Touchpoints, die mit der Gelegenheit und dem Umsatz verknüpft sind) aus Ihrem **CRM** und **Discover** entfernt

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie zum ersten Mal Touchpoint-Einstellungsregeln erstellen oder diese nur überprüfen, um die Genauigkeit zu überprüfen.

* Erstellen Sie die Liste der Daten, die Sie unterdrücken oder entfernen möchten, bevor Sie die Regeln erstellen
* Identifizieren Sie genau, welche Felder die von Ihnen eingerichteten Regeln eindeutig kennzeichnen.
* Stellen Sie sicher, dass Sie den richtigen Operator für die Regel angegeben haben
* Stellen Sie mithilfe des oben stehenden Schlüssels sicher, dass Ihre Regel im richtigen Abschnitt der Touchpoint-Einstellungen angegeben ist.
* Testen Sie Ihre Regeln, bevor Sie sie implementieren, indem Sie die Regellogik in einem Käufer-Touchpoint-Bericht in CRM replizieren, um sicherzustellen, dass die gewünschten Daten unterdrückt oder entfernt werden.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Die Überprüfung Ihrer [!UICONTROL Touchpoint-Einstellungen] ist wichtig, da sie Ihre Daten drastisch ändern können, wenn sie nicht richtig definiert sind. Als Best Practice empfehlen wir, Ihre Touchpoint-Einstellungen mindestens zweimal jährlich zu überprüfen. Dies ist eine einfache visuelle Überprüfung der Regeln, die im Abschnitt &quot;Touchpoint-Einstellungen&quot;Ihrer [!DNL Marketo Measure] -App eingerichtet wurden. Diese Überprüfung gibt Ihnen die Gewissheit, dass Ihre Touchpoint-Einstellungen aktuell sind und dass alle Änderungen entsprechend vorgenommen werden können.

Gründe für die Überprüfung Ihrer [!UICONTROL Touchpoint]-Einstellungen sind ...

* Wechsel in Ihrem Marketing-Team
* Wesentliche Aktualisierungen der Website-Struktur
* Identifizierung von Touchpoint-Daten, die nicht mehr nützlich sind
   * Jedes Mal, wenn Sie auf Touchpoint-Daten treffen, von denen Sie denken, dass sie keine Zuordnungsgutschrift erhalten sollten, sind [!DNL touchpoint suppression] -Regeln die Funktion, um sicherzustellen, dass Ihre Daten so sauber und präzise wie möglich sind.
* Änderungen an den Feldern, mit denen Sie Unterdrückungs- oder Löschregeln definieren

>[!MORELIKETHIS]
>
>* [Übersicht über das Entfernen und Unterdrücken von Touchpoints](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [Warum Touchpoints nie gelöscht werden sollten](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [Touchpoints des Käufers (BT) und Touchpoints der Käuferzuordnung (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

