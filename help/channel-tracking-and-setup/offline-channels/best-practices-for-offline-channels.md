---
description: Best Practices für Offline-Kanäle - [!DNL Marketo Measure]
title: Best Practices für Offline-Kanäle
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 4%

---

# Best Practices für Offline-Kanäle {#best-practices-for-offline-channels}

## Überblick {#overview}

Um ein genaues [!DNL Marketo Measure]-Reporting zu erhalten, müssen Ihre Marketing-Kanäle korrekt eingerichtet sein. Das Feld [!UICONTROL Marketing-]&quot; zeigt die höchste Gruppe von Marketing-Taktiken an, zu der ein Touchpoint gehören kann (z. B. Ereignisse, Webinare, Content Syndication usw.).

Bei der Einrichtung Ihrer Marketing-Kanäle gibt es zwei Aspekte: Online und Offline. Dieses Dokument konzentriert sich auf die [!DNL Marketo Measure] Best Practice-Empfehlungen für die Einrichtung und Wartung Ihrer Offline-Kanäle und wie sie über CRM-Kampagnen mit [!DNL Marketo Measure] synchronisiert werden.

Offline-Kanäle haben zwei Hauptaspekte:

1. Offline Channel Mapping , das Framework, das [!DNL Marketo Measure] angibt, zu welchem Kanal und Unterkanal der Offline-Touchpoint gehört
1. Offline-Kampagnensynchronisierung, bei der die Offline-Touchpoints erstellt werden

Offline-Touchpoints werden aus einer CRM-Kampagne erstellt und dienen der Verfolgung von Marketing-Interaktionen, die nicht über die [!DNL Marketo Measure] JavaScript, die auf den Seiten Ihrer Website implementiert ist, digital verfolgt werden können. Wenn eine CRM-Kampagne mit [!DNL Marketo Measure] synchronisiert wird, werden Touchpoints für die definierten Kampagnenmitglieder innerhalb der Kampagne erstellt.

Der Wert „Marketing-Kanal“ für diese Touchpoints basiert auf dem Feld „Typ“ in der Kampagne. Die Zuordnung von „CRM-Kampagnentyp“ zu „Marketing-Kanal“ und „Unterkanal“ wird in der Registerkarte „Offline-Kanäle“ Ihrer [!DNL Marketo Measure]-Kontoeinstellungen verwaltet. Wenn Sie sicherstellen, dass Ihre Offline-Kanal-Zuordnung korrekt und auf dem neuesten Stand ist, wird sichergestellt, dass Ihre Offline-Touchpoint-Daten den richtigen Marketing-Kanälen und -Unterkanälen in Ihren [!DNL Marketo Measure]-Berichten zugeordnet werden.

## Best Practice | Offline-Kanalzuordnung {#best-practice-offline-channel-mapping}

Unabhängig davon, ob Sie Ihre Offline-Kanäle zum ersten Mal zuordnen oder nur auf Genauigkeit überprüfen, sollten Sie die folgenden Best Practices beachten.

* Erstellen eines absichtlichen Frameworks für Ihre Offline-Kanäle
   * Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und darüber, wie sie in das Framework von [!DNL Marketo Measure] passen. Legen Sie fest, welche Kanäle und Unterkanäle in Ihren Offline-Kanälen dargestellt werden sollen und welche CRM-Kampagnentypen diese Kanäle voneinander unterscheiden
* Zuerst die aktuellen CRM-Kampagnentypwerte verwenden
   * Offline-Kanäle werden durch den CRM-Kampagnentyp definiert. Es kann jedoch erforderlich sein, den benutzerdefinierten CRM-Kampagnentyp zu erstellen, um ideale Offline-Kanal- und Unterkanalwerte zu berücksichtigen. Ideale Werte für den CRM-Kampagnentyp sollten die unten aufgeführte Benennungskonvention aufweisen:
      * KANAL - UNTERKANAL
      * Beispiel: Veranstaltung - Fachmesse
      * Dadurch wird sichergestellt, dass die Zuordnung zur Unterkanalebene so einfach und sauber wie möglich ist
* Ein Unterkanal kann nur einem CRM-Kampagnentyp zugeordnet werden
   * Mehrere CRM-Kampagnentypen können einem einzelnen Kanal zugeordnet werden, aber es kann nur ein CRM-Kampagnentyp jedem Unterkanal innerhalb jedes Kanals zugeordnet werden
* Nur Offline-CRM-Kampagnentypen sollten Offline-Kanälen zugeordnet werden, da nur Offline-Kampagnen mit [!DNL Marketo Measure] synchronisiert werden sollen, um Touchpoints zu erstellen:
   * Die &#39;Kampagnentypen&#39; des ONLINE-CRMs sollten einem [!UICONTROL Marketing-Kanal] = „NULL“ zugeordnet werden. Dieser Wert wird empfohlen, da er als „rote Markierung“ dient, die angibt, dass Ihre Offline-Kanäle überprüft wurden und jeder CRM-Kampagnentyp, der „NULL“ zugeordnet ist, ein ONLINE-Typ ist und nicht mit [!DNL Marketo Measure] synchronisiert werden sollte. Touchpoints, die sich auf „Kampagnentypen“ für Online-CRMs beziehen, würden bereits über [!DNL Marketo Measure] Online-Funktionen und -Kanäle verfolgt. Die Synchronisierung dieser Kampagnen birgt das Risiko von „doppelten“ Touchpoints/doppelter Zählung

## Best Practice | Offline-Kampagnensynchronisierung {#best-practice-offline-campaign-sync}

* Sicherstellen, dass das Feld „Typ“ in jeder CRM-Kampagne korrekt ist
   * „Typ“ bestimmt den Marketing-Kanal und Unterkanal für alle Touchpoints, die von der Kampagne bezogen werden, sobald sie synchronisiert wurden
* Unabhängig davon, ob Sie die CRM-basierte Kampagnensynchronisierungsmethode (Käufer-Touchpoints aktivieren) oder die [!DNL Marketo Measure] App-basierte Synchronisierungsmethode (benutzerdefinierte Kampagnensynchronisierung innerhalb der Registerkarte &quot;[!UICONTROL Kampagnen]&quot; Ihrer [!UICONTROL Marketo Measure]-Kontoeinstellungen) verwenden, sollten Offline-Touchpoints nur erstellt werden, wenn das Kampagnenmitglied eine tatsächliche Offline-Interaktion mit der Kampagne und Ihrer Marke hatte:
   * Bei Offline-Kanälen wie Events oder Webinaren werden „Registrierungen“ in der Regel über Formularübermittlungen auf Ihrer Website und [!DNL Marketo Measure] Online-Funktionen verfolgt. Daher sollten Kampagnenmitglieder mit dem Status „Registriert“ keinen Offline-Touchpoint von der Kampagne erhalten, um eine doppelte Zählung zu vermeiden. Offline-Touchpoints sollten nur für die „Teilnahme“ an der Veranstaltung oder dem Webinar repräsentativ sein.
   * Einige Offline-Kanäle wie Content Syndication sind insofern einfacher, als jedes Kampagnenmitglied den gleichen Status „Responded“ hat, der bedeutet, dass es tatsächlich auf die Kampagne reagiert hat. In diesem Fall laden Sie Inhalte auf eine Drittanbieter-Site herunter und sollten daher einen Offline-Touchpoint erhalten
* Bei Verwendung der Synchronisierungsmethode für benutzerdefinierte Kampagnen in der [!DNL Marketo Measure]-App müssen Sie sicherstellen, dass das Feld „Touchpoint-Datum“ auf dem Datumsfeld entweder der Kampagne oder des Kampagnenmitglieds basiert, das am meisten darauf hinweist, wann die Touchpoint-Interaktion tatsächlich stattgefunden hat
* Verwenden Sie die Schaltfläche „Touchpoint-Datum Massenaktualisierung“, wenn Sie das „Touchpoint-Datum“ für einen der Offline-Touchpoints, die aus einer CRM-Kampagne bezogen werden, überschreiben müssen. Das „Touchpoint-Datum“ muss so genau wie möglich sein, um sicherzustellen, dass der Touchpoint die genaueste „Touchpoint-Position“ und damit den korrekten Betrag der Attribution-Credits enthält

## Best Practices für die Wartung {#best-practice-for-maintenance}

Nach der Ersteinrichtung erstellt die Offline-Kanaleinrichtung entsprechend weiterhin Offline-Touchpoints. Als Best Practice empfehlen wir, die Offline-Einrichtung mindestens zweimal jährlich zu überprüfen. Dies garantiert saubere und genaue Käufer-Touchpoint-Daten.

Wenn Sie Änderungen an Ihrer Kampagnenverwaltung oder Ihren Prozessen vornehmen, müssen Sie außerdem sicherstellen, dass Sie Ihre [!DNL Marketo Measure] Offline-Kanalzuordnung und/oder Ihren Synchronisierungsprozess aktualisieren.

Trigger Zu den Änderungen, die Ihr Team möglicherweise dazu veranlassen, Aktualisierungen an der Offline-Kanaleinrichtung in [!DNL Marketo Measure] vorzunehmen, gehören:

* CRM-Kampagnentypen wurden erstellt oder bearbeitet
* Kampagnenmitglied &#39;Status&#39; erstellt oder bearbeitet
* Wenn Sie die CRM-Kampagnensynchronisierungsmethode über das Feld „Käufer-Touchpoints aktivieren“ verwenden, stellen Sie sicher, dass dieses Feld für jede erstellte CRM-Kampagne überprüft und aktualisiert wird. Wenn dieses Feld vernachlässigt wird, gibt es keine zugehörigen Offline-Touchpoint-Daten
* Wenn Sie auf Offline-Touchpoints einer CRM-Kampagne stoßen, die als Online-Touchpoints erscheinen (Marketing-Kanal = NULL), stellen Sie sicher, dass die zugehörige CRM-Kampagne überprüft und die Synchronisierung deaktiviert wird

Wenn Ihr Team vor Kurzem einen der oben genannten Vorgänge erlebt hat, empfiehlt [!DNL Marketo Measure], die Offline-Kanalzuordnung und die Offline-Kampagnen zu überprüfen, um die entsprechenden Änderungen vorzunehmen und sicherzustellen, dass sie ordnungsgemäß synchronisiert werden.

>[!MORELIKETHIS]
>
>* [Offline-Kanal-Setup](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Benutzerdefinierte Kampagnensynchronisierung - App-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Synchronisieren von Offline-Kampagnen - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [Offline-Kampagne und Kampagnenmitglieder - CRM-Synchronisation](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
>* [Kampagnensynchronisierungstermine - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
>* [Konfigurationen für mehrere Kampagnen-Datensatztypen](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Erstellen einer Kampagnenlistenansicht](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Synchronisieren historischer Daten](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
