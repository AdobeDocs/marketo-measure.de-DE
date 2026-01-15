---
description: '"[!DNL Marketo Measure] Integrationen mit Adobe Launch - [!DNL Marketo Measure]"'
title: '[!DNL Marketo Measure]-Integrationen mit Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 6%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

Die Adobe Launch-Erweiterung ist für bestehende [!DNL Marketo Measure] konzipiert, die Adobe Launch bereits auf ihrer Website verwenden. Die Erweiterung dient als Tag-Management-Lösung, mit der Sie Skripte auf der Grundlage bestimmter Ereignisse und Bedingungen konfigurieren und dynamisch auf Ihren Seiten laden können.

Nach der Installation und Konfiguration in Adobe Launch lädt die [!DNL Marketo Measure]-Erweiterung das Skript bizible.js auf die Seiten, auf denen sich Adobe Launch-Skript befindet. Marketing-Experten können bizible.js über die Adobe Launch-Konfiguration hinzufügen, anstatt die Webseite explizit zum Hinzufügen des bizible.js-Skript-Tags zu ändern.

## Konfigurieren der Adobe Launch-Erweiterung {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Weitere Informationen zu Adobe Launch und seinen Erweiterungen finden Sie unter den folgenden Links:
>
>* [[!DNL Marketo Measure] Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Übersicht über Adobe Launch](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html?lang=de){target="_blank"}
>* [Adobe Launch-Erweiterung - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Erstellen Sie eine Eigenschaft entsprechend den Schritten [in diesem Artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.

   ![1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.](assets/marketo-launch-12.png)

1. Klicken Sie **[!UICONTROL Erweiterungen]**.

   ![1. Klicken Sie auf Erweiterungen.](assets/marketo-launch-11.png)

1. Klicken Sie auf **[!UICONTROL Katalog]** und suchen Sie nach &quot;[!UICONTROL Bizible].

   ![1. Klicken Sie auf die Registerkarte Katalog und suchen Sie nach „Bizible“](assets/marketo-launch-10.png)

1. Klicken Sie in [!UICONTROL  Kachel ]Bizible Analytics“ auf **[!UICONTROL Installieren]**.

   ![1. Klicken Sie in der Kachel „Bizible Analytics“ auf Installieren.](assets/marketo-launch-7.png)

1. Geben Sie in das Feld Bizible-Konto-ID die URL Ihrer Website ein (z. B. `adobe.com`).

   ![1. Geben Sie in das Feld Bizible-Konto-ID die URL Ihres ein](assets/marketo-launch-6.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![1. Klicken Sie auf Speichern.](assets/marketo-launch-8.png)

1. Klicken Sie **[!UICONTROL Regeln]** und wählen Sie **[!UICONTROL Neue Regel erstellen]** aus.

   ![1. Klicken Sie auf Regeln und wählen Sie Neue Regel erstellen aus.](assets/marketo-launch-9.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**-Schaltfläche unter [!UICONTROL Ereignisse].

   ![1. Klicken Sie auf die Schaltfläche Hinzufügen unter Ereignisse.](assets/marketo-launch-2.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Core]** aus. Wählen Sie dann in der Dropdown-Liste Ereignistyp die Option **[!UICONTROL Bibliothek geladen (Seitenanfang)]**. Wenn Sie Ihrem Ereignis keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![1. Wählen Sie in der Dropdown-Liste Erweiterung die Option Core aus. Dann im Ereignis](assets/marketo-launch-1.png)

1. Klicken Sie auf **[!UICONTROL Schaltfläche „Hinzufügen]** unter „Aktionen“.

   ![1. Klicken Sie auf die Schaltfläche Hinzufügen unter Aktionen.](assets/marketo-launch-3.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Bizible Analytics]**. Wählen Sie dann in der Dropdown-Liste Aktionstyp die Option **[!UICONTROL Initialisieren]** aus. Wenn Sie Ihrer Aktion keinen Namen geben, wird ein Standardname angewendet. Klicken **[!UICONTROL abschließend auf]**&#x200B;Änderungen beibehalten“.

   ![1. Wählen Sie in der Dropdown-Liste Erweiterung die Option Bizible Analytics. Dann in der Aktion](assets/marketo-launch-4.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![1. Klicken Sie auf Speichern.](assets/marketo-launch-5.png)

