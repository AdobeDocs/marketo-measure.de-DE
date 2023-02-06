---
unique-page-id: 18874755
description: Hinzufügen [!DNL Marketo Measure] nach [!DNL Marketo] Landing Pages - [!DNL Marketo Measure] - Produktdokumentation
title: Hinzufügen [!DNL Marketo Measure] zu Marketo-Landingpages
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---

# Hinzufügen [!DNL Marketo Measure] zu Marketo-Landingpages {#adding-marketo-measure-to-marketo-landing-pages}

Erfahren Sie, wie Sie Tracking zu [!DNL Marketo Engage] Landingpages, da sie eine zusätzliche Bearbeitung erfordern. [!DNL Marketo Measure] JavaScript muss sowohl auf der Landingpage als auch auf der [!DNL Marketo Engage] Formular selbst. Dazu müssen Sie die [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] wie in den folgenden Anweisungen erläutert.

>[!NOTE]
>
>Wenn Sie JavaScript über einen Tag-Management-Provider bereitstellen, z. B. [!DNL Google Tag Manager]nicht manuell hinzufügen [!DNL Marketo Measure] JS in [!DNL Marketo Engage].

## Hinzufügen von [!DNL Marketo Measure] Skript für [!DNL Marketo Engage] Landing Pages {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Melden Sie sich bei Ihrer [!DNL Marketo Engage] -Konto.
1. Wählen Sie Ihre Landingpage aus und klicken Sie auf **[!UICONTROL Entwurf bearbeiten]**.
1. Ziehen Sie in das HTML-Element.
1. Geben Sie die [!DNL Marketo Measure] JavaScript in die [!UICONTROL head] Abschnitt:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Beispiel für einen Screenshot unten

1. Klicken **[!UICONTROL Speichern]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Weitere Hinweise {#additional-notes}

* Möglicherweise sind bereits andere Trackingcode-Snippets vorhanden, z. B. eine [!DNL Google Analytics] Code. Es gibt kein Problem damit. Stellen Sie sicher, dass Sie sie mit einem Semikolon trennen `;` und ein einzelnes Leerzeichen. Ein Beispiel dafür, wie dies aussehen würde, ist:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Wahrscheinlich werden mehrere Landingpage-Vorlagen verwendet. Stellen Sie sicher, dass Sie den Code zu allen Vorlagen hinzufügen, die Formulare enthalten.

* Manchmal müssen Sie bei der Bearbeitung der Vorlage für Landingpages die Seiten erneut validieren, von denen die Landingpage verwendet wird. In diesem Artikel wird [wie eine Massengenehmigung erteilt wird](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
