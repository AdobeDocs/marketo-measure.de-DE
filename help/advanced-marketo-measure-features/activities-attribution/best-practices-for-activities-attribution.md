---
description: Best Practices für die Aktivitätszuordnung - [!DNL Marketo Measure]
title: Best Practices für die Aktivitätszuordnung
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Best Practices für die Aktivitätszuordnung {#best-practices-for-activities-attribution}

## Überblick {#overview}

Die [!DNL Marketo Measure] Mit der Funktion &quot;Aktivitätszuordnung&quot;können Kunden Touchpoints aus Aktivitätsdatensätzen in Ihrem CRM erstellen. Diese Methode zum Erstellen von Touchpoints ist flexibel. Damit können Sie Regeln erstellen, die auf den Feldern &quot;Aufgabe&quot; oder &quot;Ereignis&quot; basieren, um Informationen zu erhalten. [!DNL Marketo Measure] welche Aktivität aufzeichnet, aus der Touchpoints erzeugt werden sollen und daher Zuordnungsgutschriften erhalten sollen.

Der häufigste Anwendungsfall für diese Funktion ist das Erstellen von Regeln, die Interaktionen mit Verkäufen in Ihre Touchpoint-Daten des Käufers aufnehmen. Mithilfe der Aktivitätszuordnung können Sie Ihre Verkaufs- und Marketingdaten in einer Journey ausrichten.

Für viele [!DNL Salesforce] -Instanzen kann das Aktivitätsobjekt verschiedene Datensatztypen unterbringen. Daher ist es wichtig, dass Ihre Aktivitätsregeln spezifisch und auf die Datensätze zugeschnitten sind, die Sie in Touchpoints übersetzen möchten. Die folgenden Best Practices helfen Ihnen dabei sicherzustellen, dass Sie über Ihre Aktivitätszuordnung sinnvolle und wertvolle Touchpoints erstellen.

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie zum ersten Mal Aktivitätsregeln definieren oder nur zuvor eingerichtete Aktivitätsregeln überprüfen.

* Einfach starten
   * Identifizieren Sie einige wichtige Aktivitätstypen, die Sie in Ihre [!DNL Marketo Measure] Daten eingeben und dann weitere Typen hinzufügen, sobald Sie sich mit der Zuweisung dieser Touchpoints vertraut machen
   * Wie bereits erwähnt, besteht der primäre Anwendungsfall dieser Funktion darin, Touchpoints zu erstellen, die die Wirksamkeit Ihres Sales Development-Teams verfolgen, insbesondere ausgehende Telefonanrufe und ausgehende E-Mails.

>[!NOTE]
>
>Es ist **NOT** wird empfohlen, Vertriebsaktivitäten zu verfolgen, die nach der Erstellung der Chancen stattfinden, da das Tracking eines Prozesses für Vertriebsmitarbeiter keine großen Einblicke bietet. Das Ziel besteht darin, neben Marketing-Einflüssen den Einfluss der Verkäufe zu verfolgen, in erster Linie bei der Entwicklung einer neuen Opportunity/Pipeline-Generierung.

* Verwenden Sie keine Formelfelder, um Ihre Regeln zu definieren
* Erstellen von Regeln, die spezifisch und präzise sind
   * Die Schwelle für die Erstellung eines Aktivitäts-Touchpoints sollte mit der eines Formulars oder einer Kampagnenmitgliedschaft identisch (oder ähnlich) sein: Antworten auf ausgehende E-Mails oder abgeschlossene Telefonkonversationen
* Neue Regeln immer in validieren [!DNL Salesforce] vor dem Speichern und Verarbeiten
   * Durch das Replizieren der Aktivitätsregeln in einem Berichtstyp &quot;Aufgaben und Ereignisse&quot;erhalten Sie ein klares Verständnis dafür, wie viele Touchpoints von der Regel stammen
* Arbeiten mit Ihrem Sales Opt-Team
   * Wenn Sie das Team einbinden, das am ehesten mit Ihren Aktivitätsdatensätzen oder dem Tool zur Verkaufsförderung zusammenarbeitet, stellen Sie sicher, dass Sie die richtigen Felder zum Definieren Ihrer Regeln verwenden

## Best Practice für die Wartung {#best-practice-for-maintenance}

Durch die Überprüfung Ihrer Aktivitätszuordnungsregeln mindestens zweimal jährlich stellen Sie sicher, dass Ihre Aktivitäts-Touchpoints korrekt und auf dem neuesten Stand sind. Sie möchten sicherstellen, dass diese Regeln keine unerwünschten Touchpoints erstellen, die Ihre Käuferzuordnungsdaten verwässern. Eine Übersicht darüber, wie Ihre Regeln definiert werden, hilft Ihnen und Ihrem Team, sich auf Ihre Aktivitätszuordnung und ihre Rolle in Ihrer [!DNL Marketo Measure] Daten.

Andere Gründe dafür könnten eine Überprüfung Ihrer Aktivitätsregeln Trigger haben...

* Wechsel in Ihrem Marketing-Team
* Änderungen an Feldern, die zur Definition der Aktivitätsdatensätze verwendet werden
* Änderungen oder Aktualisierungen an den Tools zur Verkaufsaktivierung

>[!MORELIKETHIS]
>
>* [Aktivitätszuordnung](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Häufig gestellte Fragen zur Zuordnung von Verkaufsaktivitäten](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
