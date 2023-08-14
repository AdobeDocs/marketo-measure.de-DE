---
unique-page-id: 18874564
description: Definition von [!DNL Marketo Measure] -Web-Sitzungen – [!DNL Marketo Measure] – Produktdokumentation
title: Definition von  [!DNL Marketo Measure] -Web-Sitzungen
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '579'
ht-degree: 100%

---

# Definition von [!DNL Marketo Measure]-Web-Sitzungen {#definition-of-marketo-measure-web-sessions}

Erfahren Sie, wie [!DNL Marketo Measure] Web-Sitzungen definiert.

Eine **Web-Sitzung** bezieht sich auf die Interaktionen einer Person mit Ihrer Website während eines bestimmten Zeitraums. Die Sitzung beginnt, wenn eine Benutzerin oder ein Benutzer auf Ihre Website gelangt.

Beispiel: Hanna besucht adobe.com/de. Mit ihrem Besuch auf der Site beginnt eine Sitzung. Wenn Hanna die Site verlässt, indem sie die Registerkarte/den Web-Browser schließt oder von der Site weg navigiert, endet die Sitzung.

Eine Benutzerin oder ein Benutzer kann nicht mehrere Sitzungen gleichzeitig öffnen. Wenn Hanna [!DNL adobe.com] auf 10 verschiedenen Registerkarten öffnet, wird nur eine Sitzung im Zusammenhang mit ihrem Besuch auf der Website erstellt.

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

[!DNL Marketo Measure] beginnt eine neue Sitzung, sobald eine Benutzerin oder ein Benutzer über einen anderen Digital-Marketing-Kanal oder eine externe Website auf Ihre Website gelangt. Dazu kann gehören:

* Eine Referral-Website
* Social-Media-Kanäle ([!DNL Facebook], [!DNL LinkedIn] usw.)
* Paid-Search-Kanäle oder organische Suchkanäle ([!DNL Google/Bing])

**Referral-Websites und Social-Media-Kanäle**

Sobald eine Besucherin oder ein Besucher von einer Referral-Website oder einem Social-Media-Kanal auf Ihre Website gelangt, beginnt eine neue Sitzung.

Hanna ist auf LinkedIn, klickt dort auf einen [!DNL Marketo Measure]-Post und wird zur Adobe-Website weitergeleitet. Dann sieht sie beim Scrollen durch [!DNL Facebook] einen anderen [!DNL Marketo Measure]-Post. Wenn sie auf diesen Post klickt und zur Adobe-Site weitergeleitet wird, endet dadurch die erste Web-Sitzung in Zusammenhang mit [!DNL LinkedIn] und eine neue Sitzung im Zusammenhang mit [!DNL Facebook] beginnt.

**Paid-Search-Kanäle oder organische Suchkanäle**

Neue Sitzungen beginnen jedes Mal, wenn eine Benutzerin oder ein Benutzer über Paid-Search-Kanäle oder organische Suchkanäle auf Ihre Site gelangt. Wenn Hanna über eine organische Suche auf der Adobe-Website landet und Ihre Website dann über eine bezahlte Anzeige (auch als „Paid Ad“ bezeichnet) in Google sofort besucht, werden zwei separate Sitzungen erstellt.

**Web Direct Traffic**

Wenn eine Besucherin oder ein Besucher Ihre Website durch Eingabe der zugehörigen URL in die Adressleiste aufruft, beginnt nicht immer eine neue Sitzung.

Wenn Hannas erste Web-Sitzung aufgrund eines Besuchs von einer Referral-Site, einem Social-Media-Kanal oder einem Paid-Search-Kanal/organischen Suchkanal beginnt und sie dann die Site per Web-Direktzugriff besucht, beginnt dadurch keine neue Sitzung.

Wenn ihre erste Web-Sitzung _dagegen_, auf einen Web-Direktzugriff zurückzuführen ist und sie dann die Website über _eine externe/Referral-Site_ besucht, wird die erste Sitzung beendet und eine neue Sitzung im Zusammenhang mit der externen/Referral-Site geöffnet.

## Google Analytics-Sitzungen {#google-analytics-sessions}

Es gibt gewisse Ähnlichkeiten, wie Sitzungen von [!DNL Marketo Measure] und Google Analytics definiert werden. Weitere Informationen dazu, wie Google Analytics Sitzungen definiert, finden Sie unter [https://support.google.com/analytics/answer/2731565?hl=de](http://support.google.com/analytics/answer/2731565?hl=de){target="_blank"}.
