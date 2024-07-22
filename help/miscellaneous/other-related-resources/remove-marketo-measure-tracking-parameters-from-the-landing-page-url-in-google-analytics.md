---
unique-page-id: 18874736
description: Entfernen Sie  [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics - [!DNL Marketo Measure]
title: Entfernen der [!DNL Marketo Measure] -Tracking-Parameter aus der Landingpage-URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 9%

---

# Entfernen Sie [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics. {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Manchmal sollten Sie beim Anzeigen von Landingpages in [!DNL Google Analytics] Tracking-Parameter aus den URLs entfernen. Andernfalls werden sie in einzelne Zeilen aufgeteilt.

Glücklicherweise ist dies eine einfache Lösung.

1. Wechseln Sie in &quot;[!DNL Google Analytics]&quot;zu &quot;[!UICONTROL Admin]&quot;> &quot;[!UICONTROL Anzeigeeinstellungen]&quot;> &quot;[!UICONTROL URL-Abfrageparameter ausschließen]&quot;.
1. Geben Sie &quot;_bt,_bk,_bm,_bn,_bg&quot;in das Feld ein (ohne die Anführungszeichen).
1. Scrollen Sie nach unten und klicken Sie auf **[!UICONTROL Speichern]**.

   Beachten Sie, dass [!DNL Google Analytics] Daten nicht erneut verarbeitet. Daher spiegelt sich diese Änderung nur in Zukunft wider und Ihre früheren Daten werden weiterhin mit den Parametern bt, bk und bm angezeigt.
