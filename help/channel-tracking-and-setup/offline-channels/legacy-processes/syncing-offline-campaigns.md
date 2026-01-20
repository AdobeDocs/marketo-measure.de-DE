---
unique-page-id: 18874600
description: Synchronisieren von Offline-Kampagnen - [!DNL Marketo Measure]
title: Synchronisieren von Offline-Kampagnen
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 5%

---

# Synchronisieren von Offline-Kampagnen {#syncing-offline-campaigns}

Es kann schwierig sein, Offline-Kampagnen genau zu verfolgen und zu verstehen, wie sie mit Ihren digitalen Marketing-Maßnahmen verglichen werden. [!DNL Marketo Measure] können Sie Touchpoints Ihren Offline-Kampagnen in [!DNL Salesforce] nachverfolgen und zuordnen, auch in Situationen, in denen eine [!DNL Salesforce]-Kampagne erst einige Wochen nach dem Ereignis erstellt wird.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

## Vor der Synchronisierung {#before-you-sync}

Im Folgenden finden Sie einige Tipps für einen effizienten Synchronisierungsprozess:

* Offline-Kampagnen beziehen sich auf Marketing-Interaktionen, die nicht online stattfinden. Dazu gehören Marketing-Kanäle wie Veranstaltungen, Webinare und Messen. Schließen Sie nur Offline-Marketing-Kampagnen ein.
* Wenn Sie Kampagnen einbeziehen möchten, die Online-Aktivitäten vor der Installation von [!DNL Marketo Measure] verfolgt haben, stellen Sie sicher, dass Sie das Touchpoint-Enddatum als Bereitstellungsdatum Ihrer JavaScript auf Ihrer Site festlegen.
* Es ist hilfreich, die [!DNL Marketo Measure] App auf der Seite Offline-Kanäle offen zu halten, damit die verschiedenen Kampagnentypen und der Marketing-Kanal, in dem die Touchpoints zusammengefasst werden, einfach identifiziert werden können.

* Überprüfen Sie alles, bevor Sie auf die Schaltfläche &quot;[!UICONTROL Speichern] klicken!

## Massenaktualisierung des Touchpoint-Datums {#bulk-update-touchpoint-date}

Im Feld Erstellungsdatum auf dem Objekt Kampagnenmitglied wird [!DNL Salesforce] das Datum angegeben, an dem das Kampagnenmitglied zur Kampagne hinzugefügt wurde. Damit der Synchronisierungsprozess reibungslos funktioniert, stellen Sie sicher, dass das Buyer Touchpoint-Datumsfeld dasselbe Datum wie das Salesforce-Kampagnenmitgliedsobjekt hat. Dieser Schritt wird mithilfe der Schaltfläche &quot;[!UICONTROL Sammelaktualisierung Touchpoint-Datum]&quot; ausgeführt, _vorher_ Sie die Option [!UICONTROL Auswahlliste] im Feld Einkäufer-Touchpoints aktivieren auswählen.

Warum ist das wichtig? Stellen Sie sich vor, Ihr Unternehmen hat im Januar einen Stand auf einer Konferenz gesponsert. Auf der Konferenz zeigten 100 Personen Interesse an Ihrem Produkt und gaben ihre Kontaktinformationen an, um E-Mail-Updates zu erhalten. Drei Wochen später haben Sie endlich eine Kampagne erstellt, [!DNL Salesforce] die Ergebnisse der Konferenz zu verfolgen.

Ihr Upload-Datum liegt drei Wochen nach dem Konferenzdatum. Um diesen Unterschied zu beheben, [!UICONTROL &#x200B; Sie mit der Schaltfläche &#x200B;]Massenaktualisierung Touchpoint-Datum“ das entsprechende Datum festlegen. Die Schaltfläche ist in der Abbildung unten dargestellt.

![](assets/1-3.png)

In diesem Fall würde das Upload-Datum um drei Wochen aufgestockt. Dieser Schritt sollte vor dem Festlegen des Felds &quot;[!UICONTROL Kunden-Touchpoints aktivieren] ausgeführt werden.

Wenn Sie also die Schaltfläche [!UICONTROL Massenaktualisierung Touchpoint-Datum] verwenden und das Touchpoint-Datum in das Datum des Ereignisses ändern, generieren [!DNL Marketo Measure] Touchpoints für das tatsächliche Datum des Ereignisses - nicht für das Datum des Uploads.

Sie können auch die Daten für alle Kampagnenmitglieder in einer vorhandenen Kampagne aktualisieren. Stellen Sie dabei sicher, dass das Datum des Touchpoints das Datum der Interaktion des Mitglieds ist. Klicken Sie auf das Buyer Touchpoint-Massenaktualisierungsdatum, filtern Sie die Liste der Kampagnenmitglieder nach Bedarf, und fügen Sie in der Option &quot;[!UICONTROL Datum auswählen]&quot; oberhalb der Liste der Kampagnenmitglieder dasselbe Datum hinzu, an dem das Ereignis stattgefunden hat.

>[!CAUTION]
>
>Stellen Sie sicher, dass Sie das Touchpoint _Datum vor dem_ aktualisieren, da Sie Touchpoints für alle Kampagnenmitglieder aktivieren.

![](assets/2-3.png)

## Erstellen einer Kampagne und Synchronisieren von Käufer-Touchpoints {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

Um eine Kampagne in [!DNL Salesforce] zu erstellen, gehen Sie zur Registerkarte [!UICONTROL Kampagnen] und wählen Sie [!UICONTROL Neu] aus, wie in der Abbildung unten dargestellt. Abhängig von Ihrer [!DNL Salesforce] müssen Sie möglicherweise Kampagnen in der oberen Leiste hinzufügen, indem Sie auf das Pluszeichen (+) klicken.

![](assets/3-3.png)

Wenn Sie diese Kampagne erstellen, klicken Sie auf das Feld [!UICONTROL Kunden-Touchpoints aktivieren] und wählen Sie eine der folgenden Optionen aus der Auswahlliste aus:

![](assets/4-3.png)

* **Alle Kampagnenmitglieder einbeziehen**
   * Diese Option ermöglicht es [!DNL Marketo Measure], jedem Kampagnenmitglied einen Touchpoint zuzuordnen.

* **Schließen Sie „Responded“-Kampagnenmitglieder ein.**
   * Diese Option wendet Touchpoints auf Kampagnenmitglieder an, die den Status „Beantwortet“ haben.

* **Alle Kampagnenmitglieder ausschließen.**
   * Diese Option schreibt keinen Mitgliedern der Kampagne Touchpoints zu und dient als Markierung, dass die Kampagne bewusst von der [!DNL Marketo Measure] ausgeschlossen wurde. Wenn Sie jemals bei einem Unfall eine Kampagne mit Käufer-Touchpoints synchronisieren, können Sie den Status in „Alle Kampagnenmitglieder ausschließen“ ändern, und die Touchpoints werden entfernt.

Sobald eine dieser Auswahlmöglichkeiten ausgewählt ist, weisen [!DNL Marketo Measure] jedem Kampagnenmitglied einen Touchpoint zu, sofern zutreffend. Einem Lead oder Kontakt, der zur Kampagne hinzugefügt wird _muss_ eine E-Mail-Adresse mit seinem Datensatz verknüpft sein, damit [!DNL Marketo Measure] einen Touchpoint erstellen können. Ohne eine E-Mail-Adresse wird [!DNL Marketo Measure] dem Kampagnenmitglied keinen Touchpoint zuweisen.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Zuordnen von Offline-Kanälen](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>[[!DNL Marketo Measure] Tutorials: Felder für Kampagnenobjekte](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
