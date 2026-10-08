---
unique-page-id: 18874783
description: Ausschließen von [!DNL Marketo Measure] aus bestimmten Forms-[!DNL Marketo Measure]
title: Ausschließen von [!DNL Marketo Measure] aus bestimmten Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
TQID: 'https://experienceleague.adobe.com/RtGjsV86NEJPvUpFGnthwVGsQVpX0LqMQdC2xBSFwZc'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%
---
# Ausschließen von [!DNL Marketo Measure] aus bestimmten Forms {#excluding-marketo-measure-from-specific-forms}

Standardmäßig werden [!DNL Marketo Measure] mit allen Formularen auf Ihrer Site verbunden. Nicht alle Formularübermittlungen sollten jedoch unbedingt verfolgt oder in ein Attributionsmodell aufgenommen werden. Dies liegt daran, dass nicht alle Formularausfüllungen als „gut“ betrachtet werden. Ein Beispiel dafür ist eine Abmeldeseite/-formular. Darüber hinaus werden Anmeldeformulare normalerweise nicht verfolgt, da dies das Attributionsmodell verwässern würde.

## So fügen Sie [!DNL Marketo Measure]-Ausschluss-Code hinzu:  {#how-to-add-marketo-measure-exclude-code}

Um zu verhindern, dass [!DNL Marketo Measure] bestimmte Formulare nachverfolgen, fügen Sie einfach &quot;[!DNL Bizible-Exclude]&quot; als „Klasse“ in Ihr Formular ein. Der Code lautet wie folgt:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
