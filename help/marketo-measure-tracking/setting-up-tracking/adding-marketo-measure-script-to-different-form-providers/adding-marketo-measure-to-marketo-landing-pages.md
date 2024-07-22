---
unique-page-id: 18874755
description: Hinzufügen von [!DNL Marketo Measure] zu [!DNL Marketo] Einstiegsseiten - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] zu Marketo-Landing-Pages
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# Hinzufügen von [!DNL Marketo Measure] zu Marketo-Einstiegsseiten {#adding-marketo-measure-to-marketo-landing-pages}

Erfahren Sie, wie Sie den Einstiegsseiten [!DNL Marketo Engage] Tracking hinzufügen, da sie zusätzliche Verarbeitungsschritte erfordern. [!DNL Marketo Measure] JavaScript muss sowohl auf der Einstiegsseite als auch im [!DNL Marketo Engage] Formular selbst vorhanden sein. Dazu müssen Sie den [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] laden, wie in den folgenden Anweisungen beschrieben.

>[!NOTE]
>
>Wenn Sie JavaScript über einen Tag-Management-Provider wie [!DNL Google Tag Manager] bereitstellen, müssen Sie [!DNL Marketo Measure] JS nicht manuell zu [!DNL Marketo Engage] hinzufügen.

## Hinzufügen von [!DNL Marketo Measure] Skript zu [!DNL Marketo Engage] Einstiegsseiten {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Melden Sie sich bei Ihrem [!DNL Marketo Engage] -Konto an.
1. Wählen Sie Ihre Landingpage aus und klicken Sie auf **[!UICONTROL Entwurf bearbeiten]**.
1. Ziehen Sie das Element HTML in den Arbeitsbereich.
1. Geben Sie den [!DNL Marketo Measure] JavaScript in den Abschnitt [!UICONTROL head] ein:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Beispiel für einen Screenshot unten

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Weitere Hinweise {#additional-notes}

* Möglicherweise sind bereits andere Trackingcode-Snippets vorhanden, z. B. ein [!DNL Google Analytics] -Code. Es gibt kein Problem damit. Achten Sie darauf, sie durch ein Semikolon `;` und ein einzelnes Leerzeichen zu trennen. Ein Beispiel dafür, wie dies aussehen würde:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Wahrscheinlich werden mehrere Landingpage-Vorlagen verwendet. Stellen Sie sicher, dass Sie den Code zu allen Vorlagen hinzufügen, die Formulare enthalten.

* Wenn Sie die Vorlage für Landingpages bearbeiten, müssen Sie manchmal die Seiten erneut validieren, von denen die Landingpage verwendet wird. In diesem Artikel wird [erläutert, wie eine Massengenehmigung durchgeführt werden kann](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
