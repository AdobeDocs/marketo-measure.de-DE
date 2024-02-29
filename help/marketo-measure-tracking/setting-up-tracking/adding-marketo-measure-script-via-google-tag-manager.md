---
unique-page-id: 18874797
description: Hinzufügen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager] - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes über [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 59%

---

# Hinzufügen eines [!DNL Marketo Measure]-Skriptes über [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Bei der [!DNL Marketo Measure]-JavaScript-Installatoin empfehlen wir ausdrücklich eine direkte [Hartcodierung des Skriptes](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} auf Ihrer Site. Ist dies jedoch nicht möglich, können Sie auch [!DNL Google Tag Manager] (GTM), um die [!DNL Marketo Measure] JS. Beachten Sie Folgendes: [!DNL Marketo Measure] Durch GTM geladene JS sind anfällig für Latenzzeiten. Latenz verursacht eine Verzögerung bei der Skriptladezeit, was dazu führen kann, dass etwa 3 bis 5 % aller Formularübermittlungen fehlen.

Wenn Sie unser Skript über GTM hinzufügen möchten, legen Sie die [!DNL Marketo Measure] Skript mit der höchsten Priorität in Ihrer Auslöserreihenfolge verwenden und sicherstellen, dass keine synchronen Skripte vor der [!DNL Marketo Measure] -Tag, um die Auswirkungen der GTM-Latenz zu reduzieren.

>[!NOTE]
>
>Verwenden Sie diese [Supportartikel von Google](https://support.google.com/tagmanager/answer/2772421?hl=de){target="_blank"} , um mehr zu erfahren.

## Hinzufügen von [!DNL Marketo Measure]-JS über [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Öffnen Sie GTM und fügen Sie das [!DNL Marketo Measure]-Skript in Ihrem Website-Container hinzu. Achten Sie darauf, das **[!UICONTROL benutzerdefinierte HTML-Tag]** auszuwählen.

1. Verwenden Sie das [!DNL Marketo Measure]-Skript unten und schließen Sie es in Ihren Container ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken Sie auf **[!UICONTROL Auslöseregel hinzufügen]**, um Google anzuweisen, unser Snippet auf *allen Seiten* zu laden.

1. Navigieren Sie auf der linken Seite zum Abschnitt mit der Container-Entwurfsübersicht. Klicken Sie auf die Schaltfläche, um eine neue Version Ihres Containers zu erstellen und die Änderungen zu veröffentlichen.
