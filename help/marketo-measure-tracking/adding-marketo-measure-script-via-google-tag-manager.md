---
description: Hinzufügen eines [!DNL Marketo Measure] -Skriptes über [!DNL Google Tag Manager]  – [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes über [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 95%

---


# Hinzufügen eines [!DNL Marketo Measure]-Skriptes über [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Bei der Installation des JavaScripts von [!DNL Marketo Measure] wird empfohlen, eine direkte [Hartkodierung im Skript der Website durchzuführen](/help/marketo-measure-tracking/adding-marketo-measure-script.md){target="_blank"}. Ist dies nicht möglich, können Sie auch [!DNL Google Tag Manager] (GTM) zum Laden des [!DNL Marketo Measure]-JS verwenden. Beachten Sie, dass [!DNL Marketo Measure]-JS, das über GTM geladen wird, anfällig für Latenz ist. Latenz verursacht eine Verzögerung bei der Skriptladezeit, was dazu führen kann, dass etwa 3–5 % aller Formularübermittlungen fehlen.

Wenn Sie unser Skript über GTM hinzufügen möchten, geben Sie dem [!DNL Marketo Measure]-Skript die höchste Priorität in der Auslösereihenfolge und stellen Sie sicher, dass keine synchronen Skripte vor dem [!DNL Marketo Measure]-Tag vorhanden sind, um etwaige Auswirkungen der GTM-Latenz zu reduzieren.

>[!NOTE]
>Weitere Informationen finden Sie [&#x200B; diesem „Support](https://support.google.com/tagmanager/answer/2772421?hl=de){target="_blank"}Artikel von Google&quot;.

## Hinzufügen von [!DNL Marketo Measure]-JS über [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Öffnen Sie GTM und fügen Sie das [!DNL Marketo Measure]-Skript in Ihrem Website-Container hinzu. Achten Sie darauf, das **[!UICONTROL benutzerdefinierte HTML-Tag]** auszuwählen.

1. Verwenden Sie das [!DNL Marketo Measure]-Skript unten und schließen Sie es in Ihren Container ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken Sie auf **[!UICONTROL Auslöseregel hinzufügen]**, um Google anzuweisen, unser Snippet auf *allen Seiten* zu laden.

1. Navigieren Sie auf der linken Seite zum Abschnitt mit der Container-Entwurfsübersicht. Klicken Sie auf die Schaltfläche, um eine Version Ihres Containers zu erstellen und die Änderungen zu veröffentlichen.
