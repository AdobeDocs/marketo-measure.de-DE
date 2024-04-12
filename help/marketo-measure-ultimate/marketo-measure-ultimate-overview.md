---
description: „[!DNL Marketo Measure] Ultimate-Übersicht – [!DNL Marketo Measure]“
title: „[!DNL Marketo Measure] Ultimate – Übersicht“
exl-id: fada9479-0671-4698-8043-c67d7977577b
feature: Integration, Tracking, Attribution
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: ht
source-wordcount: '677'
ht-degree: 100%

---

# [!DNL Marketo Measure] Ultimate – Übersicht {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (ehemals Bizible) gibt Marketing-Fachleuten Einblicke, welche Marketing-Maßnahmen zur Steigerung des Umsatzes und Maximierung des ROI für ihr Unternehmen am effektivsten sind. [!DNL Marketo Measure] ist eine Marketing-Attributionslösung, die die Kanalleistung automatisch verfolgt und in Berichten aufzeigt, welche Kanäle die Kundeninteraktion am meisten fördern. Sie bietet Ihnen außerdem die Möglichkeit, Ihre Marketing-Ausgaben entsprechend zu optimieren.

[!DNL Marketo Measure Ultimate] enthält die zusätzlichen Funktionen:

* Es können Daten aus nahezu jeder Datenquelle und aus mehreren Datenquellen desselben Typs aufgenommen werden, um alle Ihre Daten für die Attribution einzubringen.
   * Die Lösung kann mit nahezu jedem CRM verwendet werden, nicht nur Salesforce und Dynamics.
   * Es können mehrere CRM-Instanzen und/oder MAP-Instanzen mit einer Instanz von [!DNL Marketo Measure] verbunden werden.
   * Es können Drittanbieterdaten zu Webinar-Registrierung und -Teilnahme einbegracht werden.

* Ihre Daten können mit großer Flexibilität durch die Feldzuordnungs- und Transformationsfunktionen transformiert werden, um zu gewährleisten, dass die Daten die richtige Form haben.

* Zuordnungseinblicke können über das enthaltene Data Warehouse für externe Anwendungen verfügbar gemacht werden, um die Einblicke in Ihren Workflow zu integrieren. Detailliertere Ergebnisdaten und BI-basiertes Reporting, einschließlich Snowflake Data Warehouse, was Zugriff auf granulare Ergebnisdaten und die Möglichkeit bietet, jedes BI-Tool für Analysen und Berichte zu verwenden.

* Integration mit RTCDP (B2B oder B2P Edition), die eine integrierte B2B-Zuordnungslösung für RTCDP-Kundinnen und -Kunden bietet, da RTCDP und [!DNL Marketo Measure] beide mit zentralisierten Daten von Adobe Experience Platform (AEP) arbeiten.

**[!DNL Marketo Measure]– Ebenen 1–3**

![](assets/marketo-measure-ultimate-overview-1.png)

**[!DNL Marketo Measure Ultimate]**

![](assets/marketo-measure-ultimate-overview-2.png)

## Neue Funktionen in [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**Importieren von B2B-Daten über AEP**

Von Marketing-Fachleuten wird erwartet, dass sie ihre B2B-Daten (z. B. Konto, Opportunity, Kontakt, Lead, Kampagne, Kampagnenmitglied, Aktivität) in AEP einbringen. Die direkten Verbindungen von CRM und Marketo Engage sind für Ultimate nicht mehr verfügbar. Marketing-Fachleute werden weiterhin Daten von Anzeigenplattformen über direkte Verbindungen einbringen und Web-Aktivitäten über [!DNL Marketo Measure]-JavaScript nachverfolgen.

![](assets/marketo-measure-ultimate-overview-3.png)

**Standardmäßige Währungseinstellung**

[!DNL Marketo Measure Ultimate] setzt die Standardwährung auf USD, bis die Benutzerin bzw. der Benutzer sie ändert. Durch das Festlegen einer neuen Standardwährung werden die Daten ohne erneute Verarbeitung aktualisiert. Solange die ausgewählte Währung als ISO-Ziel-Code vorhanden ist, müssen keine Wechselkurse eingegeben werden.

![](assets/marketo-measure-ultimate-overview-4.png)

**[!DNL Marketo Measure Ultimate]-Sandbox**

Die Instanz von [!DNL Marketo Measure Ultimate] muss einer AEP-Sandbox zugeordnet sein, bevor die Zieldatenflüsse von [!DNL Marketo Measure] in AEP erstellt werden.

>[!NOTE]
>
>Eine Produktionsinstanz von [!DNL Marketo Measure Ultimate] muss einer AEP-Produktions-Sandbox zugeordnet werden, und eine Entwicklerinstanz von [!DNL Marketo Measure Ultimate] muss einer AEP-Entwickler-Sandbox zugeordnet werden.

Sobald die Auswahl der Sandbox-Zuordnung gespeichert wurde, können Sie sie in der Anwendung nicht mehr ändern. Um sie zu ändern, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Daten für eine bestimmte Entität (z. B. Konto) aus einer bestimmten Datenquelle können in nur einen Datensatz eingehen. Jeder Datensatz kann in nur einem Datenfluss enthalten sein. Verstöße stoppen den Datenfluss in der Laufzeit.

![](assets/marketo-measure-ultimate-overview-5.png)

**Schrittzuordnung**

Alle Regeln von [!DNL Marketo Measure Ultimate] sind datensatzspezifisch. Die Regeln für die Schrittzuordnung müssen für alle Datensätze und alle ausgewählten Schritte erstellt werden.

Es gibt sechs integrierte Schritte:

* Lead – Verloren
* Lead – Offen
* Lead – Konvertiert
* Opportunity – Verloren
* Opportunity – Offen
* Opportunity – Gewonnen

Die Abschnitte „Verloren“, „Gewonnen“ und „Konvertiert“ lassen keine benutzerdefinierten Schritte zu. Quelldaten können jedoch den integrierten Schritten Verloren/Gewonnen/Konvertiert zugeordnet werden, indem die Zuordnungsregel aktualisiert wird.

Benutzerdefinierte Schritte können nur für die Abschnitte „Offen“ definiert werden.
CRM-Schritte werden nicht mehr automatisch in die Schrittzuordnung einbezogen.

Es müssen vier integrierten Schritten Regeln zugeordnet werden (Zuordnungsregeln für die beiden anderen Schritte, „Lead – Verloren“ und „Lead – Offen“ sind optional):

* Lead – Offen
* Opportunity – Verloren
* Opportunity – Offen
* Opportunity – Gewonnen

Regelbedingungen sind datensatzspezifisch. Schrittzuordnungsregeln müssen für alle Datensätze und alle Schritte erstellt werden, mit Ausnahme von „Lead – Verloren“ und „Lead – Konvertiert“.

Keine Auswahl für die Modelle „Trichter“, „Bumerang“ oder „Benutzerdefiniert“. Für die Modelle „Trichter“, „Bumerang“ oder „Benutzerdefiniert“ werden alle Schritte ausgewählt. Es gibt eine Obergrenze für die Anzahl der Schritte, die wir unterstützen: 15 benutzerdefinierte plus 6 integrierte Schritte.

![](assets/marketo-measure-ultimate-overview-6.png)

Touchpoint-Regeln für Kampagnenmitglieder und Touchpoint-Regeln für Aktivitäten sind datensatzspezifisch.

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

Attributions-Touchpoints werden nicht in CRM geschrieben, da Ultimate über keine direkte CRM-Verbindung verfügt.

ML-Dienste von [!DNL Marketo Measure] ABM (Lead-zu-Konto-Übereinstimmung und prädiktive Interaktionsbewertung) sind für [!DNL Marketo Measure Ultimate] nicht verfügbar. Sie finden diese Dienste kostenlos in der RT-CDP B2B Edition.

## Einschränkungen {#limitations}

* Für Datenumwandlungsregeln steht nur eine begrenzte Anzahl von Feldern zur Verfügung.
* Für bestehende Benutzerinnen und Benutzer der Ebenen 1–3 gibt es keinen Migrationspfad. Es ist eine neue Implementierung erforderlich, aber wir helfen Ihnen dabei, die Daten von nachverfolgten Web-Aktivitäten aus der vorhandenen Instanz zu migrieren.

>[!MORELIKETHIS]
>
>[Ziel von Marketo Measure Ultimate](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/marketo-measure-ultimate.html?lang=de){target="_blank"}
