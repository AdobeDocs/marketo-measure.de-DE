---
description: Best Practices für Offline-Kanäle - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für Offline-Kanäle
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 0%

---

# Best Practices für Offline-Kanäle {#best-practices-for-offline-channels}

## Überblick {#overview}

Richtig [!DNL Marketo Measure] Berichterstellung, müssen Ihre Marketing-Kanäle korrekt eingerichtet sein. Der[!UICONTROL Marketingkanal]&#39; zeigt die Gruppe der Marketing-Taktiken auf höchster Ebene an, zu der ein Touchpoint gehören kann (z. B. Ereignisse, Webinare, Inhaltssynchronisierung usw.).

Die Einrichtung Ihrer Marketing-Kanäle umfasst zwei Aspekte: online und offline. Dieses Dokument konzentriert sich auf die [!DNL Marketo Measure] Best Practices für die Einrichtung und Verwaltung Ihrer Offline-Kanäle und deren Synchronisierung mit [!DNL Marketo Measure] über CRM-Kampagnen.

Offline-Kanäle haben zwei Hauptaspekte:

1. Offline-Kanalzuordnung, das Framework, das [!DNL Marketo Measure] zu welchem Kanal und Subkanal der Offline-Touchpoint gehört
1. Offline-Kampagnensynchronisation , bei der Offline-Touchpoints erstellt werden

Offline-Touchpoints werden in einer CRM-Kampagne erstellt und dienen zur Verfolgung von Marketinginteraktionen, die nicht digital über die [!DNL Marketo Measure] JavaScript, das auf den Seiten Ihrer Website implementiert ist. Wenn eine CRM-Kampagne mit [!DNL Marketo Measure], werden Touchpoints für die definierten Campaign-Mitglieder in der Kampagne erstellt.

Der Wert &quot;Marketing-Kanal&quot;für diese Touchpoints basiert auf dem Feld &quot;Typ&quot;in der Kampagne. Die Zuordnung von &#39;CRM-Kampagnentyp&#39; zu &#39;Marketing-Kanal&#39; und &#39;Subchannel&#39; wird im Tab &#39;Offline-Kanäle&#39; Ihrer [!DNL Marketo Measure] Kontoeinstellungen. Wenn Sie sicherstellen, dass Ihr Offline-Kanal-Mapping korrekt und aktuell ist, garantieren Sie, dass Ihre Offline-Touchpoint-Daten den korrekten Marketing-Kanälen und Subkanälen in Ihren [!DNL Marketo Measure] Berichterstellung.

## Best Practice | Offline-Kanalzuordnung {#best-practice-offline-channel-mapping}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie Ihre Offline-Kanäle zum ersten Mal zuordnen oder sie nur überprüfen, um sicherzustellen, dass sie korrekt sind.

* Erstellen eines absichtlichen Frameworks für Ihre Offline-Kanäle
   * Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und darüber, wie sie in die [!DNL Marketo Measure] Framework. Bestimmen Sie, welche Kanäle und Unterkanäle in Ihren Offline-Kanälen angezeigt werden sollen und welche CRM-Kampagnentypen diese Kanäle voneinander unterscheiden.
* Arbeiten Sie zunächst an der Nutzung Ihrer aktuellen CRM-Kampagnenwerte &quot;Typ&quot;.
   * Offline-Kanäle werden durch den &#39;Typ&#39; der CRM-Kampagne definiert. Es kann jedoch erforderlich sein, den &#39;Typ&#39; der benutzerdefinierten CRM-Kampagne zu erstellen, um die idealen Offline-Kanal- und Subkanalwerte aufzunehmen. Ideale benutzerdefinierte CRM-Kampagnentyp-Werte sollten die unten dargestellte Namenskonvention aufweisen:
      * KANAL - SUBKANAL
      * Beispiel: Event - Tradeshow
      * Dadurch wird sichergestellt, dass die Zuordnung zur Subkanalebene so einfach und sauber wie möglich ist.
* Nur ein Unterkanal kann einem CRM-Kampagnentyp zugeordnet werden.
   * Mehrere CRM-Kampagnentypen können einem einzelnen Kanal zugeordnet werden, aber jedem Unterkanal innerhalb eines Kanals kann nur ein CRM-Kampagnentyp zugeordnet werden.
* Nur die &quot;Typen&quot;der OFFLINE CRM-Kampagne sollten Offline-Kanälen zugeordnet werden, da nur Offline-Kampagnen mit [!DNL Marketo Measure] zum Erstellen von Touchpoints:
   * Die &#39;Typen&#39; der ONLINE-CRM-Kampagne sollten einer [!UICONTROL Marketingkanal] = &quot;NULL&quot;. Dieser Wert wird empfohlen, da er als &quot;rote Markierung&quot;dient, die angibt, dass Ihre Offline-Kanäle geprüft wurden und jeder CRM-Kampagnentyp, der &quot;NULL&quot;zugeordnet ist, ein ONLINE-Typ ist und nicht mit synchronisiert werden sollte. [!DNL Marketo Measure]. Touchpoints im Zusammenhang mit Online-CRM-Kampagnentypen werden bereits über nachverfolgt. [!DNL Marketo Measure] Online-Funktionen und -Kanäle. Die Synchronisierung dieser Kampagnen birgt das Risiko, Touchpoints zu &quot;duplizieren&quot;bzw. die Zählung zu verdoppeln

## Best Practice | Offline-Kampagnensynchronisation {#best-practice-offline-campaign-sync}

* Stellen Sie sicher, dass das Feld &quot;Typ&quot; in jeder CRM-Kampagne korrekt ist.
   * &#39;Typ&#39; bestimmt Marketing-Kanal und Subkanal für alle Touchpoints, die aus der Kampagne bezogen werden, sobald sie synchronisiert wurden
* Ob die CRM-basierte Methode zur Kampagnensynchronisierung (Käufer-Touchpoints aktivieren) oder die [!DNL Marketo Measure] App-basierte Synchronisierungsmethode (benutzerdefinierte Kampagnensynchronisierung innerhalb der[!UICONTROL Kampagnen]Registerkarte &#39; Ihres [!UICONTROL Marketo-Maßnahme] Kontoeinstellungen) sollten Offline-Touchpoints nur erstellt werden, wenn der Campaign-Mitglied über eine tatsächliche Offline-Interaktion mit der Kampagne und Ihrer Marke verfügt:
   * Für Offline-Kanäle wie Ereignisse oder Webinare: &quot;Registrierungen&quot;werden in der Regel über Formularübermittlungen auf Ihrer Website verfolgt und [!DNL Marketo Measure] Online-Funktionalität. Deshalb sollten Campaign-Mitglieder mit dem Status &quot;Registriert&quot;keinen Offline-Touchpoint von der Kampagne erhalten, um eine doppelte Zählung zu vermeiden. Offline-Touchpoints sollten nur für die &quot;Teilnahme&quot;an der Veranstaltung oder dem Webinar repräsentativ sein.
   * Einige Offline-Kanäle wie die Inhaltssynchronisierung sind in der Regel einfacher, da jedes Campaign-Mitglied denselben Status &quot;reagiert&quot;hat, der angibt, dass es tatsächlich auf die Kampagne geantwortet hat. In diesem Fall sollten Sie Inhalte auf einer Drittanbieter-Site herunterladen und daher einen Offline-Touchpoint erhalten.
* Bei Verwendung der Methode zur benutzerspezifischen Kampagnensynchronisierung im [!DNL Marketo Measure] App, stellen Sie sicher, dass das Feld &quot;Touchpoint-Datum&quot;auf dem Datumsfeld des Campaign- oder Campaign-Mitglieds basiert, das am deutlichsten darauf hinweist, wann die Touchpoint-Interaktion tatsächlich stattgefunden hat
* Verwenden Sie die Schaltfläche &quot;Touchpoint-Datum-Massenaktualisierung&quot;, wenn Sie das &quot;Touchpoint-Datum&quot;für einen der Offline-Touchpoints überschreiben müssen, die aus einer CRM-Kampagne stammen. Das &quot;Touchpoint-Datum&quot;muss so genau wie möglich sein, um sicherzustellen, dass der Touchpoint die genaueste &quot;Touchpoint-Position&quot;und damit die richtige Menge an Attributionsguthaben enthält.

## Best Practice für die Wartung {#best-practice-for-maintenance}

Nach der Ersteinrichtung werden bei Ihrer Offline-Kanal-Einrichtung weiterhin Offline-Touchpoints entsprechend erstellt. Als Best Practice empfehlen wir, Ihre Offline-Einrichtung mindestens zweimal jährlich zu überprüfen. Dadurch werden saubere und präzise Buyer-Touchpoint-Daten garantiert.

Wenn Sie außerdem Änderungen an Ihrer Kampagnenverwaltung oder Ihren Kampagnenprozessen vornehmen, müssen Sie sicherstellen, dass Sie Ihre [!DNL Marketo Measure] Offline-Kanal-Mapping und/oder Synchronisierungsprozess.

Änderungen, die Ihr Team möglicherweise Trigger für Aktualisierungen der Offline-Kanal-Einrichtung in der [!DNL Marketo Measure] kann Folgendes umfassen:

* CRM-Kampagnentyp(en) erstellt oder bearbeitet
* Kampagnenmitglieder - Status erstellt oder bearbeitet
* Wenn Sie die CRM-Kampagnensynchronisierungsmethode über das Feld &quot;Käufer-Touchpoints aktivieren&quot;verwenden, stellen Sie sicher, dass dieses Feld für jede erstellte CRM-Kampagne überprüft und aktualisiert wird. Wenn dieses Feld vernachlässigt wird, gibt es keine verwandten Offline-Touchpoint-Daten
* Wenn Sie aus einer CRM-Kampagne Offline-Touchpoints finden, die als Online-Touchpoints gelten (Marketing-Kanal = NULL), überprüfen Sie, ob die zugehörige CRM-Kampagne überprüft und die Synchronisierung deaktiviert ist.

Wenn Ihr Team vor kurzem einen der oben genannten Punkte erfahren hat, [!DNL Marketo Measure] empfiehlt, dass Sie die Offline-Kanal-Zuordnung und Offline-Kampagnen überprüfen, um die entsprechenden Änderungen vorzunehmen und sicherzustellen, dass sie ordnungsgemäß synchronisiert werden.

>[!MORELIKETHIS]
>
>* [Offline-Kanal-Einrichtung](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Benutzerdefinierte Kampagnensynchronisierung - App-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Synchronisieren von Offline-Kampagnen - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [Offline-Campaign- und Campaign-Mitglieder - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [Kampagnensynchronisierungsdaten - CRM-Synchronisierung](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [Konfigurationen für mehrere Kampagnentypen](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Erstellen einer Kampagnenlisten-Ansicht](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Synchronisieren historischer Daten](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

