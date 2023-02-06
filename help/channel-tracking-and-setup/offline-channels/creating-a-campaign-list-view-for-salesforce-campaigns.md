---
unique-page-id: 18874718
description: Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce Campaigns] - [!DNL Marketo Measure] - Produktdokumentation
title: Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce] Kampagnen
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Erstellen einer Kampagnenlisten-Ansicht für [!DNL Salesforce] Kampagnen {#creating-a-campaign-list-view-for-salesforce-campaigns}

Erfahren Sie, wie Sie eine Listenansicht für die Kampagnen erstellen, die Sie mit Käufer-Touchpoints synchronisieren möchten.

Die Kampagnenlistenansicht, die erstellt werden kann, ermöglicht es Ihnen, einen &quot;go-to&quot;-Speicherort anzuzeigen und die Felder &quot;Typ&quot; und &quot;Käufer-Touchpoints aktivieren&quot;zu verwalten, um sicherzustellen, dass jede Ihrer [!DNL Salesforce] Kampagnen, die Ihre Offline-Marketing-Kanäle informieren, ordnungsgemäß eingerichtet sind.

1. Navigieren Sie zur Registerkarte Kampagnen unter [!DNL Salesforce] und eine neue Listenansicht erstellen
1. Benennen Sie die Ansicht &quot;Kampagnen, mit denen synchronisiert werden soll&quot;. [!DNL Marketo Measure].&quot;
1. Wir möchten, dass diese Liste nur die Kampagnen anzeigt, mit denen wir synchronisieren möchten [!DNL Marketo Measure] Daher benötigen wir einige Filter:

   * **Typ** [GLEICH] &quot;Alle Kampagnentypen, die wir Ihren Offline-Kanälen zugeordnet haben&quot;. Siehe Implementierungsplan oder Registerkarte Offline-Kanäle in [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mein Konto -> Einstellungen -> Offline-Kanäle). Über das Lupensymbol können Sie die gewünschten Typen auswählen (die einem Offline-Marketingkanal zugeordnet sind).

      * Wählen Sie für jeden Filter maximal 3 Typen aus. In einem Filterfeld können maximal Zeichen verwendet werden. Beginnen Sie mit 3 Typen pro Filter und fügen Sie bei Bedarf zusätzliche Zeilen von &quot;Typ&quot;-Filtern hinzu.
   * **Erstellungsdatum** [GRÖSSER ODER GLEICH] Ihre [!DNL Marketo Measure] Startdatum. Ihr Startdatum finden Sie im ROI-Dashboard im Abschnitt [!DNL Marketo Measure] App. Wählen Sie einfach &quot;Seit Erstellungsdatum&quot;im Datumsbereich des Bindestrichs aus und es wird Ihr Startdatum angezeigt.
   * **&#42;Record Type&#42;** - Um Änderungen in der Listenansicht vorzunehmen, müssen Sie einen Filter für den Datensatztyp hinzufügen. Jeder zu bearbeitende Kampagnensatz muss denselben Datensatztyp aufweisen.


1. Bearbeiten Sie die ausgewählten Felder, um sie in der Listenansicht anzuzeigen. Die vollständige Einrichtung der Listenansicht sollte wie im folgenden Beispiel aussehen:

   In dieser Ansicht können Sie Ihre Kampagnen sehen und bei Bedarf die Felder &quot;Typ&quot;und &quot;Käufer-Touchpoints aktivieren&quot;bearbeiten. Beim Erstellen neuer Kampagnen, die mit synchronisiert werden sollen [!DNL Marketo Measure], werden sie in dieser Ansicht angezeigt und Sie können alle Einstellungen für diese Kampagnen direkt in der Liste verwalten.

   Um Inline-Änderungen über die Listenansicht vorzunehmen, müssen Sie sicherstellen, dass Folgendes in Ihrer [!DNL Salesforce] setup:

   * **[!UICONTROL Einrichtung]** > **[!UICONTROL Benutzeroberfläche]** > **[!UICONTROL Inline-Bearbeitung aktivieren]**
   * Außerdem müssen erweiterte Listen aktiviert werden (direkt unter dem Feld für die Inline-Bearbeitung)
   * Stellen Sie sicher, dass Sie über Berechtigungen für die Felder verfügen.

>[!MORELIKETHIS]
>
>[Beheben häufiger Probleme bei der Inline-Bearbeitung der Listenansicht](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
