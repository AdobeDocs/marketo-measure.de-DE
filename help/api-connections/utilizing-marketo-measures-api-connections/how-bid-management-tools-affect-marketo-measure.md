---
unique-page-id: 18874720
description: Wie sich Gebotsverwaltungs-Tools auf [!DNL Marketo Measure] auswirken - [!DNL Marketo Measure]
title: Wie sich Gebotsverwaltungs-Tools auf [!DNL Marketo Measure] auswirken
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
TQID: 'https://experienceleague.adobe.com/gcugeRrHUi4qetrYBpUavRyrBHVpB0qCzPo4OYMI4hw'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
    internal-label: APIs
  - id: 7da342c5-06ee-5869-b3e8-b73d5bf75a9d
    internal-label: Integration
  - id: 3968a9c0-3e19-5a76-a1f0-f5a9a986c53a
    internal-label: UTM Parameters
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%
---
# Wie sich Gebotsverwaltungs-Tools auf [!DNL Marketo Measure] auswirken {#how-bid-management-tools-affect-marketo-measure}

Erfahren Sie, wie sich Bid-Management-Plattformen auf die [!DNL Marketo Measure]-Fähigkeit auswirken, AdWords und BingAds zu verfolgen, und wie Sie Tracking-Vorlagen mit unseren Parametern einrichten, um sicherzustellen, dass alles korrekt verfolgt wird.

Kenshoo und Marin sind großartige Tools, mit denen Marketing-Experten ihre Werbekampagnen mit verschiedenen Suchmaschinen verfolgen, verwalten und optimieren können. Damit [!DNL Marketo Measure] Parameter an diese Anzeigen-URLs angehängt werden können, müssen Sie eine Tracking-Vorlage mit unseren [!DNL Marketo Measure] einrichten. Es ist nicht möglich, Ihre Werbeplattformen mit Ihrem [!DNL Marketo Measure]-Konto zu verbinden und das automatische Tagging zu aktivieren, da dies dazu führt, dass das [!DNL Marketo Measure]-Tagging-System mit dem Tagging-System von Kenshoo/Marin konkurriert. Dies führt dazu, dass unsere Parameter verändert und falsch angehängt werden. Um dies zu umgehen, müssen Tracking-Vorlagen mit [!DNL Marketo Measure] Parametern in Kenshoo und Marin eingerichtet werden.

## Für [!DNL Adwords] Konten {#for-adwords-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf **[!UICONTROL Registerkarte]** Kampagnen“.
* Klicken Sie auf **[!UICONTROL Link]** Freigegebene Bibliothek“ in der Seitennavigationsleiste.
* Klicken Sie auf **URL-Optionen**.
* Klicken Sie neben „Tracking-Vorlage“ auf **Bearbeiten**.
* Geben Sie die URL ein:

  * Wenn alle Ihre Werbe-URLs ein &quot;?“ Verwenden Sie in ihnen diese URL:
    * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
  * Wenn KEINE Ihrer Werbe-URLs ein &quot;?“ aufweist Verwenden Sie in ihnen diese URL:
    * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Für [!DNL Bing Ads] Konten {#for-bing-ads-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf **[!UICONTROL Registerkarte]** Kampagnen“.
* Klicken Sie auf **[!UICONTROL Link]** Freigegebene Bibliothek“ in der Seitennavigationsleiste.
* Klicken Sie auf **URL-Optionen**.
* Klicken Sie neben „Tracking-Vorlage“ auf **Bearbeiten**.
* Geben Sie die URL ein:

  * Wenn alle Ihre Werbe-URLs ein &quot;?“ Verwenden Sie in ihnen diese URL:
    * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
  * Wenn KEINE Ihrer Werbe-URLs ein &quot;?“ aufweist Verwenden Sie in ihnen diese URL:
    * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
