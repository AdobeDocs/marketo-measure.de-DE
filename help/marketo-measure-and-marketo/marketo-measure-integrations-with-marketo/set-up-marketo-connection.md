---
unique-page-id: 42762762
description: Einrichten der Marketo-Verbindung - [!DNL Marketo Measure]
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
TQID: https://experienceleague.adobe.com/IQhZzu6iqS-5BdooPRA6-A8BoJtQ936NRFJHPGu3Xp4
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: c8f57308-7e33-4e41-a385-b55041c78939
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 0%

---

# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung mit Marketo ein.

>[!PREREQUISITES]
>
>[Nur API-Benutzerrolle erstellen](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html){target="_blank"} für die Verbindung [!DNL Marketo Measure]/Marketo Engage.

1. Klicken Sie [!DNL Marketo Measure] auf die Dropdown **[!UICONTROL Liste Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![](assets/set-up-marketo-connection-1.png)

1. Klicken [!UICONTROL &#x200B; unter &quot;]&quot; auf **[!UICONTROL Verbindungen]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Klicken Sie **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Klicken Sie auf **[!UICONTROL Verbinden]**-Schaltfläche neben Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. Melden Sie sich auf einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an. Navigieren Sie **Admin** > **Web-Services**. Scrollen Sie nach unten zur REST-API. Markieren und speichern Sie den Endpunkt und die Identity Service-URL. Sie benötigen sie in den folgenden Schritten.

   ![](assets/set-up-marketo-connection-5.png)

1. Wählen Sie noch in Marketo Engage **LaunchPoint** in der Baumstruktur links aus. Suchen Sie den benutzerdefinierten Service, den Sie mit Marketo Measure verbinden möchten, und klicken Sie auf **Details anzeigen**.

   ![](assets/set-up-marketo-connection-6.png)

1. Markieren und speichern Sie die Client-ID und den geheimen Client-Schlüssel. Klicken Sie auf **Schließen**.

   ![](assets/set-up-marketo-connection-7.png)

1. Füllen Sie [!DNL Marketo Measure] die Felder mit den erfassten Daten aus.

   ![](assets/set-up-marketo-connection-8.png)

1. Nachdem Sie die Werte eingegeben haben, klicken Sie auf **[!UICONTROL Authentifizieren]**. Ihr Marketo Engage-Konto ist mit [!DNL Marketo Measure] verbunden.

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] ruft die Marketo-API in Ihrem Namen auf, ohne Ihre Marketo-API-Beschränkungen zu nutzen, sodass Sie sich keine Gedanken über Obergrenzen und Kreditzuweisungen bei anderen Integrationen machen müssen.
