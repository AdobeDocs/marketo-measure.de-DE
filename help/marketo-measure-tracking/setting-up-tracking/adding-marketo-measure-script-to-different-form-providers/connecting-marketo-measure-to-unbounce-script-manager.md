---
unique-page-id: 18874743
description: Verbinden von [!DNL Marketo Measure] mit dem Unbounce-Skript-Manager - [!DNL Marketo Measure]
title: Verbinden von [!DNL Marketo Measure] zum Aufheben von Bounces in Script Manager
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 5%

---

# Verbinden von [!DNL Marketo Measure] mit dem Unbounce Script Manager {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] lässt sich direkt in Unbounce integrieren, sodass Sie die digitale Marketingquelle Ihrer Landingpage-Konversionen direkt in [!DNL Salesforce] verfolgen können. Um die Verbindung herzustellen, fügen Sie einfach das Skript [!DNL Marketo Measure] zu Ihrem Unbounce Script Manager hinzu. So geht es.

1. Melden Sie sich bei Ihrem [!DNL Unbounce] -Konto an.
1. Klicken Sie auf **[!UICONTROL Einstellungen]** > **[!UICONTROL Skript-Manager]** > **[!UICONTROL Skript hinzufügen]**.
1. Wählen Sie im Popup-Fenster [!UICONTROL Benutzerdefiniertes Skript] aus und geben Sie ihm den Namen &quot;[!DNL Marketo Measure Marketing Analytics]&quot;. Klicken Sie auf **[!UICONTROL Skriptdetails hinzufügen]**.
1. Wählen Sie die Platzierung im Head aus. Schließen Sie das Skript auf der Haupt-Landingpage und im Dialogfeld &quot;Formularbestätigung&quot;ein. Fügen Sie das Skript [!DNL Marketo Measure] unten in das Feld ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Die Integration von [!DNL Marketo Measure] funktioniert auf Landingpages zum Aufheben der Bounce-Wiedergabe, sofern sie auf Ihrer Domäne (z. B. landing.mysite.com) gehostet werden und nicht auf Seiten, die die Domäne unbounce.com verwenden.
