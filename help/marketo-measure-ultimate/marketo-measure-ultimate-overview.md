---
description: '[!DNL Marketo Measure] Ultimate Overview - [!DNL Marketo Measure] - Produktdokumentation'
title: '[!DNL Marketo Measure] Ultimate - Übersicht'
exl-id: fada9479-0671-4698-8043-c67d7977577b
source-git-commit: 59d42e5065ec0db7143208743fd053f5e6c1af7b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 1%

---

# [!DNL Marketo Measure] Ultimate - Übersicht {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (ehemals Bizible) gibt Marketing-Experten Einblicke, welche Marketing-Maßnahmen bei der Steigerung des Umsatzes und der Maximierung der Kapitalrendite für ihr Unternehmen am effektivsten sind. [!DNL Marketo Measure] ist eine Marketing-Attributionslösung, die automatisch verfolgt und Berichte zur Kanalleistung erstellt, Einblicke in die Kanäle bietet, die die Kundeninteraktion am meisten fördern, und es Ihnen ermöglicht, Ihre Marketing-Ausgaben entsprechend zu optimieren.

[!DNL Marketo Measure Ultimate] enthält die zusätzlichen Funktionen:

* Erfassen Sie Daten aus nahezu jeder Datenquelle sowie aus mehreren Datenquellen desselben Typs, um alle Ihre Daten für die Attribution einzubringen.
   * Verwendung mit nahezu jedem CRM, nicht nur Salesforce und Dynamics.
   * Verbinden mehrerer CRM-Instanzen und/oder MAP-Instanzen mit einer Instanz [!DNL Marketo Measure] -Instanz.
   * Einbinden von Drittanbieter-Webinar-Registrierungs- und Beitragsdaten.

* Transformieren Sie Ihre Daten mit großer Flexibilität durch Feldzuordnungs- und -umwandlungsfunktionen, um die richtige Datenform zu gewährleisten.

* Machen Sie Zuordnungseinblicke über das enthaltene Data Warehouse für externe Anwendungen verfügbar, um die Einblicke in Ihren Workflow zu integrieren. Detailliertere Ergebnisdaten und BI-basierte Berichte, einschließlich Snowflake-Data Warehouse, die Zugriff auf granulare Ergebnisdaten und die Möglichkeit bietet, jedes BI-Tool für Analysen und Berichte zu verwenden.

* Integration mit RTCDP (B2B oder B2P Edition), die eine integrierte B2B-Zuordnungslösung für RTCDP-Kunden als RTCDP-Kunden bietet und [!DNL Marketo Measure] Beide arbeiten aus zentralen Adobe Experience Platform-Daten (AEP).

**[!DNL Marketo Measure]Ebenen 1-3**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## Neue Funktionen in [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**Importieren von B2B-Daten über AEP**

Von Marketingexperten wird erwartet, dass sie ihre B2B-Daten (z. B. Konto, Chancen, Kontakt, Lead, Kampagne, Kampagnenmitglied, Aktivität) über AEP übermitteln. Die direkten CRM- und Marketo Engage-Verbindungen sind für Ultimate nicht mehr verfügbar. Marketingexperten werden weiterhin Ad Platform-Daten über direkte Verbindungen und Tracking-Webaktivitäten über [!DNL Marketo Measure] JavaScript.

![](assets/marketo-measure-ultimate-overview-3.png)

**Standardwährungseinstellung**

[!DNL Marketo Measure Ultimate] setzt die Standardwährung auf USD, bis der Benutzer sie ändert. Durch das Festlegen einer neuen Standardwährung werden die Daten ohne erneute Verarbeitung aktualisiert. Solange die ausgewählte Währung als ISO-Zielcode vorhanden ist, müssen keine Konversionsraten übermittelt werden.

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]Sandbox**

[!DNL Marketo Measure Ultimate] -Instanz muss einer AEP-Sandbox zugeordnet sein, bevor die [!DNL Marketo Measure] Zieldatenflüsse in AEP.

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] Die Produktionsinstanz muss einer AEP-Produktions-Sandbox, einer [!DNL Marketo Measure Ultimate] -Entwicklerinstanz einer AEP-Entwickler-Sandbox zugeordnet werden.

Sobald die Auswahl der Sandbox-Zuordnung gespeichert wurde, können Sie sie derzeit nicht mehr in der Anwendung ändern. Um es zu ändern, wenden Sie sich bitte an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Daten für eine bestimmte Entität (z. B. Konto) aus einer bestimmten Datenquelle können nur in einen Datensatz übertragen werden. Jeder Datensatz kann nur in einem Datenfluss enthalten sein. Verstöße stoppen den Datenfluss zur Laufzeit.

![](assets/marketo-measure-ultimate-overview-5.png)

**Kartierung der Stadien**

Alle [!DNL Marketo Measure Ultimate] -Regeln sind datasetspezifisch. Die Regeln für die Staging-Zuordnung müssen für alle Datensätze und alle ausgewählten Phasen erstellt werden.

Es gibt sechs integrierte Phasen:

* Lead-Verlust
* Lead-Öffnung
* Lead konvertiert
* Chancen verloren
* Opportunity Open
* Opportunity Gewonnen

Die Abschnitte &quot;Lost&quot;, &quot;Won&quot;und &quot;Converted&quot;erlauben keine benutzerdefinierten Bühnen. Quelldaten können jedoch den integrierten Phasen &quot;Lost/Won/Converted&quot;zugeordnet werden, indem die Zuordnungsregel aktualisiert wird.

Benutzerdefinierte Bühnen können nur für offene Abschnitte definiert werden.
CRM-Bühnen werden nicht mehr automatisch in das Staging-Mapping einbezogen.

Vier integrierte Phasen müssen Regeln zugeordnet werden (Zuordnungsregeln für die beiden anderen, Lead-Verlust und Lead-Konvertierung, sind optional):

* Lead-Öffnung
* Chancen verloren
* Opportunity Open
* Opportunity Gewonnen

Regelbedingungen sind Datensatzspezifisch. Staging-Zuordnungsregeln müssen für alle Datensätze und alle Phasen erstellt werden, mit Ausnahme von &quot;Lead verloren&quot;und &quot;Lead konvertiert&quot;.

Keine Auswahl für Trichter vs. Bomerang vs. benutzerdefiniertes Modell. Alle Bühnen werden für Trichter, Bumerang und benutzerdefiniertes Modell ausgewählt. Es gibt eine Grenze dafür, wie viele Phasen wir unterstützen: 15 benutzerdefinierte und 6 integrierte Phasen.

![](assets/marketo-measure-ultimate-overview-6.png)

Touchpoint-Regeln für Campaign-Mitglieder und Touchpoint-Regeln für Aktivitäten sind datasetspezifisch.

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

Attributions-Touchpoints werden nicht in CRM geschrieben, da Ultimate über keine direkte CRM-Verbindung verfügt.

[!DNL Marketo Measure] ABM ML-Dienste (Lead-to-Account Matching und Predictive Engagement Score) sind nicht verfügbar für [!DNL Marketo Measure Ultimate]. Sie finden diese Dienste kostenlos in der RT-CDP B2B Edition.

## Einschränkungen {#limitations}

* Für Datenumwandlungsregeln stehen derzeit nur begrenzte Felder zur Verfügung.
* Für bestehende Tier 1/2/3-Benutzer gibt es keinen Migrationspfad. Erfordert eine neue Implementierung, aber wir helfen Ihnen dabei, die getrackten Web-Aktivitätsdaten von der vorhandenen Instanz zu migrieren.

>[!MORELIKETHIS]
>
>[Zielverbindung](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md){target="_blank"}
