---
unique-page-id: 18874519
description: Hinzufügen von [!DNL Marketo Measure] Skript zu Lightbox Forms - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 2%

---

# Hinzufügen von [!DNL Marketo Measure] Skript zu Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript ordnungsgemäß zu einem Formular in einer Lightbox hinzufügen.

Eine Lightbox öffnet ein Formular vor Ihrem Inhalt, wenn der Besucher eine bestimmte Aktion durchführt (d. h. beim Klicken auf einen bestimmten Teil der Seite, Verbringen einer bestimmten Zeit auf der Seite usw.). In der Regel bitten wir darum, die [!DNL Marketo Measure] JavaScript im Kopf der Landingpage platzieren zu lassen. Für Formulare in einer Lightbox ist jedoch ein zusätzlicher Schritt erforderlich.

Da ein Formular in einer Lightbox im Wesentlichen ein Formular in einem iFrame ist, wird das Skript in diesem iFrame platziert.

Suchen Sie zunächst den iFrame, in dem sich das Formular [!UICONTROL Lightbox] befindet.

![](assets/1.png)

Platzieren Sie als Nächstes die [!DNL Marketo Measure] JavaScript im iFrame.

![](assets/2.png)

Wenn die JavaScript hinzugefügt wird, werden schließlich die Formularübermittlungen anhand der folgenden Anweisungen verfolgt:

1. Kopieren Sie die URL der Landingpage, die das Formular [!UICONTROL Lightbox] enthält.
1. Öffnen Sie einen Inkognito-Browser und fügen Sie die URL ein.
1. Senden Sie das Formular mit einer eindeutigen E-Mail-Adresse.
1. Vergewissern Sie sich, dass der Test nachverfolgt wurde, indem Sie in Ihrem CRM-System die verwendete E-Mail-Adresse überprüfen und sicherstellen, dass die Touchpoint-Daten ausgefüllt werden.
