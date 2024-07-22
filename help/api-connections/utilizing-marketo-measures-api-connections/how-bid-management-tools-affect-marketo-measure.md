---
unique-page-id: 18874720
description: Wie sich Angebotsmanagement-Tools auf [!DNL Marketo Measure] - [!DNL Marketo Measure] auswirken
title: Auswirkungen der Bid-Management-Tools auf [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# Wie sich Angebotsmanagement-Tools auf [!DNL Marketo Measure] auswirken {#how-bid-management-tools-affect-marketo-measure}

Erfahren Sie, wie sich Angebotsverwaltungsplattformen auf die [!DNL Marketo Measure]-Fähigkeit auswirken, AdWords und BingAds zu verfolgen, und wie Sie Tracking-Vorlagen mit unseren Parametern einrichten, um sicherzustellen, dass alles korrekt verfolgt wird.

Kenshoo und Marin sind großartige Tools, mit denen Marketing-Experten ihre Werbekampagnen mit verschiedenen Suchmaschinen verfolgen, verwalten und optimieren können. Damit [!DNL Marketo Measure] -Parameter an diese Anzeigen-URLs angehängt werden können, müssen Sie eine Tracking-Vorlage mit unseren [!DNL Marketo Measure] -Parametern einrichten. Es ist nicht möglich, Ihre Anzeigenplattformen mit Ihrem [!DNL Marketo Measure] -Konto zu verbinden und das automatische Tagging zu aktivieren, da dadurch das [!DNL Marketo Measure] -Tagging-System mit dem Tagging-System von Kenshoo/Marin konkurriert. Dies führt dazu, dass unsere Parameter geändert und falsch angehängt werden. Um dies zu umgehen, müssen in Kenshoo und Marin Tracking-Vorlagen mit [!DNL Marketo Measure] -Parametern eingerichtet werden.

## Für [!DNL Adwords] Konten {#for-adwords-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf die Registerkarte **[!UICONTROL Kampagnen]** .
* Klicken Sie in der Seitennavigationsleiste auf den Link **[!UICONTROL Freigegebene Bibliothek]** .
* Klicken Sie auf **URL options**.
* Klicken Sie neben &quot;Tracking-Vorlage&quot;auf **Bearbeiten**.
* Füllen Sie die URL aus:

   * Wenn ALLE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Wenn KEINE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Für [!DNL Bing Ads] Konten {#for-bing-ads-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf die Registerkarte **[!UICONTROL Kampagnen]** .
* Klicken Sie in der Seitennavigationsleiste auf den Link **[!UICONTROL Freigegebene Bibliothek]** .
* Klicken Sie auf **URL options**.
* Klicken Sie neben &quot;Tracking-Vorlage&quot;auf **Bearbeiten**.
* Füllen Sie die URL aus:

   * Wenn ALLE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Wenn KEINE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
