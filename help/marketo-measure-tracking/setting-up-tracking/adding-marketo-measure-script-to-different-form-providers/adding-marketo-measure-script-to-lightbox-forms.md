---
unique-page-id: 18874519
description: Hinzufügen [!DNL Marketo Measure] Script to Lightbox Forms - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 2%

---

# Hinzufügen [!DNL Marketo Measure] Skript für Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript auf ein Formular in einer Lightbox anwenden.

Eine Lightbox öffnet ein Formular vor Ihrem Inhalt, wenn der Besucher eine bestimmte Aktion ausführt (z. B. Klicken auf einen bestimmten Teil der Seite, Verbringen eines bestimmten Zeitraums auf der Seite usw.). Normalerweise bitten wir nur um die [!DNL Marketo Measure] JavaScript im Kopf der Landingpage platziert, aber für Formulare in einer Lightbox ist ein zusätzlicher Schritt erforderlich.

Da ein Formular in einer Lightbox im Grunde ein Formular in einem iFrame ist, müssen wir unser Skript in diesem iFrame platzieren.

Suchen Sie zunächst den iFrame im [!UICONTROL Lightbox] -Formular lebt in.

![](assets/1.png)

Platzieren Sie als Nächstes die [!DNL Marketo Measure] JavaScript im iFrame.

![](assets/2.png)

Wenn das JavaScript hinzugefügt wird, empfehlen wir abschließend, die Verfolgung von Formularübermittlungen anhand der folgenden Anweisungen zu überprüfen:

1. Kopieren Sie die URL der Landingpage, die die [!UICONTROL Lightbox] Formular.
1. Öffnen Sie einen Inkognito-Browser und fügen Sie die URL ein.
1. Senden Sie das Formular mit einer eindeutigen E-Mail-Adresse.
1. Vergewissern Sie sich, dass der Test nachverfolgt wurde, indem Sie in Ihrem CRM-System überprüfen, ob die verwendete E-Mail-Adresse eindeutig ist. Stellen Sie sicher, dass die Touchpoint-Daten ausgefüllt sind.
