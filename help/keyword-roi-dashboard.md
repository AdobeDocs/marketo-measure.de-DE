---
description: Keyword ROI Dashboard - [!DNL Marketo Measure] - Produkt
title: Keyword-ROI-Dashboard
feature: Reporting
exl-id: 9c85a3ad-1806-4e30-b0fb-686760aea587
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---

# Keyword-ROI-Dashboard {#keyword-roi-dashboard}

Das Dashboard „Keyword-ROI“ bietet detaillierte Einblicke in die Leistung von Kampagnen mit Paid Search. Es bietet eine umfassende Analyse der Kosten auf Keyword-Ebene, des zugeordneten Umsatzes und der neu generierten Leads und Chancen und stellt so ein klares Verständnis des Keyword-ROI sicher.

Fragen, die das Dashboard beantwortet:

* Wie hoch ist der ROI für jedes Keyword in Google Adwords, LinkedIn und Bing Ads?
* Wie werden die Kosten und die zugeordneten Einnahmen nach einzelnen Keywords aufgeschlüsselt?
* Wie viele Leads und Chancen wurden aus jedem Keyword erstellt?

## Dashboard-Komponenten {#dashboard-components}

### Zusammenfassungstabelle für Schlüsselwort-ROI {#keyword-roi-summary-table}

Tabelle mit zugewiesenen Einnahmen, Kosten und ROI, segmentiert nach einzelnen Keywords, für eine detaillierte Aufschlüsselung.

Schlüsseln Sie die einzelnen Keywords auf, um die von ihnen beeinflussten Opportunities anzuzeigen.

**Spalten:**

* **Keyword**
* **Kampagne**
* **Werbekonto-ID**
* **Ad-Kontoname**
* **Anzeigengruppen-ID**
* **Anzeigengruppenname**
* **Kosten**: Gesamtkosten aus verbundenen Datenquellen.
* **Attributierter Umsatz**: Der Gesamtumsatzbeitrag, basierend auf dem ausgewählten Attributionsmodell, von Opportunities mit Touchpoints, die innerhalb des gefilterten Datumszeitraums geschlossen wurden
* **Realisierter zugewiesener Umsatz**: Der Gesamtumsatzbeitrag, basierend auf dem ausgewählten Attributionsmodell, von Opportunitys mit Touchpoints innerhalb des gefilterten Datumszeitraums, unabhängig davon, wann sie geschlossen wurden.
* **Nicht realisierter zugewiesener Pipeline-Umsatz**: Pipeline-Umsatz in Verbindung mit Touchpoints (offene Vertriebschancen), die innerhalb des gefilterten Datumszeitraums erstellt wurden.
* **Einfacher ROI**: Attributierter Umsatz dividiert durch die Kosten in der gefilterten Datumsperiode.
* **Realisierter ROI**: Realisierter zugewiesener Umsatz dividiert durch die Kosten im gefilterten Datumsbereich.

### Leads und Vertriebschancen nach Schlüsselwort-Tabelle {#leads-and-opportunities-by-keyword-table}

Tabelle mit neuen Leads, Vertriebschancen und zugehörigen Kosten, die nach einzelnen Keywords segmentiert sind, für eine detaillierte Aufschlüsselung.

Schlüsseln Sie die einzelnen Keywords auf, um die von ihnen beeinflussten Opportunities anzuzeigen.

**Spalten:**

* **Keyword**
* **Kampagne**
* **Werbekonto-ID**
* **Ad-Kontoname**
* **Anzeigengruppen-ID**
* **Anzeigengruppenname**
* **Kosten**
* **Neue Leads**: Gesamtzahl der neu generierten Leads, einschließlich sowohl kontaktierter als auch nicht kontaktierter Leads.
* **Kosten pro neuem Lead**: Die durchschnittlichen Kosten pro neuem Lead, abgeleitet von den Gesamtkosten dividiert durch die Gesamtzahl neuer Leads.
* **Neue Opportunitys**: Gesamtzahl der neu generierten Opportunitys, einschließlich sowohl kontaktierter als auch unberührter Opportunitys.
* **Kosten pro neuer Opportunity**: Die durchschnittlichen Kosten pro neuer Opportunity, abgeleitet von den Gesamtkosten dividiert durch die Gesamtzahl neuer Opportunitys.

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum
   * Basierend auf:
      * Erstellungsdatum: Leads, neue Opportunities
      * Anfallsdatum für Kosten: Kosten
      * Abschlussdatum: Attributierter Umsatz (einfacher ROI), Abschlüsse
      * Touchpoint-Datum: Touchpoints aus realisiertem zugeordneten Umsatz (realisierter ROI)
* Attributionsmodell
* Keyword
* Kampagne
