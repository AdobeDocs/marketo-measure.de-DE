---
unique-page-id: 42762762
description: Einrichten der Marketo-Verbindung - [!DNL Marketo Measure]
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung zu Marketo ein.

>[!PREREQUISITES]
>
>[Benutzerrolle &quot;Nur API erstellen&quot;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) für die [!DNL Marketo Measure]/Marketo Engage-Verbindung.

1. In [!DNL Marketo Measure], klicken Sie auf die **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![](assets/set-up-marketo-connection-1.png)

1. under [!UICONTROL Integrationen]klicken **[!UICONTROL Verbindungen]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Klicks **[!UICONTROL Einrichten einer neuen CRM-Verbindung]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Klicken Sie auf **[!UICONTROL Verbinden]** neben Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. Melden Sie sich in einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an. Navigieren Sie zu **Admin** > **Web-Services**. Scrollen Sie nach unten zur REST-API. Markieren und speichern Sie den Endpunkt und die ID-Dienst-URL. Sie werden sie ein wenig brauchen.

   ![](assets/set-up-marketo-connection-5.png)

1. Wählen Sie noch im Marketo Engage aus. **LaunchPoint** im Baum auf der linken Seite. Suchen Sie den benutzerdefinierten Dienst, den Sie mit Marketo Measure verbinden möchten, und klicken Sie auf **Details anzeigen**.

   ![](assets/set-up-marketo-connection-6.png)

1. Markieren und speichern Sie die Client-ID und das Client Secret. Klicken Sie auf **Schließen**.

   ![](assets/set-up-marketo-connection-7.png)

1. Zurück in [!DNL Marketo Measure], füllen Sie die Felder mit den soeben erfassten Daten aus.

   ![](assets/set-up-marketo-connection-8.png)

1. Klicken Sie nach Eingabe der Werte auf **[!UICONTROL Authentifizieren]**. Ihr Marketo Engage-Konto wird dann mit [!DNL Marketo Measure].

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] ruft in Ihrem Namen die Marketo-API auf, ohne die Marketo-API-Beschränkungen zu verbrauchen. Daher müssen Sie sich keine Gedanken über die Obergrenze und die Zuordnung von Krediten zu anderen Integrationen machen.
