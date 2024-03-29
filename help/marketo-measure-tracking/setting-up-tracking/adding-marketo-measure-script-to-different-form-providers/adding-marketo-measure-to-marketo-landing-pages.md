---
unique-page-id: 18874755
description: Hinzufügen [!DNL Marketo Measure] nach [!DNL Marketo] Landing Pages - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu Marketo-Landing-Pages
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# Hinzufügen [!DNL Marketo Measure] zu Marketo-Landingpages {#adding-marketo-measure-to-marketo-landing-pages}

Erfahren Sie, wie Sie Tracking zu [!DNL Marketo Engage] Landingpages, da sie eine zusätzliche Bearbeitung erfordern. [!DNL Marketo Measure] JavaScript muss sowohl auf der Landingpage als auch auf der [!DNL Marketo Engage] Formular selbst. Dazu müssen Sie die [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] wie in den folgenden Anweisungen erläutert.

>[!NOTE]
>
>Wenn Sie JavaScript über einen Tag-Management-Provider bereitstellen, z. B. [!DNL Google Tag Manager]nicht manuell hinzufügen [!DNL Marketo Measure] JS in [!DNL Marketo Engage].

## Hinzufügen von [!DNL Marketo Measure] Skript für [!DNL Marketo Engage] Landing Pages {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Melden Sie sich bei Ihrer [!DNL Marketo Engage] -Konto.
1. Wählen Sie Ihre Landingpage aus und klicken Sie auf **[!UICONTROL Entwurf bearbeiten]**.
1. Ziehen Sie das Element HTML in den Arbeitsbereich.
1. Geben Sie die [!DNL Marketo Measure] JavaScript in die [!UICONTROL head] Abschnitt:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Beispiel für einen Screenshot unten

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Weitere Hinweise {#additional-notes}

* Möglicherweise sind bereits andere Trackingcode-Snippets vorhanden, z. B. [!DNL Google Analytics] Code. Es gibt kein Problem damit. Trennen Sie sie unbedingt durch ein Semikolon `;` und ein einzelnes Leerzeichen. Ein Beispiel dafür, wie dies aussehen würde:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Wahrscheinlich werden mehrere Landingpage-Vorlagen verwendet. Stellen Sie sicher, dass Sie den Code zu allen Vorlagen hinzufügen, die Formulare enthalten.

* Wenn Sie die Vorlage für Landingpages bearbeiten, müssen Sie manchmal die Seiten erneut validieren, von denen die Landingpage verwendet wird. In diesem Artikel wird [wie eine Massengenehmigung erteilt wird](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
