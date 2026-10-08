---
description: Entfernen Sie [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in der Google Analytics-Anleitung für Marketo Measure-Benutzer
title: Entfernen [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%
---
# Entfernen [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Wenn Sie Landingpages in [!DNL Google Analytics] anzeigen, sollten Sie manchmal Tracking-Parameter aus den URLs entfernen. Andernfalls teilen sie sich in einzelne Zeilen auf.

Glücklicherweise ist dies eine einfache Lösung.

1. Navigieren Sie [!DNL Google Analytics] zu [!UICONTROL Admin] > [!UICONTROL Anzeigeeinstellungen] > [!UICONTROL URL-Abfrageparameter ausschließen].
1. Geben Sie „_bt,_bk,_bm,_bn,_bg“ in das Feld ein (ohne die Anführungszeichen).
1. Scrollen Sie nach unten und klicken Sie auf **[!UICONTROL Speichern]**.

   Beachten Sie, dass [!DNL Google Analytics] Daten nicht erneut verarbeitet. Daher wird diese Änderung nur in Zukunft berücksichtigt und Ihre früheren Daten werden weiterhin mit den Parametern bt, bk und bm angezeigt.
