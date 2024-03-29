---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Launch - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integrationen mit Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

Die Adobe Launch-Erweiterung ist für bestehende [!DNL Marketo Measure] Benutzer, die bereits Adobe Launch auf ihrer Website verwenden. Die Erweiterung dient als Tag-Management-Lösung, mit der Sie Skripte basierend auf bestimmten Ereignissen und Bedingungen auf Ihren Seiten konfigurieren und dynamisch laden können.

Wenn Sie Adobe Launch installiert und konfiguriert haben, wird die [!DNL Marketo Measure] -Erweiterung lädt das Skript bizible.js auf den Seiten, auf denen das Adobe Launch-Skript vorhanden ist. Dadurch können Marketingexperten bizible.js über die Adobe Launch-Konfiguration hinzufügen, anstatt die Webseite explizit zu ändern und das Skript-Tag bizible.js hinzuzufügen.

## Konfigurieren der Adobe Launch-Erweiterung {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Unter den folgenden Links erfahren Sie mehr über Adobe Launch und seine Erweiterungen:
>
>* [[!DNL Marketo Measure] Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Adobe Launch-Übersicht](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Übersicht über die Adobe Launch-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Erstellen Sie eine Eigenschaft anhand der Schritte [in diesem Artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klicken Sie auf die von Ihnen erstellte Eigenschaft.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klicks **[!UICONTROL Erweiterungen]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klicken Sie auf **[!UICONTROL Katalog]** Registerkarte und suchen Sie nach &quot;[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. Im [!UICONTROL Bizible Analytics] tile, click **[!UICONTROL Installieren]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Geben Sie im Feld Bizible AccountId die URL Ihrer Website ein (z. B. `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >Dieses Feld ist nicht die &quot;Konto-ID&quot;in der Tabelle Business_Prod.Business. Alle Webaktivitäten über die angegebene URL (z. B. `adobe.com`) werden der [!DNL Marketo Measure] Mandanten.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klicks **[!UICONTROL Regeln]**, wählen Sie **[!UICONTROL Neue Regel erstellen]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]** Schaltfläche unter [!UICONTROL Veranstaltungen].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Wählen Sie in der Dropdown-Liste Erweiterung die Option **[!UICONTROL Core]**. Wählen Sie dann in der Dropdown-Liste Ereignistyp die Option **[!UICONTROL Bibliothek geladen (Seitenanfang)]**. Wenn Sie Ihrem Ereignis keinen Namen geben, wird ein Standardwert angewendet. Klicks **[!UICONTROL Änderungen beibehalten]** wann geschehen.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klicken Sie auf **[!UICONTROL Hinzufügen]** unter &quot;Aktionen&quot;angezeigt.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Wählen Sie in der Dropdownliste Erweiterung die Option **[!UICONTROL Bizible Analytics]**. Wählen Sie dann in der Dropdown-Liste Aktionstyp die Option **[!UICONTROL Initialisieren]**. Wenn Sie Ihrer Aktion keinen Namen geben, wird ein Standardwert angewendet. Klicks **[!UICONTROL Änderungen beibehalten]** wann geschehen.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
