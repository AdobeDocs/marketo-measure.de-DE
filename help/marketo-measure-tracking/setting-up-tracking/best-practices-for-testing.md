---
unique-page-id: 18874722
description: Best Practices für Tests - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für Tests
exl-id: ff95a1a9-d324-47f5-b47d-39014dff77e4
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 33%

---

# Best Practices für Tests {#best-practices-for-testing}

Sie sollten alle verschiedenen Formulartypen testen, um die [!DNL Marketo Measure] JavaScript funktioniert ordnungsgemäß.

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
>Sie können einen [!DNL Marketo Measure][!DNL Marketo Measure]-Stock-Bericht wie Leads mit Touchpoints verwenden oder sich das Lead-/Kontakt-Seiten-Layout ansehen, wenn Sie Ihre Seiten-Layouts mit [!DNL Marketo Measure]-Details aktualisieren. Dies könnte einige Zeit in Anspruch nehmen, bis die Daten verarbeitet werden.
