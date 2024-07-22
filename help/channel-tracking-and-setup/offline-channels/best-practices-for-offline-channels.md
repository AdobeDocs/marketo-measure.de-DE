---
description: Best Practices für Offline-Kanäle - [!DNL Marketo Measure]
title: Best Practices für Offline-Kanäle
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 4%

---

# Best Practices für Offline-Kanäle {#best-practices-for-offline-channels}

## Überblick {#overview}

Um eine genaue [!DNL Marketo Measure] Berichterstellung zu erhalten, müssen Ihre Marketing-Kanäle korrekt eingerichtet sein. Das Feld &quot;[!UICONTROL Marketing-Kanal]&quot;enthält die Gruppe der Marketing-Taktiken auf höchster Ebene, zu der ein Touchpoint gehören kann (z. B. Ereignisse, Webinare, Inhaltssynchronisierung usw.).

Bei der Einrichtung Ihrer Marketing-Kanäle gibt es zwei Aspekte: Online und Offline. Dieses Dokument konzentriert sich auf die Best Practices für die Einrichtung und Pflege Ihrer Offline-Kanäle und darauf, wie diese mit [!DNL Marketo Measure] über CRM-Kampagnen synchronisiert werden.[!DNL Marketo Measure]

Offline-Kanäle haben zwei Hauptaspekte:

1. Offline-Kanalzuordnung, das Framework, das [!DNL Marketo Measure] angibt, zu welchem Kanal und Unterkanal der Offline-Touchpoint gehört
1. Offline-Kampagnensynchronisation , bei der Offline-Touchpoints erstellt werden

Offline-Touchpoints werden in einer CRM-Kampagne erstellt und dienen dazu, Marketinginteraktionen zu verfolgen, die nicht digital über die auf den Webseiten Ihrer Website implementierte JavaScript [!DNL Marketo Measure] verfolgt werden können. Wenn eine CRM-Kampagne mit [!DNL Marketo Measure] synchronisiert wird, werden Touchpoints für die definierten Campaign-Mitglieder in der Kampagne erstellt.

Der Wert &quot;Marketing-Kanal&quot;für diese Touchpoints basiert auf dem Feld &quot;Typ&quot;in der Kampagne. Die Zuordnung von &#39;CRM-Kampagnentyp&#39; zu &#39;Marketing-Kanal&#39; und &#39;Subchannel&#39; wird im Tab &#39;Offline-Kanäle&#39; Ihrer [!DNL Marketo Measure] Kontoeinstellungen verwaltet. Wenn Sie sicherstellen, dass Ihr Offline-Kanal-Mapping korrekt und aktuell ist, garantieren Sie, dass Ihre Offline-Touchpoint-Daten den korrekten Marketing-Kanälen und Subkanälen in Ihrem [!DNL Marketo Measure] -Reporting zugeordnet werden.

## Best Practice | Offline-Kanalzuordnung {#best-practice-offline-channel-mapping}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie Ihre Offline-Kanäle zum ersten Mal zuordnen oder sie nur überprüfen, um sicherzustellen, dass sie korrekt sind.

* Erstellen eines absichtlichen Frameworks für Ihre Offline-Kanäle
   * Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und darüber, wie sie in das Framework von [!DNL Marketo Measure] passen. Bestimmen Sie, welche Kanäle und Unterkanäle in Ihren Offline-Kanälen dargestellt werden sollen und welche CRM-Kampagnentypen diese Kanäle voneinander unterscheiden.
* Arbeiten Sie zunächst an der Nutzung Ihrer aktuellen CRM-Kampagnenwerte &quot;Typ&quot;.
   * Offline-Kanäle werden durch den &#39;Typ&#39; der CRM-Kampagne definiert. Es kann jedoch erforderlich sein, den &#39;Typ&#39; der benutzerdefinierten CRM-Kampagne zu erstellen, um die idealen Offline-Kanal- und Subkanalwerte aufzunehmen. Ideale benutzerdefinierte CRM-Kampagnentyp-Werte sollten die unten dargestellte Namenskonvention aufweisen:
      * KANAL - SUBKANAL
      * Beispiel: Event - Tradeshow
      * Dadurch wird sichergestellt, dass die Zuordnung zur Subkanalebene so einfach und sauber wie möglich ist.
* Ein Unterkanal kann nur einem CRM-Kampagnentyp zugeordnet werden.
   * Mehrere CRM-Kampagnentypen können einem einzelnen Kanal zugeordnet werden, aber jedem Unterkanal innerhalb eines Kanals kann nur ein CRM-Kampagnentyp zugeordnet werden.
* Nur die &quot;Typen&quot;der OFFLINE-CRM-Kampagne sollten Offline-Kanälen zugeordnet werden, da nur Offline-Kampagnen mit [!DNL Marketo Measure] synchronisiert werden sollen, um Touchpoints zu erstellen:
   * Die &#39;Typen&#39; der ONLINE CRM-Kampagne sollten einem [!UICONTROL Marketingkanal] = &quot;NULL&quot;zugeordnet werden. Dieser Wert wird empfohlen, da er als &quot;rote Markierung&quot;dient, die angibt, dass Ihre Offline-Kanäle geprüft wurden und jeder CRM-Kampagnentyp, der &quot;NULL&quot;zugeordnet ist, ein ONLINE-Typ &quot;Typ&quot;ist und nicht mit [!DNL Marketo Measure] synchronisiert werden sollte. Touchpoints im Zusammenhang mit Online-CRM-Kampagnentypen werden bereits über [!DNL Marketo Measure] Online-Funktionen und -Kanäle verfolgt. Die Synchronisierung dieser Kampagnen birgt das Risiko, Touchpoints zu &quot;duplizieren&quot;bzw. die Zählung zu verdoppeln

## Best Practice | Offline-Kampagnensynchronisierung {#best-practice-offline-campaign-sync}

* Stellen Sie sicher, dass das Feld &quot;Typ&quot; in jeder CRM-Kampagne korrekt ist.
   * &#39;Typ&#39; bestimmt Marketing-Kanal und Subkanal für alle Touchpoints, die aus der Kampagne bezogen werden, sobald sie synchronisiert wurden
* Unabhängig davon, ob Sie die CRM-basierte Methode der Kampagnensynchronisierung (Käufer-Touchpoints aktivieren) oder die [!DNL Marketo Measure] App-basierte Synchronisierungsmethode (benutzerdefinierte Kampagnensynchronisierung im Tab &#39;[!UICONTROL Kampagnen]&#39; Ihrer [!UICONTROL Marketo Measure] Kontoeinstellungen) verwenden, sollten Offline-Touchpoints nur erstellt werden, wenn der Kampagnenmitglieder eine tatsächliche Offline-Interaktion mit der Kampagne und Ihrer Marke hatte:
   * Für Offline-Kanäle wie Ereignisse oder Webinare: &quot;Registrierungen&quot;werden in der Regel über Formularübermittlungen auf Ihrer Website und [!DNL Marketo Measure] Online-Funktionen verfolgt. Deshalb sollten Campaign-Mitglieder mit dem Status &quot;Registriert&quot;keinen Offline-Touchpoint von der Kampagne erhalten, um eine doppelte Zählung zu vermeiden. Offline-Touchpoints sollten nur für die &quot;Teilnahme&quot;an der Veranstaltung oder dem Webinar repräsentativ sein.
   * Einige Offline-Kanäle wie die Inhaltssynchronisierung sind einfacher, da jedes Campaign-Mitglied denselben &quot;reagierten&quot;Status hat, der angibt, dass es tatsächlich auf die Kampagne geantwortet hat. In diesem Fall sollten Sie Inhalte auf einer Drittanbieter-Site herunterladen und daher einen Offline-Touchpoint erhalten.
* Stellen Sie bei Verwendung der Methode zur benutzerspezifischen Kampagnensynchronisierung in der [!DNL Marketo Measure] -App sicher, dass das Feld &quot;Touchpoint-Datum&quot;auf dem Datumsfeld des Campaign- oder Campaign-Mitglieds basiert, das am deutlichsten darauf hinweist, wann die Touchpoint-Interaktion tatsächlich stattgefunden hat
* Verwenden Sie die Schaltfläche &quot;Touchpoint-Datum-Massenaktualisierung&quot;, wenn Sie das &quot;Touchpoint-Datum&quot;für einen der Offline-Touchpoints überschreiben müssen, die aus einer CRM-Kampagne stammen. Das &quot;Touchpoint-Datum&quot;muss so genau wie möglich sein, um sicherzustellen, dass der Touchpoint die genaueste &quot;Touchpoint-Position&quot;und damit den korrekten Betrag der Attribution enthält.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Nach der Ersteinrichtung werden bei Ihrer Offline-Kanal-Einrichtung weiterhin Offline-Touchpoints entsprechend erstellt. Als Best Practice empfehlen wir, Ihre Offline-Einrichtung mindestens zweimal jährlich zu überprüfen. Dadurch werden saubere und genaue Buyer Touchpoint-Daten garantiert.

Wenn Sie außerdem Änderungen an Ihrer Kampagnenverwaltung oder Ihren Kampagnenprozessen vornehmen, müssen Sie sicherstellen, dass Sie Ihr [!DNL Marketo Measure] Offline-Kanal-Mapping und/oder Ihren Synchronisierungsprozess aktualisieren.

Zu den Änderungen, die Ihr Team möglicherweise Trigger haben könnten, Aktualisierungen am Offline-Kanal-Setup in [!DNL Marketo Measure] vorzunehmen, zählen unter anderem:

* CRM-Kampagnentypen, erstellt oder bearbeitet
* Kampagnenmitglieder - Status erstellt oder bearbeitet
* Wenn Sie die CRM-Kampagnensynchronisierungsmethode über das Feld &quot;Käufer-Touchpoints aktivieren&quot;verwenden, achten Sie darauf, dass dieses Feld für jede erstellte CRM-Kampagne überprüft und aktualisiert wird. Wenn dieses Feld vernachlässigt wird, gibt es keine verwandten Offline-Touchpoint-Daten
* Wenn Sie aus einer CRM-Kampagne Offline-Touchpoints finden, die als Online-Touchpoints gelten (Marketing-Kanal = NULL), überprüfen Sie, ob die zugehörige CRM-Kampagne überprüft und die Synchronisierung deaktiviert ist.

Wenn Ihr Team kürzlich einen der oben genannten Punkte erfahren hat, empfiehlt [!DNL Marketo Measure], Ihre Offline-Kanal-Zuordnung und Offline-Kampagnen zu überprüfen, um die entsprechenden Änderungen vorzunehmen und sicherzustellen, dass sie ordnungsgemäß synchronisiert werden.

>[!MORELIKETHIS]
>
>* [Offline-Kanal-Einrichtung](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Benutzerdefinierte Kampagnensynchronisierung - App-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Synchronisieren von Offline-Kampagnen - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [Offline-Campaign- und Campaign-Mitglieder - CRM-Synchronisation](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
>* [Kampagnensynchronisierungsdaten - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
>* [Konfigurationen für mehrere Kampagnenersatztypen](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Erstellen einer Kampagnenlisten-Ansicht](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Synchronisieren historischer Daten](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
