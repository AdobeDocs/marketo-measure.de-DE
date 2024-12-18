---
description: '[!DNL Salesforce] Paketkonsolidierung - [!DNL Marketo Measure]'
title: '[!DNL Salesforce] Paketkonsolidierung'
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---

# [!DNL Salesforce] Paketkonsolidierung {#salesforce-package-consolidation}

Um das Benutzererlebnis zu verbessern und die Nutzung zu vereinfachen, werden bestehende Pakete in ein einzelnes, umfassendes Paket kompiliert.

## Package-Beschaffung {#package-retirement}

Als Folge dieser Konsolidierung werden die aktuellen Pakete V1, V2_EXT, V2_Security und alle Berichterstellungspakete nach August 2023 eingestellt. Wenn Sie das V2-Paket bereits installiert haben, müssen Sie es auf die neue konsolidierte Version aktualisieren.

## Neues Konsolidierungspaket {#new-consolidated-package}

Das neue konsolidierte V2-Paket umfasst alle Funktionen und Funktionen der vorherigen Pakete und bietet so ein verbessertes Benutzererlebnis. Dieses aktualisierte Paket ermöglicht ein effizienteres Tracking der Marketing- und Verkaufsleistung und ermöglicht tiefere Einblicke in das Kundenverhalten.

Es gibt zwei neue Felder, um Ihre Berichterstellungsfunktionen zu verbessern:

* form_name: Dieses Feld ist jetzt in BT-/BAT-Objekten verfügbar und ermöglicht Benutzenden das Erstellen von Berichten anhand von Formularnamen.
* user_touchpoint_id: Dieses Feld ermöglicht Benutzern das Erstellen von Berichten mit Touchpoint-Zählungen für Unique Users (`bizible2__User_Touchpoint_V2__c` in Salesforce).

## Unterstützung und Übergang {#support-and-transition}

Das [Supportteam](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} ist verfügbar, um alle Fragen zu beantworten und einen reibungslosen Übergang zum neuen konsolidierten Paket zu gewährleisten.

## Erforderliche Aktionen {#retired-actions}

* Wenn Sie das V2-Paket bereits installiert haben, müssen Sie es auf die neue konsolidierte Version aktualisieren.
* Wenn Sie über Berichte oder Dashboards aus einem beliebigen Reporting-Paket verfügen, können Sie diese ohne erforderliche Änderungen einfach neu erstellen, da alle Felder im konsolidierten Paket vorhanden sind.
* Wenn Sie Berichte mit Feldern im V2_EXT-Paket haben, können Sie sie im konsolidierten Paket mithilfe der folgenden Schritte neu erstellen:
   * Alle Daten in den Feldern V2_EXT sind in Touchpoint-Feldern verfügbar. So können Sie Ihre Berichte ändern, um Daten aus den entsprechenden V2-Touchpoint-Feldern abzurufen, indem Sie einen Filter für die Touchpoint-Position hinzufügen.
   * Beispielbericht, in dem alle Leads mit Werbeinhalt FT abgerufen werden, die &quot;Outreach&quot;-Text enthalten.
      * V2_EXT-Abfrage:
         * bizible2_ext_ad_content_FT_c enthält Outreach

![](assets/package-consolidation-1.png)

* Entsprechende Abfrage im konsolidierten Paket:
   * bizible2__Touchpoint_Position__c enthält FT AND
   * bizible2__ad_content__c enthält Outreach

![](assets/salesforce-package-consolidation-2.png)

## FAQs {#faq}

**Wird das konsolidierte Paket Konflikte mit Feldern in meinem vorhandenen Paket haben?**

Sie müssen Ihr Paket nicht deinstallieren, bevor Sie das konsolidierte Paket installieren. Es gibt keine Konflikte in Feldern, da sie sich in einem anderen Namespace befinden.

**Wie kann ich die Daten aus meinen aktuellen Paketen aufstocken?**

Sie können ein Ticket [mit Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} für die Aufstockung und Wiederaufbereitung von BT/BAT-Daten einreichen, um die Felder &quot;Touchpoint-ID&quot;und &quot;Formular-ID&quot;auszufüllen.

**Sind die Felder in den Paketen V1 und V2_EXT im konsolidierten Paket verfügbar?**

Ja. Das konsolidierte Paket enthält dieselben Felder in V1 mit weiteren Aufschlüsselungen nach Objekten und V2_EXT-Feldern über Touchpoint-Felder.

**Können Berichte, die V2_EXT-Felder verwenden, im konsolidierten Paket neu erstellt werden?**

Ja. Führen Sie die Schritte im Abschnitt [Erforderliche Aktionen](#retired-actions) aus.
