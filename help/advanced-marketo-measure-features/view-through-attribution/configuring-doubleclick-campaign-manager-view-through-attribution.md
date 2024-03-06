---
unique-page-id: 18874781
description: Konfiguration der doppelten Klick-Kampagnen-Manager-Ansicht über Attribution - [!DNL Marketo Measure]
title: Konfiguration der DoubleClick Campaign Manager-Ansicht über Attribution
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---

# Konfiguration der DoubleClick Campaign Manager-Ansicht über Attribution {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Anzeigen durch Attribution {#measuring-view-through-attribution}

>[!NOTE]
>
>Wenn Sie die [!DNL Marketo Measure] und [!DNL DoubleClick Campaign Manager] Integration, benötigen wir eine [API-Verbindung](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) so können wir Details der Kampagnen und kreativen Inhalte herunterladen, um die Anzeigen zu lösen.

So erhalten Sie genauere Einblicke aus der Ansicht durch das Tracking mit [!DNL Doubleclick Campaign Manager], muss unser Tracking-Pixel konfiguriert werden.

Weitere Informationen zum [!DNL Marketo Measure] Durchsicht der Attributionsfunktionen, siehe [Häufig gestellte Fragen zur Marketo Measure-Ansicht durch Attribution](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md).

[!DNL Marketo Measure] wird als Huckepack-Tag betrachtet, da es sich um einen Drittanbieter-Aufruf über das DCM-Anzeigen-Tag handelt. Piggyback-Tags funktionieren nicht mit Bild-Tags, sondern nur mit iFrame- oder JavaScript-Tags. Nach Angaben des DCM-Supports hat sich dies in letzter Zeit nicht geändert und war immer der Fall. Standard-Tags werden seit dem 2. Oktober 2017 nicht mehr unterstützt, beeinträchtigen jedoch nicht die Fähigkeit von [!DNL Marketo Measure] , um die Impressionen zu verfolgen.

Wenn Sie eine Hierarchie der übergeordneten Elemente und untergeordneten Elemente in DCM verwenden, muss unser Tag für das Impression-Tracking auf allen Ebenen angewendet werden.

## Hinzufügen des Bild-Tags {#how-to-add-the-image-tag}

Fügen Sie das Tag unter der Advertiser-Einstellung in DoubleClick hinzu und erstellen Sie ein Impressionsereignis-Tag.

1. Fügen Sie den folgenden Code als 1x1-Bildpixel hinzu.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Vergewissern Sie sich nach dem Hinzufügen, dass die Trennzeichen wie folgt zugeordnet sind. Dies sollte automatisch erfolgen, sobald das -Tag angewendet wird:

   v = %eadv! [!DNL Expand] Advertiser-ID\
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

A: dfatrafficking, dfareporting, userinfo.email

**F: Wie lange kann der Import von Ausgabedaten dauern?**

A: Bis zu 6 Stunden

**F: Wie lange kann der Import von Anzeigendaten dauern?**

A: Bis zu 6 Stunden
