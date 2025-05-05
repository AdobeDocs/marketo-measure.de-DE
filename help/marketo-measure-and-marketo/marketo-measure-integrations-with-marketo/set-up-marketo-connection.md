---
unique-page-id: 42762762
description: Einrichten der Marketo-Verbindung - [!DNL Marketo Measure]
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 1%

---

# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung mit Marketo ein.

>[!PREREQUISITES]
>
>[Nur API-Benutzerrolle erstellen](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html){target="_blank"} für die [!DNL Marketo Measure]/Marketo Engage-Verbindung.

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

1. Wählen Sie noch im Marketo Engage **LaunchPoint** in der Baumstruktur auf der linken Seite aus. Suchen Sie den benutzerdefinierten Service, den Sie mit Marketo Measure verbinden möchten, und klicken Sie auf **Details anzeigen**.

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
