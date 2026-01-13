---
description: '[!DNL Salesforce]-Paketkonsolidierung - [!DNL Marketo Measure]'
title: '[!DNL Salesforce] Paketkonsolidierung'
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 6%

---


# [!DNL Salesforce] Paketkonsolidierung {#salesforce-package-consolidation}

Um das Benutzererlebnis zu verbessern und die Verwendung zu vereinfachen, werden vorhandene Pakete in ein einziges, umfassendes Paket kompiliert.

## Außerkraftsetzung von Kits {#package-retirement}

Infolge dieser Konsolidierung werden die aktuellen Versionen 1, 2_EXT, 2_Security und alle Reporting-Pakete nach August 2023 eingestellt. Wenn Sie das V2-Paket bereits installiert haben, müssen Sie es auf die neue konsolidierte Version aktualisieren.

## Neues konsolidiertes Paket {#new-consolidated-package}

Das neue konsolidierte V2-Paket enthält alle Funktionen und Leistungsmerkmale der vorherigen Pakete und bietet so ein verbessertes Benutzererlebnis. Dieses aktualisierte Paket ermöglicht ein effizienteres Tracking der Marketing- und Verkaufsleistung und tiefere Einblicke in das Kundenverhalten.

Es gibt zwei neue Felder, um Ihre Reporting-Funktionen zu verbessern:

* form_name: Dieses Feld ist jetzt in BT-/BAT-Objekten verfügbar und ermöglicht Benutzenden das Erstellen von Berichten anhand von Formularnamen.
* user_Touchpoint_id: Dieses Feld ermöglicht Benutzern das Erstellen von Berichten mit eindeutigen Benutzer-Touchpoint-Zahlen (`bizible2__User_Touchpoint_V2__c` in Salesforce).

## Support und Transition {#support-and-transition}

Das [Support-Team](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} steht Ihnen bei allen Fragen und für einen reibungslosen Übergang zum neuen konsolidierten Package zur Verfügung.

## Erforderliche Aktionen {#retired-actions}

* Wenn Sie das V2-Paket bereits installiert haben, müssen Sie es auf die neue konsolidierte Version aktualisieren.
* Wenn Sie Berichte oder Dashboards aus einem beliebigen Reporting-Paket haben, können Sie diese einfach neu erstellen, ohne dass Änderungen erforderlich sind, da alle Felder im konsolidierten Paket vorhanden sind.
* Wenn Sie Berichte haben, die Felder im V2_EXT-Paket verwenden, können Sie diese mithilfe der folgenden Schritte im konsolidierten Paket neu erstellen:
   * Alle Daten in V2_EXT-Feldern sind in Touchpoint-Feldern verfügbar, sodass Sie Ihre Berichte ändern können, um Daten aus den entsprechenden V2-Touchpoint-Feldern abzurufen, indem Sie einen Filter für die Touchpoint-Position hinzufügen.
   * Beispielbericht zum Abrufen aller Leads mit Anzeigeninhalts-FT mit „Reichweitentext“.
      * V2_EXT-Abfrage:
         * bizible2_ext__Ad_Content_FT__c enthält Kontaktaufnahme

![Beispielberichtsfilter mit dem FT-Feld „V2_EXT-Anzeigeninhalt“](assets/package-consolidation-1.png)

* Entsprechende Abfrage im konsolidierten Paket:
   * Bizible2__Touchpoint_Position__c enthält FT UND
   * Bizible2__Ad_Content__c enthält Kontaktaufnahme

![Entsprechender Berichtsfilter unter Verwendung konsolidierter Touchpoint-Felder](assets/salesforce-package-consolidation-2.png)

## FAQs {#faq}

**Weist das konsolidierte Paket Konflikte mit Feldern in meinem vorhandenen Paket auf?**

Sie müssen Ihr Paket nicht deinstallieren, bevor Sie das konsolidierte Paket installieren. Es gibt keine Konflikte in Feldern, da sie sich in einem anderen Namespace befinden.

**Wie kann ich die Daten aus meinen aktuellen Paketen aufstocken?**

Sie können ein Ticket ([ Support) ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} Aufstockung und Neuverarbeitung von BT-/BAT-Daten zum Ausfüllen von Touchpoint-ID- und Formular-ID-Feldern einreichen.

**Werden die Felder in den Paketen V1 und V2_EXT im konsolidierten Paket verfügbar sein?**

Ja. Das konsolidierte Paket enthält dieselben Felder in V1 mit weiteren Aufschlüsselungen nach Objekten und V2_EXT-Feldern über Touchpoint-Felder.

**Können Berichte, die V2_EXT-Felder verwenden, im konsolidierten Paket neu erstellt werden?**

Ja. Führen Sie die Schritte im Abschnitt [Erforderliche Aktionen](#retired-actions) aus.
