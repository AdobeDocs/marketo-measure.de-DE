---
unique-page-id: 18874720
description: Auswirkungen der Angebotsmanagement-Tools [!DNL Marketo Measure] - [!DNL Marketo Measure] - Produktdokumentation
title: Auswirkungen der Angebotsmanagement-Tools [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 0%

---

# Auswirkungen der Angebotsmanagement-Tools [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

Erfahren Sie, wie sich Angebotsverwaltungsplattformen auf die [!DNL Marketo Measure] Möglichkeit zur Verfolgung von AdWords und BingAds sowie zur Einrichtung von Tracking-Vorlagen mit unseren Parametern, um sicherzustellen, dass alles korrekt verfolgt wird.

Kenshoo und Marin sind großartige Tools, mit denen Marketing-Experten ihre Werbekampagnen mit verschiedenen Suchmaschinen verfolgen, verwalten und optimieren können. Zur [!DNL Marketo Measure] Parameter, die an diese Anzeigen-URLs angehängt werden sollen, müssen Sie mit unserer [!DNL Marketo Measure] Parameter. Es ist nicht möglich, Ihre Anzeigenplattformen mit Ihren [!DNL Marketo Measure] Konto erstellen und automatisches Tagging aktivieren, da dies die [!DNL Marketo Measure] Tagging-System, um mit dem Tagging-System von Kenshoo/Marin zu konkurrieren. Dadurch werden unsere Parameter geändert und falsch angehängt. Um dies zu umgehen, verfolgen Sie Vorlagen mit [!DNL Marketo Measure] -Parameter in Kenshoo und Marin eingerichtet werden.

## Für [!DNL Adwords] Konten {#for-adwords-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf **[!UICONTROL Kampagnen]** Registerkarte.
* Klicken Sie auf **[!UICONTROL Freigegebene Bibliothek]** in der Seitennavigationsleiste.
* Klicken **URL-Optionen**.
* Klicken Sie neben &quot;Tracking-Vorlage&quot;auf **Bearbeiten**.
* Füllen Sie die URL aus:

   * Wenn ALLE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Wenn KEINE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Für [!DNL Bing Ads] Konten {#for-bing-ads-accounts}

Richten Sie eine Tracking-Vorlage wie folgt ein:

* Klicken Sie auf **[!UICONTROL Kampagnen]** Registerkarte.
* Klicken Sie auf **[!UICONTROL Freigegebene Bibliothek]** in der Seitennavigationsleiste.
* Klicken **URL-Optionen**.
* Klicken Sie neben &quot;Tracking-Vorlage&quot;auf **Bearbeiten**.
* Füllen Sie die URL aus:

   * Wenn ALLE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Wenn KEINE Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
