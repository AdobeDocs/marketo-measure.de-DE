---
unique-page-id: 18874783
description: Ausschließen von [!DNL Marketo Measure] aus einer bestimmten Forms - [!DNL Marketo Measure]
title: Ausschließen von [!DNL Marketo Measure] von bestimmter Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 4%

---

# Ausschließen von [!DNL Marketo Measure] aus einer bestimmten Forms {#excluding-marketo-measure-from-specific-forms}

Standardmäßig hängt [!DNL Marketo Measure] an alle Formulare auf Ihrer Site an. Nicht alle Formularübermittlungen sollten jedoch unbedingt nachverfolgt oder in ein Attributionsmodell aufgenommen werden. Dies liegt daran, dass nicht alle Formulare als &quot;gut&quot;betrachtet werden. Ein Beispiel hierfür ist eine Abmeldeseite/-Formular. Darüber hinaus werden Anmeldeformulare in der Regel nicht verfolgt, da dies das Attributionsmodell verwässert.

## Hinzufügen von [!DNL Marketo Measure]-Ausschluss-Code:  {#how-to-add-marketo-measure-exclude-code}

Um zu verhindern, dass [!DNL Marketo Measure] bestimmte Formulare verfolgt, fügen Sie einfach &quot;[!DNL Bizible-Exclude]&quot;als &quot;Klasse&quot;in Ihr Formular ein. Der Code lautet wie folgt:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
