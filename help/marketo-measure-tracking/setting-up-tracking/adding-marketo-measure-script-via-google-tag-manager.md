---
unique-page-id: 18874797
description: Hinzufügen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager] - [!DNL Marketo Measure] - Produktdokumentation
title: Hinzufügen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Hinzufügen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Bei der Installation der [!DNL Marketo Measure] JavaScript verwenden, empfehlen wir dringend [Hartkodierung des Skripts](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target="_blank"} direkt in Ihre Site. Ist dies jedoch nicht möglich, können Sie auch [!DNL Google Tag Manager] (GTM), um die [!DNL Marketo Measure] JS. Bitte beachten Sie, dass [!DNL Marketo Measure] Durch GTM geladene JS sind anfällig für Latenzzeiten. Latenz verursacht eine Verzögerung bei der Skriptladezeit, was dazu führen kann, dass etwa 3-5 % aller Formularübermittlungen fehlen.

Wenn Sie unser Skript über GTM hinzufügen möchten, legen Sie bitte die [!DNL Marketo Measure] Skript mit der höchsten Priorität in Ihrer Auslöserreihenfolge verwenden und sicherstellen, dass keine synchronen Skripte vor der [!DNL Marketo Measure] -Tag, um die Auswirkungen der GTM-Latenz zu reduzieren.

>[!NOTE]
>
>Verwenden Sie diese [Supportartikel von Google](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} , um mehr zu erfahren.

## Hinzufügen [!DNL Marketo Measure] JS über [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Öffnen Sie GTM und fügen Sie die [!DNL Marketo Measure] Skript in Ihrem Website-Container. Stellen Sie sicher, dass Sie **[!UICONTROL Benutzerdefiniertes HTML-Tag]**.

1. Verwenden Sie die [!DNL Marketo Measure] unten und fügen Sie es in Ihren Container ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klicken **[!UICONTROL Auslöserregel hinzufügen]** damit Sie Google anweisen können, unser Snippet zu laden *Alle Seiten*.

1. Navigieren Sie auf der linken Seite zum Abschnitt Übersicht über Container-Entwurf . Klicken Sie auf die Schaltfläche , um eine neue Version Ihres Containers zu erstellen und die Änderungen zu veröffentlichen.
