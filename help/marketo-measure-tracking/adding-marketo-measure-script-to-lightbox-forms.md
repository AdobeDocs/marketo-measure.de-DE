---
description: Anleitung  [!DNL Marketo Measure]  Hinzufügen von Skripten zu Lightbox Forms für Marketo Measure-Benutzer
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Lightbox Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Hinzufügen [!DNL Marketo Measure] Skripts zu Lightbox Forms {#adding-marketo-measure-script-to-lightbox-forms}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript ordnungsgemäß zu einem Formular in einer Lightbox hinzufügen.

Eine Lightbox öffnet ein Formular vor Ihrem Inhalt, wenn der Besucher eine bestimmte Aktion ausführt (d. h. auf einen bestimmten Teil der Seite klickt, eine bestimmte Zeit auf der Seite verbringt usw.). Normalerweise möchten wir die [!DNL Marketo Measure] JavaScript im Kopf der Landingpage platzieren. Für Formulare in einer Lightbox ist jedoch ein zusätzlicher Schritt erforderlich.

Da ein Formular innerhalb einer Lightbox im Grunde ein Formular innerhalb eines iFrames ist, wird das Skript innerhalb dieses iFrames platziert.

Suchen Sie zunächst den iFrame, in dem [!UICONTROL Lightbox]-Formular vorhanden ist.

![Suchen Sie zunächst den iFrame, in dem sich das Lightbox-Formular befindet.](assets/adding-providers-8.png)

Platzieren Sie anschließend die [!DNL Marketo Measure] JavaScript im iFrame.

![Platzieren Sie als Nächstes die Marketo Measure JavaScript im iFrame.](assets/adding-providers-5.png)

Wenn die JavaScript hinzugefügt wird, werden Übermittlungen von Formularen durch Befolgen der folgenden Anweisungen überprüft:

1. Kopieren Sie die URL der Landingpage, die das Formular [!UICONTROL Lightbox] enthält.
1. Öffnen Sie einen Inkognito-Browser und fügen Sie die URL ein.
1. Senden Sie das Formular mit einer eindeutigen E-Mail-Adresse.
1. Vergewissern Sie sich, dass der Test verfolgt wurde, indem Sie in Ihrem CRM nach der verwendeten eindeutigen E-Mail-Adresse suchen und sicherstellen, dass die Touchpoint-Daten ausgefüllt sind.
