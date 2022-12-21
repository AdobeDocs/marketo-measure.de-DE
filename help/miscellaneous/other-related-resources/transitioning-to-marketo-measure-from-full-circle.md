---
unique-page-id: 18874535
description: Übergang zu [!DNL Marketo Measure] aus dem vollständigen Kreis - [!DNL Marketo Measure] - Produktdokumentation
title: Übergang zu [!DNL Marketo Measure] aus dem vollständigen Kreis
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Übergang zu [!DNL Marketo Measure] aus dem vollständigen Kreis {#transitioning-to-marketo-measure-from-full-circle}

Umstieg vom vollständigen Kreis auf [!DNL Marketo Measure]? Du bist nicht allein. Hier sind die wichtigsten Überlegungen, die Sie beachten sollten, und die Lektionen, die wir von anderen Kunden gelernt haben, die den Wechsel vorgenommen haben.

## Kampagnenbasiertes Tracking im Vergleich zum Multi-Source-Tracking {#campaign-based-tracking-vs-multi-source-tracking}

Alle Interaktionen in [!UICONTROL Vollständiger Kreis] werden über die Mitgliedschaft in einer CRM-Kampagne verfolgt. Mit [!DNL Marketo Measure], wird die Einkaufs-Journey durch eine Kombination unserer JavaScript-, CRM-Kampagnenmitgliedschaften und CRM-Aktivitätsdatensätze kompiliert. Es kann schwierig sein, die mentale Umstellung von &quot;Alle Interaktionen müssen in einer CRM-Kampagne nachverfolgt werden, damit unser Attributionsbericht funktioniert&quot;auf &quot;nur diese Untergruppe von Interaktionen muss in einer CRM-Kampagne nachverfolgt werden, damit unsere Attributionsberichterstellung funktioniert&quot;vorzunehmen.

Allgemein gesagt, wie [!DNL Marketo Measure] erstellt Touchpoint-Datensätze für die wichtigsten Interaktionstypen:

* Ausfüllen des Formulars auf Ihrer Website: [!DNL Marketo Measure] JavaScript
* Seitenansichten Ihrer Site(s): Erstellt von [!DNL Marketo Measure] JavaScript nur dann verwenden, wenn diese Seitenansicht einen bestimmten CRM-Meilenstein (z. B. Lead- oder Opportunity-Erstellung) verursacht hat
* Offline-Interaktionen wie Konferenzen oder Messen: Mitgliedschaft in einer CRM-Kampagne
* Digitale Interaktionen, die überall im Internet stattfinden, wo Ihre Site nicht vorkommt (z. B. ein Webinar, das auf einer Drittanbieter-Website gehostet wird, die einen Listen-Upload generiert): Mitgliedschaft in einer CRM-Kampagne
* Interaktionen mit Ihrem Vertriebsteam: CRM-Aktivitätsdatensätze

Wenn Sie sich mit der Verwaltung Ihrer CRM-Kampagnen auskennen und bestehende Prozesse beibehalten möchten, ist das in Ordnung. Es tut nicht weh [!DNL Marketo Measure] um weiterhin alle Interaktionen in CRM-Kampagnen zu verfolgen. Sie können eine Logik entwerfen, die nur Touchpoints aus einer gewünschten Untergruppe von Kampagnen erstellt, um eine Touchpoint-Duplizierung zu vermeiden.

## Sichtbarkeit vs. Attribution {#visibility-vs-attribution}

Bei den meisten &quot;Full Circle&quot;-Setups sehen Sie jede einzelne Interaktion, die eine Person mit Ihren Marketing- oder Verkaufsbemühungen hat. Seitenansichten, wiederholte Seitenbesuche, Mitgliedschaft in doppelten und doppelten Kampagnen - Vollständiger Kreis deckt all diese Kampagnen auf. Wenn Sie eine Seite 300-mal anzeigen, erstellt Full Circle 300 doppelte Kampagnen und gibt Ihnen eine Mitgliedschaft in jeder dieser Kampagnen. [!DNL Marketo Measure] nicht, und das war eine bewusste Designentscheidung von unserer Seite.

[!DNL Marketo Measure] soll Ihnen eine Attributionsgeschichte vermitteln, die aussagekräftige Interaktionen offenbart und die Gewichtung entsprechend auf die wirkungsvollsten Touchpoints verteilt. Beispiel: die [!DNL Marketo Measure] -Framework zeigt keine Seitenansichten (ohne Formularelemente) als routinemäßige Touchpoints an. Eine eigenständige Seitenansicht wirkt sich wahrscheinlich nicht darauf aus, eine Einkaufs-Journey vorwärts zu treiben. Wir erstellen jedoch einen Touchpoint, wenn es sich um die neueste Interaktion vor einem festgelegten CRM-Meilenstein (z. B. Lead- oder Opportunity Creation) handelt. Wir wollen Ihnen nicht alles zeigen. Wir möchten Ihnen das Wichtige aus der Sicht der Attribution zeigen.

Arbeiten mit [!DNL Marketo Measure] rep , um angemessene Erwartungen darüber zu setzen, welche Daten Ihrem Team nicht mehr zur Verfügung stehen.

## Pre-[!DNL Marketo Measure] Daten {#pre-marketo-measure-data}

Es wird empfohlen, mit der Berichterstellung und Datenerfassung ab dem Tag der Bereitstellung der [!DNL Marketo Measure] JavaScript in die Zukunft versetzt, was bei früheren Full Circle-Kunden doppelt so hoch ist. Beachten Sie die beiden obigen Abschnitte: Sie sind es gewohnt, eine höhere Datenmenge zu sehen, und Sie sind an alle diese Daten aus der Mitgliedschaft in CRM-Kampagnen gewöhnt. Wenn Sie sich dafür entscheiden, einige oder alle dieser Daten aus der vorherigen [!DNL Marketo Measure] -Implementierung verwenden, vergleichen Sie Äpfel nicht mit Äpfeln während des gesamten JavaScript-Implementierungsdatums.

Wir verstehen jedoch, dass viele Kunden diese historischen Daten benötigen. insbesondere wenn Sie einen längeren Verkaufszyklus (mehr als 90 Tage) haben, sollten Sie [!DNL Marketo Measure] Sichtbarkeit in der Vorstufe[!DNL Marketo Measure] Daten. Diskutieren Sie dies sorgfältig mit Ihrem [!DNL Marketo Measure] rep und beachten Sie immer, dass eine Verzögerung des Implementierungsdatums zu Verbesserungen oder Rückgängen der Kanalleistung oder -interaktion sowie zu anderen möglicherweise falschen Ergebnissen führen kann.

## Zusammenfassung {#in-summary}

Sie sind in guter Gesellschaft, und wir haben vielen anderen Kunden geholfen, diese Änderungen zu bewältigen. Arbeiten mit [!DNL Marketo Measure] beraten Sie sich, um die oben genannten Auswirkungen sowie alle sonstigen Bedenken zu verstehen, die Sie möglicherweise haben.
