---
unique-page-id: 18874747
description: Hinzufügen  [!DNL Marketo Measure]  Skripts zu Sitecore-Seiten - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Sitecore-Seiten
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
TQID: https://experienceleague.adobe.com/sXO-rCY3NbxX0AztYt-o3f-tpJFlrncLIb7-NvEjZO0
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 126
ht-degree: 3%

---

# Hinzufügen [!DNL Marketo Measure] Skripts zu Sitecore-Seiten {#adding-marketo-measure-script-to-sitecore-pages}

Content-Management-Systeme können über die Standardimplementierung hinaus zusätzliche Schritte erfordern, damit [!DNL Marketo Measure] Formularübermittlungen erkennen können. Im folgenden Prozess wird beschrieben, wie Sie den [!DNL Marketo Measure] JavaScript-Code zu Ihren [!DNL Sitecore] hinzufügen.

Für Sites mit Sitecore-Seiten:

1. Melden Sie sich bei Sitecore an und navigieren Sie zu Ihrer Website. Suchen Sie den Ordner [!UICONTROL Konfiguration], der sich auf derselben Ebene wie Ihr [!UICONTROL Startseite] Element und [!UICONTROL Metadaten] Ordner befindet.
1. Klicken Sie auf das **[!UICONTROL +]** neben dem Ordner [!UICONTROL Konfiguration].
1. Klicken Sie auf das **[!UICONTROL +]** neben dem Ordner [!UICONTROL Tools].
1. Wählen Sie das [!UICONTROL JavaScript]-Element aus.
1. Klicken Sie auf der [!UICONTROL Inhalt]-Registerkarte auf den Link **[!UICONTROL Sperren und bearbeiten]**, um das Element zur Bearbeitung zu entsperren.
1. Suchen Sie den Abschnitt [!UICONTROL JavaScript]. Wenn er noch nicht erweitert ist, klicken Sie auf das **[!UICONTROL +]**.
1. Geben Sie Ihr Skript ein: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Klicken **[!UICONTROL oben]** auf „Speichern“.
