---
description: Anleitung zu E-Mail-Tracking-Parametern für Marketo Measure-Benutzende
title: E-Mail-Verfolgungsparameter
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 4%

---

# E-Mail-Verfolgungsparameter {#email-tracking-parameter}

Mit dem [!DNL Marketo Measure]-E-Mail-Tracking-Parameter können Marketing-Fachleute E-Mail-Klicks als Formularübermittlungen behandeln, sodass Touchpoints für diese Aktionen generiert werden. Ohne Verwendung eines E-Mail-Tracking-Parameters werden Clickthroughs aus einer E-Mail nur als „Web-Besuche“ behandelt, bis der Benutzer über eine Formularübermittlung oder einen Web-Chat tatsächlich mit der Site interagiert.

## Anwendungsszenarien  {#use-cases}

**Anmeldung zum Webinar**: Das Marketing-Team sendet per E-Mail eine Einladung mit einer einzigen Schaltfläche, um sich für ein Webinar zu registrieren. Da die E-Mail bereits über die Informationen der Person verfügt, werden sie durch einen einzigen Klick automatisch registriert. Die Landingpage enthält den E-Mail-Tracking-Parameter. Wenn der Besucher also auf die Bestätigungsseite klickt und auf ihr landet, kann [!DNL Marketo Measure] die E-Mail-Adresse erfassen und das Clickthrough als Formularausfüllen behandeln, wodurch ein Touchpoint generiert wird.

**Content-Download**: Das Content-Marketing-Team möchte ein kürzlich veröffentlichtes E-Book mit einem direkten Download-Link aus einer E-Mail bewerben. Wenn die E-Mail-Vorlage erstellt wird, enthält die Download-Bestätigungsseite den E-Mail-Tracking-Parameter, damit [!DNL Marketo Measure] beim Durchklicken die E-Mail-Adresse erfassen können. Ohne ein Formular auf der Website ausfüllen zu müssen, können [!DNL Marketo Measure] einen Touchpoint für den Inhalts-Download generieren. Dies liegt daran, dass sie die E-Mail auf der Bestätigungsseite mit dem E-Mail-Tracking-Parameter erhalten hat.

## Funktionsweise {#how-it-works}

Wenn ein Besucher auf Ihre Site kommt, erwartet [!DNL Marketo Measure], eine Landingpage mit entweder einer E-Mail-Adresse oder einer [!DNL Salesforce]-ID zu finden, damit wir diesen Besuch mit einer „Formularübermittlung“ verknüpfen und einen Touchpoint für diese Aktivität generieren können.

Als -Kunde erstellen Sie eine E-Mail-Vorlage wie gewohnt. Sobald es Zeit ist, der Landingpage für die Aktion hinzuzufügen, die Sie verfolgen möchten, müssen Sie entweder das Token, das Variable-Tag oder das Makro bestimmen, das Ihre Marketing-Automatisierungsplattform akzeptiert, um den Wert für jede Person dynamisch anzuzeigen.

Marketo Measure akzeptiert die folgenden Werte: E-Mail-Adresse, Salesforce-Lead-ID oder Salesforce-Kontakt-ID.

## Tag-Beispiele {#tag-examples}

| Marketing-Automatisierung | Token/Tag/Makro | Beispiel | Hilfsmaterial |
| --- | --- | --- | --- |
| Marketo | {{lead.Email Address}} | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}> | [Token - Übersicht](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html) |
| Pardot | %%email%% oder %%USER_CRM_ID%% | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%> | [Pardot-Variablentags-Referenz](https://help.salesforce.com/s/articleView?language=en_US&id=pardot_variable_tags_reference.htm&type=5) |
| HubSpot | (über Editor eingefügt) | k. A. | [HubSpot - Personalisieren von Inhalten](https://knowledge.hubspot.com/website-pages/personalize-your-content) |
| Act-On | (über Message Composer eingefügt) | k. A. | [Act-On personalisieren Sie E-Mail-Inhalte](https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data) |

Und schließlich müssen Sie in [!DNL Marketo Measure] den Tracking-Parameter angeben, damit [!DNL Marketo Measure] den Wert für die E-Mail oder die ID finden können. Der Standardwert ist „mailId“, wie in den Beispielen oben und im folgenden Screenshot gezeigt. Geben Sie den Wert in Ihre Einstellungen in [!DNL Marketo Measure] ein und klicken Sie dann auf **[!UICONTROL Speichern]**.

![Und schließlich müssen Sie in Marketo Measure den Tracking-Parameter angeben](assets/marketo-engage-activities-01.png)
