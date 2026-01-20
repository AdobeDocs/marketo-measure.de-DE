---
unique-page-id: 18874722
description: Best Practices für Tests - [!DNL Marketo Measure]
title: Best Practices für Tests
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 19%

---

# Best Practices für Tests {#best-practices-for-testing}

Sie sollten alle verschiedenen Formulartypen testen, um sicherzustellen, dass die [!DNL Marketo Measure] JavaScript ordnungsgemäß funktioniert.

## Empfohlener Testprozess {#recommended-test-process}

1. Verwenden Sie einen Inkognito-Browser oder löschen Sie Ihre Cookies zwischen jedem Formularübermittlungstest _und_ verwenden Sie jedes Mal eine andere E-Mail-Adresse.

   >[!TIP]
   >
   >Es empfiehlt sich, eine gefälschte E-Mail zu verwenden, die etwas enthält, das darauf hinweist, dass es sich um einen Test handelt, sowie die Tageszeit. Beispiel: `testing830am@test.com`.

1. Beginnen Sie Ihre Suche mit einer Suchmaschine (z. B. `google.com`) oder navigieren Sie direkt zu einem Formular.

1. Senden Sie das Formular mit einer eindeutigen E-Mail-Adresse auf Ihrer Website.

1. Notieren Sie sich die URL der Seite, auf der Sie das Formular senden, und die verwendete E-Mail-Adresse.

1. Suchen Sie den Eintrag, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

>[!NOTE]
>
>Sie können einen [!DNL Marketo Measure] Stock-Bericht verwenden, z. B. Leads mit [!DNL Marketo Measure] Touchpoints, oder sich das Lead/Kontakt-Seiten-Layout ansehen, wenn Sie Ihre Seiten-Layouts mit [!DNL Marketo Measure] Details aktualisieren möchten. Es kann einige Zeit dauern, bis die Daten verarbeitet werden.
