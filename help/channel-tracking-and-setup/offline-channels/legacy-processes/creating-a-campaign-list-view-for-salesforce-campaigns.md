---
unique-page-id: 18874718
description: Erstellen einer Kampagnenlisten-Ansicht für  [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]
title: Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce] -Kampagnen
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 5%

---

# Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce] Kampagnen {#creating-a-campaign-list-view-for-salesforce-campaigns}

Erfahren Sie, wie Sie eine Listenansicht für die Kampagnen erstellen, die Sie mit Käufer-Touchpoints synchronisieren möchten.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

Die Kampagnenlisten-Ansicht, die erstellt werden kann, ermöglicht es Ihnen, einen &quot;go-to&quot;-Speicherort anzuzeigen und die Felder &quot;Typ&quot;und &quot;Käufer-Touchpoints aktivieren&quot;zu verwalten, um sicherzustellen, dass jede Ihrer [!DNL Salesforce] Kampagnen, die Ihre Offline-Marketing-Kanäle informieren, ordnungsgemäß eingerichtet ist.

1. Gehen Sie in [!DNL Salesforce] zur Registerkarte Kampagnen und erstellen Sie eine neue Listenansicht.
1. Nennen Sie die Ansicht &quot;Kampagnen, die mit [!DNL Marketo Measure] synchronisiert werden sollen&quot;.
1. Wir möchten, dass diese Liste nur die Kampagnen anzeigt, die wir mit [!DNL Marketo Measure] synchronisieren möchten, sodass wir ein paar Filter benötigen:

   * **Typ** [GLEICH] &#39;Alle Kampagnentypen, die wir Ihren Offline-Kanälen zugeordnet haben&#39;. Siehe Implementierungsplan oder Registerkarte Offline-Kanäle in [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mein Konto -> Einstellungen -> Offline-Kanäle). Über das Lupensymbol können Sie die gewünschten Typen auswählen (die einem Offline-Marketingkanal zugeordnet sind).

      * Wählen Sie für jeden Filter maximal 3 Typen aus. In einem Filterfeld können maximal Zeichen verwendet werden. Beginnen Sie mit 3 Typen pro Filter und fügen Sie bei Bedarf zusätzliche Zeilen von &quot;Typ&quot;-Filtern hinzu.

   * **Erstellungsdatum** [GRÖSSER ODER GLEICH] Ihr [!DNL Marketo Measure] Startdatum. Ihr Startdatum finden Sie im ROI-Dashboard in der [!DNL Marketo Measure] App. Wählen Sie einfach &quot;Seit Erstellungsdatum&quot;im Datumsbereich des Bindestrichs aus und es wird Ihr Startdatum angezeigt.
   * **&#42;Record Type&#42;** - Um in der Listenansicht Änderungen vorzunehmen, müssen Sie einen Filter für den Record Type hinzufügen. Jeder zu bearbeitende Kampagnensatz muss denselben Datensatztyp aufweisen.

1. Bearbeiten Sie die ausgewählten Felder, um sie in der Listenansicht anzuzeigen. Die vollständige Einrichtung der Listenansicht sollte wie im folgenden Beispiel aussehen:

   In dieser Ansicht können Sie Ihre Kampagnen sehen und bei Bedarf die Felder &quot;Typ&quot;und &quot;Käufer-Touchpoints aktivieren&quot;bearbeiten. Wenn Sie neue Kampagnen erstellen, die mit [!DNL Marketo Measure] synchronisiert werden sollen, werden diese in dieser Ansicht angezeigt. Sie können alle Einstellungen für diese Kampagnen direkt in der Liste verwalten.

   Um Inline-Änderungen über die Listenansicht vorzunehmen, müssen Sie sicherstellen, dass in Ihrer [!DNL Salesforce] -Einrichtung auch Folgendes zutrifft:

   * **[!UICONTROL Einrichtung]** > **[!UICONTROL Benutzeroberfläche]** > **[!UICONTROL Inline-Bearbeitung aktivieren]**
   * Außerdem müssen erweiterte Listen aktiviert werden (direkt unter dem Feld für die Inline-Bearbeitung)
   * Stellen Sie sicher, dass Sie über Berechtigungen für die Felder verfügen.

>[!MORELIKETHIS]
>
>[Beheben häufiger Probleme bei der Inline-Bearbeitung der Listenansicht](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
