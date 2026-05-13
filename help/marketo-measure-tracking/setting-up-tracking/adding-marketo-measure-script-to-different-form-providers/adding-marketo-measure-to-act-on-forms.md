---
unique-page-id: 18874753
description: Hinzufügen von  [!DNL Marketo Measure] -zu-Akt-auf-Forms - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu Act-On-Formularen
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
TQID: https://experienceleague.adobe.com/BUdHiCxfaG7a8Tays-Oqg9ZJQjSZJMM4-ChPHuF0RCg
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 77
ht-degree: 6%

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
