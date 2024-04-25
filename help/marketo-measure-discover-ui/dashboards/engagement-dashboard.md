---
description: Interaktions-Dashboard - [!DNL Marketo Measure] - Produkt
title: Interaktions-Dashboard
feature: Reporting
exl-id: dc8bcbe4-d470-4cd3-a2d9-804fdebe7121
source-git-commit: db71635a77d6e2555c442fb45371fd5a93e3c502
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Interaktions-Dashboard {#engagement-dashboard}

Im Interaktionsdashboard werden Benutzerinteraktionsmetriken sorgfältig verfolgt. Es zeigt Touchpoints, die Anzahl der beteiligten Personen und die durchschnittlichen Touchpoints pro Person. Verwenden Sie das Balkendiagramm der Zeitreihen für eine monatliche, vierteljährliche oder jährliche Ansicht sowie das Balkendiagramm für detaillierte Einblicke in Kanal, Subkanal und Kampagne. Dieses Tool ist für das Verständnis der Interaktionsmuster und die Feinabstimmung Ihrer Interaktionsstrategien von wesentlicher Bedeutung.

Wir verfolgen jede Kundeninteraktion als Benutzer-Touchpoints (UTs), die &quot;rohen&quot;erfassten Datenpunkte, die als Grundlage für Interaktionsmetriken in unserem Dashboard dienen. Nicht alle UTs entwickeln sich zu Käufer-Touchpoints (BTs) oder Buyer Attribution Touchpoints (BATs), da diese ausgewählte Ergebnisse sind, um bestimmte Kundeninteraktionen umsatzbezogenen Aktivitäten zuzuordnen. Beachten Sie, dass Unterdrückungsregeln keine Auswirkungen auf UTs oder das Interaktions-Dashboard haben.

* **Touchpoints des Benutzers**: Touchpoints, die aus allen Interaktionen erstellt wurden.
* **Touchpoints des Käufers**: Für die Zuordnung von Lead und Kontakt ausgewählte Touchpoints. BTs sind nicht mit Chancen verknüpft und haben keine zugehörigen Einnahmen.
* **Touchpoints der Käuferzuordnung**: Für die Opportunity-Attribution ausgewählte Touchpoints. BVT haben Auswirkungen auf die Einnahmen, da sie mit Chancen verbunden sind.

Die Verwendung von BTs oder BATs zur Messung der Interaktion würde das wahre Ausmaß der Kundeninteraktionen unterstreichen, da die Interaktion über die bloße Attribution hinausgeht.

Fragen zu den Antworten des Dashboards:

* Wie viele Leute waren verlobt? Wie hoch ist die durchschnittliche Touchanzahl pro engagierter Person?
* Wie unterscheidet sich die Anzahl der Touchpoints von Personen, die innerhalb eines bestimmten Kanals/Subkanals/einer bestimmten Kampagne auf einen Kontakt geklickt haben?
* Wie viele Touchpoints gab es in einem bestimmten Kanal oder Subkanal? Wie hat sich das im Laufe der Zeit verändert?

>[!NOTE]
>
>Die Interaktionsmetriken &quot;Konto&quot;und &quot;Chancen&quot;sind für die Veröffentlichung im ersten Halbjahr 2024 geplant.

## Dashboard-Komponenten {#dashboard-components}

### KPI-Kacheln {#kpi-tiles}

* Touchpoints: Die Gesamtzahl der generierten rohen Touchpoints.
   * Touchpoints der Käuferzuordnung und Touchpoints der Käuferzuordnung sind Attributionsergebnisse, die durch Auswahl bestimmter Touchpoints für Gutschriften erstellt werden. Nicht alle Touchpoints werden als BTs und BATs ausgewählt.
* Touchpoints für Personen: Die Gesamtzahl der Personen mit Touchpoints.
* Touchpoints pro Person: Durchschnittliche Anzahl der Touchpoints pro Person, die berührt wurden.

### Touchpoints und Personen, die im Zeitverlauf berührt werden {#touchpoints-and-people-touched-over-time}

Das Balkendiagramm der Zeitreihen zeigt die Anzahl der Touchpoints, Touchpoints für Personen und Touchpoints pro Person für jeden Monat, jedes Quartal und jedes Jahr.

* Verwenden Sie die Drilldown- und Up-Funktionen, um die Daten nach Monat, Quartal oder Jahr zu kategorisieren.
* Bewegen Sie den Mauszeiger über eine Leiste oder Zeile, um detaillierte Informationen anzuzeigen.

Fragen zu den Grafikantworten:

* Wie hat sich die Anzahl der Touchpoints und Personen, die Touch erfahren haben, im Laufe der Zeit verändert?
* Wie unterscheiden sich die Touchpoints pro Person von einem Quartal/Monat zum nächsten?

![](assets/engagement-dashboard-1.png)

### Touchpoints/Personen, die nach Kanal kontaktiert wurden {#touchpoints-people-touched-by-channel}

Balkendiagramm mit Touchpoints oder Touch-Personen, segmentiert nach Kanal/Subkanal/Kampagne.

* Verwenden Sie die Drilldown- und Up-Funktionen, um die Daten nach Subchannel und Campaign zu kategorisieren.
* Bewegen Sie den Mauszeiger über die einzelnen Balken, um die Touchpoints oder Personen anzuzeigen, die berührt wurden.

Fragen zu den Grafikantworten:

* Welcher Kanal/Subkanal/welche Kampagne hat die höchste Interaktion erzielt?
* Wie unterscheidet sich die Anzahl der Touchpoints von Personen, die innerhalb eines bestimmten Kanals/Subkanals/einer bestimmten Kampagne auf einen Kontakt geklickt haben?

![](assets/engagement-dashboard-2.png)

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum (basierend auf dem Touchpoint-Datum)
* Kanal, Subkanal
* Kampagne
