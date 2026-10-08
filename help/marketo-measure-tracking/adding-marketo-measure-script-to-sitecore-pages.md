---
description: Hinzufügen [!DNL Marketo Measure] Skripts zu Sitecore-Seiten für Marketo Measure-Benutzer
title: Hinzufügen [!DNL Marketo Measure] Skripts zu Sitecore-Seiten
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 0%
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
