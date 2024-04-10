---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Launch - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integrationen mit Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 6aaf6fd26f19e9382cc559e54558e1c5d84cfd6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 2%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

Die Adobe Launch-Erweiterung ist für bestehende [!DNL Marketo Measure] Benutzende, die Adobe Launch bereits auf ihrer Website verwenden. Die Erweiterung dient als Tag-Management-Lösung, mit der Sie basierend auf bestimmten Ereignissen und Bedingungen Skripte konfigurieren und dynamisch auf Ihren Seiten laden können.

Nach der Installation und Konfiguration in Adobe Launch [!DNL Marketo Measure] lädt das bizible.js-Skript auf den Seiten, auf denen sich das Adobe Launch-Skript befindet. Auf diese Weise können Marketing-Fachleute bizible.js über die Adobe Launch-Konfiguration hinzufügen, anstatt die Webseite explizit zu ändern und das Skript-Tag bizible.js hinzuzufügen.

## Konfigurieren der Adobe Launch-Erweiterung {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Weitere Informationen zu Adobe Launch und seinen Erweiterungen finden Sie unter den folgenden Links:
>
>* [[!DNL Marketo Measure] Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Adobe Launch - Übersicht](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Adobe Launch-Erweiterung - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Erstellen Sie eine Eigenschaft wie folgt [In diesem Artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klick **[!UICONTROL Erweiterungen]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Katalog]** und suchen Sie nach &quot;[!UICONTROL Bizible].“

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. In der [!UICONTROL Bizible Analytics] Kachel, Klick **[!UICONTROL Installieren von]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Geben Sie in das Feld Bizible-Konto-ID die URL Ihrer Website ein (zum Beispiel `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klick **[!UICONTROL Regeln]** und wählen Sie dann **[!UICONTROL Neue Regel erstellen]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** Schaltfläche unter [!UICONTROL -Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung aus. **[!UICONTROL Core]**. Wählen Sie dann in der Dropdown-Liste Ereignistyp Folgendes aus **[!UICONTROL Bibliothek geladen (Seitenanfang)]**. Wenn Sie Ihrem Ereignis keinen Namen geben, wird ein Standardname angewendet. Klick **[!UICONTROL Änderungen beibehalten]** Wenn fertig.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Hinzufügen]** Schaltfläche unter „Aktionen„.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung aus. **[!UICONTROL Bizible Analytics]**. Wählen Sie dann in der Dropdown-Liste Aktionstyp aus **[!UICONTROL initialize]**. Wenn Sie Ihrer Aktion keinen Namen geben, wird ein Standardname angewendet. Klick **[!UICONTROL Änderungen beibehalten]** Wenn fertig.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

