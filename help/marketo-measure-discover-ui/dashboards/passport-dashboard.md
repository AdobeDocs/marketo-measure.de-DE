---
description: Passport-Dashboard - [!DNL Marketo Measure] - Produkt
title: Passport-Dashboard
hide: true
hidefromtoc: true
feature: Reporting
source-git-commit: b3d4ea085d851908d52fb62fe58d860ae5c09099
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 1%

---

# Passport-Dashboard {#passport-dashboard}

Das Passport-Dashboard bietet Marketing-Experten eine dynamische Ansicht von Leads, Kontakten und Möglichkeiten, während sie innerhalb eines bestimmten Zeitraums verschiedene Phasen durchlaufen. Durch Filterung nach einem bestimmten Datum können Benutzer auch eine Momentaufnahme der Datensätze für diesen Tag abrufen.

>[!NOTE]
>
>Dieses Dashboard befindet sich derzeit in der Betaversion. Während dieser Übergangsphase werden sowohl die aktuellen als auch die neuen Dashboards verfügbar sein. Das aktuelle Dashboard wird nicht mehr unterstützt, sobald wir die optimale Funktionalität vollständig übernommen und sichergestellt haben.

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

### Kontakte in der Phase nach Staging-Name {#contacts-in-stage-by-stage-name}

* Jede Phase zeigt die Anzahl der Leads oder Kontakte mit Touchpoints, die innerhalb eines bestimmten Zeitraums durch sie geleitet wurden.
   * Ob &quot;Lead&quot;oder &quot;Kontakt&quot;angezeigt werden soll, hängt von der in den Einstellungen > Attributionseinstellungen > Standard-Dashboard-Objekt festgelegten Voreinstellung ab.
   * Wenn ein Lead oder Kontakt innerhalb dieses Zeitraums mehrere Phasen durchläuft, wird er in jeder Phase gezählt, in der er durchläuft.
* Terminalphasen wie &quot;Geschlossene Gewinne&quot;und &quot;Geschlossene Verluste&quot;sind ausgeschlossen.
* Sowohl das Start- als auch das Enddatum sind inklusive.

![](assets/passport-dashboard-2.png)

## Filterbereich {#filter-pane}

Dieses Dashboard verfügt über die folgenden Einstellungen und Filter:

* Datum (basierend auf dem Übergangsdatum)
* Attributionsmodell
* Kanal, Subkanal
* Kampagne
* Segmente

>[!MORELIKETHIS]
>
>[Dashboard-Grundlagen](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
