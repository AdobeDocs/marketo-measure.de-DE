---
unique-page-id: 18874608
description: '[!DNL Marketo Measure] - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Parameter'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
TQID: https://experienceleague.adobe.com/IurdaUgr2R1vxfOP4bcXp8TSUj4ymkA-R9kZ9put4Ug
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
subfeature_v2:
  - id: fabdc8ff-b627-44fc-b09d-973166bc2b14
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 91%

---

# [!DNL Marketo Measure]-Parameter {#marketo-measure-parameters}

## [!DNL Marketo Measure]-Parameter – Erklärung {#marketo-measure-parameters-explained}

Um weitere Einblicke in die Verwendung von UTMs zu gewinnen, hängt [!DNL Marketo Measure] benutzerdefinierte Parameter an Ihre Anzeigen in [!DNL Google] AdWords, Bing Ads und [!DNL Facebook] Ads an. [!DNL Marketo Measure] ist zur Automatisierung eines Großteils des Einrichtungsprozesses mit diesen Plattformen integriert. Wenn Sie sich für die Verwendung des automatischen Taggings entscheiden, hängt [!DNL Marketo Measure] seine Parameter automatisch an die URLs Ihrer Anzeigen an. [!DNL Marketo Measure] lädt außerdem Ihre Marketing-Kosten automatisch von den Plattformen herunter und lädt sie in die [!DNL Marketo Measure]-App.

Beispiel einer URL ohne Parameter:

`http://adobe.com/landing-page?myParam=foo`

Beispiel einer URL mit [!DNL Marketo Measure]-Parametern:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords-Parameter {#adwords-parameters}

* `_bk={keyword}`
   * Stellt den Suchbegriff dar, den die Person in der Suchmaschine verwendet hat.
   * Ähnelt dem Parameter „UTM-Begriff“.

* `_bt={creative}`
   * Stellt die kreative ID oder den Namen dar.
   * Ähnelt dem UTM-Inhaltsparameter.

* `_bm={matchtype}`
   * Gibt an, wie genau der Suchbegriff übereinstimmt.
   * Mithilfe von Suchbegriffübereinstimmungstypen können Sie steuern, welche Suchvorgänge Ihre Anzeige auslösen. Sie können beispielsweise eine breite Übereinstimmung verwenden, um Ihre Anzeige einer breiten Zielgruppe anzuzeigen, oder Sie können eine genaue Übereinstimmung verwenden, um bestimmte Kundengruppen anzusprechen.
   * Die drei Übereinstimmungstypen sind: breit, unscharf und exakt.

>[!TIP]
>
>Weitere Informationen zu Übereinstimmungstypen finden [&#x200B; in einem entsprechenden AdWords-Artikel](https://support.google.com/adwords/answer/2497836?hl=de){target="_blank"}.

* `_bn={network}`
   * Stellt den Anzeigennetzwerktyp (Anzeige [&#x200B; Suche) &#x200B;](https://support.google.com/adwords/answer/1752334?hl=de){target="_blank"}.
   * Ähnelt dem UTM-Quellparameter.

* `_bg={adgroupID}`
   * Stellt die ID der Anzeigengruppe dar, zu der die Anzeige gehört

>[!NOTE]
>
>Umleitungs-URL-Parameter werden nicht unterstützt.

## Bing-Anzeigen-Parameter {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook-Parameter {#facebook-parameters}

* `_bf ={creative}`
   * Dies stellt die kreative ID oder den Namen dar
