---
unique-page-id: 18874759
description: ' [!DNL Marketo Measure] - [!DNL Hubspot] - [!DNL Marketo Measure]'
title: Wird  [!DNL Marketo Measure]  hinzugefügt [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 1%

---

# Hinzufügen von [!DNL Marketo Measure] zu [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Erfahren Sie, wie Sie die [!DNL Marketo Measure] JavaScript hinzufügen, um Ihre [!DNL Hubspot] Landingpages und Formularübermittlungen zu verfolgen.

HubSpot unterscheidet sich ein wenig von anderen Marketing-Automatisierungssystemen insofern, als es Ihre Landingpages / Formulare UND Ihre Website hosten kann. Beachten Sie, dass die folgenden Anweisungen für [!DNL Marketo Measure] Tracking von Aktivitäten auf [!DNL Hubspot] gehosteten Seiten gelten. Wenn Sie Ihre Website mit einer anderen CMS als [!DNL Hubspot] betreiben (z. B. Wordpress), müssen Sie die [!DNL Marketo Measure] JavaScript auch dieser CMS hinzufügen.

>[!NOTE]
>
>Wenn Sie die JavaScript über einen Tag-Management-Anbieter wie [!DNL Google Tag Manager] bereitstellen, müssen Sie die [!DNL Marketo Measure] JavaScript nicht manuell hartcodieren.

## Erste Schritte {#getting-started}

Nachdem Sie sich bei Ihrem [!DNL Hubspot]-Konto angemeldet haben, führen Sie die folgenden Schritte aus.

1. Navigieren Sie zum Inhalt.

1. Klicken Sie **[!UICONTROL Inhaltseinstellungen]**.

1. Klicken [!UICONTROL &#x200B; in „Inhaltseinstellungen] auf die Site-Header-HTML (siehe Abbildung unten).

1. Fügen Sie das folgende Skript in Ihre `<header>` ein:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Er sollte wie folgt aussehen:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>Möglicherweise gibt es bereits andere Trackingcode-Snippets in diesem Bereich, z. B. einen Google Analytics-Code. Achten Sie darauf, sie durch ein Semikolon `;` und ein einziges Leerzeichen zu trennen:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
