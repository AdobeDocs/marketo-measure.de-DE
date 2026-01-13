---
description: Konfigurieren der DoubleClick Campaign Manager-Ansicht über Attribution - [!DNL Marketo Measure]
title: Konfiguration der DoubleClick Campaign Manager-Ansicht über Attribution
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 26%

---


# Konfiguration der DoubleClick Campaign Manager-Ansicht über Attribution {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Ansicht durch Attribution messen {#measuring-view-through-attribution}

>[!IMPORTANT]
>Aus Datenschutzgründen werden Drittanbieter-Cookies immer seltener verwendet. Die von Google Chrome angekündigte Einstellung von Drittanbieter-Cookies im 3. Quartal 2024 stellt effektiv das Ende dieser Tracking-Methode dar. Daher stellt Adobe die Marketo Measure-Funktionen, die auf Drittanbieter-Cookies basieren, ein. Dies betrifft insbesondere das Domain-übergreifende Tracking und die Viewthrough-Attribution, die das Impressions-Cookie von Google/DoubleClick verwenden. Andere Funktionen von Marketo Measure sind davon nicht betroffen. Die Verwendung von Erstanbieter-Cookies ist ebenfalls nicht betroffen. In Anbetracht des Zeitplans von Google ist das geplante Einstellungsdatum der beiden oben genannten Funktionen der 1.6.2024. Zugehörige Daten, die vor diesem Datum erfasst wurden, stehen Adobe-Kundinnen und -Kunden weiterhin zur Verfügung.

>[!NOTE]
>Wenn Sie die Integration von [!DNL Marketo Measure] und [!DNL DoubleClick Campaign Manager] verwenden, benötigen wir eine [API-Verbindung](/help/api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) damit wir Details zu den Kampagnen und Kreativen herunterladen können, um die Anzeigen aufzulösen.

Um die Anzeige von insight durch Tracking mit [!DNL Doubleclick Campaign Manager] detaillierter zu gestalten, muss unser Tracking-Pixel konfiguriert werden.

Weitere Informationen zur Funktion „Durch Attribution anzeigen[!DNL Marketo Measure] finden Sie unter Häufig gestellte Fragen zur Ansicht über Attribution durch [Marketo Measure](/help/advanced-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md).

[!DNL Marketo Measure] wird als Huckepack-Tag betrachtet, da es sich um einen Drittanbieteraufruf über das DCM-Werbe-Tag handelt. Piggyback-Tags funktionieren nicht mit Bild-Tags, sondern nur mit iframe- oder JavaScript-Tags. Laut DCM-Support hat sich dies in letzter Zeit nicht geändert und war immer der Fall. Standard-Tags werden seit dem 2. Oktober 2017 nicht mehr unterstützt, haben jedoch keine Auswirkungen auf die Möglichkeit von [!DNL Marketo Measure], die Impressionen zu verfolgen.

Wenn Sie eine übergeordnete und untergeordnete Hierarchie in DCM verwenden, müssen wir unser Tag auf alle Ebenen für das Impression-Tracking anwenden.

## Hinzufügen des Bild-Tags {#how-to-add-the-image-tag}

Fügen Sie das Tag unter der Advertiser-Einstellung zu DoubleClick hinzu und erstellen Sie ein Impression Event-Tag.

1. Fügen Sie den folgenden Code als 1x1-Bildpixel hinzu.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Bestätigen Sie nach dem Hinzufügen, dass die Trennzeichen wie folgt zugeordnet sind. Dies sollte automatisch erfolgen, sobald das Tag angewendet wird:

   v = %HEADV! [!DNL Expand] Advertiser-ID\
   a = %eAid! Anzeigen-ID erweitern\
   c = %ecid! Creative-ID erweitern\
   s = %ESID! Site-ID erweitern\
   p = %EPID! Platzierungs-ID erweitern\
   m = %m Match-Code-Makro\
   n = %n Makro mit Zufallszahl

   ![DCM-Flutlicht-Tag mit Marketo Measure-Makros konfiguriert](assets/1.png)

## FAQs {#faq}

**F: Ist das Bild-Tag sicher?**

A: Ja. Es handelt sich nicht um ein JavaScript-Tag, sondern um ein Bild-Tag.

**F: Welche Berechtigungen benötigt der verbundene Benutzer?**

A: Datenhandel, dfReporting, userinfo.email

**F: Wie lange kann es dauern, Ausgabendaten zu importieren?**

A: Bis zu 6 Stunden

**F: Wie lange kann es dauern, um Anzeigendaten zu importieren?**

A: Bis zu 6 Stunden
