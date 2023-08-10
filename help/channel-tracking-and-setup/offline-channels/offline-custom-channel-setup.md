---
unique-page-id: 18874598
description: Offline-Einrichtung des benutzerdefinierten Kanals - [!DNL Marketo Measure] - Produktdokumentation
title: Offline-Einrichtung benutzerdefinierter Kanäle
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 1%

---

# Offline-Einrichtung benutzerdefinierter Kanäle {#offline-custom-channel-setup}

## Erste Schritte {#getting-started}

Im Vergleich zur [!DNL Marketo Measure] behandelt Online-Kanal-Regeln, werden Sie feststellen, dass die Offline-Kanalregeln keine Verwendung einer Tabelle erfordern. Im Implementierungsplan ist jedoch immer noch eine Tabelle enthalten, da dies hilfreich sein kann, wenn Sie sich Gedanken darüber machen, wie Sie Ihre Offline-Kanäle organisieren möchten.

Die Tabelle enthält drei Spalten:

![](assets/1-2.png)

**[!UICONTROL Salesforce] Kampagnentyp** - Hinzufügen von Kampagnentypen, die in [!DNL Salesforce] here

* Dies kann beispielsweise eine E-Mail, ein Webinar, eine Konferenz oder ein beliebiger Wert sein, den Sie für dieses Feld erstellt haben und dem Sie Touchpoints zuordnen möchten.

**[!UICONTROL Kanal]** - Fügen Sie hier Ihre verschiedenen Marketing-Kanäle hinzu.

**[!UICONTROL Subchannel]** - Fügen Sie hier alle entsprechenden Unterkanäle hinzu.

## Offline-Kanallogik {#offline-channel-logic}

[!DNL Marketo Measure] Die Offline-Kanal-Logik wird durch das Campaign-Objekt bestimmt, insbesondere durch die [!DNL Salesforce] Kampagnentyp. Jede Offline-Anstrengung muss über eine [!DNL Salesforce] Kampagnentyp, z. B. Dinner oder Händler, weil [!DNL Marketo Measure] verlässt sich auf dieses Feld, um zu verstehen, welchem Kanal und SubChannel er zugeordnet werden soll.

Die SFDC-Kampagnentypen werden auf der Registerkarte Offline-Kanal angezeigt, die unter [!DNL Salesforce] Kampagnentyp. Bitte beachten Sie, dass [!DNL Marketo Measure] kann nur SFDC-Kampagnentypen für Kampagnen importieren, denen Käuferkontaktpunkte zugeordnet sind.

![](assets/2-2.png)

Hier können Sie die Kanal-/Subkanal-Zuordnung im [!DNL Marketo Measure] App. Dazu gehört wahrscheinlich die Erstellung neuer Kanäle und Unterkanäle im [!DNL Marketo Measure] App verwenden, was im Abschnitt Kanäle erstellen der App ausgeführt wird, wie in der Abbildung unten dargestellt. Neue Kanäle und Unterkanäle müssen für [!DNL Marketo Measure] um zu verstehen, wo Touchpoints gepusht werden. Sie können entscheiden, wie Kampagnentypen zugeordnet werden sollen.

![](assets/3-2.png)

## Beispiel für die Kanalzuordnung {#channel-mapping-example}

Angenommen, Sie nehmen an zwei [!DNL Salesforce] Konferenzen pro Jahr. Jede Konferenz ist jedoch sehr unterschiedlich und hat eine eigene Zielgruppe. Sie möchten wissen, welche von beiden mehr Wert bringt. In der [!DNL Salesforce] -Umgebung verwenden, können Sie der Januar-Veranstaltung den Kampagnentyp &quot;Konferenz&quot;geben, Ihren Kanal nennen.[!DNL Salesforce],&quot; und Ihrem Unterkanal &quot;Konferenz im Januar&quot;.

Jetzt wollen Sie dasselbe für die Juni-Konferenz tun. Da es sich hier auch um eine Konferenz handelt, kann der gleiche Kampagnentyp, in diesem Fall &quot;Konferenz&quot;, verwendet werden. Der Kanal ist identisch. [!DNL Salesforce]und der Unterkanal für diese zweite Konferenz ist &quot;Juni-Konferenz&quot;. Das ist aus organisatorischer Sicht sinnvoll. Es ist jedoch sehr verwirrend für die [!DNL Marketo Measure] Logik zum Lesen und Anwenden dieser Regeln, da beide Kampagnen denselben Kampagnentyp aufweisen. [!DNL Marketo Measure] -Skript kann keine Daten von einem Typ zu zwei verschiedenen Unterkanälen zuordnen. Das bedeutet, dass Sie für jeden Unterkanal einen neuen Kampagnentyp erstellen müssen, die Unterkanäle jedoch denselben Kanal haben können.

Nachfolgend finden Sie ein Beispiel für eine Logik, die [!DNL Marketo Measure] nicht lesen können:

![](assets/4-2.png)

Im obigen Szenario möchten Sie einen eindeutigen Kampagnentyp erstellen, da Sie denselben Kampagnentyp nicht zwei verschiedenen Unterkanälen zuordnen können. Stattdessen möchten Sie eindeutige Typen wie die folgenden einrichten:

![](assets/5-2.png)

Alle vorhandenen Kampagnentypen müssen in Ihrer Kanalzuordnung enthalten sein und &quot;NULL&quot;sollte als Kanal hinzugefügt werden.

Nehmen Sie sich Zeit, um [!DNL Salesforce] um die Anzahl und Art Ihrer vorhandenen Datensatztypen zu bestimmen, die Sie einbeziehen möchten, und ob Sie zusätzliche Kampagnen basierend auf den oben genannten Informationen erstellen müssen. Sobald Sie alle erforderlichen Informationen ausgefüllt haben, können Sie sie hochladen.

Weitere Informationen [Synchronisieren offline [!DNL Salesforce] Kampagnen mit [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md).

## Umgang mit SFDC-Kampagnen für Online-Marketing-Maßnahmen {#handling-sfdc-campaigns-for-online-marketing-efforts}

Marketing-Teams erstellen häufig [!DNL Salesforce] Kampagnen zur Verfolgung verschiedener Digital Marketing-Maßnahmen. Mit dieser Vorgehensweise gibt es kein Problem. Es ist jedoch wichtig, diese Kampagnen anders zu behandeln als echte Offline-Kampagnen wie beispielsweise Briefpost oder Konferenzen. Kampagnen, die sich auf digitale Ereignisse beziehen (Interaktionen, die auf Ihrer Website stattfinden), sollten nicht mit [!DNL Marketo Measure]. Die Synchronisierung dieser Kampagnen würde zu einer Duplizierung von Touchpoints führen, da die [!DNL Marketo Measure] JavaScript verfolgt bereits Online-Bemühungen.

Ein weiterer Tipp für die Verarbeitung von Kampagnen für Online-Aktivitäten ist die Zuordnung der [!DNL Salesforce] Kampagnentyp auf NULL. Erstellen Sie dazu zunächst einen Kanal im [!DNL Marketo Measure] App mit dem Titel NULL , wie in der Abbildung unten dargestellt. Dies finden Sie im Abschnitt [!DNL Marketo Measure] App unter **Kanäle erstellen** Abschnitt. Dies ist hilfreich, wenn eine nicht zu synchronisierende Kampagne versehentlich synchronisiert wird. Es ist einfach, die Kampagne zu finden und den Synchronisierungsstatus zu korrigieren, indem man sich alles ansieht, was unter NULL zusammengefasst ist.

![](assets/6-2.png)

## Eingeben Ihrer Offline-Kanalregeln in die App {#entering-your-offline-channel-rules-to-the-app}

Nachdem Sie die Tabelle mit Ihren benutzerdefinierten Regeln bearbeitet und aktualisiert haben, besteht der nächste Schritt darin, diese Kanalzuordnung im [!DNL Marketo Measure] App - Sie laden keine Tabelle für Offline-Kanäle hoch. Stattdessen geben Sie die Informationen in die Auswahllisten ein, wie in der Abbildung unten dargestellt. Klicken Sie auf **[!UICONTROL Offline-Kanäle]** unter **[!UICONTROL Kanäle]** Abschnitt.

![](assets/7-2.png)

>[!TIP]
>
>Möchten Sie _when_ a [!DNL Salesforce] Kampagnentyp wird nach [!DNL Marketo Measure] Kanalzuordnung? Gehen Sie einfach zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Kampagnen]** > **[!UICONTROL Felder]** > **[!UICONTROL Typ]**. Sie können dann sehen, welche Werte in der Auswahlliste enthalten sind und welche inaktiv sind. Inaktive Typen werden nicht als auswählbarer Typ in unserem &quot;[!UICONTROL Offline-Kanäle]&quot;. Bitte beachten Sie, dass dieser Vorgang einige Minuten bis zu 48 Stunden dauern kann.

Klicks **[!UICONTROL Speichern]** wenn Sie fertig sind und [!DNL Marketo Measure] lädt die Änderungen hoch und verarbeitet die Daten erneut.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Universität: Zuordnen von Offline-Kanälen](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] Universität: Synchronisieren von Offline-Kampagnen](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Integration von Marketo Engage-Programmen](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)
