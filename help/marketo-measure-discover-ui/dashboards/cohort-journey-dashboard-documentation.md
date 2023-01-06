---
unique-page-id: 42762648
description: Dokumentation zum Journey-Dashboard für Kohorten - [!DNL Marketo Measure] - Produktdokumentation
title: Dokumentation zum Kohorten-Journey-Dashboard
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
source-git-commit: 28f1400e8e13c091e8ea2a3bef115a0db810c2e0
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Dokumentation zum Kohorten-Journey-Dashboard {#cohort-journey-dashboard-documentation}

Mit den Dashboards &quot;Kohortenauswirkungen&quot;und &quot;Trichter&quot;können Marketingexperten den Fortschritt von einer Kohortenphase für einen ausgewählten Zeitraum anzeigen und die Konversionsrate messen.

Der Hauptunterschied besteht darin, wie wir jede Entität aus der Kohortenphase zählen.

* Kohortentrichter: Das Ergebnis jeder Phase ergibt sich direkt aus der vorherigen Phase.

   * Es werden nur Datensätze gezählt, die nach der festgelegten Kohortenstartzeit durch die einzelnen Phasen des Trichters geraten sind.

![](assets/cohort-journey-dashboard-documentation-1.png)

* Auswirkungen der Kohorte: Das Ergebnis jeder Phase ergibt sich aus der Kohorte und nicht aus der vorherigen Phase.

   * Alle Datensätze in jeder Phase werden so lange gezählt, wie sie nach der festgelegten Kohortenstartzeit erfolgten. Dieses Dashboard enthält natürlich mehr Datensätze als das Trichter-Dashboard, da wir uns ansehen, wie die Entitäten von der Kohortenphase aus beeinflusst wurden, nicht nur die Bewegung durch den Trichter.

![](assets/cohort-journey-dashboard-documentation-2.png)

Jedes Dashboard verfügt über zwei Kacheln:

* Kohortenumsatz: Die gesamte Opportunität aus allen Gelegenheiten in der Journey-Kachel der Kohorte.
* Kohorte-Journey: Der Fortschritt zu jeder Journey-Phase ab der Anfangs-Kohortenphase für einen ausgewählten Zeitraum.

>[!NOTE]
>
>In allen Discover-Dashboards kann nur ein Personenobjekt (Lead oder Kontakt) gemeldet werden. Dies wird in [!UICONTROL Einstellungen] > [!UICONTROL Berichterstellung] > [!UICONTROL Attributionseinstellungen] > [!UICONTROL Standard-Dashboard-Objekt].

Die Dashboards unterstützen die folgenden Filter:

* Kohortenphase: Wählen Sie die Anfangs-Kohorte aus. Datensätze in allen folgenden Phasen werden aus den Datensätzen in der Kohortenphase entwickelt.
* Datumsbereich der Kohorte: Wählen Sie den Zeitraum für die ausgewählte Kohortenphase aus. Zusammen mit der Kohortenphase wird der Startdatensatz definiert.
* Abschaltdatum: Wählen Sie das Datum aus, bis zu dem der Fortschritt des Datensatzes in allen folgenden Phasen erfolgen muss. Die Standardeinstellung ist heute. Beachten Sie, dass dies für alle anderen Phasen als die Kohortenphase gilt.
* Kanal: die Datensätze nach Kanälen filtern. Ein Datensatz ist mit einem Kanal verknüpft, wenn einer seiner Touchpoints mit dem Kanal verknüpft ist.
* Subchannel: die Datensätze nach Unterkanälen filtern. Ein Datensatz ist mit einem Unterkanal verknüpft, wenn einer seiner Touchpoints mit dem Unterkanal verknüpft ist.
* Kampagne: die Datensätze nach Kampagnen filtern. Ein Datensatz ist mit einer Kampagne verknüpft, wenn einer seiner Touchpoints mit der Kampagne verknüpft ist.
* Kampagnenquelle: die Datensätze nach Kampagnenquellen zu filtern. Beispiel-Kampagnenquellen: [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], usw. Ein Datensatz wird mit einer Kampagnenquelle verknüpft, wenn einer seiner Touchpoints mit der Kampagnenquelle verknüpft ist.
* Segmentfilter: die Datensätze nach benutzerdefinierten Segmenten filtern. Ein Datensatz ist mit einem Segment verknüpft, wenn einer seiner Touchpoints mit dem Segment verknüpft ist.

In allen Filtern wird die Logik &quot;AND&quot;verwendet.

>[!NOTE]
>
>Segmentfilter gelten nur für die LC-Phase und danach. Wenn die Kohortenstufe unbekannt oder bekannt ist und einer der Segmentfilter einen Wert aufweist, gibt das Dashboard keine Ergebnisse zurück.

Zu den Phasen gehören unbekannte, bekannte, LC, ausgewählte Trichterphasen in den offenen Lead-/Kontaktstadien (Einstellungen > CRM > Staging-Zuordnung), OC, ausgewählte Trichterphasen in den Open Opportunity Stages (Einstellungen > CRM > Staging-Zuordnung) und Angebote (Geschlossene Chancen).

>[!NOTE]
>
>Die Anzahl der Datensätze für eine Journey-Phase, die als eine andere Phase als die Kohortenphase definiert ist, umfasst alle neuen Datensätze, die sich auf die Kohortendatensätze beziehen und die nach dem Startdatum des ausgewählten Zeitraums und vor dem Abschaltdatum erstellt werden. Dies ist eine angebliche Kausalität.

Sie können die einzelnen Balken im Drilldown-Verfahren anzeigen, um die Datensätze für jede Phase anzuzeigen.

* Für &quot;Unbekannt&quot;werden anonyme Besucherdetails angezeigt.
* Bekannte Besucherdetails werden angezeigt.
* Bei LC- und Open Lead/Contact-Bühnen werden Lead-/Kontaktdetails angezeigt.
* Bei OC, Open Opportunity-Phasen und Deals werden Details zu Opportunity angezeigt.
