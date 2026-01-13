---
description: Einrichten der Marketo-Verbindung - [!DNL Marketo Measure]
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---


# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung mit Marketo ein.

>[!PREREQUISITES]
>
>[Nur API-Benutzerrolle erstellen](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html?lang=de){target="_blank"} für die Verbindung [!DNL Marketo Measure]/Marketo Engage.

1. Klicken Sie [!DNL Marketo Measure] auf die Dropdown **[!UICONTROL Liste Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![Dropdown-Liste Mein Konto bei Marketo Measure mit Einstellungsoption](assets/set-up-marketo-connection-1.png)

1. Klicken [!UICONTROL &#x200B; unter &quot;]&quot; auf **[!UICONTROL Verbindungen]**.

   ![Menü „Integrationen“ mit Option „Verbindungen“](assets/set-up-marketo-connection-2.png)

1. Klicken Sie **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![Schaltfläche „Neue CRM-Verbindung einrichten“](assets/set-up-marketo-connection-3.png)

1. Klicken Sie auf **[!UICONTROL Verbinden]**-Schaltfläche neben Marketo.

   ![Schaltfläche „Verbinden“ neben der Option Marketo-Integration](assets/set-up-marketo-connection-4.png)

1. Melden Sie sich auf einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an. Navigieren Sie **Admin** > **Web-Services**. Scrollen Sie nach unten zur REST-API. Markieren und speichern Sie den Endpunkt und die Identity Service-URL. Sie benötigen sie in den folgenden Schritten.

   ![Marketo Web Services-Seite mit REST-API-Endpunkt und Identitäts-URLs](assets/set-up-marketo-connection-5.png)

1. Wählen Sie noch in Marketo Engage **LaunchPoint** in der Baumstruktur links aus. Suchen Sie den benutzerdefinierten Service, den Sie mit Marketo Measure verbinden möchten, und klicken Sie auf **Details anzeigen**.

   ![LaunchPoint-Menü mit benutzerdefiniertem Service und Option „Details anzeigen“](assets/set-up-marketo-connection-6.png)

1. Markieren und speichern Sie die Client-ID und den geheimen Client-Schlüssel. Klicken Sie auf **Schließen**.

   ![Details zum LaunchPoint-Service mit Client-ID und Client-Geheimnis](assets/set-up-marketo-connection-7.png)

1. Füllen Sie [!DNL Marketo Measure] die Felder mit den erfassten Daten aus.

   ![Marketo-Verbindungsformular mit Endpunkt- und Berechtigungsfeldern](assets/set-up-marketo-connection-8.png)

1. Nachdem Sie die Werte eingegeben haben, klicken Sie auf **[!UICONTROL Authentifizieren]**. Ihr Marketo Engage-Konto ist mit [!DNL Marketo Measure] verbunden.

   ![Bestätigungsnachricht für erfolgreiche Marketo-Verbindung](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >[!DNL Marketo Measure] ruft die Marketo-API in Ihrem Namen auf, ohne Ihre Marketo-API-Beschränkungen zu nutzen, sodass Sie sich keine Gedanken über Obergrenzen und Kreditzuweisungen bei anderen Integrationen machen müssen.
