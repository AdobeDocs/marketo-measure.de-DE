---
description: Hinzufügen von  [!DNL Marketo Measure] -on-Forms-Anleitungen für Marketo Measure-Benutzer
title: Hinzufügen von [!DNL Marketo Measure] zu Act-On-Formularen
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 6%

---

# Hinzufügen von [!DNL Marketo Measure] zu Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Anleitungen {#directions}

1. Wählen Sie im Formular, das Sie bearbeiten, die **[!UICONTROL Einstellungen]** in der rechten Ecke aus.
1. Suchen Sie nach einem Bereich mit [!UICONTROL  Bezeichnung „Externe Web-Analyse“.] Hier legen Sie das [!DNL Marketo Measure]-Trackingcode-Snippet ab.

## JavaScript von [!DNL Marketo Measure]  {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Möglicherweise gibt es bereits andere Trackingcode-Snippets in diesem Bereich, z. B. einen [!DNL Google Analytics]. Achten Sie darauf, sie durch ein Semikolon `;` und ein einziges Leerzeichen zu trennen:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
