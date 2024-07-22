---
unique-page-id: 18874598
description: Offline-Einrichtung des benutzerdefinierten Kanals - [!DNL Marketo Measure]
title: Offline-Einrichtung benutzerdefinierter Kanäle
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 1%

---

# Offline-Einrichtung benutzerdefinierter Kanäle {#offline-custom-channel-setup}

## Erste Schritte {#getting-started}

Im Vergleich zur Verarbeitung von Online-Kanal-Regeln durch [!DNL Marketo Measure] werden Sie feststellen, dass die Offline-Kanalregeln keine Tabellenkalkulation erfordern. Im Implementierungsplan ist jedoch immer noch eine Tabelle enthalten, da dies hilfreich sein kann, wenn Sie sich Gedanken darüber machen, wie Sie Ihre Offline-Kanäle organisieren möchten.

Die Tabelle enthält drei Spalten:

![](assets/1-2.png)

**[!UICONTROL Salesforce] Kampagnentyp** - Fügen Sie hier die in [!DNL Salesforce] identifizierten Kampagnentypen hinzu

* Dies kann beispielsweise eine E-Mail, ein Webinar, eine Konferenz oder ein beliebiger Wert sein, den Sie für dieses Feld erstellt haben und dem Sie Touchpoints zuordnen möchten.

**[!UICONTROL Kanal]** - Fügen Sie hier Ihre verschiedenen Marketingkanäle hinzu

**[!UICONTROL Subchannel]** - hier alle entsprechenden Subkanäle hinzufügen

## Offline-Kanallogik {#offline-channel-logic}

[!DNL Marketo Measure] Die Offline-Kanal-Logik wird durch das Campaign-Objekt bestimmt, insbesondere durch den Kampagnentyp [!DNL Salesforce]. Jede Offline-Anstrengung muss über einen Kampagnentyp vom Typ &quot;[!DNL Salesforce]&quot; verfügen, wie z. B. Dinner oder Messen, da [!DNL Marketo Measure] sich auf dieses Feld verlässt, um zu verstehen, welchen Kanal und welchen SubChannel zugeordnet werden sollen.

Die SFDC-Kampagnentypen werden auf der Registerkarte Offline-Kanal angezeigt, die unter [!DNL Salesforce] Kampagnentyp aufgeführt ist. Beachten Sie, dass [!DNL Marketo Measure] nur SFDC-Kampagnentypen für Kampagnen importieren kann, denen Käuferkontaktpunkte zugeordnet sind.

![](assets/2-2.png)

Hier können Sie die Kanal-/Subkanal-Zuordnung in der [!DNL Marketo Measure] -App erstellen. Dazu gehört wahrscheinlich das Erstellen neuer Kanäle und Subkanäle in der App [!DNL Marketo Measure] , was im Abschnitt Kanäle erstellen der App ausgeführt wird, wie in der Abbildung unten dargestellt. Für [!DNL Marketo Measure] müssen neue Kanäle und Unterkanäle erstellt werden, um zu verstehen, wo Touchpoints gepusht werden sollen. Sie können entscheiden, wie Kampagnentypen zugeordnet werden sollen.

![](assets/3-2.png)

## Beispiel für die Kanalzuordnung {#channel-mapping-example}

Nehmen wir beispielsweise an, Sie nehmen an zwei [!DNL Salesforce] Konferenzen im Jahr teil. Jede Konferenz ist jedoch sehr unterschiedlich und hat eine eigene Zielgruppe. Sie möchten wissen, welche von beiden mehr Wert bringt. In Ihrer [!DNL Salesforce] -Umgebung können Sie der Januar-Veranstaltung den Kampagnentyp &quot;Konferenz&quot;geben, Ihren Kanal &quot;[!DNL Salesforce]&quot;und Ihren Unterkanal &quot;Januar-Konferenz&quot;nennen.

Jetzt wollen Sie dasselbe für die Juni-Konferenz tun. Da es sich hier auch um eine Konferenz handelt, kann der gleiche Kampagnentyp, in diesem Fall &quot;Konferenz&quot;, verwendet werden. Der Kanal ist derselbe, [!DNL Salesforce] und der Unterkanal für diese zweite Konferenz ist &quot;Juni-Konferenz&quot;. Das ist aus organisatorischer Sicht sinnvoll. Es ist jedoch sehr verwirrend, diese Regeln mit der Logik [!DNL Marketo Measure] zu lesen und anzuwenden, da beide Kampagnen denselben Kampagnentyp aufweisen. Das Skript [!DNL Marketo Measure] kann keine Daten von einem Typ zu zwei verschiedenen Unterkanälen zuordnen. Das bedeutet, dass Sie für jeden Unterkanal einen neuen Kampagnentyp erstellen müssen, die Unterkanäle jedoch denselben Kanal haben können.

Nachstehend finden Sie ein Beispiel für eine Logik, die [!DNL Marketo Measure] nicht lesen kann:

![](assets/4-2.png)

Im obigen Szenario möchten Sie einen eindeutigen Kampagnentyp erstellen, da Sie denselben Kampagnentyp nicht zwei verschiedenen Unterkanälen zuordnen können. Stattdessen möchten Sie eindeutige Typen wie die folgenden einrichten:

![](assets/5-2.png)

Alle vorhandenen Kampagnentypen müssen in Ihrer Kanalzuordnung enthalten sein und &quot;NULL&quot;sollte als Kanal hinzugefügt werden.

Nehmen Sie sich Zeit, um in &quot;[!DNL Salesforce]&quot;zu gehen, um die Anzahl und Art Ihrer vorhandenen Datensatztypen zu ermitteln, die Sie einbeziehen möchten, und um festzustellen, ob Sie zusätzliche Kampagnen basierend auf den oben genannten Informationen erstellen müssen. Sobald Sie alle erforderlichen Informationen ausgefüllt haben, können Sie sie hochladen.

Erfahren Sie mehr über [Synchronisieren von Offline-Kampagnen [!DNL Salesforce] mit [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## Umgang mit SFDC-Kampagnen für Online-Marketing-Maßnahmen {#handling-sfdc-campaigns-for-online-marketing-efforts}

Marketing-Teams können in der Regel [!DNL Salesforce]-Kampagnen erstellen, um verschiedene digitale Marketingbemühungen zu verfolgen. Mit dieser Vorgehensweise gibt es kein Problem. Es ist jedoch wichtig, diese Kampagnen anders zu behandeln als echte Offline-Kampagnen wie beispielsweise Briefpost oder Konferenzen. Kampagnen, die sich auf digitale Ereignisse beziehen (Interaktionen, die auf Ihrer Website stattfinden), sollten nicht mit [!DNL Marketo Measure] synchronisiert werden. Die Synchronisierung dieser Kampagnen würde zu einer Duplizierung der Touchpoints führen, da die [!DNL Marketo Measure] JavaScript bereits Online-Bemühungen verfolgt.

Ein weiterer Tipp für die Verarbeitung von Kampagnen für Online-Aktivitäten besteht darin, den Kampagnentyp &quot;[!DNL Salesforce]&quot;NULL zuzuordnen. Erstellen Sie dazu zunächst einen Kanal in der App [!DNL Marketo Measure] mit dem Titel NULL, wie in der Abbildung unten dargestellt. Dies befindet sich in der [!DNL Marketo Measure] -App unter dem Abschnitt **Kanäle erstellen** . Dies ist hilfreich, wenn eine nicht zu synchronisierende Kampagne versehentlich synchronisiert wird. Es ist einfach, die Kampagne zu finden und den Synchronisierungsstatus zu korrigieren, indem man sich alles ansieht, was unter NULL zusammengefasst ist.

![](assets/6-2.png)

## Eingeben Ihrer Offline-Kanalregeln in die App {#entering-your-offline-channel-rules-to-the-app}

Nachdem Sie die Tabelle bearbeitet und mit Ihren benutzerdefinierten Regeln aktualisiert haben, besteht der nächste Schritt darin, dieses Kanalzuordnungs-Mapping in der [!DNL Marketo Measure] -App neu zu erstellen. Sie werden keine Tabelle für Offline-Kanäle hochladen. Stattdessen geben Sie die Informationen in die Auswahllisten ein, wie in der Abbildung unten dargestellt. Klicken Sie dazu unter dem Abschnitt **[!UICONTROL Kanäle]** auf **[!UICONTROL Offline-Kanäle]** .

![](assets/7-2.png)

>[!TIP]
>
>Möchten Sie _bestimmen, wann_ ein [!DNL Salesforce] Kampagnentyp in die [!DNL Marketo Measure] -Kanalzuordnung gezogen wird? Gehen Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Kampagnen]** > **[!UICONTROL Felder]** > **[!UICONTROL Typ]**. Sie können dann sehen, welche Werte in der Auswahlliste enthalten sind und welche inaktiv sind. Inaktive Kanäle werden in unserem Abschnitt &quot;[!UICONTROL Offline-Kanäle]&quot; nicht als auswählbarer Typ angezeigt. Beachten Sie, dass dieser Vorgang einige Minuten bis zu 48 Stunden dauern kann.

Klicken Sie auf **[!UICONTROL Speichern]** , wenn Sie fertig sind, und [!DNL Marketo Measure] lädt die Änderungen hoch und verarbeitet die Daten erneut.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Tutorials: Zuordnen von Offline-Kanälen](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>* [[!DNL Marketo Measure] Tutorials: Synchronisieren von Offline-Kampagnen](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/syncing-offline-campaigns){target="_blank"}
>
>* [Marketo Engage Programmintegration](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}
