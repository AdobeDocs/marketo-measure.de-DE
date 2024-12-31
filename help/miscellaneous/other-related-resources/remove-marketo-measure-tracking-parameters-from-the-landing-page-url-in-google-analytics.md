---
unique-page-id: 18874736
description: Entfernen  [!DNL Marketo Measure]  Tracking-Parameter aus der Landingpage-URL in Google Analytics - [!DNL Marketo Measure]
title: Entfernen der [!DNL Marketo Measure] -Tracking-Parameter aus der Landingpage-URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 9%

---

# Entfernen [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Wenn Sie Landingpages in [!DNL Google Analytics] anzeigen, sollten Sie manchmal Tracking-Parameter aus den URLs entfernen. Andernfalls teilen sie sich in einzelne Zeilen auf.

Glücklicherweise ist dies eine einfache Lösung.

1. Navigieren Sie [!DNL Google Analytics] zu [!UICONTROL Admin] > [!UICONTROL Anzeigeeinstellungen] > [!UICONTROL URL-Abfrageparameter ausschließen].
1. Geben Sie „_bt,_bk,_bm,_bn,_bg“ in das Feld ein (ohne die Anführungszeichen).
1. Scrollen Sie nach unten und klicken Sie auf **[!UICONTROL Speichern]**.

   Beachten Sie, dass [!DNL Google Analytics] Daten nicht erneut verarbeitet. Daher wird diese Änderung nur in Zukunft berücksichtigt und Ihre früheren Daten werden weiterhin mit den Parametern bt, bk und bm angezeigt.
