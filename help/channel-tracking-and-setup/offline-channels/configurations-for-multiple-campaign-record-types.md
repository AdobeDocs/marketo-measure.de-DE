---
unique-page-id: 18874686
description: Konfigurationen für mehrere Kampagnentypen - [!DNL Marketo Measure] - Produktdokumentation
title: Konfigurationen für mehrere Kampagnentypen
exl-id: 10499556-a591-4630-9149-ae676e6494af
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 8%

---

# Konfigurationen für mehrere Kampagnentypen {#configurations-for-multiple-campaign-record-types}

**Fehlende Picklist-Werte aus dem Feld &quot;Käufer-Touchpoints aktivieren&quot;**

Wenn Ihre SFDC-Organisation mehrere Kampagnentyps verwendet, müssen die Picklist-Werte für &quot;Käufer-Touchpoints aktivieren&quot;für jeden Datensatztyp hinzugefügt werden. Gehen Sie wie folgt vor, um die Optionen hinzuzufügen.

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Kampagnen]** > **[!UICONTROL Datensatztypen]**.

   ![](assets/1.jpg)

1. Wählen Sie die Kampagnentypen aus, indem Sie auf die Schaltfläche **[!UICONTROL Beschriftung für Datentyp]**, nicht die [!UICONTROL edit] Schaltfläche.

   ![](assets/2.jpg)

1. Hier werden Sie mit den verfügbaren Picklists für diesen Datensatztyp auf den Bildschirm gebracht. Auswählen **[!UICONTROL Bearbeiten]** neben dem Feld &quot;Käufer-Touchpoints aktivieren&quot;.

   ![](assets/3.jpg)

1. Fügen Sie alle drei Werte aus der Gruppe &quot;Verfügbare Werte&quot;zur Gruppe &quot;Ausgewählte Werte&quot;hinzu.

   ![](assets/4.jpg)

1. Legen Sie den Standardwert auf &quot;None&quot;fest und klicken Sie auf **[!UICONTROL Speichern]**. Wiederholen Sie diese Schritte für alle weiteren Kampagnenersatztypen.
