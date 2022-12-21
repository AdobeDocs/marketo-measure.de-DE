---
unique-page-id: 18874722
description: Best Practices für Tests - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für Tests
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# Best Practices für Tests {#best-practices-for-testing}

Sie sollten alle verschiedenen Formulartypen testen, um sicherzustellen, dass die [!DNL Marketo Measure] JavaScript funktioniert ordnungsgemäß.

## Empfohlener Testprozess {#recommended-test-process}

1. Verwenden Sie einen Inkognito-Browser oder leeren Sie Ihre Cookies zwischen jedem Formularübermittlungstest. _und_ jedes Mal eine andere E-Mail-Adresse verwenden.

   >[!TIP]
   >
   >Es empfiehlt sich, eine gefälschte E-Mail zu verwenden, die einen Hinweis darauf enthält, dass es sich um einen Test handelt, sowie die Tageszeit. Beispiel: `testing830am@test.com`.

1. Starten Sie Ihre Suche bei einer Suchmaschine (z. B. `google.com`) oder direkt zu einem Formular navigieren.

1. Senden Sie das Formular auf Ihrer Website mit einer eindeutigen E-Mail-Adresse.

1. Notieren Sie sich die URL der Seite, auf der Sie das Formular senden, und die verwendete E-Mail-Adresse.

1. Suchen Sie den Datensatz, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

>[!NOTE]
>
>Sie können eine [!DNL Marketo Measure] Bestandsbericht wie Leads mit [!DNL Marketo Measure] Touchpoints oder das Layout der Seite &quot;Lead/Kontakt&quot;anzeigen, wenn Sie Ihre Seitenlayouts mit [!DNL Marketo Measure] Details. Dies könnte einige Zeit in Anspruch nehmen, bis die Daten verarbeitet werden.
