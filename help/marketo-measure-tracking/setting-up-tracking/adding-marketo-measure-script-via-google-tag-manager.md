---
unique-page-id: 18874797
description: Hinzufügen eines [!DNL Marketo Measure] Skriptes über [!DNL Google Tag Manager] – [!DNL Marketo Measure] – Produktdokumentation
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes über [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '200'
ht-degree: 100%

---

# Hinzufügen eines [!DNL Marketo Measure]-Skriptes über [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Bei der [!DNL Marketo Measure]-JavaScript-Installatoin empfehlen wir ausdrücklich eine direkte [Hartcodierung des Skriptes](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} auf Ihrer Site. Ist dies jedoch nicht möglich, können Sie auch [!DNL Google Tag Manager] (GTM) zum Laden des [!DNL Marketo Measure]-JS verwenden. Beachten Sie, dass durch GTM geladenes [!DNL Marketo Measure]-JS latenzanfällig ist. Latenz verursacht eine Verzögerung bei der Skriptladezeit, was dazu führen kann, dass etwa 3 bis 5 % aller Formularübermittlungen fehlen.

Wenn Sie unser Skript über GTM hinzufügen möchten, geben Sie dem [!DNL Marketo Measure]-Skript die höchste Priorität in der Auslösereihenfolge und stellen Sie sicher, dass keine synchronen Skripte vor dem [!DNL Marketo Measure]-Tag vorhanden sind, um etwaige Auswirkungen der GTM-Latenz zu reduzieren.

>[!NOTE]
>
>Weitere Informationen finden Sie in diesem [Support-Artikel von Google](https://support.google.com/tagmanager/answer/2772421?hl=de){target="_blank"}.

## Hinzufügen von [!DNL Marketo Measure]-JS über [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Öffnen Sie GTM und fügen Sie das [!DNL Marketo Measure]-Skript in Ihrem Website-Container hinzu. Achten Sie darauf, das **[!UICONTROL benutzerdefinierte HTML-Tag]** auszuwählen.

1. Verwenden Sie das [!DNL Marketo Measure]-Skript unten und schließen Sie es in Ihren Container ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken Sie auf **[!UICONTROL Auslöseregel hinzufügen]**, um Google anzuweisen, unser Snippet auf *allen Seiten* zu laden.

1. Navigieren Sie auf der linken Seite zum Abschnitt mit der Container-Entwurfsübersicht. Klicken Sie auf die Schaltfläche, um eine neue Version Ihres Containers zu erstellen und die Änderungen zu veröffentlichen.
