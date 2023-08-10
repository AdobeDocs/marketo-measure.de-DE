---
unique-page-id: 42762648
description: Dokumentation zum Journey-Dashboard für Kohorten - [!DNL Marketo Measure] - Produktdokumentation
title: Dokumentation zum Kohorten-Journey-Dashboard
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# Dokumentation zum Kohorten-Journey-Dashboard {#cohort-journey-dashboard-documentation}

Mit den Dashboards &quot;Kohortenauswirkungen&quot;und &quot;Trichter&quot;können Marketingexperten den Fortschritt von einer Kohortenphase für einen ausgewählten Zeitraum anzeigen und die Konversionsrate messen.

Der Hauptunterschied besteht darin, wie wir jede Entität aus der Kohortenphase zählen.

* Kohortentrichter: Das Ergebnis jeder Phase wird direkt aus der vorherigen Phase abgeleitet.

   * Es werden nur Datensätze gezählt, die nach der festgelegten Kohortenstartzeit durch die einzelnen Phasen des Trichters geraten sind.

![](assets/cohort-journey-dashboard-documentation-1.png)

* Kohortenauswirkungen: Das Ergebnis jeder Phase stammt aus der Kohortenphase, nicht aus der vorherigen Phase.

   * Alle Datensätze in jeder Phase werden so lange gezählt, wie sie nach der festgelegten Kohortenstartzeit erfolgten. Dieses Dashboard enthält natürlich mehr Datensätze als das Trichter-Dashboard, da wir uns ansehen, wie die Entitäten von der Kohortenphase aus beeinflusst wurden, nicht nur die Bewegung durch den Trichter.

![](assets/cohort-journey-dashboard-documentation-2.png)

Jedes Dashboard verfügt über zwei Kacheln:

* Kohortenumsatz: Der gesamte Opportunitätsbetrag aus allen Gelegenheiten in der Phase der Angebote der Kohorten-Journey-Kachel.
* Journey der Kohorte: Der Fortschritt von der Kohortenphase bis zu den einzelnen Journey-Phasen für einen ausgewählten Zeitraum.

>[!NOTE]
>
>In allen Discover-Dashboards kann nur ein Personenobjekt, entweder &quot;Lead&quot;oder &quot;Kontakt&quot;, gemeldet werden. Dies wird in [!UICONTROL Einstellungen] > [!UICONTROL Berichterstellung] > [!UICONTROL Attributionseinstellungen] > [!UICONTROL Standard-Dashboard-Objekt].

Die Dashboards unterstützen die folgenden Filter:

* Kohortenphase: Wählen Sie die Kohortenphase für den Start aus. Datensätze in allen folgenden Phasen werden aus den Datensätzen in der Kohortenphase entwickelt.
* Datumsbereich der Kohorte: Wählen Sie den Zeitraum für die ausgewählte Kohortenphase aus. Zusammen mit der Kohortenphase wird der Startdatensatz definiert.
* Datum der Außerkraftsetzung: Wählen Sie das Datum aus, bis zu dem der Fortschritt des Datensatzes in allen folgenden Phasen erfolgen muss. Die Standardeinstellung ist heute. Beachten Sie, dass dies für alle anderen Phasen als die Kohortenphase gilt.
* Kanal: Filtern Sie die Datensätze nach Kanälen. Ein Datensatz ist mit einem Kanal verknüpft, wenn einer seiner Touchpoints mit dem Kanal verknüpft ist.
* Unterkanal: zum Filtern der Datensätze nach Unterkanälen. Ein Datensatz ist mit einem Unterkanal verknüpft, wenn einer seiner Touchpoints mit dem Unterkanal verknüpft ist.
* Kampagne: Filtern Sie die Datensätze nach Kampagnen. Ein Datensatz ist mit einer Kampagne verknüpft, wenn einer seiner Touchpoints mit der Kampagne verknüpft ist.
* Kampagnenquelle: Filtern Sie die Datensätze nach Kampagnenquellen. Beispiel-Kampagnenquellen: [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], usw. Ein Datensatz wird mit einer Kampagnenquelle verknüpft, wenn einer seiner Touchpoints mit der Kampagnenquelle verknüpft ist.
* Segmentfilter: Filtern Sie die Datensätze nach benutzerdefinierten Segmenten. Ein Datensatz ist mit einem Segment verknüpft, wenn einer seiner Touchpoints mit dem Segment verknüpft ist.

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
