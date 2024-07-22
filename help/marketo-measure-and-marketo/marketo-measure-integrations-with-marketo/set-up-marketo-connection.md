---
unique-page-id: 42762762
description: Einrichten der Marketo-Verbindung - [!DNL Marketo Measure]
title: Einrichten der Marketo-Verbindung
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 1%

---

# Einrichten der Marketo-Verbindung {#set-up-marketo-connection}

So richten Sie Ihre Verbindung zu Marketo ein.

>[!PREREQUISITES]
>
>[Erstellen Sie eine Benutzerrolle &quot;Nur API&quot;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) für die [!DNL Marketo Measure]/Marketo Engage-Verbindung.

1. Klicken Sie in [!DNL Marketo Measure] auf die Dropdown-Liste **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]** aus.

   ![](assets/set-up-marketo-connection-1.png)

1. Klicken Sie unter [!UICONTROL Integrationen] auf **[!UICONTROL Verbindungen]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Klicken Sie auf **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Verbinden]** neben Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. Melden Sie sich in einer neuen Registerkarte bei Ihrem Marketo Engage-Konto an. Wechseln Sie zu **Admin** > **Webdienste**. Scrollen Sie nach unten zur REST-API. Markieren und speichern Sie den Endpunkt und die ID-Dienst-URL. Sie benötigen sie in den folgenden Schritten.

   ![](assets/set-up-marketo-connection-5.png)

1. Wählen Sie noch im Marketo Engage-Fenster im Baum links **LaunchPoint** aus. Suchen Sie den benutzerdefinierten Dienst, mit dem Sie eine Verbindung mit Marketo Measure herstellen möchten, und klicken Sie auf **Details anzeigen**.

   ![](assets/set-up-marketo-connection-6.png)

1. Markieren und speichern Sie die Client-ID und das Client Secret. Klicken Sie auf **Schließen**.

   ![](assets/set-up-marketo-connection-7.png)

1. Füllen Sie in [!DNL Marketo Measure] die Felder mit den erfassten Daten aus.

   ![](assets/set-up-marketo-connection-8.png)

1. Klicken Sie nach Eingabe der Werte auf **[!UICONTROL Authentifizieren]**. Ihr Marketo Engage-Konto ist mit [!DNL Marketo Measure] verbunden.

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] führt Aufrufe an die Marketo-API in Ihrem Namen durch, ohne die Marketo-API-Beschränkungen zu verbrauchen. Daher müssen Sie sich keine Gedanken über Begrenzungen und die Zuordnung von Krediten zu anderen Integrationen machen.
