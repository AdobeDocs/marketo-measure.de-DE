---
unique-page-id: 18874757
description: Hinzufügen von [!DNL Marketo Measure] JavaScript zu [!DNL Pardot] - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] JavaScript zu [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Hinzufügen von [!DNL Marketo Measure] JavaScript zu [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] Formulare erfordern eine zusätzliche Verarbeitung innerhalb der Formularvorlage, bevor Skript auf der Site eingefügt wird, damit [!DNL Marketo Measure] die Formularübermittlungen erkennen kann. Der Prozess ist einfach. Es ist nur erforderlich, das Tracking-Skript [!DNL Marketo Measure] in die Formularvorlage [!DNL Pardot] zu platzieren.

## Schrittweise Anleitungen {#step-by-step-instructions}

Nachdem Sie sich bei Ihrem [!DNL Pardot] -Konto angemeldet haben, führen Sie die folgenden Schritte aus.

1. Navigieren Sie zu **[!UICONTROL Marketing]**.

1. Klicken Sie auf **[!UICONTROL Landingpages]**.

1. Wählen Sie **[!UICONTROL Layout-Vorlage]** aus.

   ![](assets/1-3.png)

1. Legen Sie die entsprechende Layoutvorlage fest und klicken Sie rechts auf **[!UICONTROL Bearbeiten]**.

   ![](assets/2-1.png)

1. Kopieren Sie den JavaScript-Code [!DNL Marketo Measure] direkt vor dem schließenden -Header-Tag auf Ihrer HTML-Seite und fügen Sie ihn ein.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Führen Sie diese Schritte für alle entsprechenden Landingpage-Layoutvorlagen aus.

1. Stellen Sie sicher, dass sich die [!DNL Marketo Measure] JavaScript auch auf der allgemeinen Site-Seite befindet.

   Innerhalb der [!DNL Pardot]-Layout-Vorlage sieht der Code etwa so aus:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Weitere Hinweise {#additional-notes}

Wenn der [!DNL Pardot] IFrame das folgende HTML-Tag aufweist:

`<base href="http://go.pardot.com">`

_Und_ Der IFrame selbst ist eigentlich eine sichere Seite (HTTPS) und nicht unsicher (HTTP). Beim Laden des Skripts im [!DNL Pardot] IFrame versucht der Browser, eine HTTP-Version des Skripts auf einer HTTPS-Seite zu laden, die fehlschlägt und das Tracking unterbricht. Die Lösung besteht darin, das Skript im IFrame [!DNL Pardot] zu aktualisieren, um die sichere Version des Skripts zu laden:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

In diesem Bereich gibt es möglicherweise bereits andere Trackingcode-Snippets, z. B. einen [!DNL Google Analytics] -Code. Trennen Sie sie unbedingt durch ein Semikolon `;` und ein einzelnes Leerzeichen, wie in diesem Beispiel gezeigt:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
