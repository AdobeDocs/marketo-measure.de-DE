---
unique-page-id: 18874736
description: Entfernen [!DNL Marketo Measure] Tracking-Parameter aus der Landingpage-URL in Google Analytics - [!DNL Marketo Measure] - Produktdokumentation
title: Entfernen der [!DNL Marketo Measure] -Tracking-Parameter aus der Landingpage-URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 18%

---

# Entfernen der[!DNL Marketo Measure]-Tracking-Parameter aus der Landingpage-URL in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Manchmal beim Anzeigen von Landingpages in [!DNL Google Analytics], sollten Sie Tracking-Parameter aus den URLs entfernen. Andernfalls werden sie in einzelne Zeilen aufgeteilt.

Glücklicherweise ist dies eine einfache Lösung.

1. In [!DNL Google Analytics], gehen Sie zu [!UICONTROL Admin] >[!UICONTROL Anzeigeeinstellungen] >[!UICONTROL Ausschluss von URL-Abfrageparametern].
1. Geben Sie &quot;_bt,_bk,_bm,_bn,_bg&quot;in das Feld ein (ohne die Anführungszeichen).
1. Scrollen Sie nach unten und klicken Sie auf **[!UICONTROL Speichern]**.

   Bedenken Sie Folgendes [!DNL Google Analytics] verarbeitet keine Daten erneut. Daher spiegelt sich diese Änderung nur in Zukunft wider und Ihre früheren Daten werden weiterhin mit den Parametern bt, bk und bm angezeigt.
