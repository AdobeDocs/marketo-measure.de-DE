---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Launch - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Integrationen mit Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# [!DNL Marketo Measure]-Integrationen mit Adobe Launch {#marketo-measure-integrations}

Die Adobe Launch-Erweiterung ist für bestehende [!DNL Marketo Measure] konzipiert, die Adobe Launch bereits auf ihrer Website verwenden. Die Erweiterung dient als Tag-Management-Lösung, mit der Sie Skripte auf der Grundlage bestimmter Ereignisse und Bedingungen konfigurieren und dynamisch auf Ihren Seiten laden können.

Nach der Installation und Konfiguration in Adobe Launch lädt die [!DNL Marketo Measure]-Erweiterung das Skript bizible.js auf die Seiten, auf denen sich Adobe Launch-Skript befindet. Marketing-Experten können bizible.js über die Adobe Launch-Konfiguration hinzufügen, anstatt die Webseite explizit zum Hinzufügen des bizible.js-Skript-Tags zu ändern.

## Konfigurieren der Adobe Launch-Erweiterung {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>Weitere Informationen zu Adobe Launch und seinen Erweiterungen finden Sie unter den folgenden Links:
> [[!DNL Marketo Measure] Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
> [Übersicht über Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html?lang=de){target="_blank"}
> [Adobe Launch-Erweiterung - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Erstellen Sie eine Eigenschaft entsprechend den Schritten [in diesem Artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.

   ![Adobe Launch-Eigenschaftsauswahl-Bildschirm mit verfügbaren Eigenschaften](assets/marketo-measure-integrations-1.png)

1. Klicken Sie **[!UICONTROL Erweiterungen]**.

   ![Registerkarte „Erweiterungen“ in den Eigenschafteneinstellungen von Adobe Launch](assets/marketo-measure-integrations-2.png)

1. Klicken Sie auf **[!UICONTROL Katalog]** und suchen Sie nach &quot;[!UICONTROL Bizible].

   ![Erweiterungskatalogsuche mit Bizible-Erweiterung](assets/marketo-measure-integrations-3.png)

1. Klicken Sie in [!UICONTROL  Kachel ]Bizible Analytics“ auf **[!UICONTROL Installieren]**.

   ![Bizible Analytics-Erweiterungskachel mit Schaltfläche „Installieren“](assets/marketo-measure-integrations-4.png)

1. Geben Sie in das Feld Bizible-Konto-ID die URL Ihrer Website ein (z. B. `adobe.com`).

   ![Konfiguration der Bizible-Erweiterung mit dem Feld „AccountId“](assets/marketo-measure-integrations-5.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![Schaltfläche „Speichern“ für die Konfiguration der Bizible-Erweiterung](assets/marketo-measure-integrations-6.png)

1. Klicken Sie **[!UICONTROL Regeln]** und wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

   ![Registerkarte „Regeln“ mit der Schaltfläche „Neue Regel erstellen“](assets/marketo-measure-integrations-7.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**-Schaltfläche unter [!UICONTROL Ereignisse].

   ![Schaltfläche Hinzufügen im Abschnitt Ereignisse der Regelkonfiguration](assets/marketo-measure-integrations-8.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Core]** aus. Wählen Sie dann in der Dropdown-Liste Ereignistyp die Option **[!UICONTROL Bibliothek geladen (Seitenanfang)]**. Wenn Sie Ihrem Ereignis keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![Dialogfeld für die Ereigniskonfiguration mit der Haupterweiterung und dem Ereignistyp „Bibliothek geladen“](assets/marketo-measure-integrations-9.png)

1. Klicken Sie auf **[!UICONTROL Schaltfläche „Hinzufügen]** unter „Aktionen“.

   ![Schaltfläche „Hinzufügen“ im Abschnitt „Aktionen“ der Regelkonfiguration](assets/marketo-measure-integrations-10.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Bizible Analytics]**. Wählen Sie dann in der Dropdown-Liste Aktionstyp die Option **[!UICONTROL Initialisieren]** aus. Wenn Sie Ihrer Aktion keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![Dialogfeld für die Aktionskonfiguration mit der Bizible Analytics-Erweiterung und dem Aktionstyp „Initialisieren“](assets/marketo-measure-integrations-11.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![Schaltfläche „Speichern“ für die Regelkonfiguration](assets/marketo-measure-integrations-12.png)

