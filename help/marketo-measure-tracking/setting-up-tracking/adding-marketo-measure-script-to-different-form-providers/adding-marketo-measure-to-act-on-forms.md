---
unique-page-id: 18874753
description: Hinzufügen [!DNL Marketo Measure] zum Handeln in Forms - [!DNL Marketo Measure] - Produktdokumentation
title: Hinzufügen [!DNL Marketo Measure] zum Handeln in Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# Hinzufügen [!DNL Marketo Measure] zum Handeln in Forms {#adding-marketo-measure-to-act-on-forms}

## Anweisungen {#directions}

1. Wählen Sie im Formular, das Sie bearbeiten, die **[!UICONTROL Einstellungen]** in der rechten Ecke.
1. Suchen Sie nach einem Bereich mit der Bezeichnung [!UICONTROL &quot;Externe Web-Analyse.&quot;] Hier legen Sie die [!DNL Marketo Measure] Trackingcode-Snippet.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Es gibt möglicherweise bereits andere Trackingcode-Snippets in diesem Bereich, z. B. eine [!DNL Google Analytics] Code. Achten Sie darauf, sie mithilfe eines Semikolons zu trennen `;` und ein einzelnes Leerzeichen wie folgt:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
