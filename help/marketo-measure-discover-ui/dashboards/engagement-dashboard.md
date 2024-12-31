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

Das Interaktions-Dashboard verfolgt die Metriken der Benutzerinteraktion sorgfältig. Es zeigt Touchpoints, die Anzahl der interagierenden Personen und die durchschnittlichen Touchpoints pro Person. Verwenden Sie das Zeitreihen-Balkendiagramm für eine monatliche, vierteljährliche oder jährliche Ansicht und das Balkendiagramm für detaillierte Kanal-, Unterkanal- und Kampagnen-Insights. Dieses Tool ist wichtig, um Interaktionsmuster zu verstehen und Ihre Interaktionsstrategien zu optimieren.

Wir verfolgen jede Kundeninteraktion als Benutzer-Touchpoints (UTs), die „rohen“ erfassten Datenpunkte, die als Grundlage für Interaktionsmetriken auf unserem Dashboard dienen. Nicht alle UTs entwickeln sich zu Buyer Touchpoints (BT) oder Buyer Attribution Touchpoints (BAT), da dies ausgewählte Ergebnisse sind, um bestimmte Kundeninteraktionen umsatzbezogenen Aktivitäten zuzuordnen. Beachten Sie, dass sich Unterdrückungsregeln nicht auf UTS oder das Interaktions-Dashboard auswirken.

* **Benutzer-Touchpoints**: Touchpoints, die aus allen Interaktionen erstellt werden.
* **Käufer-Touchpoints**: Touchpoints ausgewählt für Lead- und Kontaktzuordnung. BT sind nicht mit Opportunities verknüpft und haben keinen zugehörigen Umsatz.
* **Attribution-Touchpoints des Käufers**: Touchpoints für die Attribution von Opportunities ausgewählt. BAT wirkt sich auf den Umsatz aus, da sie mit Opportunitys verknüpft sind.

Die Verwendung von nur BT oder BAT zur Messung der Interaktion würde das wahre Ausmaß der Kundeninteraktionen unterbewerten, da die Interaktion breiter ist als nur die Attribution.

Fragen, die das Dashboard beantwortet:

* Wie viele Leute waren verlobt? Wie viele Kontakte hat eine interagierende Person im Durchschnitt?
* Wie hoch ist die Anzahl der Touchpoints im Vergleich zu Personen, die innerhalb eines bestimmten Kanals/Unterkanals/einer bestimmten Kampagne kontaktiert wurden?
* Wie viele Touchpoints gab es in einem bestimmten Kanal oder Unterkanal? Wie hat sie sich im Laufe der Zeit verändert?

>[!NOTE]
>
>Account- und Opportunity-Interaktionsmetriken sind für die Veröffentlichung im ersten Halbjahr 2024 geplant.

## Dashboard-Komponenten {#dashboard-components}

### KPI-Kacheln {#kpi-tiles}

* Touchpoints: Die Gesamtzahl der generierten rohen Touchpoints.
   * Käufer-Touchpoints und Käufer-Attribution-Touchpoints sind Attributionsergebnisse, die durch die Auswahl bestimmter Touchpoints für eine Gutschrift erstellt werden. Nicht alle Touchpoints sind als BT und BAT ausgewählt.
* Kontaktierte Personen: Die Gesamtzahl der Personen mit Touchpoints.
* Touchpoints pro Person: Durchschnittliche Anzahl an Touchpoints pro Person, die kontaktiert wurden.

### Kontaktpunkte und Personen im Zeitverlauf {#touchpoints-and-people-touched-over-time}

Das Zeitreihen-Balkendiagramm zeigt die Anzahl der Touchpoints, Personen, die kontaktiert wurden, und Touchpoints pro Person für jeden Monat, jedes Quartal und jedes Jahr an.

* Verwenden Sie die Aufschlüsselungs- und Nach-oben-Funktionen, um die Daten nach Monat, Quartal oder Jahr zu kategorisieren.
* Bewegen Sie den Mauszeiger über einen Balken oder eine Linie, um detaillierte Informationen anzuzeigen.

Fragen, die in der Tabelle beantwortet werden:

* Wie hat sich die Anzahl der Touchpoints und Personen, die kontaktiert werden, im Laufe der Zeit entwickelt?
* Wie sehen die Kontaktpunkte pro Person im Vergleich von einem Quartal/Monat zum nächsten aus?

![](assets/engagement-dashboard-1.png)

### Touchpoints/Personen, die über einen Kanal kontaktiert werden {#touchpoints-people-touched-by-channel}

Balkendiagramm mit Touchpoints oder nach Kanal/Unterkanal/Kampagne segmentierten Kontakten.

* Verwenden Sie die Drilldown- und Nach-oben-Funktionen, um die Daten nach Unterkanal und Kampagne zu kategorisieren.
* Bewegen Sie den Mauszeiger über jede Leiste, um die Touchpoints oder Personen mit Touchpoints anzuzeigen.

Fragen, die in der Tabelle beantwortet werden:

* Welcher Kanal/Unterkanal/welche Kampagne führte zu der größten Interaktion?
* Wie hoch ist die Anzahl der Touchpoints im Vergleich zu Personen, die innerhalb eines bestimmten Kanals/Unterkanals/einer bestimmten Kampagne kontaktiert wurden?

![](assets/engagement-dashboard-2.png)

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum (basierend auf Touchpoint-Datum)
* Kanal, Unterkanal
* Kampagne
