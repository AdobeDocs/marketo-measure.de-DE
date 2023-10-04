---
unique-page-id: 18874682
description: Marketing-Kanäle und -Unterkanäle – Produktdokumentation zu  [!DNL Marketo Measure]
title: Marketing-Kanäle und -Unterkanäle
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '472'
ht-degree: 100%

---

# Marketing-Kanäle und -Unterkanäle {#marketing-channels-and-subchannels}

## Zweck {#purpose}

Zu definieren, was in [!DNL Marketo Measure] Kanäle und Unterkanäle sind, wie sie sich auf Ihre Inhalte beziehen, wie sich zwei Klassifizierungen unterscheiden und wie sie in der App [!DNL Marketo Measure] verwendet werden.

## Überblick {#overview}

Marketing-Kanäle helfen Ihnen bei der Kategorisierung (oder Einsortierung in „Buckets“) Ihrer Marketing-Aktivitäten, damit Berichte einfacher erstellt werden können, sowohl im ROI-Dash von [!DNL Marketo Measure] als auch in Ihrem CRM-System. [!DNL Marketo Measure] verfügt über 12 vorkonfigurierte Kanäle (die Sie anpassen/umbenennen können, um sie den Konventionen Ihres Unternehmens anzupassen) sowie die Möglichkeit, weitere benutzerdefinierte Kanäle zu erstellen, um eine noch detailliertere Filterung zu ermöglichen.

Jedes Mal, wenn jemand eine der Inhaltsseiten Ihrer Site besucht (unabhängig davon, ob es sich bei diesem Inhalt um eine Webseite, den Download eines Whitepapers, eine Seiten-URL usw. handelt), wird dieser Lead anhand verschiedener in der URL enthaltener UTM-Parameter in einem Kanal/Unterkanal in einen „Bucket“ sortiert, der auf verschiedenen UTM-Parametern aus der URL basiert.

* Medium
* Quelle
* Kampagne
* Landingpage
* Verweisende Website

Um anzupassen, in welchen „Bucket“ (Eimer) Ihre Leads auf Grundlage ihrer UTM-Parameter fallen, können Sie Kanalregeln verwenden. Um weitere Informationen zum Einrichten und Warten Ihrer Kanalregeln zu erhalten, [klicken Sie hier](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Erfahren Sie, wie Sie Ihre [Online-Kanäle](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) und [Offline-Kanäle](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) einrichten und was sie unterscheidet.

**Marketing-Kanal**

Der Marketing-Kanal ist die breiteste Klassifizierungsstufe und kann eine Vielzahl von Unterkanälen abdecken. Sie können dies als den „Typ“ des Unterkanals betrachten, aus dem Ihre Leads stammen. Beispiele für Marketing-Kanäle sind **Paid Search, organische Suche, Anzeigen,** und **Paid Social**. Der Marketing-Kanal entspricht in der Regel dem Parameterwert „utm_medium“ in Ihrer URL.

**Unterkanal**

Unterkanäle sind das zweite Puzzleteil beim Einsortieren der eingehenden Leads in Buckets. Unterkanäle geben Aufschluss darüber, _welche_ Iteration Ihres Marketing-Kanals genau verwendet wurde. Beispielsweise können Sie im Marketing-Kanal „Paid Social“ Unterkanäle für **AdWords**, **BingAds**, **Facebook** usw. haben. Der Unterkanal entspricht in der Regel dem Parameterwert „utm_source“ in Ihrer URL.

## Anwendungsbeispiel {#use-case-example}

Das folgende Diagramm zeigt ein Beispiel für einen Marketing-Kanal, einen Unterkanel und einen Inhalt, der auf einer Web-Seite mit der folgenden URL basiert:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

In diesem Fall ist der Inhalt, auf den die Benutzerin bzw. der Benutzer zugreifen möchte, das Einleitungshandbuch für die B2B-Marketing-Attribution. [!DNL Marketo Measure] analysiert die URL, die zu diesem Inhalt führt, mithilfe der in dieser Organisation eingerichteten Kanalregeln und verwendet sie, um diesen Lead in den Marketing-Kanal „Paid Social“ und den Unterkanal „LinkedIn“ einzusortieren.

![](assets/1.jpg)

Weitere Beispiele …

**Marketing-Kanal (Medium)**

* PPC
* Paid Social
* Organic Social
* E-Mail
* Veranstaltungen und Konferenzen
* Organische Suche/SEO
* PR
* Empfehlungsprogramme

**Unterkanal (Touchpoint-Quelle)**

* Google AdWords
* BingAds
* Facebook-Anzeigen
* Adroll
* DoubleClick
* Capterra
* Drip-Kampagnen
* LinkedIn-Anzeigen

**Inhalt (Whitepapers, Seiten-URLs, Blog-Beiträge)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
