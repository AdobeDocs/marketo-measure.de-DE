---
unique-page-id: 18874718
description: Erstellen einer Kampagnenlistenansicht für [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]
title: Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce] -Kampagnen
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 5%

---

# Erstellen einer Kampagnenlistenansicht für [!DNL Salesforce] Kampagnen {#creating-a-campaign-list-view-for-salesforce-campaigns}

Erfahren Sie, wie Sie eine Listenansicht für die Kampagnen erstellen, die Sie mit Käufer-Touchpoints synchronisieren möchten.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

In der Listenansicht der Kampagne, die erstellt werden kann, haben Sie die Möglichkeit, einen „go-to“-Speicherort zu wählen, um die Felder „Typ“ und „Käufer-Touchpoints aktivieren“ anzuzeigen und zu verwalten, um sicherzustellen, dass jede Ihrer [!DNL Salesforce] Kampagnen, die Ihre Offline-Marketing-Kanäle informieren, ordnungsgemäß eingerichtet ist.

1. Gehen Sie zur Registerkarte Kampagnen in [!DNL Salesforce] und erstellen Sie eine neue Listenansicht
1. Nennen Sie die Ansicht „Kampagnen, die mit [!DNL Marketo Measure] synchronisiert werden sollen“.
1. Wir möchten, dass diese Liste nur die Kampagnen anzeigt, mit denen wir synchronisieren möchten[!DNL Marketo Measure] Daher benötigen wir einige Filter:

   * **Typ** [GLEICH] „Alle Kampagnentypen, die wir Ihren Offline-Kanälen zugeordnet haben“. Weitere Informationen finden Sie in Ihrem Implementierungsplan oder auf der Registerkarte „Offline-Kanäle“ in [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mein Konto -> Einstellungen -> Offline-Kanäle). Sie können die gewünschten Typen (die einem Offline-Marketing-Kanal zugeordnet sind) über das Lupensymbol auswählen.

      * Wählen Sie maximal 3 Typen für jeden Filter. Es gibt eine Begrenzung von Zeichen, die Sie in einem Filterfeld haben können. Beginnen Sie mit 3 Typen pro Filter und fügen Sie bei Bedarf zusätzliche Zeilen von „Typ“-Filtern hinzu.

   * **Erstellungsdatum** [GRÖSSER ODER GLEICH] Ihr [!DNL Marketo Measure]. Ihr Startdatum finden Sie im ROI-Dashboard der [!DNL Marketo Measure] App. Wählen Sie einfach &#39;Seit Erstellungsdatum&#39; im Datumsbereich des Bindestrichs aus und es wird Ihr Startdatum angezeigt.
   * **&#42;Datensatztyp&#42;**: Um Änderungen in der Listenansicht vorzunehmen, müssen Sie einen Filter für Datensatztyp hinzufügen. Jeder Kampagnendatensatz, den Sie möglicherweise bearbeiten müssen, muss vom gleichen Datensatztyp sein.

1. Ausgewählte Felder bearbeiten, um sie in der Listenansicht anzuzeigen. Die vollständige Einrichtung der Listenansicht sollte wie im folgenden Beispiel aussehen:

   In dieser Ansicht können Sie Ihre Kampagnen anzeigen und die Felder „Typ“ und „Käufer-Touchpoints aktivieren“ bearbeiten, falls erforderlich. Wenn Sie neue Kampagnen erstellen, die mit [!DNL Marketo Measure] synchronisiert werden sollen, werden sie in dieser Ansicht angezeigt, und Sie können alle Einstellungen für diese Kampagnen direkt in der Liste verwalten.

   Um Inline-Bearbeitungen über die Listenansicht vorzunehmen, müssen Sie sicherstellen, dass auch in Ihrer [!DNL Salesforce]-Einrichtung Folgendes zutrifft:

   * **[!UICONTROL Setup]** > **[!UICONTROL Benutzeroberfläche]** > **[!UICONTROL Inline-Bearbeitung aktivieren]**
   * Außerdem müssen erweiterte Listen aktiviert sein (direkt unter dem Feld für Inline-Bearbeitung)
   * Stellen Sie sicher, dass Sie über Berechtigungen für die Felder verfügen

>[!MORELIKETHIS]
>
>[Beheben häufiger Probleme bei der Inline-Bearbeitung von Listenansichten](http://help.salesforce.com/articleView?id=000003911&language=en_US&type=1){target="_blank"}
