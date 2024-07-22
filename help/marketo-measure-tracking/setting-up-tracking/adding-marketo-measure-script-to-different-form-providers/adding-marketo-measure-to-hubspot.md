---
unique-page-id: 18874759
description: Hinzufügen von [!DNL Marketo Measure] zu [!DNL Hubspot] - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# Hinzufügen von [!DNL Marketo Measure] zu [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript hinzufügen, um Ihre [!DNL Hubspot] -Landingpages und Formularübermittlungen zu verfolgen.

Hubspot unterscheidet sich etwas von anderen Marketing-Automatisierungssystemen insofern, als es Ihre Landingpages/Formulare UND Ihre Website hosten kann. Beachten Sie, dass die folgenden Anweisungen dazu dienen, die Tracking-Aktivität von [!DNL Marketo Measure] auf [!DNL Hubspot] gehosteten Seiten zu verfolgen. Wenn Sie Ihre Website mit einem anderen CMS als [!DNL Hubspot] (z. B. Wordpress) versorgen, müssen Sie auch die [!DNL Marketo Measure] JavaScript zu diesem CMS hinzufügen.

>[!NOTE]
>
>Wenn Sie die JavaScript über einen Tag-Management-Provider wie [!DNL Google Tag Manager] bereitstellen, müssen Sie die [!DNL Marketo Measure] JavaScript nicht manuell in Ihre Website hartcodieren.

## Erste Schritte {#getting-started}

Nachdem Sie sich bei Ihrem [!DNL Hubspot] -Konto angemeldet haben, führen Sie die folgenden Schritte aus.

1. Navigieren Sie zu Inhalt .

1. Klicken Sie auf **[!UICONTROL Inhaltseinstellungen]**.

1. Klicken Sie in den [!UICONTROL Inhaltseinstellungen] auf die HTML &quot;Site-Kopfzeile&quot;(siehe Abbildung unten).

1. Fügen Sie das folgende Skript in Ihrem `<header>` hinzu:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Sie sollte wie folgt aussehen:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>In diesem Bereich gibt es möglicherweise bereits andere Trackingcode-Snippets, z. B. Google Analytics-Code. Achten Sie darauf, sie durch ein Semikolon `;` und ein einzelnes Leerzeichen zu trennen, z. B.:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
