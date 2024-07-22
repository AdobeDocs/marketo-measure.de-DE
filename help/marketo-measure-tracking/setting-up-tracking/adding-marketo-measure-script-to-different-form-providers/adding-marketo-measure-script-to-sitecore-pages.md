---
unique-page-id: 18874747
description: Hinzufügen von [!DNL Marketo Measure] Skript zu Sitecore-Seiten - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Sitecore-Seiten
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 3%

---

# Hinzufügen von [!DNL Marketo Measure] Skript zu Sitecore-Seiten {#adding-marketo-measure-script-to-sitecore-pages}

Content Management-Systeme können zusätzliche Schritte erfordern, die über die standardmäßige Skript-Implementierung hinausgehen, damit [!DNL Marketo Measure] Formularübermittlungen erkennen kann. Im folgenden Prozess wird beschrieben, wie Sie Ihren [!DNL Sitecore] -Seiten das JavaScript [!DNL Marketo Measure] hinzufügen.

Für Sites mit Sitecore-Seiten:

1. Melden Sie sich bei SiteStore an und navigieren Sie zu Ihrer Website. Suchen Sie den Ordner [!UICONTROL Konfiguration] , der sich auf derselben Ebene wie das Element [!UICONTROL Home] und den Ordner [!UICONTROL Metadata] befindet.
1. Klicken Sie auf das Symbol **[!UICONTROL +]** neben dem Ordner [!UICONTROL Konfiguration] .
1. Klicken Sie auf das Symbol &quot;**[!UICONTROL +]**&quot;neben dem Ordner &quot;[!UICONTROL Tools]&quot;.
1. Wählen Sie das Element [!UICONTROL Javascript] aus.
1. Klicken Sie auf der Registerkarte [!UICONTROL Inhalt] auf den Link **[!UICONTROL Sperren und Bearbeiten]** , um das Element für die Bearbeitung zu entsperren.
1. Suchen Sie den Abschnitt [!UICONTROL &#39;JavaScript&#39;] . Wenn sie noch nicht erweitert ist, klicken Sie auf **[!UICONTROL +]**.
1. Geben Sie unser Skript ein: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Klicken Sie oben links auf **[!UICONTROL Speichern]** .
