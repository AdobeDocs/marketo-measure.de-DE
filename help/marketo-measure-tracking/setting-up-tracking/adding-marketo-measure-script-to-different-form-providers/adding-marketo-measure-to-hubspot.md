---
unique-page-id: 18874759
description: Hinzufügen [!DNL Marketo Measure] nach [!DNL Hubspot] - [!DNL Marketo Measure]
title: Hinzufügen [!DNL Marketo Measure] nach [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# Hinzufügen [!DNL Marketo Measure] nach [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript zur Verfolgung Ihrer [!DNL Hubspot] Landingpages und Formularübermittlungen.

Hubspot unterscheidet sich etwas von anderen Marketing-Automatisierungssystemen insofern, als es Ihre Landingpages/Formulare UND Ihre Website hosten kann. Beachten Sie, dass die folgenden Anweisungen dazu dienen, [!DNL Marketo Measure] Tracking-Aktivität in [!DNL Hubspot]- gehostete Seiten. Wenn Sie Ihre Website mit einem anderen CMS als [!DNL Hubspot] (z. B. Wordpress) müssen Sie die [!DNL Marketo Measure] auch JavaScript auf dieses CMS.

>[!NOTE]
>
>Wenn Sie JavaScript über einen Tag-Management-Provider bereitstellen, z. B. [!DNL Google Tag Manager], müssen Sie die [!DNL Marketo Measure] JavaScript in Ihre Website.

## Erste Schritte {#getting-started}

Sobald Sie sich bei Ihrem [!DNL Hubspot] -Konto verwenden, führen Sie die folgenden Schritte aus.

1. Navigieren Sie zu Inhalt .

1. Klicks **[!UICONTROL Inhaltseinstellungen]**.

1. Within [!UICONTROL Inhaltseinstellungen]klicken Sie auf die HTML &quot;Site-Kopfzeile&quot;(siehe Abbildung unten).

1. Fügen Sie das folgende Skript in Ihre `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Sie sollte wie folgt aussehen:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>In diesem Bereich gibt es möglicherweise bereits andere Trackingcode-Snippets, z. B. Google Analytics-Code. Achten Sie darauf, sie durch ein Semikolon zu trennen `;` und ein einzelnes Leerzeichen wie folgt:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
