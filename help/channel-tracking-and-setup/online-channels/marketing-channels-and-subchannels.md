---
unique-page-id: 18874682
description: Marketing-Kanäle und -Subkanäle - [!DNL Marketo Measure] - Produktdokumentation
title: Marketing-Kanäle und -Subkanäle
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 4%

---

# Marketing-Kanäle und -Subkanäle {#marketing-channels-and-subchannels}

## Zweck {#purpose}

So definieren Sie, in welchen Kanälen und Unterkanälen sich die [!DNL Marketo Measure], wie sie mit Ihrem Inhalt zusammenhängen, der Unterschied zwischen den beiden Klassifizierungen und wie sie innerhalb der [!DNL Marketo Measure] App.

## Überblick {#overview}

Marketing-Kanäle helfen Ihnen bei der Kategorisierung (oder &quot;Zusammenfassung&quot;) Ihrer Marketing-Aktivitäten, damit Berichte einfacher erstellt werden können. Dies geschieht sowohl in der [!DNL Marketo Measure] ROI-Dash sowie in Ihrem CRM. [!DNL Marketo Measure] verfügt über 12 vorkonfigurierte Kanäle (die Sie anpassen/umbenennen können, um die Konventionen Ihres Unternehmens anzupassen) sowie die Möglichkeit, benutzerdefinierte Kanäle weiter zu erstellen, um eine noch detailliertere Filterung zu ermöglichen.

Jedes Mal, wenn Sie einen Besucher auf einer Ihrer Inhaltsseiten auf Ihrer Site erhalten (unabhängig davon, ob es sich bei diesem Inhalt um eine Webseite, einen Download in Whitepaper, eine Seiten-URL usw. handelt), wird dieser Lead anhand verschiedener in der URL enthaltener UTM-Parameter in einem Kanal/Subkanal &quot;zusammengefasst&quot;:

* Mittel
* Quelle
* Kampagne
* Landing Page
* Verweisende Website

Um anzupassen, in welchen &quot;Behälter&quot;Ihre Leads auf Grundlage ihrer UTM-Parameter fallen, können Sie Kanalregeln verwenden. Weitere Informationen zum Einrichten und Warten Ihrer Kanalregeln finden Sie unter [Hier klicken](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Erfahren Sie, wie Sie Ihre [Online-Kanäle](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) und [Offline-Kanäle](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)sowie den Unterschied zwischen ihnen.

**Marketing-Kanal**

Der Marketing-Kanal ist die umfassendste Classification-Ebene und kann eine Vielzahl von Subkanälen abdecken. Sie können dies als den &quot;Typ&quot;des Subkanals betrachten, aus dem Ihre Leads stammen. Beispiele für Marketing-Kanäle sind **Gebührenpflichtige Suche, Kostenlose Suche, Anzeige,** und **Paid Social**. Der Marketing-Kanal entspricht in der Regel dem Parameterwert utm_medium in Ihrer URL.

**Unterkanal**

Subkanäle sind das zweite Puzzleteil beim Buckeln der eingehenden Leads. Subkanäle erzählen genau die Geschichte von _,_ wurde verwendet. Im gebührenpflichtigen Social-Marketing-Kanal können Sie beispielsweise Subkanäle für **AdWords**, **BingAds**, **Facebook**, usw. Der Subchannel entspricht in der Regel dem Parameterwert utm_source in Ihrer URL.

## Anwendungsbeispiel {#use-case-example}

Das folgende Diagramm zeigt ein Beispiel für einen Marketing-Kanal, einen Subkanal und einen Inhalt, der auf einer Webseite mit der folgenden URL basiert:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

In diesem Fall ist der Inhalt, auf den der Benutzer zugreifen möchte, das Einleitungshandbuch für die B2B Marketing Attribution. [!DNL Marketo Measure] analysiert die URL, die zu diesem Inhalt führt, mithilfe der in dieser Organisation eingerichteten Kanalregeln und verwendet sie, um diesen Lead in den Marketingkanal &quot;Paid Social&quot;und den Unterkanal &quot;LinkedIn&quot;zu &quot;bündeln&quot;.

![](assets/1.jpg)

Weitere Beispiele..

**Marketingkanal (mittel)**

* PPC
* Paid Social
* Organisch Social
* E-Mail
* Veranstaltungen und Konferenzen
* Organische Suche/SEO
* PR
* Verweisprogramme

**Subkanal (Touchpoint-Quelle)**

* Google AdWords
* BingAds
* Facebook-Anzeigen
* Admin
* Doppelklicken
* Capterra
* Drip-Kampagnen
* linkedIn Ads

**Inhalt (Whitepaper, Seiten-URLs, Blog-Beiträge)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
