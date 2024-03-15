---
unique-page-id: 18874600
description: Synchronisieren von Offline-Kampagnen - [!DNL Marketo Measure]
title: Synchronisieren von Offline-Kampagnen
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Synchronisieren von Offline-Kampagnen {#syncing-offline-campaigns}

Es kann schwierig sein, Offline-Kampagnen genau zu verfolgen und zu verstehen, wie sie im Vergleich zu Ihren digitalen Marketing-Maßnahmen aussehen. [!DNL Marketo Measure] ermöglicht es Ihnen, Touchpoints zu Ihren Offline-Kampagnen in zu verfolgen und ihnen zuzuordnen. [!DNL Salesforce], auch in Situationen, in denen eine [!DNL Salesforce] Die Kampagne wird erst einige Wochen nach der Veranstaltung erstellt.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir empfehlen Benutzern, die [neuer, verbesserter In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

## Vor der Synchronisierung {#before-you-sync}

Im Folgenden finden Sie einige Tipps für einen effizienten Synchronisierungsprozess:

* Offline-Kampagnen beziehen sich auf Marketinginteraktionen, die nicht online stattfinden. Dazu gehören Marketing-Kanäle wie Veranstaltungen, Webinare und Messen. Schließen Sie nur Offline-Marketing-Kampagnen ein.
* Wenn Sie Kampagnen einbeziehen möchten, die die Online-Aktivität vor der Installation verfolgt haben [!DNL Marketo Measure]stellen Sie sicher, dass Sie das Enddatum des Touchpoints als das Datum festlegen, an dem unser JavaScript auf Ihrer Site bereitgestellt wurde.
* Es ist hilfreich, die [!DNL Marketo Measure] -App auf der Seite &quot;Offline-Kanäle&quot;geöffnet, damit die verschiedenen Kampagnentypen sowie der Marketing-Kanal, in den die Touchpoints zusammengefasst werden, leicht identifiziert werden können.

* Überprüfen Sie alles, bevor Sie auf &quot;[!UICONTROL Speichern]&quot;-Schaltfläche!

## Touchpoint-Datum für Massenaktualisierung {#bulk-update-touchpoint-date}

In [!DNL Salesforce], notiert das Feld Erstellungsdatum im Campaign-Member-Objekt das Datum, an dem das Kampagnenmitglied zur Kampagne hinzugefügt wurde. Damit der Synchronisierungsprozess reibungslos abläuft, stellen Sie sicher, dass das Feld für das Touchpoint-Datum des Käufers dasselbe Datum wie das Datum für das Salesforce Campaign-Member-Objekt hat. Dieser Schritt wird mit dem[!UICONTROL Schaltfläche &quot;Touchpoint-Datum Massenaktualisierung&quot;],&quot; _before_ Sie wählen die [!UICONTROL picklist] im Feld Käufer-Touchpoints aktivieren .

Warum ist das wichtig? Stellen Sie sich einen Moment vor, dass Ihr Unternehmen einen Stand auf einer Konferenz im Januar gesponsert hat. Auf der Konferenz zeigten 100 Personen Interesse an Ihrem Produkt und legten ihre Kontaktdaten vor, um E-Mail-Updates zu erhalten. Drei Wochen später haben Sie schließlich eine Kampagne in [!DNL Salesforce] die Ergebnisse der Konferenz zu verfolgen.

Ihr Upload-Datum würde drei Wochen nach dem Konferenzdatum liegen. Um diesen Unterschied zu beheben, muss die Variable [!UICONTROL Touchpoint-Datum für Massenaktualisierung] kann verwendet werden, um das entsprechende Datum festzulegen. Die Schaltfläche ist in der Abbildung unten dargestellt.

![](assets/1-3.png)

In diesem Fall würde das Upload-Datum um drei Wochen aufgestockt. Dieser Schritt sollte vor dem Festlegen der[!UICONTROL Käufer-Touchpoints aktivieren]&quot;.

Kurz gesagt, wenn Sie die [!UICONTROL Touchpoint-Datum für Massenaktualisierung] und ändern Sie das Touchpoint-Datum in das Datum des Ereignisses, [!DNL Marketo Measure] generiert Touchpoints für das tatsächliche Datum des Ereignisses, nicht für das Datum des Uploads.

Sie können auch die Daten für alle Kampagnenmitglieder einer vorhandenen Kampagne aktualisieren. Stellen Sie dabei sicher, dass das Datum des Touchpoints das Datum der Interaktion des Mitglieds ist. Klicken Sie auf das Touchpoint-Datum für das Massen-Update des Käufers, filtern Sie die Liste der Kampagnenmitglieder nach Bedarf und im[!UICONTROL Datum auswählen]&quot; oberhalb der Liste der Kampagnenmitglieder, fügen Sie das Datum hinzu, an dem das Ereignis stattgefunden hat.

>[!CAUTION]
>
>Aktualisieren Sie unbedingt das Touchpoint-Datum. _before_ aktivieren Sie Touchpoints für alle Kampagnenmitglieder.

![](assets/2-3.png)

## Erstellen einer Kampagne und Synchronisieren von Touchpoints des Käufers {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

So erstellen Sie eine Kampagne in [!DNL Salesforce], navigieren Sie zum [!UICONTROL Kampagnen] Registerkarte und wählen Sie &quot;[!UICONTROL Neu]&quot;, wie in der Abbildung unten dargestellt. Je nach [!DNL Salesforce] -Setup verwenden, müssen Sie möglicherweise der oberen Leiste Kampagnen hinzufügen, indem Sie auf das Pluszeichen (+) klicken.

![](assets/3-3.png)

Klicken Sie beim Erstellen dieser Kampagne auf die Schaltfläche[!UICONTROL Käufer-Touchpoints aktivieren]&quot; und wählen Sie eine der folgenden Optionen aus der Auswahlliste aus:

![](assets/4-3.png)

* **Alle Kampagnenmitglieder einschließen**
   * Diese Option ermöglicht [!DNL Marketo Measure] , um jedem Kampagnenmitglied einen Touchpoint zuzuordnen.

* **Kampagnenmitglieder mit &quot;Reaktion&quot;einschließen.**
   * Diese Option wendet Touchpoints auf Kampagnenmitglieder an, die den Status &quot;Beantwortet&quot;haben.

* **Schließen Sie alle Kampagnenmitglieder aus.**
   * Diese Option weist keinen Mitgliedern der Kampagne Touchpoints zu und dient als Markierung, von der die Kampagne absichtlich ausgeschlossen wurde [!DNL Marketo Measure]. Wenn Sie eine Kampagne bei Unfall mit Touchpoints des Käufers synchronisieren, können Sie den Status auf &quot;Alle Mitglieder der Kampagne ausschließen&quot;ändern und die Touchpoints werden entfernt.

Sobald eine dieser Auswahlmöglichkeiten ausgewählt wurde, [!DNL Marketo Measure] weist jedem Kampagnenmitglied gegebenenfalls einen Touchpoint zu. Lead oder Kontakt , der der Kampagne hinzugefügt wird _must_ mit ihrem Datensatz verknüpfte E-Mail-Adresse haben, um [!DNL Marketo Measure] um einen Touchpoint zu erstellen. Ohne E-Mail-Adresse [!DNL Marketo Measure] weist dem Kampagnenmitglied keinen Touchpoint zu.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Zuordnen von Offline-Kanälen](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>[[!DNL Marketo Measure] Tutorials: Kampagnenobjektfelder](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
