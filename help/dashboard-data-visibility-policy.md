---
description: Beschreibt die Regeln zur Datensichtbarkeit, die in Discover-Dashboards angewendet werden, damit Benutzende verstehen, welche Datensätze enthalten sind
title: Richtlinie zur Dashboard-Datensichtbarkeit
feature: Reporting
exl-id: 5f6f7173-617e-459d-992f-8a8b6c2db7cb
hidefromtoc: 'yes'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: d24e0b99-7796-5c7d-831d-d71a1d725f01
    internal-label: Reporting
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 14%
---
# Richtlinie zur Dashboard-Datensichtbarkeit {#dashboard-data-visibility-policy}

Um in unseren Dashboards ein besseres Erlebnis zu bieten, haben wir Richtlinien zur Datensichtbarkeit für Objekte festgelegt, über die wir berichten. Beachten Sie Folgendes: Wenn Sie sich mit unseren neuen Discover-Dashboards vertraut machen, werden Sie möglicherweise niedrigere Zahlen im Vergleich zu den alten Dashboards feststellen. Dies ist auf eine Änderung unserer Datendarstellungsmethode zurückzuführen, bei der die neuen Dashboards jetzt über spezifische Richtlinien für die Sichtbarkeit verfügen. Im Gegensatz zu unseren alten Discover Dashboards, die alle verfügbaren Daten anzeigen, zeigt die neue Version nur die Daten gemäß der Sichtbarkeitsrichtlinie an. In diesem Artikel soll klargestellt werden, wie Sichtbarkeitsrichtlinien für verschiedene Datenobjekte funktionieren, und es soll sichergestellt werden, dass die Berichte transparent und präzise interpretiert werden.

| Objekt | Sichtbarkeit |
| --- | --- |
| Konto | Dauerhaft |
| Kontakt | Dauerhaft |
| Lead | Dauerhaft |
| User Touchpoints | Letzte 5 Jahre, basierend auf dem Touchpoint-Datum |
| Kosten | Letzte 2 Jahre |
| Konversionsraten | Letzte 2 Jahre |
| Opportunity | Letzte 2 Jahre, basierend auf Opportunity-Abschlussdatum |
| Stadienübergänge (Lead und Opportunity) | Letzte 5 Jahre, basierend auf Übergang im Datum |
| Kampagne | Dauerhaft |
| Kampagnenmitglieder | Letzte 5 Jahre, basierend auf dem Erstellungsdatum des Kampagnenmitglieds |
| CRM-Aufgaben | Letzte 5 Jahre, basierend auf dem Erstellungsdatum der Aufgabe |
| CRM-Ereignisse | Letzte 5 Jahre, basierend auf dem Startdatum des Ereignisses |
| Aktivitäten (Marketo und AEP) | Letzte 5 Jahre, basierend auf dem Ereignisdatum |
| Sessions | Letzte 5 Jahre, basierend auf dem Ereignisdatum |
| Seitenansichten | Letzte 5 Jahre, basierend auf dem Ereignisdatum |
| Formularsendungen | Letzte 5 Jahre, basierend auf dem Ereignisdatum |
