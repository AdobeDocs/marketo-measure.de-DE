---
description: '[!DNL Marketo Measure] - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Parameter'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '230'
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
>Weitere Informationen zu Übereinstimmungstypen finden [ in einem entsprechenden AdWords-Artikel](https://support.google.com/adwords/answer/2497836?hl=de){target="_blank"}.

* `_bn={network}`
   * Stellt den Anzeigennetzwerktyp (Anzeige [ Suche) ](https://support.google.com/adwords/answer/1752334?hl=de){target="_blank"}.
   * Ähnelt dem UTM-Quellparameter.

* `_bg={adgroupID}`
   * Stellt die ID der Anzeigengruppe dar, zu der die Anzeige gehört

>[!NOTE]
>Umleitungs-URL-Parameter werden nicht unterstützt.

## Bing-Anzeigen-Parameter {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook-Parameter {#facebook-parameters}

* `_bf ={creative}`
   * Dies stellt die kreative ID oder den Namen dar
