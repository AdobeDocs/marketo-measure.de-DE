---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Launch - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Integrationen mit Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 4%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

Die Adobe Launch-Erweiterung ist für bestehende [!DNL Marketo Measure] konzipiert, die Adobe Launch bereits auf ihrer Website verwenden. Die Erweiterung dient als Tag-Management-Lösung, mit der Sie Skripte auf der Grundlage bestimmter Ereignisse und Bedingungen konfigurieren und dynamisch auf Ihren Seiten laden können.

Nach der Installation und Konfiguration in Adobe Launch lädt die [!DNL Marketo Measure]-Erweiterung das Skript bizible.js auf die Seiten, auf denen sich Adobe Launch-Skript befindet. Marketing-Experten können bizible.js über die Adobe Launch-Konfiguration hinzufügen, anstatt die Webseite explizit zum Hinzufügen des bizible.js-Skript-Tags zu ändern.

## Konfigurieren der Adobe Launch-Erweiterung {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Weitere Informationen zu Adobe Launch und seinen Erweiterungen finden Sie unter den folgenden Links:
>
>* [[!DNL Marketo Measure] Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=de#catalog){target="_blank"}
>* [Übersicht über Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html?lang=de){target="_blank"}
>* [Adobe Launch-Erweiterung - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html?lang=de){target="_blank"}

1. Erstellen Sie eine Eigenschaft entsprechend den Schritten [in diesem Artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=de#go-to-the-data-collection-interface){target="_blank"}.

1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klicken Sie **[!UICONTROL Erweiterungen]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klicken Sie auf **[!UICONTROL Katalog]** und suchen Sie nach &quot;[!UICONTROL Bizible].

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. Klicken Sie in [!UICONTROL &#x200B; Kachel &#x200B;]Bizible Analytics“ auf **[!UICONTROL Installieren]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Geben Sie in das Feld Bizible-Konto-ID die URL Ihrer Website ein (z. B. `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klicken Sie **[!UICONTROL Regeln]** und wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**-Schaltfläche unter [!UICONTROL Ereignisse].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Core]** aus. Wählen Sie dann in der Dropdown-Liste Ereignistyp die Option **[!UICONTROL Bibliothek geladen (Seitenanfang)]**. Wenn Sie Ihrem Ereignis keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klicken Sie auf **[!UICONTROL Schaltfläche „Hinzufügen]** unter „Aktionen“.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Bizible Analytics]**. Wählen Sie dann in der Dropdown-Liste Aktionstyp die Option **[!UICONTROL Initialisieren]** aus. Wenn Sie Ihrer Aktion keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

