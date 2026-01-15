---
description: Ausschließen  [!DNL Marketo Measure] aus spezifischen Forms-Anleitungen für Marketo Measure-Benutzende
title: Ausschließen von [!DNL Marketo Measure] von bestimmter Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# Ausschließen von [!DNL Marketo Measure] aus bestimmten Forms {#excluding-marketo-measure-from-specific-forms}

Standardmäßig werden [!DNL Marketo Measure] mit allen Formularen auf Ihrer Site verbunden. Nicht alle Formularübermittlungen sollten jedoch unbedingt verfolgt oder in ein Attributionsmodell aufgenommen werden. Dies liegt daran, dass nicht alle Formularausfüllungen als „gut“ betrachtet werden. Ein Beispiel dafür ist eine Abmeldeseite/-formular. Darüber hinaus werden Anmeldeformulare normalerweise nicht verfolgt, da dies das Attributionsmodell verwässern würde.

## So fügen Sie [!DNL Marketo Measure]-Ausschluss-Code hinzu:  {#how-to-add-marketo-measure-exclude-code}

Um zu verhindern, dass [!DNL Marketo Measure] bestimmte Formulare nachverfolgen, fügen Sie einfach &quot;[!DNL Bizible-Exclude]&quot; als „Klasse“ in Ihr Formular ein. Der Code lautet wie folgt:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
