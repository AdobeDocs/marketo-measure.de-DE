---
unique-page-id: 18874519
description: Hinzufügen [!DNL Marketo Measure] Script to Lightbox Forms - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 2%

---

# Hinzufügen [!DNL Marketo Measure] Skript für Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript auf ein Formular in einer Lightbox anwenden.

Eine Lightbox öffnet ein Formular vor Ihrem Inhalt, wenn der Besucher eine bestimmte Aktion durchführt (d. h. beim Klicken auf einen bestimmten Teil der Seite, Verbringen einer bestimmten Zeit auf der Seite usw.). In der Regel bitten wir um die [!DNL Marketo Measure] JavaScript im Kopf der Landingpage platziert, aber für Formulare in einer Lightbox ist ein zusätzlicher Schritt erforderlich.

Da ein Formular in einer Lightbox im Wesentlichen ein Formular in einem iFrame ist, wird das Skript in diesem iFrame platziert.

Suchen Sie zunächst den iFrame im [!UICONTROL Lightbox] -Formular lebt in.

![](assets/1.png)

Platzieren Sie als Nächstes die [!DNL Marketo Measure] JavaScript im iFrame.

![](assets/2.png)

Wenn das JavaScript hinzugefügt wird, werden schließlich die Formularübermittlungen anhand der folgenden Anweisungen verfolgt:

1. Kopieren Sie die URL der Landingpage, die die [!UICONTROL Lightbox] Formular.
1. Öffnen Sie einen Inkognito-Browser und fügen Sie die URL ein.
1. Senden Sie das Formular mit einer eindeutigen E-Mail-Adresse.
1. Vergewissern Sie sich, dass der Test nachverfolgt wurde, indem Sie in Ihrem CRM-System die verwendete E-Mail-Adresse überprüfen und sicherstellen, dass die Touchpoint-Daten ausgefüllt werden.
