---
description: Keyword-ROI-Dashboard - [!DNL Marketo Measure]  - Produkt
title: Keyword-ROI-Dashboard
feature: Reporting
source-git-commit: 3424f8a63da40f8762defae1e6ae22ebe60530d0
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 3%

---

# Keyword-ROI-Dashboard {#keyword-roi-dashboard}

Das Dashboard &quot;Keyword-ROI&quot;bietet detaillierte Einblicke in die Leistung gebührenpflichtiger Suchkampagnen. Es bietet eine umfassende Analyse der Kosten auf Keyword-Ebene, des zugeordneten Umsatzes sowie der neu generierten Leads und Chancen, um ein klares Verständnis des ROI der Keyword zu gewährleisten.

Fragen zu den Antworten des Dashboards:

* Wie hoch ist der ROI für jeden Suchbegriff in Google Adwords, LinkedIn und Bing Ads?
* Wie werden Kosten und zurechenbarer Umsatz nach einzelnen Suchbegriffen aufgeschlüsselt?
* Wie viele Leads und Möglichkeiten wurden von den einzelnen Keywords erstellt?

## Dashboard-Komponenten {#dashboard-components}

### Suchbegriff-ROI-Zusammenfassungstabelle {#keyword-roi-summary-table}

Tabelle mit zurechenbarem Umsatz, Kosten und ROI, segmentiert nach einzelnen Suchbegriffen, für eine detaillierte Aufschlüsselung.

Führen Sie einen Drilldown in spezifische Suchbegriffe durch, um die von den einzelnen Suchbegriffen beeinflussten Chancen zu sehen.

**Spalten:**

* **Suchbegriff**
* **Kampagne**
* **Anzeigen-Konto-ID** (in Kürze verfügbar)
* **Name des Anzeigenkontos** (in Kürze verfügbar)
* **Anzeigengruppen-ID** (in Kürze verfügbar)
* **Anzeigengruppenname** (in Kürze verfügbar)
* **Kosten**: Gesamtkosten aus verbundenen Datenquellen.
* **Zugewiesener Umsatz**: Der gesamte Umsatzbeitrag, basierend auf dem ausgewählten Attributionsmodell, aus Chancen mit Touchpoints, die innerhalb des gefilterten Datumszeitraums geschlossen wurden.
* **Erzielter zugewiesener Umsatz**: Der Gesamtumsatzbeitrag, der auf Grundlage des ausgewählten Attributionsmodells aus Chancen mit Touchpoints innerhalb des gefilterten Datumszeitraums stammt, unabhängig davon, wann sie geschlossen wurden.
* **Nicht realisierter zugewiesener Pipeline-Umsatz**: Pipeline-Umsatz in Verbindung mit Touchpoints (Offene Möglichkeiten), die innerhalb des gefilterten Datumszeitraums erstellt wurden.
* **Einfacher ROI**: Zugewiesener Umsatz dividiert durch Kosten im gefilterten Datumszeitraum.
* **Realized ROI**: Realisierte, zurechenbare Einnahmen dividiert durch Kosten im gefilterten Datumszeitraum.

### Interessenten und Chancen nach Suchbegriffstabelle {#leads-and-opportunities-by-keyword-table}

Tabelle mit neuen Leads, Chancen und verbundenen Kosten, segmentiert nach einzelnen Keywords, für eine detaillierte Aufschlüsselung.

Führen Sie einen Drilldown in spezifische Suchbegriffe durch, um die von den einzelnen Suchbegriffen beeinflussten Chancen zu sehen.

**Spalten:**

* **Suchbegriff**
* **Kampagne**
* **Anzeigen-Konto-ID** (in Kürze verfügbar)
* **Name des Anzeigenkontos** (in Kürze verfügbar)
* **Anzeigengruppen-ID** (in Kürze verfügbar)
* **Anzeigengruppenname** (in Kürze verfügbar)
* **Kosten**
* **Neue Leads**: Gesamtzahl der neu generierten Leads, einschließlich sowohl berührter als auch unberührter Leads.
* **Kosten pro neuem Lead**: Die durchschnittlichen Kosten pro neuem Lead, abgeleitet aus den Gesamtkosten geteilt durch die Gesamtzahl neuer Leads.
* **Neue Möglichkeiten**: Gesamtzahl der neu geschaffenen Chancen, einschließlich sowohl berührter als auch unberührter Chancen.
* **Kosten pro neuer Chance**: Die durchschnittlichen Kosten pro neuer Chance, abgeleitet aus den Gesamtkosten geteilt durch die Gesamtzahl neuer Chancen.

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum
   * Basierend auf:
      * Erstellungsdatum: News Leads, neue Chancen
      * Anschaffungskosten Datum: Kosten
      * Abschlussdatum: zugeordneter Umsatz (einfacher ROI), Geschäfte
      * Touchpoint-Datum: Touchpoints aus realisiertem, zugeordneten Umsatz (realisierter ROI)
* Attributionsmodell
* Keyword
* Kampagne
