---
description: Konfigurationen für mehrere Campaign-Datensatztypen - [!DNL Marketo Measure]
title: Konfigurationen für mehrere Kampagneneintragstypen
exl-id: 10499556-a591-4630-9149-ae676e6494af
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 7%

---


# Konfigurationen für mehrere Kampagneneintragstypen {#configurations-for-multiple-campaign-record-types}

**Fehlende Auswahllistenwerte im Feld „Käufer-Touchpoints aktivieren“**

Wenn Ihre SFDC-Organisation mehrere Kampagnendatensatztypen verwendet, müssen für jeden Datensatztyp die Werte der Auswahlliste für die „Käufer-Touchpoints aktivieren“ hinzugefügt werden. Gehen Sie wie folgt vor, um die Optionen hinzuzufügen.

1. Navigieren Sie **[!UICONTROL Setup]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Kampagnen]** > **[!UICONTROL Datensatztypen]**.

   ![Liste der Eintragstypen in Salesforce Campaign](assets/1.jpg)

1. Wählen Sie die Datensatztypen der Kampagne aus, indem Sie auf **[!UICONTROL Beschriftung Datensatztyp]** und nicht auf die Schaltfläche [!UICONTROL Bearbeiten] klicken.

   ![Detailseite für Kampagnendatensatztyp](assets/2.jpg)

1. Hier werden Sie mit den verfügbaren Auswahllisten für diesen Datensatztyp auf den Bildschirm gebracht. Wählen **[!UICONTROL Bearbeiten]** neben dem Feld „Käufer-Touchpoints aktivieren“ aus.

   ![Abschnitt „Picklisten“ mit dem Feld „Käufer-Touchpoints aktivieren“](assets/3.jpg)

1. Fügen Sie alle drei Werte aus der Gruppe „Verfügbare Werte“ zur Gruppe „Ausgewählte Werte“ hinzu.

   ![Bearbeiten Aktivieren Sie die Werte der Auswahlliste für Käufer-Touchpoints](assets/4.jpg)

1. Setzen Sie den Standardwert auf „Keine“ und klicken Sie auf **[!UICONTROL Speichern]**. Wiederholen Sie diesen Vorgang für alle weiteren Kampagnendatensatztypen.
