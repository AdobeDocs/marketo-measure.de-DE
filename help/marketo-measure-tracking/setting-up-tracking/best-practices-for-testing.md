---
unique-page-id: 18874722
description: Best Practices für Tests - [!DNL Marketo Measure]
title: Best Practices für Tests
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 16%

---

# Best Practices für Tests {#best-practices-for-testing}

Sie sollten alle verschiedenen Formulartypen testen, um sicherzustellen, dass der [!DNL Marketo Measure] JavaScript ordnungsgemäß funktioniert.

## Empfohlener Testprozess {#recommended-test-process}

1. Verwenden Sie einen Inkognito-Browser oder löschen Sie Ihre Cookies zwischen den einzelnen Formularübermittlungstests _und_, verwenden Sie jedes Mal eine andere E-Mail-Adresse.

   >[!TIP]
   >
   >Es empfiehlt sich, eine gefälschte E-Mail zu verwenden, die einen Hinweis darauf enthält, dass es sich um einen Test handelt, sowie die Tageszeit. Beispiel: `testing830am@test.com`.

1. Starten Sie Ihre Suche bei einer Suchmaschine (z. B. `google.com`) oder navigieren Sie direkt zu einem Formular.

1. Senden Sie das Formular auf Ihrer Website mit einer eindeutigen E-Mail-Adresse.

1. Notieren Sie sich die URL der Seite, auf der Sie das Formular senden, und die verwendete E-Mail-Adresse.

1. Suchen Sie den Datensatz, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

>[!NOTE]
>
>Sie können einen [!DNL Marketo Measure] Lagerbericht verwenden, z. B. Leads mit [!DNL Marketo Measure] Touchpoints, oder sich das Layout der Lead-/Kontaktseite ansehen, wenn Sie Ihre Seitenlayouts mit [!DNL Marketo Measure] Details aktualisieren möchten. Dies könnte einige Zeit in Anspruch nehmen, bis die Daten verarbeitet werden.
