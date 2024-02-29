---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] Parameter - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Parameter"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# [!DNL Marketo Measure]-Parameter {#marketo-measure-parameters}

## [!DNL Marketo Measure] Parameter - Erklärung {#marketo-measure-parameters-explained}

Um weitere Einblicke aus der Verwendung von UTM zu gewinnen, [!DNL Marketo Measure] hängt benutzerdefinierte Parameter an Ihre Anzeigen in [!DNL Google] AdWords, Bing Ads und [!DNL Facebook] Anzeigen. [!DNL Marketo Measure] Integration mit diesen Plattformen zur Automatisierung des Einrichtungsprozesses. Wenn Sie sich für die Verwendung des automatischen Tagging entscheiden, [!DNL Marketo Measure] hängt seine Parameter automatisch an die URLs Ihrer Anzeigen an. [!DNL Marketo Measure] lädt Ihre Marketingkosten automatisch von den Plattformen herunter und lädt sie in die [!DNL Marketo Measure] App.

Beispiel einer URL ohne Parameter:

`http://adobe.com/landing-page?myParam=foo`

Beispiel einer URL mit [!DNL Marketo Measure] Parameter:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## AdWords-Parameter {#adwords-parameters}

* `_bk={keyword}`
   * Stellt den Suchbegriff dar, den die Person in der Suchmaschine verwendet hat.
   * Sie ähnelt dem UTM-Begriffsparameter.

* `_bt={creative}`
   * Stellt die kreative ID oder den Namen dar.
   * Sie ähnelt dem UTM-Inhaltsparameter.

* `_bm={matchtype}`
   * Gibt an, wie eng der Suchbegriff abgeglichen wurde.
   * Mithilfe von Suchbegriffübereinstimmungstypen können Sie steuern, welche Suchvorgänge Trigger Ihrer Anzeige sind. Sie können beispielsweise eine breite Übereinstimmung verwenden, um Ihre Anzeige einer breiten Zielgruppe anzuzeigen, oder Sie können die genaue Übereinstimmung verwenden, um bestimmte Kundengruppen anzusprechen.
   * Die drei Übereinstimmungstypen sind: breit, unscharf und exakt.

>[!TIP]
>
>Weitere Informationen zu Übereinstimmungstypen finden Sie unter [Hier finden Sie einen relevanten AdWords-Artikel](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * Stellt den Netzwerktyp der Anzeige dar: [Anzeigen oder Suchen](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * Dies ähnelt dem Parameter &quot;UTM Source&quot;.

* `_bg={adgroupID}`
   * Stellt die ID der Anzeigengruppe dar, zu der die Anzeige gehört

>[!NOTE]
>
>Umleitungs-URL-Parameter werden nicht unterstützt.

## Bing Ads-Parameter {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook-Parameter {#facebook-parameters}

* `_bf ={creative}`
   * Dies stellt die kreative ID oder den Namen dar
