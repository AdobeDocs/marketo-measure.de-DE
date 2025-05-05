---
unique-page-id: 18874753
description: Hinzufügen von  [!DNL Marketo Measure] -zu-Akt-auf-Forms - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu Act-On-Formularen
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

---

# Hinzufügen von [!DNL Marketo Measure] zu Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Anleitungen {#directions}

1. Wählen Sie im Formular, das Sie bearbeiten, die **[!UICONTROL Einstellungen]** in der rechten Ecke aus.
1. Suchen Sie nach einem Bereich mit [!UICONTROL &#x200B; Bezeichnung „Externe Web-Analyse“.] Hier legen Sie das [!DNL Marketo Measure]-Trackingcode-Snippet ab.

## JavaScript von [!DNL Marketo Measure]  {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Möglicherweise gibt es bereits andere Trackingcode-Snippets in diesem Bereich, z. B. einen [!DNL Google Analytics]. Achten Sie darauf, sie durch ein Semikolon `;` und ein einziges Leerzeichen zu trennen:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
