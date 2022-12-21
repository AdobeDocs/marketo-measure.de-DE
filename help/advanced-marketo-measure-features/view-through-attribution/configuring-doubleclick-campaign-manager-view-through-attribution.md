---
unique-page-id: 18874781
description: Konfiguration der doppelten Klick-Kampagnen-Manager-Ansicht über Attribution - [!DNL Marketo Measure] - Produktdokumentation
title: Konfiguration der Doppelklick-Kampagnen-Manager-Ansicht über Attribution
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Konfiguration der Doppelklick-Kampagnen-Manager-Ansicht über Attribution {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Anzeigen durch Attribution {#measuring-view-through-attribution}

>[!NOTE]
>
>Wenn Sie die [!DNL Marketo Measure] und der DoubleClick Campaign Manager-Integration benötigen wir eine [API-Verbindung](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) so können wir Details der Kampagnen und kreativen Inhalte herunterladen, um die Anzeigen zu lösen.

Um genauere Einblicke aus der Ansicht über das Tracking mit Doubleclick Campaign Manager zu erhalten, muss unser Tracking-Pixel konfiguriert werden.

Bitte [Hier klicken](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) Weitere Informationen zu [!DNL Marketo Measure] Durchsicht der Attributionsfunktionen.

[!DNL Marketo Measure] wird als Huckepack-Tag betrachtet, da es sich um einen Drittanbieter-Aufruf über das DCM-Anzeigen-Tag handelt. Piggyback-Tags funktionieren nicht mit Bild-Tags, sondern nur mit iFrame- oder JavaScript-Tags. Nach Angaben des DCM-Supports hat sich dies in letzter Zeit nicht geändert und war immer der Fall. Standard-Tags werden seit dem 2. Oktober 2017 nicht mehr unterstützt, beeinträchtigen jedoch nicht die Fähigkeit von [!DNL Marketo Measure] , um die Impressionen zu verfolgen.

Wenn Sie eine Hierarchie der übergeordneten Elemente und untergeordneten Elemente in DCM verwenden, muss unser Tag für das Impression-Tracking auf allen Ebenen angewendet werden.

## Hinzufügen des Bild-Tags {#how-to-add-the-image-tag}

Sie fügen das Tag unter der Einstellung &quot;Advertiser&quot;in DoubleClick hinzu und erstellen ein Impressionsereignis-Tag.

1. Fügen Sie den folgenden Code als 1x1-Bildpixel hinzu.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Vergewissern Sie sich nach dem Hinzufügen, dass die Trennzeichen wie folgt zugeordnet sind. Dies sollte automatisch erfolgen, sobald das Tag angewendet wird:

   v = %eadv! Advertiser-ID erweitern\
   a = %eaid! Anzeigen-ID erweitern\
   c = %ecid! Creative-ID erweitern\
   s = %esid! Erweitern der Site-ID\
   p = %epid! Platzierungs-ID erweitern\
   m = %m Match Code Makro\
   n = %n zufällige Zahlenmakro

   ![](assets/1.png)

## FAQs {#faq}

**F: Ist das Bild-Tag sicher?**

A: Ja. Es handelt sich nicht um ein JavaScript-Tag, sondern um ein Bild-Tag.

**F: Welche Berechtigungen benötigt der verbundene Benutzer?**

A: datrafficking, dfareporting, userinfo.email

**F: Wie lange kann das Importieren von Ausgabedaten dauern?**

A: Bis zu 6 Stunden

**F: Wie lange kann der Import von Anzeigendaten dauern?**

A: Bis zu 6 Stunden
