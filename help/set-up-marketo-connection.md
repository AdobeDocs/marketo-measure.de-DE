---
description: Einrichten der Marketo-Verbindungsanleitung für Marketo Measure-Benutzende
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---

# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung mit Marketo ein.

>[!PREREQUISITES]
>
>[Nur API-Benutzerrolle erstellen](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) für die Verbindung [!DNL Marketo Measure]/Marketo Engage.

1. Klicken Sie [!DNL Marketo Measure] auf die Dropdown **[!UICONTROL Liste Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![1. Klicken Sie in Marketo Measure auf die Dropdown-Liste Mein Konto und](assets/set-connection-7.png)

1. Klicken [!UICONTROL &#x200B; unter &quot;]&quot; auf **[!UICONTROL Verbindungen]**.

   ![1. Klicken Sie unter Integrationen auf Verbindungen.](assets/set-connection-8.png)

1. Klicken Sie **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![1. Klicken Sie auf Neue CRM-Verbindung einrichten &#x200B;](assets/set-connection-9.png)

1. Klicken Sie auf **[!UICONTROL Verbinden]**-Schaltfläche neben Marketo.

   ![1. Klicken Sie auf die Schaltfläche Verbinden neben Marketo.](assets/set-connection-5.png)

1. Melden Sie sich auf einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an. Navigieren Sie **Admin** > **Web-Services**. Scrollen Sie nach unten zur REST-API. Markieren und speichern Sie den Endpunkt und die Identity Service-URL. Sie benötigen sie in den folgenden Schritten.

   ![1. Melden Sie sich auf einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an.](assets/set-connection-6.png)

1. Wählen Sie noch in Marketo Engage **LaunchPoint** in der Baumstruktur links aus. Suchen Sie den benutzerdefinierten Service, den Sie mit Marketo Measure verbinden möchten, und klicken Sie auf **Details anzeigen**.

   ![1. Wählen Sie noch in Marketo Engage LaunchPoint in der Baumstruktur auf der &#x200B;](assets/set-connection-4.png)

1. Markieren und speichern Sie die Client-ID und den geheimen Client-Schlüssel. Klicken Sie auf **Schließen**.

   ![1. Markieren und speichern Sie die Client-ID und den geheimen Client-Schlüssel. Klicken Sie auf Schließen.](assets/set-connection-3.png)

1. Füllen Sie [!DNL Marketo Measure] die Felder mit den erfassten Daten aus.

   ![1. Zurück in Marketo Measure, füllen Sie die Felder mit den Daten](assets/set-connection-1.png)

1. Nachdem Sie die Werte eingegeben haben, klicken Sie auf **[!UICONTROL Authentifizieren]**. Ihr Marketo Engage-Konto ist mit [!DNL Marketo Measure] verbunden.

   ![1. Nachdem Sie die Werte eingegeben haben, klicken Sie auf Authentifizieren . Ihre Marketo Engage](assets/set-connection-2.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] ruft die Marketo-API in Ihrem Namen auf, ohne Ihre Marketo-API-Beschränkungen zu nutzen, sodass Sie sich keine Gedanken über Obergrenzen und Kreditzuweisungen bei anderen Integrationen machen müssen.
