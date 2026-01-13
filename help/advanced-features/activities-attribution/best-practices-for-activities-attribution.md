---
description: Best Practices für Attributionsaktivitäten - [!DNL Marketo Measure]
title: Best Practices für die Aktivitätszuordnung
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 4%

---


# Best Practices für die Aktivitätszuordnung {#best-practices-for-activities-attribution}

## Überblick {#overview}

Mit der Attributionsfunktion für [!DNL Marketo Measure] Aktivitäten können Kunden aus Aktivitätsdatensätzen in Ihrem CRM Touchpoints erstellen. Diese Methode zur Erstellung von Touchpoints ist flexibel. Damit können Sie auf der Grundlage von „Aufgabe“- oder „Ereignis“-Feldern Regeln erstellen, um [!DNL Marketo Measure] zu informieren, aus welchen Aktivitätsdatensätzen Touchpoints erzeugt werden sollen, und so Attributionsgutschriften zu erhalten.

Der häufigste Anwendungsfall für diese Funktion besteht darin, Regeln zu erstellen, die Verkaufsinteraktionen in Ihre Käufer-Touchpoint-Daten integrieren. Die Attribution von Aktivitäten ermöglicht es Ihnen, Ihre Verkaufs- und Marketingdaten in einer Journey zusammenzufassen.

In vielen [!DNL Salesforce] kann das Aktivitätsobjekt verschiedene Datensatztypen enthalten. Daher ist es wichtig, dass Ihre Aktivitätsregeln spezifisch und auf die Datensätze zugeschnitten sind, die Sie in Touchpoints übersetzen möchten. Mit den folgenden Best Practices können Sie über Ihre Attributionsaktivitäten aussagekräftige und wertvolle Touchpoints erstellen.

## Best Practices {#best-practice}

Unabhängig davon, ob Sie Aktivitätsregeln zum ersten Mal definieren oder nur zuvor eingerichtete Aktivitätsregeln überprüfen, sollten Sie die folgenden Best Practices beachten.

* Einfach starten
   * Identifizieren Sie einige wichtige Aktivitätstypen, die Sie in Ihre [!DNL Marketo Measure] integrieren möchten, und fügen Sie dann weitere Typen hinzu, wenn Sie sich mit der Zuweisung dieser Touchpoints vertraut machen
   * Wie bereits erwähnt, besteht der primäre Anwendungsfall dieser Funktion darin, Touchpoints zu erstellen, die die Wirksamkeit Ihres Sales Development Teams verfolgen, insbesondere ausgehende Telefonanrufe und ausgehende E-Mails

>[!NOTE]
>Es wird **NICHT** empfohlen, Vertriebsaktivitäten zu verfolgen, die nach der Erstellung der Opportunity erfolgen, da die Verfolgung eines Sales Executives-Prozesses nicht viel insight bietet. Ziel ist es, den Vertriebseinfluss neben dem Marketing-Einfluss zu verfolgen, vor allem bei der Entwicklung einer neuen Opportunity-/Pipeline-Generation

* Verwenden Sie keine Formelfelder, um Ihre Regeln zu definieren
* Erstellen Sie spezifische und präzise Regeln
   * Der Schwellenwert für die Erstellung eines Aktivitäts-Touchpoints sollte mit dem Ausfüllen eines Formulars oder der Kampagnenmitgliedschaft übereinstimmen (oder ähnlich sein): Antworten auf eine ausgehende E-Mail oder abgeschlossene Telefongespräche
* Vor dem Speichern und Verarbeiten neue Regeln in [!DNL Salesforce] immer validieren
   * Durch die Replikation der Aktivitätsregeln in einem Berichtstyp „Aufgaben und Ereignisse“ erhalten Sie ein klares Verständnis davon, wie viele Touchpoints genau aus der Regel stammen
* Arbeiten mit Ihrem Vertriebschancen-Team
   * Wenn Sie das Team einbinden, das Ihrem Aktivitätsdatensatz oder Verkaufs-Aktivierungs-Tool am nächsten ist, stellen Sie sicher, dass Sie die richtigen Felder zum Definieren Ihrer Regeln verwenden

## Best Practices für die Wartung {#best-practice-for-maintenance}

Wenn Sie Ihre Attributionsregeln für Aktivitäten mindestens zweimal jährlich überprüfen, können Sie sicherstellen, dass Ihre Touchpoints für Aktivitäten korrekt und auf dem neuesten Stand sind. Sie sollten sicherstellen, dass diese Regeln keine unerwünschten Touchpoints erzeugen, die Ihre Käuferzuordnungsdaten verwässern. Eine Übersicht über die Definition Ihrer Regeln hilft Ihnen und Ihrem Team, sich mit Ihren Attributionsaktivitäten und ihrer Rolle in Ihren [!DNL Marketo Measure]-Daten vertraut zu machen.

Andere Gründe, die Trigger für eine Überprüfung Ihrer Aktivitätsregeln sein könnten, sind…

* Wechsel in Ihrem Marketing-Team
* Änderungen an Feldern, die zur Definition der Aktivitätsdatensätze verwendet werden
* Änderungen oder Aktualisierungen Ihrer Sales Enablement Tools

>[!MORELIKETHIS]
> [Aktivitäten Attribution](/help/advanced-features/activities-attribution/salesforce-activities-attribution.md)
> [Vertriebsaktivitäten Attribution FAQ](/help/advanced-features/activities-attribution/activities-attribution-faq.md)
