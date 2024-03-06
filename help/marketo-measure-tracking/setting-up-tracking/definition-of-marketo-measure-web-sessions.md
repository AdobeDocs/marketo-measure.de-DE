---
unique-page-id: 18874564
description: Definition [!DNL Marketo Measure] Web-Sitzungen - [!DNL Marketo Measure]
title: Definition von  [!DNL Marketo Measure] -Web-Sitzungen
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 61%

---

# Definition von [!DNL Marketo Measure]-Web-Sitzungen {#definition-of-marketo-measure-web-sessions}

Erfahren Sie, wie [!DNL Marketo Measure] Web-Sitzungen definiert.

Eine **Web-Sitzung** bezieht sich auf die Interaktionen einer Person mit Ihrer Website während eines bestimmten Zeitraums. Die Sitzung beginnt, wenn eine Benutzerin oder ein Benutzer auf Ihre Website gelangt.

Beispiel: Hanna besucht adobe.com/de. Mit ihrem Besuch auf der Site beginnt eine Sitzung. Wenn Hanna die Site verlässt, indem sie die Registerkarte/den Web-Browser schließt oder von der Site weg navigiert, endet die Sitzung.

Eine Benutzerin oder ein Benutzer kann nicht mehrere Sitzungen gleichzeitig öffnen. Wenn Haley geöffnet wird [!DNL adobe.com] in zehn verschiedenen Tabs wurde nur eine Sitzung im Zusammenhang mit ihrem Besuch auf der Website erstellt.

## Wie definiert [!DNL Marketo Measure] eine neue Sitzung? {#how-does-marketo-measure-define-a-new-session}

Wann eine Sitzung endet und eine neue Sitzung beginnt, wird durch verschiedene Aspekte bestimmt. Es gibt zwei Hauptmöglichkeiten, wie [!DNL Marketo Measure]-Sitzungen enden können:

* **zeitbasierter Ablauf**
* **kanalbasierter Ablauf**

## Zeitbasierter Ablauf {#time-based-expiration}

**Wie lange dauert eine Sitzung?**

[!DNL Marketo Measure]-Sitzungen enden nach 30 Minuten Inaktivität auf der Website. Beispiel:

Wenn Hanna adobe.com/de besucht, beginnt eine Sitzung. Sie erkundet die Website für einige Minuten und geht dann von ihrem Computer weg, lässt aber die Website geöffnet. Nach 30 Minuten Inaktivität endet die Sitzung.

Zurzeit betrachtet [!DNL Marketo Measure] nur die Seitennavigation und Formularübermittlung als Aktivität. Scrollen durch die Web-Seite oder Bewegen des Mauszeigers über ein Element auf der Seite gilt nicht als Aktivität. Wenn Hanna also adobe.com/de besucht, um einen Blogpost zu lesen, und sie dafür eine Stunde braucht, endet ihre Web-Sitzung nach 30 Minuten, selbst wenn sie weiterhin durch den Inhalt auf der Seite scrollt.

## Kanalbasierter Ablauf {#channel-based-expiration}

[!DNL Marketo Measure] beginnt eine neue Sitzung, sobald ein Benutzer über einen anderen digitalen Marketingkanal oder eine externe Website auf Ihre Website gelangt. Dazu kann gehören:

* Eine Referral-Website
* Social-Kanäle ([!DNL Facebook], [!DNL LinkedIn]usw.)
* Paid-Search-Kanäle oder organische Suchkanäle ([!DNL Google/Bing])

**Referral-Websites und Social-Media-Kanäle**

Jedes Mal, wenn ein Besucher von einer verweisenden Website oder einem sozialen Kanal auf Ihre Website gelangt, beginnt eine neue Sitzung.

Angenommen, Haley ist auf LinkedIn, klickt auf einen [!DNL Marketo Measure] und wird auf die Adobe-Website umgeleitet. Dann sieht sie beim Scrollen durch [!DNL Facebook] einen anderen [!DNL Marketo Measure]-Post. Wenn sie auf diesen Beitrag klickt und auf die Adobe-Site umgeleitet wird, führt dies zur ersten Websitzung, die sich auf [!DNL LinkedIn] zu beenden und eine neue Sitzung im Zusammenhang mit [!DNL Facebook] beginnt.

**Paid-Search-Kanäle oder organische Suchkanäle**

Neue Sitzungen beginnen jedes Mal, wenn ein Benutzer über gebührenpflichtige oder kostenlose Suchkanäle auf Ihre Site gelangt. Wenn Haley über eine kostenlose Suche auf die Adobe-Website gelangt und Ihre Website dann über eine gebührenpflichtige Anzeige in Google sofort besucht, werden zwei separate Sitzungen erstellt.

**Web Direct Traffic**

Wenn eine Besucherin oder ein Besucher Ihre Website durch Eingabe der zugehörigen URL in die Adressleiste aufruft, beginnt nicht immer eine neue Sitzung.

Wenn Hannas erste Web-Sitzung aufgrund eines Besuchs von einer Referral-Site, einem Social-Media-Kanal oder einem Paid-Search-Kanal/organischen Suchkanal beginnt und sie dann die Site per Web-Direktzugriff besucht, beginnt dadurch keine neue Sitzung.

_Jedoch_, wenn die erste Websitzung von Haley von Web Direct stammt, und sie dann die Website über besucht _eine externe/Verweis-Site_, wird die erste Sitzung beendet und eine neue Sitzung im Zusammenhang mit der externen/Verweissite geöffnet.

## Google Analytics-Sitzungen {#google-analytics-sessions}

Es gibt gewisse Ähnlichkeiten, wie Sitzungen von [!DNL Marketo Measure] und Google Analytics definiert werden. Weitere Informationen zur Definition von Sitzungen durch Google Analytics finden Sie unter: [https://support.google.com/analytics/answer/2731565?hl=en](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
