---
unique-page-id: 18874743
description: 'Verbinden [!DNL Marketo Measure] zum Aufheben des Bounce-Skript-Managers : [!DNL Marketo Measure] - Produktdokumentation'
title: Verbinden [!DNL Marketo Measure] zum Aufheben des Bounce-Skript-Managers
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Verbinden [!DNL Marketo Measure] zum Aufheben des Bounce-Skript-Managers {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] direkt mit Unbounce integriert wird, sodass Sie die Digital-Marketing-Quelle Ihrer Landingpage-Konversionen direkt in verfolgen können. [!DNL Salesforce]. Um die Verbindung herzustellen, fügen Sie einfach die [!DNL Marketo Measure] Skript zu Ihrem Unbounce Script Manager hinzufügen. So geht es.

1. Melden Sie sich bei Ihrer [!DNL Unbounce] -Konto.
1. Klicken **[!UICONTROL Einstellungen]** > **[!UICONTROL Skript-Manager]** > **[!UICONTROL Skript hinzufügen]**.
1. Wählen Sie im Popup-Fenster [!UICONTROL Benutzerdefiniertes Skript] und benennen Sie es &quot;[!DNL Marketo Measure Marketing Analytics].&quot; Klicken **[!UICONTROL Skriptdetails hinzufügen]**.
1. Wählen Sie die Platzierung im Head aus. Schließen Sie das Skript auf der Haupt-Landingpage und im Dialogfeld &quot;Formularbestätigung&quot;ein. Fügen Sie die [!DNL Marketo Measure] unten in das Feld ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken **[!UICONTROL Speichern]**.

Die [!DNL Marketo Measure] Die Integration funktioniert auf Unbounce-Landingpages, solange diese auf Ihrer Domäne (z. B. landing.mysite.com) gehostet werden und nicht auf Seiten, die die Domäne unbounce.com verwenden.
