---
description: Wechsel zu  [!DNL Marketo Measure]  Vollkreisanleitung für Marketo Measure-Benutzer
title: Übergang zu [!DNL Marketo Measure] aus dem vollständigen Kreis
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# Übergang von Kreis zu [!DNL Marketo Measure] {#transitioning-to-marketo-measure-from-full-circle}

Den Wechsel von Full Circle zu [!DNL Marketo Measure]? Du bist nicht allein. Beachten Sie dabei die wichtigsten Aspekte und die Erfahrungen, die wir von anderen Kunden erhalten haben, die diesen Wechsel vollzogen haben.

## Kampagnenbasiertes Tracking im Vergleich zum Tracking mit mehreren Source {#campaign-based-tracking-vs-multi-source-tracking}

Alle Interaktionen in [!UICONTROL Full Circle] werden über die CRM-Kampagnenmitgliedschaft verfolgt. Bei [!DNL Marketo Measure] wird die Kauf-Journey durch eine Kombination unserer JavaScript-, CRM-Kampagnenmitgliedschaft und CRM-Aktivitätsdatensätze kompiliert. Es kann schwierig sein, den mentalen Wechsel weg von „Alle Interaktionen müssen in einer CRM-Kampagne verfolgt werden, damit unsere Attributionsberichte funktionieren“ hin zu „nur diese Untergruppe von Interaktionen muss in einer CRM-Kampagne verfolgt werden, damit unsere Attributionsberichte funktionieren“ zu vollziehen.

Im Allgemeinen wird hier beschrieben, wie [!DNL Marketo Measure] Touchpoint-Datensätze für die wichtigsten Interaktionstypen erstellt:

* Formulare auf Ihren Sites ausfüllen: [!DNL Marketo Measure] JavaScript
* Seitenansichten auf Ihren Sites: Wird von [!DNL Marketo Measure] JavaScript nur erstellt, wenn diese Seitenansicht zu einem bestimmten CRM-Meilenstein geführt hat (z. B. Lead- oder Opportunity-Erstellung)
* Offline-Interaktionen wie Konferenzen oder Messen: CRM-Kampagnenmitgliedschaft
* Digitale Interaktionen, die überall im Internet stattfinden, wo es sich nicht um Ihre Website handelt (z. B. ein auf einer Drittanbieter-Website gehostetes Webinar, das einen Listen-Upload generiert): CRM-Kampagnenmitgliedschaft
* Interaktionen mit dem Vertriebsteam: CRM-Aktivitätseinträge

Wenn Sie mit der CRM-Kampagnenverwaltung vertraut sind und es vorziehen, vorhandene Prozesse beizubehalten, ist das in Ordnung. Es schadet [!DNL Marketo Measure] nicht, weiterhin alle Interaktionen in CRM-Kampagnen zu verfolgen. Sie können eine Logik entwerfen, die nur Touchpoints aus einer gewünschten Untergruppe von Kampagnen erstellt, um eine Duplizierung von Touchpoints zu vermeiden.

## Sichtbarkeit vs. Attribution {#visibility-vs-attribution}

Bei den meisten Full-Circle-Setups sehen Sie jede Interaktion einer Person mit Ihren Marketing- oder Vertriebsaktivitäten. Seitenansichten, wiederholte Seitenbesuche, Mitgliedschaft in dreifach vorhandenen Kampagnen - all dies wird im Vollkreis dargestellt. Wenn Sie eine Seite 300-mal anzeigen, erstellt Full Circle 300 doppelte Kampagnen und gibt Ihnen eine Mitgliedschaft in jeder davon. [!DNL Marketo Measure] nicht, und das war eine bewusste Design-Entscheidung von unserer Seite.

[!DNL Marketo Measure] bietet Ihnen eine Attributionsgeschichte, die aussagekräftige Interaktionen aufzeigt und das Gewicht angemessen auf die wirkungsvollsten Touchpoints verteilt. Beispielsweise zeigt das [!DNL Marketo Measure]-Framework keine Seitenansichten (ohne Formularausfüllungen) als routinemäßige Touchpoints. Eine eigenständige Seitenansicht hat wahrscheinlich keine Auswirkungen darauf, ob ein Kauf-Journey vorangebracht wird. Wir erstellen jedoch einen Touchpoint, wenn es sich um die letzte Interaktion vor einem bestimmten CRM-Meilenstein handelt (z. B. Lead- oder Opportunity-Erstellung). Wir wollen euch nicht alles zeigen. Wir möchten Ihnen die Dinge zeigen, die von einem Attributions-Standpunkt aus wichtig sind.

Arbeiten Sie mit Ihrem [!DNL Marketo Measure] zusammen, um angemessene Erwartungen zu definieren, welche Daten Ihrem Team nicht mehr zur Verfügung stehen werden.

## [!DNL Marketo Measure] Daten {#pre-marketo-measure-data}

Die Standardempfehlung besteht darin, ab dem Tag, an dem Sie [!DNL Marketo Measure] JavaScript bereitgestellt haben, mit dem Reporting und der Datenerfassung zu beginnen. Für ehemalige Full Circle-Kunden bedeutet dies eine Verdoppelung. Denken Sie an die beiden obigen Abschnitte: Sie sind es gewohnt, eine höhere Datenmenge zu sehen, und Sie sind es gewohnt, all diese Daten aus einer CRM-Kampagnenmitgliedschaft zu beziehen. Wenn Sie sich dafür entscheiden, einige oder alle dieser Daten aus vor Ihrer [!DNL Marketo Measure]-Implementierung einzubeziehen, vergleichen Sie Äpfel nicht mit Äpfeln über das JavaScript-Implementierungsdatum hinweg.

Dennoch wissen wir, dass viele Kunden diese historischen Daten benötigen. Insbesondere wenn Sie einen längeren Verkaufszyklus haben (mehr als 90 Tage), möchten Sie vielleicht [!DNL Marketo Measure] Einblick in [!DNL Marketo Measure] Daten geben. Besprechen Sie dies sorgfältig mit Ihrem [!DNL Marketo Measure] und denken Sie immer daran, dass eine Verzerrung über das Implementierungsdatum hinweg zu Verbesserungen oder Rückgängen der Kanalleistung oder Interaktion und anderen möglicherweise falschen Rückschlüssen führen kann.

## Zusammenfassung {#in-summary}

Sie befinden sich in guter Gesellschaft und wir haben zahlreichen anderen Kunden bei der Handhabung dieser Änderungen geholfen. Wenden Sie sich an Ihren [!DNL Marketo Measure], um die oben genannten Auswirkungen und andere mögliche Bedenken zu verstehen.
