---
unique-page-id: 18874535
description: Übergang zu  [!DNL Marketo Measure]  vom vollständigen Kreis - [!DNL Marketo Measure]
title: Übergang zu [!DNL Marketo Measure] aus dem vollständigen Kreis
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Übergang vom vollständigen Kreis zu [!DNL Marketo Measure] {#transitioning-to-marketo-measure-from-full-circle}

Wechseln Sie vom vollständigen Kreis zu [!DNL Marketo Measure]? Du bist nicht allein. Hier sind die wichtigsten Überlegungen, die Sie beachten sollten, und die Lektionen, die wir von anderen Kunden gelernt haben, die den Wechsel vorgenommen haben.

## Kampagnenbasiertes Tracking im Vergleich zum Tracking mit mehreren Source {#campaign-based-tracking-vs-multi-source-tracking}

Alle Interaktionen im vollen Kreis  werden durch die Mitgliedschaft in einer CRM-Kampagne verfolgt. Mit [!DNL Marketo Measure] wird die Einkaufs-Journey durch eine Kombination unserer Datensätze zu JavaScript, CRM-Kampagnen und CRM-Aktivitäten kompiliert. Es kann schwierig sein, die mentale Umstellung von &quot;Alle Interaktionen müssen in einer CRM-Kampagne nachverfolgt werden, damit unser Attributionsbericht funktioniert&quot;auf &quot;nur diese Untergruppe von Interaktionen muss in einer CRM-Kampagne nachverfolgt werden, damit unsere Attributionsberichterstellung funktioniert&quot;vorzunehmen.

Im Allgemeinen erstellt [!DNL Marketo Measure] Touchpoint-Datensätze für die wichtigsten Interaktionstypen:

* Ausfüllen von Formularen auf Ihren Sites: [!DNL Marketo Measure] JavaScript
* Seitenansichten auf Ihren Sites: Erstellt von [!DNL Marketo Measure] JavaScript nur, wenn diese Seitenansicht einen festgelegten CRM-Meilenstein (z. B. Lead- oder Opportunity-Erstellung) verursacht hat
* Offline-Interaktionen wie Konferenzen oder Messen: Mitgliedschaft in CRM-Kampagnen
* Digitale Interaktionen, die überall im Internet stattfinden, wo nicht Ihre Site ist (z. B. ein Webinar, das auf einer Drittanbieter-Website gehostet wird, die einen Listen-Upload generiert): CRM-Kampagnenmitgliedschaft
* Interaktionen mit dem Sales-Team: Datensätze zu CRM-Aktivitäten

Wenn Sie sich mit der Verwaltung von CRM-Kampagnen auskennen und bestehende Prozesse beibehalten möchten, ist das in Ordnung. Es tut [!DNL Marketo Measure] nicht weh, weiterhin alle Interaktionen in CRM-Kampagnen zu verfolgen. Sie können eine Logik entwerfen, die nur Touchpoints aus einer gewünschten Untergruppe von Kampagnen erstellt, um eine Touchpoint-Duplizierung zu vermeiden.

## Sichtbarkeit vs. Attribution {#visibility-vs-attribution}

Bei den meisten &quot;Full Circle&quot;-Setups sehen Sie jede Interaktion, die eine Person mit Ihren Marketing- oder Verkaufsbemühungen hat. Seitenansichten, wiederholte Seitenbesuche, Mitgliedschaft in dreifachen Kampagnen - Vollständiger Kreis deckt all diese Bereiche auf. Wenn Sie eine Seite 300-mal anzeigen, erstellt Full Circle 300 doppelte Kampagnen und gibt Ihnen eine Mitgliedschaft in jeder dieser Kampagnen. [!DNL Marketo Measure] nicht, und das war eine bewusste Designentscheidung von unserer Seite.

[!DNL Marketo Measure] zielt darauf ab, Ihnen eine Zuordnungsgeschichte zu liefern, die aussagekräftige Interaktionen offenbart und die Gewichtung entsprechend auf die wirkungsvollsten Touchpoints verteilt. Das Framework [!DNL Marketo Measure] beispielsweise deckt keine Seitenansichten (ohne Formularelemente) als routinemäßige Touchpoints auf. Eine eigenständige Seitenansicht wirkt sich wahrscheinlich nicht auf die Weiterentwicklung einer Einkaufs-Journey aus. Wir erstellen jedoch einen Touchpoint, wenn dies die letzte Interaktion vor einem bestimmten CRM-Meilenstein (z. B. Lead- oder Opportunity Creation) ist. Wir wollen Ihnen nicht alles zeigen. Wir möchten Ihnen das Wichtige aus der Sicht der Attribution zeigen.

Arbeiten Sie mit Ihrem [!DNL Marketo Measure] -Rep zusammen, um angemessene Erwartungen darüber zu setzen, welche Daten Ihrem Team nicht mehr zur Verfügung stehen.

## Pre-[!DNL Marketo Measure] Daten {#pre-marketo-measure-data}

Es wird empfohlen, mit der Berichterstellung und Datenerfassung ab dem Tag zu beginnen, an dem Sie die [!DNL Marketo Measure] JavaScript bereitgestellt haben. Dies gilt für frühere Full Circle-Kunden. Denken Sie an die beiden obigen Abschnitte: Sie sind es gewohnt, eine höhere Datenmenge zu sehen, und Sie sind an alle diese Daten aus der Mitgliedschaft in CRM-Kampagnen gewöhnt. Wenn Sie sich dafür entscheiden, einige oder alle dieser Daten aus der Zeit vor Ihrer [!DNL Marketo Measure]-Implementierung einzubeziehen, vergleichen Sie Äpfel nicht über das JavaScript-Implementierungsdatum hinweg mit Äpfeln.

Dennoch wissen wir sicherlich, dass viele Kunden diese historischen Daten benötigen. Insbesondere wenn Sie einen längeren Verkaufszyklus (mehr als 90 Tage) haben, sollten Sie [!DNL Marketo Measure] Einblicke in Daten vor [!DNL Marketo Measure] geben. Besprechen Sie dies sorgfältig mit Ihrem [!DNL Marketo Measure] -Rep und beachten Sie immer, dass eine Verzögerung während des Implementierungsdatums zu Verbesserungen oder Rückgängen der Kanalleistung oder -interaktion und anderen möglicherweise falschen Rückschlüssen führen kann.

## Zusammenfassung {#in-summary}

Sie sind in guter Gesellschaft, und wir haben vielen anderen Kunden geholfen, diese Änderungen zu bewältigen. Arbeiten Sie mit Ihrem [!DNL Marketo Measure] -Rep zusammen, um die oben genannten Auswirkungen und sonstigen Bedenken zu verstehen, die Sie möglicherweise haben.
