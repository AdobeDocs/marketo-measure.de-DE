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

Das Pass-Dashboard bietet Marketing-Experten eine dynamische Ansicht von Leads, Kontakten und Opportunities beim Übergang durch verschiedene Stadien innerhalb eines bestimmten Zeitraums. Durch Filtern nach einem bestimmten Datum können Benutzer auch eine Momentaufnahme der Datensätze für diesen Tag abrufen.

**Fragen, die das Board beantwortet:**

* Wie viele Leads, Kontakte oder Opportunities gab es in jeder nicht-terminalen Phase an einem ausgewählten Tag?
* Wie viele verschiedene Leads oder Kontakte haben während eines bestimmten Zeitraums in jedem Übergangsstadium den Vorgang durchlaufen?
   * _Beispiel_: Wenn sich Lead A am 1/1/2023 in Phase 1 befand und bis 3/31/2023 auf Stufe 5 vorrückte, würde die Passanalyse für das 1. Quartal 2023 Lead A in den Stufen 1 bis 5 zählen.
* Wie viele einzigartige Opportunitys wurden in einem bestimmten Zeitraum durch jede Übergangsphase geleitet?

## Dashboard-Komponenten {#dashboard-components}

### Vertriebschancen in Phase nach Name des Stadiums {#opportunities-in-stage-by-stage-name}

* Jedes Stadium zeigt die Anzahl der Opportunitys mit Touchpoints, die in einem bestimmten Zeitraum durchlaufen wurden.
   * Wenn eine Opportunity innerhalb dieses Zeitraums mehrere Stadien durchläuft, wird sie in jedem Stadium gezählt, das sie durchläuft.
* Terminalphasen wie „Closed Won“ und „Closed Lost“ sind ausgeschlossen.
* Start- und Enddatum sind inklusive.

![](assets/passport-dashboard-1.png)

### Leads oder Kontakte in der Phase nach Name der Phase {#leads-or-contacts-in-stage-by-stage-name}

* In jedem Schritt wird die Anzahl der Leads oder Kontakte mit Touchpoints angezeigt, die in einem bestimmten Zeitraum durchlaufen wurden.
   * Ob „Lead“ oder „Kontakt“ angezeigt werden soll, hängt von den Voreinstellungen ab, die in festgelegt sind: Einstellungen > Attributionseinstellungen > Standard-Dashboard-Objekt.
   * Wenn ein Lead oder Kontakt in diesem Zeitraum mehrere Phasen durchläuft, wird er in jedem Schritt gezählt, den er durchläuft.
* Terminalphasen wie „Closed Won“ und „Closed Lost“ sind ausgeschlossen.
* Start- und Enddatum sind inklusive.

![](assets/passport-dashboard-2.png)

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum (basierend auf Übergangsdatum)
* Kanal, Unterkanal
* Kampagne
* Segmente

>[!MORELIKETHIS]
>
>* [Entdecken Sie die Grundlagen von Dashboards](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Richtlinie für die Datensichtbarkeit im Dashboard](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}
