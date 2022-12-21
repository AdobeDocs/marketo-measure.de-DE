---
unique-page-id: 18874564
description: Definition [!DNL Marketo Measure] Web-Sitzungen - [!DNL Marketo Measure] - Produktdokumentation
title: Definition [!DNL Marketo Measure] Web-Sitzungen
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Definition [!DNL Marketo Measure] Web-Sitzungen {#definition-of-marketo-measure-web-sessions}

Erfahren Sie mehr [!DNL Marketo Measure] definiert Websitzungen.

A **Websitzung** bezieht sich auf die Interaktionen einer Person mit Ihrer Website während eines bestimmten Zeitraums. Die Sitzung beginnt, wenn ein Benutzer auf Ihre Website gelangt.

Beispiel: Haley besucht adobe.com. Ihr Besuch auf der Site beginnt eine Sitzung. Wenn Haley die Site verlässt, indem er die Registerkarte/den Webbrowser schließt oder von der Site weg navigiert, endet die Sitzung.

Ein Benutzer kann nicht mehrere Sitzungen gleichzeitig öffnen. Wenn Haley geöffnet wird [!DNL adobe.com] in 10 verschiedenen Tabs wurde nur eine Sitzung im Zusammenhang mit ihrem Besuch auf der Website erstellt.

## Wie funktioniert [!DNL Marketo Measure] eine neue Sitzung definieren? {#how-does-marketo-measure-define-a-new-session}

Es gibt einige Dinge, die bestimmen, wann eine Sitzung endet und wann eine neue Sitzung beginnt. Die beiden Hauptwege [!DNL Marketo Measure] Sitzungen können enden:

* **Zeitlicher Ablauf**
* **Kanalbasierter Ablauf**

## Zeitbasierter Ablauf {#time-based-expiration}

**Wie lange dauert eine Sitzung?**

[!DNL Marketo Measure] Sitzungen enden nach einer Inaktivität von 30 Minuten auf der Website. Beispiel:

Wenn Haley adobe.com besucht, beginnt eine Sitzung. Sie erforscht die Website für einige Minuten und geht dann von ihrem Computer weg, lässt aber die Website offen. Nach 30 Minuten Inaktivität endet die Sitzung.

Zurzeit [!DNL Marketo Measure] betrachtet nur die Seitennavigation und die Formularübermittlung als Aktivität. Scrollen durch die Webseite oder Bewegen des Mauszeigers über ein Element auf der Seite wird nicht als Aktivität betrachtet. Wenn Haley also adobe.com besucht, um einen Blogpost zu lesen, und es eine Stunde dauert, bis sie liest, endet ihre Websitzung nach 30 Minuten, selbst wenn sie durch den Inhalt auf der Seite scrollt.

## Kanalbasierter Ablauf {#channel-based-expiration}

[!DNL Marketo Measure] beginnt eine neue Sitzung, sobald ein Benutzer über einen anderen digitalen Marketingkanal oder eine externe Website auf Ihre Website gelangt. Unter anderem:

* Verweiswebsite
* Social-Kanäle ([!DNL Facebook], [!DNL LinkedIn]usw.)
* Gebührenpflichtige oder kostenlose Suchkanäle ([!DNL Google/Bing])

**Verweisende Websites und Social-Kanäle**

Jedes Mal, wenn ein Besucher von einer verweisenden Website oder einem sozialen Kanal auf Ihre Website gelangt, beginnt eine neue Sitzung.

Haley ist auf LinkedIn, klickt auf einen [!DNL Marketo Measure] und wird zur Adobe-Website weitergeleitet. Dann beim Scrollen durch [!DNL Facebook], sieht Haley eine andere [!DNL Marketo Measure] Post. Wenn sie auf diesen Beitrag klickt und zur Adobe-Site weitergeleitet wird, führt dies zur ersten Websitzung, die sich auf [!DNL LinkedIn] zu beenden und eine neue Sitzung im Zusammenhang mit [!DNL Facebook] beginnt.

**Gebührenpflichtige oder kostenlose Suchkanäle**

Neue Sitzungen beginnen jedes Mal, wenn ein Benutzer über gebührenpflichtige oder kostenlose Suchkanäle auf Ihre Site gelangt. Wenn Haley über eine kostenlose Suche auf die Adobe-Website gelangt und Ihre Website dann über eine gebührenpflichtige Anzeige in Google sofort besucht, werden zwei separate Sitzungen erstellt.

**Web Direct Traffic**

Wenn ein Besucher Ihre Website aufruft, indem er die URL Ihrer Website in die Adressleiste eingibt, beginnt nicht immer eine neue Sitzung.

Wenn die erste Websitzung von Haley aufgrund eines Besuchs von einer Site, einem sozialen Kanal oder einem gebührenpflichtigen/kostenlosen Suchkanal beginnt und sie dann die Site über einen Web-Direktzugriff besucht, würde dies nicht dazu führen, dass eine neue Sitzung beginnt.

_Jedoch_, wenn die erste Websitzung von Haley von Web Direct stammt, und sie dann die Website über besucht _eine externe/Verweis-Site_, wird die erste Sitzung beendet und eine neue Sitzung im Zusammenhang mit der externen/Verweissite geöffnet.

## Google Analytics-Sitzungen {#google-analytics-sessions}

Es gibt einige Ähnlichkeiten zur [!DNL Marketo Measure] und Google Analytics definieren Sitzungen. Weitere Informationen dazu, wie Google Analytics Sitzungen definieren, finden Sie unter: [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target=&quot;_blank&quot;}
