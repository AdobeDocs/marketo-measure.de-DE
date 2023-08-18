---
unique-page-id: 42762600
description: Momentaufnahme-Dashboard-Dokumentation - [!DNL Marketo Measure] - Produktdokumentation
title: Dokumentation zum Momentaufnahmen-Dashboard
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
feature: Reporting
source-git-commit: f8a37a996afefe78900e57e1eb166cdd50b5347f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---

# Dokumentation zum Momentaufnahmen-Dashboard {#snapshot-dashboard-documentation}

Mit dem Snapshot-Dashboard können Sie den Status Ihres CRM jederzeit anzeigen, mit der Verteilung der Datensätze über Lead-/Kontakt- und Opportunity-Phasen.

Dieses Dashboard besteht aus zwei Kacheln:

* **Lead-/Kontaktaufnahme:** Die Anzahl der Lead- oder Kontaktdatensätze in jeder Phase des ausgewählten Datums.

>[!NOTE]
>
>In allen Discover-Dashboards kann nur ein Personenobjekt, entweder &quot;Lead&quot;oder &quot;Kontakt&quot;, gemeldet werden. Dies wird in [!UICONTROL Einstellungen] > [!UICONTROL Berichterstellung] > [!UICONTROL Attributionseinstellungen] > [!UICONTROL Standard-Dashboard-Objekt].

* **Opportunity Snapshot:** Die Anzahl der Opportunity-Einträge in jeder Phase am ausgewählten Datum.

Dieses Dashboard unterstützt die folgenden Filter (alle Filter gelten für beide Kacheln):

* Momentaufnahmen-Datum: Wählen Sie das Datum der Momentaufnahme aus.
* CRM-Konto-ID/-Name: Filtern Sie die Datensätze nach CRM-Konto-IDs oder Namen.

>[!NOTE]
>
>Vorschläge zeigen nur Namen an.

* Kanal: Filtern Sie die Datensätze nach Kanälen. Ein Datensatz ist mit einem Kanal verknüpft, wenn einer seiner Touchpoints mit dem Kanal verknüpft ist.
* Unterkanal: zum Filtern der Datensätze nach Unterkanälen. Ein Datensatz ist mit einem Unterkanal verknüpft, wenn einer seiner Touchpoints mit dem Unterkanal verknüpft ist.
* Kampagne: Filtern Sie die Datensätze nach Kampagnen. Ein Datensatz ist mit einer Kampagne verknüpft, wenn einer seiner Touchpoints mit der Kampagne verknüpft ist.
* Kampagnenquelle: Filtern Sie die Datensätze nach Kampagnenquellen. Beispiel-Kampagnenquellen: [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], usw. Ein Datensatz wird mit einer Kampagnenquelle verknüpft, wenn einer seiner Touchpoints mit der Kampagnenquelle verknüpft ist.
* Konto-ID/-Name der Anzeige: Filtern Sie die Datensätze nach IDs oder Namen des Anzeigenkontos. Ein Datensatz wird einem Anzeigenkonto zugeordnet, wenn einer seiner Touchpoints über die ausgewählten Anzeigenkonten einer Kampagne zugeordnet ist.

>[!NOTE]
>
>Vorschläge zeigen nur Namen an.

* Segmentfilter: Filtern Sie die Datensätze nach benutzerdefinierten Segmenten. Ein Datensatz ist mit einem Segment verknüpft, wenn einer seiner Touchpoints mit dem Segment verknüpft ist.

In allen Filtern wird die Logik &quot;AND&quot;verwendet.

>[!NOTE]
>
>Wenn sich ein Datensatz am ausgewählten Datum in der Phase ändert, wird der Datensatz für die - und -Phasen sowie alle Durchlaufphasen gezählt.

## Lead / Kontakt Momentaufnahme {#lead-contact-snapshot}

![](assets/one.png)

Die Phasen umfassen FT-, LC- und ausgewählte Trichterphasen in offenen Lead-/Kontaktphasen ([!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Staging-Zuordnung]).

Sie können von jeder Leiste aus einen Drilldown durchführen, um die Lead-/Kontaktdatensätze für jede Phase anzuzeigen.

## Opportunity Momentaufnahme {#opportunity-snapshot}

![](assets/two.png)

Die Phasen umfassen FT, LC, ausgewählte Trichterphasen in offenen Lead-/Kontaktphasen ([!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Staging-Zuordnung]). Und OC und ausgewählte Trichterphasen in offenen Opportunity-Phasen ([!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Staging-Zuordnung]).

Sie können von jeder Leiste aus einen Drilldown durchführen, um die Opportunity-Datensätze für jede Phase anzuzeigen.
