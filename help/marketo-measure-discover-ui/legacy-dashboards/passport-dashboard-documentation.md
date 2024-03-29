---
unique-page-id: 42762628
description: Dokumentation zum Passport-Dashboard - [!DNL Marketo Measure]
title: Dokumentation zum Passport-Dashboard
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 2%

---

# Dokumentation zum Passport-Dashboard {#passport-dashboard-documentation}

Mit dem Passport-Dashboard können Marketingexperten Leads/Kontakte und Chancen anzeigen, die während eines bestimmten Zeitraums in jeder Pipeline-Phase stattgefunden haben.

Dieses Dashboard besteht aus zwei Kacheln:

* Chancen: Die Anzahl der Opportunity-Einträge, die während des angegebenen Zeitraums durch jede Phase weitergegeben werden.
* Leads/Kontakte: Die Anzahl der Lead- oder Kontaktdatensätze, die während des angegebenen Zeitraums durch die einzelnen Phasen geleitet wurden.

>[!NOTE]
>
>In allen Discover-Dashboards kann nur ein Personenobjekt, entweder &quot;Lead&quot;oder &quot;Kontakt&quot;, gemeldet werden. Dies wird in [!UICONTROL Einstellungen] > [!UICONTROL Berichterstellung] > [!UICONTROL Attributionseinstellungen] > [!UICONTROL Standard-Dashboard-Objekt].

Dieses Dashboard unterstützt die folgenden Filter (alle Filter gelten für beide Kacheln):

* Datum: Wählen Sie den Zeitraum aus.
* Kanal: Filtern Sie die Datensätze nach Kanälen. Ein Datensatz ist mit einem Kanal verknüpft, wenn einer seiner Touchpoints mit dem Kanal verknüpft ist.
* Unterkanal: zum Filtern der Datensätze nach Unterkanälen. Ein Datensatz ist mit einem Unterkanal verknüpft, wenn einer seiner Touchpoints mit dem Unterkanal verknüpft ist.
* Kampagne: Filtern Sie die Datensätze nach Kampagnen. Ein Datensatz ist mit einer Kampagne verknüpft, wenn einer seiner Touchpoints mit der Kampagne verknüpft ist.
* Kampagnenquelle: Filtern Sie die Datensätze nach Kampagnenquellen. Beispiele für Kampagnenquellen sind Adwords, BingAds, Facebook, LinkedIn usw. Ein Datensatz wird mit einer Kampagnenquelle verknüpft, wenn einer seiner Touchpoints mit der Kampagnenquelle verknüpft ist.
* CRM-Kontoname: Filtern Sie die Datensätze nach CRM-Kontonamen.
* Segmentfilter: Filtern Sie die Datensätze nach benutzerdefinierten Segmenten. Ein Datensatz ist mit einem Segment verknüpft, wenn einer seiner Touchpoints mit dem Segment verknüpft ist.

In allen Filtern wird die Logik &quot;AND&quot;verwendet.

>[!NOTE]
>
>Wenn sich ein Datensatz am ausgewählten Datum in der Phase ändert, wird der Datensatz für die - und -Phasen sowie alle Durchlaufphasen gezählt.

## Opportunitys {#opportunities}

![](assets/one-1.png)

Zu den Phasen gehören OC, ausgewählte Trichterphasen in Open Opportunity Stages ([!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Staging-Zuordnung]) und Won Opportunity-Phasen ([!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Staging-Zuordnung]).

>[!NOTE]
>
>Bei &quot;Won&quot;-Bühnen werden die Datensätze nur für Datensätze gezählt, die während des ausgewählten Zeitraums in die Bühne überführt werden.

Sie können von jeder Leiste aus einen Drilldown durchführen, um die Opportunity-Datensätze für jede Phase anzuzeigen.

## Leads/Kontakte {#leads-contacts}

![](assets/two-1.png)

Zu den Phasen gehören FT, LC, ausgewählte Trichterphasen in &quot;Open Lead/Contact Stages on Settings&quot;- CRM - &quot;Staging Mapping&quot;und &quot;Converted Lead/Contact Stages on Settings&quot;- &quot;CRM&quot;- &quot;Staging Mapping&quot;.

>[!NOTE]
>
>Bei konvertierten Bühnen werden nur Datensätze gezählt, die während des ausgewählten Zeitraums in die Bühne überführt wurden.

Sie können von jeder Leiste aus einen Drilldown durchführen, um die Lead-/Kontaktdatensätze für jede Phase anzuzeigen.
