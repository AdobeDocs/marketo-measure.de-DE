---
description: ROI-Dashboard - [!DNL Marketo Measure] - Produkt
title: ROI-Dashboard
feature: Reporting
exl-id: 878db6e0-3ac7-4f4c-b993-bd7a1cfa0638
source-git-commit: 403b31acce25ddc9c1dcafbd53008b6e2868b3df
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 3%

---

# ROI-Dashboard {#roi-dashboard}

Das ROI-Dashboard bietet Marketing-Experten einen detaillierten Überblick über die Investitionsrenditen über Kanäle, Unterkanäle und Kampagnen hinweg. Sie schlüsselt Kosten- und Umsatzmuster sorgfältig auf und zeigt gleichzeitig Metriken wie Kosten-pro-Interessent-, Deal- und Opportunities auf, um ein umfassendes Verständnis der Marketing-Attribution zu gewährleisten.

**Fragen, die die Pinnwand beantwortet**

* Wie hoch waren die ROI-Werte für jeden Kanal, jeden Unterkanal und jede Kampagne?
* Wie wurden die Kosten und Einnahmen auf die einzelnen Kanäle, Unterkanäle und Kampagnen verteilt?
* Was waren die Kosten pro Lead, Kosten pro Deal und Kosten pro Opportunity?

## Dashboard-Komponenten {#dashboard-components}

### KPI-Kacheln {#kpi-tiles}

* **Kosten**: Gesamtkosten aus verbundenen Datenquellen und manuell hochgeladene Kosten.
* **Zugewiesener Umsatz**: Der Gesamtumsatzbeitrag aus Chancen mit Touchpoints, die innerhalb des gefilterten Datumszeitraums geschlossen wurden, basierend auf dem ausgewählten Attributionsmodell.
* **Realisierte zugewiesene Umsätze**: Der Gesamtumsatzbeitrag aus Chancen mit Touchpoints innerhalb des gefilterten Datumszeitraums, basierend auf dem ausgewählten Attributionsmodell, unabhängig vom Zeitpunkt ihrer Schließung.
* **Gesamtzahl neuer Leads**: Gesamtzahl der neu generierten Leads, einschließlich berührter und unberührter Leads.
* **Kosten pro neuem Lead**: Die durchschnittlichen Kosten pro neuer Lead, abgeleitet aus den Gesamtkosten dividiert durch die Gesamtzahl neuer Leads.
* **Neue Möglichkeiten insgesamt**: Gesamtzahl der neu generierten Chancen, einschließlich sowohl berührter als auch unberührter Chancen.
* **Kosten pro neuer Chance**: Die durchschnittlichen Kosten pro neuer Chance, abgeleitet aus den Gesamtkosten dividiert durch die Gesamtzahl der neuen Chancen.
* **Angebote insgesamt**: Die Anzahl der &quot;geschlossenen Gewinnen&quot;-Chancen, einschließlich Chancen ohne Touchpoints.
* **Einfacher ROI**: Zugewiesener Umsatz dividiert durch Kosten im gefilterten Datumszeitraum.
* **Realisierter ROI**: Zugewiesener Umsatz dividiert durch Kosten im gefilterten Datumszeitraum.

![](assets/roi-dashboard-1.png)

### Kosten und Umsatz nach Kanaldiagramm {#cost-and-revenue-by-channel-graph}

Balkendiagramm zur Darstellung von Kosten und Umsatz, das eine vergleichende Sicht auf die Größenordnung der Balken in Bezug auf verschiedene Kanäle, Unterkanäle und Kampagnen bietet.

* Verwenden Sie die Drilldown- und Up-Funktionen, um die Daten nach Subchannel und Campaign zu kategorisieren.
* Bewegen Sie den Mauszeiger über die einzelnen Balken, um die einfachen und realisierten ROIs anzuzeigen.

**Fragen zu den Grafikantworten**

* Wie hoch waren die ROI-Werte für jeden Kanal, jeden Unterkanal und jede Kampagne?
* Gibt es Ausreißer-Kanäle oder Subkanäle mit ungewöhnlich hohen oder niedrigen Kosten im Verhältnis zum Umsatz?

![](assets/roi-dashboard-2.png)

### Realisierter und einfacher ROI im Zeitverlauf {#realized-vs-simple-roi-over-time}

Zeitreihenliniendiagramm, das den Vergleich zwischen realisiertem und einfachem ROI anzeigt und deren Fortschritt im Zeitverlauf verfolgt.

* Bewegen Sie den Mauszeiger über einen Abschnitt im Diagramm, um die einfachen und realisierten ROIs anzuzeigen.

**Fragen zu den Grafikantworten**

* Wie unterscheidet sich der realisierte ROI von dem einfachen ROI über bestimmte Zeiträume?
* Wie steht der Trend des realisierten ROI zu signifikanten Marketing-Ereignissen im selben Zeitraum?

![](assets/roi-dashboard-3.png)

### Zeitverlaufsdiagramm {#cost-over-time-graph}

Gestapeltes Balkendiagramm mit Gesamtkosten, segmentiert nach verknüpften Kanälen für jeden Monat/Quartal/Jahr.

* Verwenden Sie die Drilldown- und Up-Funktionen, um die Daten nach Monat, Quartal oder Jahr zu kategorisieren.
* Bewegen Sie den Mauszeiger über ein Balkensegment oder den Abstand zwischen Balken, um detaillierte Informationen anzuzeigen.

**Fragen zu den Grafikantworten**

* Wie vergleichen sich die Gesamtkosten aller Kanäle von einem Quartal/Monat zum nächsten?
* Wie haben sich die Kosten für einen bestimmten Kanal im Laufe der Zeit entwickelt?

![](assets/roi-dashboard-4.png)

### Kosten nach Kanaldiagramm {#cost-by-channel-graph}

Balkendiagramm mit den nach Kanal/Subkanal/Kampagne segmentierten Marketingausgaben.

* Verwenden Sie die Drilldown- und Up-Funktionen, um die Daten nach Kanal/Subkanal/Kampagne zu kategorisieren.

**Fragen zu den Grafikantworten**

* Welche Unterkanäle oder Kampagnen innerhalb eines primären Kanals weisen die höchste Zuordnung auf?
* Welche Marketing-Wege (Kanal, Unterkanal oder Kampagne) scheinen im Vergleich zu anderen unterfinanziert?

![](assets/roi-dashboard-5.png)

### ROI-Zusammenfassungstabelle {#roi-summary-table}

Tabelle mit zurechenbaren Einnahmen, Kosten und ROI, segmentiert nach einzelnen Kanälen, für eine detaillierte Aufschlüsselung.

* Klicken Sie auf das &quot;+&quot;-Symbol neben jedem Kanal, um die Aufschlüsselung nach Subkanal und Kampagne anzuzeigen.

**Spalten**

* Kanal/Subkanal/Kampagne
* Kosten
* Attributierter Umsatz
* Realisierte zugewiesene Umsätze
* Einfacher ROI
* Realisierter ROI
* Nicht realisierter zugewiesener Pipeline-Umsatz: Pipeline-Umsatz in Verbindung mit Touchpoints (Open Opportunities), die innerhalb des gefilterten Datumszeitraums erstellt wurden.

### Tabelle der Marketing-Ausgaben {#marketing-spend-table}

Tabelle mit Kosten, neuen Leads, Chancen und Angeboten, die nach einzelnen Kanälen segmentiert sind, für eine detaillierte Aufschlüsselung.

* Klicken Sie auf das &quot;+&quot;-Symbol neben jedem Kanal, um die Aufschlüsselung nach Subkanal und Kampagne anzuzeigen.

**Spalten**

* Kanal/Subkanal/Kampagne
* Kosten
* New Leads
* Kosten pro neuem Lead
* Neue Chancen
* Kosten pro neuer Chance
* Abschlüsse
* Kosten pro Abschluss

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum
   * Basierend auf:
      * Erstellungsdatum: News Leads, neue Chancen
      * Anschaffungskosten Datum: Kosten
      * Abschlussdatum: zugeordneter Umsatz (einfacher ROI), Geschäfte
      * Touchpoint-Datum: Touchpoints aus realisiertem, zugeordneten Umsatz (realisierter ROI)
* Attributionsmodell
* Kanal, Subkanal
* Kampagne

>[!MORELIKETHIS]
>
>* [Entdecken Sie die Grundlagen von Dashboards](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Dashboard-Richtlinie zur Datenanzeige](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}

