---
description: Hinzufügen von [!DNL Marketo Measure] zu Aktionsleitfäden für Forms für Marketo Measure-Benutzende
title: Hinzufügen von [!DNL Marketo Measure] zu Act-On Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 1%
---
# Hinzufügen von [!DNL Marketo Measure] zu Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Anleitungen {#directions}

1. Wählen Sie im Formular, das Sie bearbeiten, die **[!UICONTROL Einstellungen]** in der rechten Ecke aus.
1. Suchen Sie nach einem Bereich mit [!UICONTROL &#x200B; Bezeichnung „Externe Web-Analyse“] Hier legen Sie das [!DNL Marketo Measure]-Trackingcode-Snippet ab.

## JavaScript von [!DNL Marketo Measure] {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Möglicherweise gibt es bereits andere Trackingcode-Snippets in diesem Bereich, z. B. einen [!DNL Google Analytics]. Achten Sie darauf, sie durch ein Semikolon `;` und ein einziges Leerzeichen zu trennen:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
