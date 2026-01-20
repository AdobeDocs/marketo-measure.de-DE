---
unique-page-id: 18874743
description: Verbindung  [!DNL Marketo Measure]  Skript-Manager „Unbounce“ herstellen - [!DNL Marketo Measure]
title: Verbinden von [!DNL Marketo Measure] zum Aufheben von Bounces in Script Manager
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 7%

---

# Verbinden von [!DNL Marketo Measure] mit dem Unbounce-Skript-Manager {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] ist direkt mit Unbounce integriert, sodass Sie die digitale Marketing-Quelle Ihrer Landingpage-Konversionen direkt in [!DNL Salesforce] verfolgen können. Um die Verbindung herzustellen, fügen Sie einfach das [!DNL Marketo Measure]-Skript zu Ihrem Unbounce-Skript-Manager hinzu. Und so geht das.

1. Melden Sie sich bei Ihrem [!DNL Unbounce] an.
1. Klicken Sie **[!UICONTROL Einstellungen]** > **[!UICONTROL Skript-Manager]** > **[!UICONTROL Skript hinzufügen]**.
1. Wählen Sie im Popup &quot;[!UICONTROL  Script“ aus ] benennen Sie es &quot;[!DNL Marketo Measure Marketing Analytics]&quot;. Klicken Sie **[!UICONTROL Skriptdetails hinzufügen]**.
1. Platzierung im Kopf auswählen. Einbinden des Skripts in die Haupt-Landingpage und das Dialogfeld zur Formularbestätigung. Fügen Sie das unten stehende [!DNL Marketo Measure] in das Feld ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Die [!DNL Marketo Measure]-Integration funktioniert auf Unbounce-Landingpages, solange diese auf Ihrer Domain (z. B. landing.mysite.com) gehostet werden und nicht auf denen, die die Domain unbounce.com verwenden.
