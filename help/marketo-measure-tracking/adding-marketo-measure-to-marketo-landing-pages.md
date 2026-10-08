---
description: Hinzufügen von [!DNL Marketo Measure] zur Anleitung für Marketo Measure-Benutzer zu Marketo-Landingpages
title: Hinzufügen von [!DNL Marketo Measure] zu Marketo-Landingpages
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%
---
# Hinzufügen von [!DNL Marketo Measure] zu Marketo-Landingpages {#adding-marketo-measure-to-marketo-landing-pages}

Erfahren Sie, wie Sie Tracking zu [!DNL Marketo Engage] Landingpages hinzufügen, da diese zusätzliche Verarbeitungsschritte erfordern. [!DNL Marketo Measure] JavaScript muss sowohl auf der Landingpage als auch im [!DNL Marketo Engage] Formular selbst vorhanden sein. Dazu müssen Sie die [!DNL Marketo Measure] JavaScript wie in den folgenden Anweisungen beschrieben in [!DNL Marketo Engage] laden.

>[!NOTE]
>
>Wenn Sie die JavaScript über einen Tag-Management-Anbieter wie [!DNL Google Tag Manager] bereitstellen, müssen Sie [!DNL Marketo Measure] JS nicht manuell zu [!DNL Marketo Engage] hinzufügen.

## Hinzufügen [!DNL Marketo Measure] Skripts zu [!DNL Marketo Engage] Landingpages {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Melden Sie sich bei Ihrem [!DNL Marketo Engage] an.
1. Wählen Sie Ihre Landingpage aus und klicken Sie auf **[!UICONTROL Entwurf bearbeiten]**.
1. Ziehen Sie das Element HTML .
1. Geben Sie die [!DNL Marketo Measure] JavaScript im Abschnitt [!UICONTROL head] ein:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Beispiel im folgenden Screenshot

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![1. Klicken Sie auf Speichern.](assets/adding-pages-1.png)

## Weitere Hinweise {#additional-notes}

* Möglicherweise sind bereits andere Trackingcode-Snippets vorhanden, z. B. ein [!DNL Google Analytics]. Es ist kein Problem damit, stellen Sie sicher, dass Sie sie mit einem Semikolon `;` und einem einzigen Leerzeichen trennen. Ein Beispiel dafür, wie dies aussehen würde:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Es ist wahrscheinlich, dass Sie mehrere Landingpage-Vorlagen verwenden. Stellen Sie sicher, dass Sie den Code zu allen Vorlagen hinzufügen, die Formulare enthalten.

* Wenn Sie die Vorlage für Landingpages bearbeiten, müssen Sie manchmal die Seiten, von denen die Landingpage verwendet wird, erneut genehmigen. In diesem Artikel wird [Massenvalidierung“ &#x200B;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
