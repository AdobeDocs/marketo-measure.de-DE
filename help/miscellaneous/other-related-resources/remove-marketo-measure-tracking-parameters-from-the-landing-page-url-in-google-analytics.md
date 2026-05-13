---
unique-page-id: 18874736
description: Entfernen  [!DNL Marketo Measure]  Tracking-Parameter aus der Landingpage-URL in Google Analytics - [!DNL Marketo Measure]
title: Entfernen der [!DNL Marketo Measure] -Tracking-Parameter aus der Landingpage-URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
TQID: https://experienceleague.adobe.com/vKhwWUT0VQ1Kr-3-dWVWt08S4848Q0Bn4HYrGgHawb8
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 117
ht-degree: 8%

---

# Entfernen [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Wenn Sie Landingpages in [!DNL Google Analytics] anzeigen, sollten Sie manchmal Tracking-Parameter aus den URLs entfernen. Andernfalls teilen sie sich in einzelne Zeilen auf.

Glücklicherweise ist dies eine einfache Lösung.

1. Navigieren Sie [!DNL Google Analytics] zu [!UICONTROL Admin] > [!UICONTROL Anzeigeeinstellungen] > [!UICONTROL URL-Abfrageparameter ausschließen].
1. Geben Sie „_bt,_bk,_bm,_bn,_bg“ in das Feld ein (ohne die Anführungszeichen).
1. Scrollen Sie nach unten und klicken Sie auf **[!UICONTROL Speichern]**.

   Beachten Sie, dass [!DNL Google Analytics] Daten nicht erneut verarbeitet. Daher wird diese Änderung nur in Zukunft berücksichtigt und Ihre früheren Daten werden weiterhin mit den Parametern bt, bk und bm angezeigt.
