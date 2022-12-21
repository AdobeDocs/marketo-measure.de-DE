---
unique-page-id: 42762628
description: Dokumentation zum Passport-Dashboard - [!DNL Marketo Measure] - Produktdokumentation
title: Dokumentation zum Passport-Dashboard
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# Dokumentation zum Passport-Dashboard {#passport-dashboard-documentation}

Das Passport-Dashboard ermöglicht es Marketingexperten, Leads/Kontakte und Chancen anzuzeigen, die während eines bestimmten Zeitraums in jeder Pipeline-Phase stattgefunden haben.

Dieses Dashboard besteht aus zwei Kacheln:

* Chancen: Die Anzahl der Opportunity-Einträge, die während des angegebenen Zeitraums durch die einzelnen Phasen geleitet wurden.
* Interessenten/Ansprechpartner: Die Anzahl der Lead- oder Kontaktdatensätze, die während des angegebenen Zeitraums durch die einzelnen Phasen geleitet wurden.

>[!NOTE]
>
>In allen Discover-Dashboards kann nur ein Personenobjekt (Lead oder Kontakt) gemeldet werden. Dies wird in [!UICONTROL Einstellungen] > [!UICONTROL Berichterstellung] > [!UICONTROL Attributionseinstellungen] > [!UICONTROL Standard-Dashboard-Objekt].

Dieses Dashboard unterstützt die folgenden Filter (alle Filter gelten für beide Kacheln):

* Datum: Wählen Sie den Zeitraum aus.
* Kanal: die Datensätze nach Kanälen filtern. Ein Datensatz ist mit einem Kanal verknüpft, wenn einer seiner Touchpoints mit dem Kanal verknüpft ist.
* Subchannel: die Datensätze nach Unterkanälen filtern. Ein Datensatz ist mit einem Unterkanal verknüpft, wenn einer seiner Touchpoints mit dem Unterkanal verknüpft ist.
* Kampagne: die Datensätze nach Kampagnen filtern. Ein Datensatz ist mit einer Kampagne verknüpft, wenn einer seiner Touchpoints mit der Kampagne verknüpft ist.
* Kampagnenquelle: die Datensätze nach Kampagnenquellen zu filtern. Beispiele für Kampagnenquellen sind AdWords, BingAds, Facebook, LinkedIn usw. Ein Datensatz wird mit einer Kampagnenquelle verknüpft, wenn einer seiner Touchpoints mit der Kampagnenquelle verknüpft ist.
* CRM-Kontoname: die Datensätze nach CRM-Kontonamen filtern.
* Segmentfilter: die Datensätze nach benutzerdefinierten Segmenten filtern. Ein Datensatz ist mit einem Segment verknüpft, wenn einer seiner Touchpoints mit dem Segment verknüpft ist.

In allen Filtern wird die Logik &quot;AND&quot;verwendet.

>[!NOTE]
>
>Wenn sich ein Datensatz am ausgewählten Datum in der Phase ändert, wird der Datensatz für die - und -Phasen sowie alle Durchlaufphasen gezählt.

## Opportunities {#opportunities}

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
