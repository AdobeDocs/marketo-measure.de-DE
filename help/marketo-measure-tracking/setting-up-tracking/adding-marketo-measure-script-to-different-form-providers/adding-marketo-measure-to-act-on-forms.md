---
unique-page-id: 18874753
description: Hinzufügen von [!DNL Marketo Measure] zum Aktions-Forms - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu Act-On-Formularen
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

---

# Hinzufügen von [!DNL Marketo Measure] zum Aktiv-Forms {#adding-marketo-measure-to-act-on-forms}

## Anweisungen {#directions}

1. Wählen Sie im Formular, das Sie bearbeiten, die Option **[!UICONTROL Einstellungen]** in der rechten Ecke aus.
1. Suchen Sie nach einem Bereich mit der Bezeichnung &quot;[!UICONTROL &quot;External Web Analytics&quot;.] Hier legen Sie das Trackingcode-Fragment [!DNL Marketo Measure] ab.

## JavaScript von [!DNL Marketo Measure]  {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>In diesem Bereich gibt es möglicherweise bereits andere Trackingcode-Snippets, z. B. einen [!DNL Google Analytics] -Code. Trennen Sie sie unbedingt mit einem Semikolon `;` und einem einzelnen Leerzeichen, z. B.:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
