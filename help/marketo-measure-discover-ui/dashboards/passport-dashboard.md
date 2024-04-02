---
description: Passport-Dashboard - [!DNL Marketo Measure] - Produkt
title: Passport-Dashboard
feature: Reporting
exl-id: 0fbd9714-7d9c-4330-b35f-d011e17c3bfe
source-git-commit: 403b31acce25ddc9c1dcafbd53008b6e2868b3df
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 3%

---

# Passport-Dashboard {#passport-dashboard}

Das Passport-Dashboard bietet Marketing-Experten eine dynamische Ansicht von Leads, Kontakten und Möglichkeiten, während sie innerhalb eines bestimmten Zeitraums verschiedene Phasen durchlaufen. Durch Filterung nach einem bestimmten Datum können Benutzer auch eine Momentaufnahme der Datensätze für diesen Tag abrufen.

**Fragen, die die Pinnwand beantwortet:**

* Wie viele Leads, Kontakte oder Möglichkeiten gab es an einem beliebigen Tag in jeder Phase ohne Terminalfenster?
* Wie viele verschiedene Leads oder Kontakte sind während eines bestimmten Zeitraums durch die einzelnen Phasen der Transition fortgeschritten?
   * _Beispiel_: Wäre Lead A am 1.1.2023 in Phase 1 gewesen und bis zum 31.3.2023 auf Stufe 5 erweitert worden, würde die Passport-Analyse Q1 2023 Lead A in den Stufen 1 bis 5 zählen.
* Wie viele einmalige Gelegenheiten haben während eines bestimmten Zeitraums durch die einzelnen Übergangsphasen hinweg gegeben?

## Dashboard-Komponenten {#dashboard-components}

### Möglichkeiten in der Phase nach Staging-Namen {#opportunities-in-stage-by-stage-name}

* Jede Phase zeigt die Anzahl der Möglichkeiten mit Touchpoints, die innerhalb eines bestimmten Zeitraums durch sie geleitet wurden.
   * Wenn eine Gelegenheit innerhalb dieses Zeitraums mehrere Phasen durchläuft, wird sie in jeder Phase gezählt, in der sie vergeht.
* Terminalphasen wie &quot;Geschlossene Gewinne&quot;und &quot;Geschlossene Verluste&quot;sind ausgeschlossen.
* Sowohl das Start- als auch das Enddatum sind inklusive.

![](assets/passport-dashboard-1.png)

### Leads oder Kontakte in der Staging-Umgebung nach Staging-Name {#leads-or-contacts-in-stage-by-stage-name}

* Jede Phase zeigt die Anzahl der Leads oder Kontakte mit Touchpoints, die innerhalb eines bestimmten Zeitraums durch sie geleitet wurden.
   * Ob &quot;Lead&quot;oder &quot;Kontakt&quot;angezeigt werden soll, hängt von der in den Einstellungen > Attributionseinstellungen > Standard-Dashboard-Objekt festgelegten Voreinstellung ab.
   * Wenn ein Lead oder Kontakt innerhalb dieses Zeitraums mehrere Phasen durchläuft, wird er in jeder Phase gezählt, in der er durchläuft.
* Terminalphasen wie &quot;Geschlossene Gewinne&quot;und &quot;Geschlossene Verluste&quot;sind ausgeschlossen.
* Sowohl das Start- als auch das Enddatum sind inklusive.

![](assets/passport-dashboard-2.png)

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum (basierend auf dem Übergangsdatum)
* Kanal, Subkanal
* Kampagne
* Segmente

>[!MORELIKETHIS]
>
>* [Entdecken Sie die Grundlagen von Dashboards](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Dashboard-Richtlinie zur Datenanzeige](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}
