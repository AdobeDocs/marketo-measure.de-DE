---
unique-page-id: 18874580
description: Verbinden von Marketo Measure mit Salesforce - [!DNL Marketo Measure]
title: Verbinden von Marketo Measure mit Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Verbinden von Marketo Measure mit Salesforce {#connect-marketo-measure-to-salesforce}

Dieser Artikel bietet einen Überblick darüber, wie Sie Ihr [!DNL Salesforce]-Konto mit Ihrem [!DNL Marketo Measure]-Konto verbinden.

## Verbinden von [!DNL Marketo Measure] mit [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Verwenden Sie einen Inkognito-Browser, um sich bei [!DNL Marketo Measure] anzumelden.

1. Navigieren Sie in der Menüleiste oben im Bildschirm zu **[!UICONTROL Mein Konto]** und klicken Sie auf die Option **[!UICONTROL Einstellungen]** .

1. Klicken Sie in der Spalte mit den Einstellungsoptionen auf der linken Seite unter dem Abschnitt [!UICONTROL Integrationen] auf **[!UICONTROL Verbindungen]** .

   ![](assets/connect-marketo-measure-to-salesforce-1.png)

1. Klicken Sie im Abschnitt CRM unter Verbindungen auf **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![](assets/connect-marketo-measure-to-salesforce-2.png)

1. Es wird ein Popup-Fenster angezeigt, in dem Sie aufgefordert werden, die CRM-Verbindung auszuwählen. Klicken Sie neben dem [!DNL Salesforce] -Logo auf **[!UICONTROL Verbinden]** .

   ![](assets/connect-marketo-measure-to-salesforce-3.png)

1. Es wird ein endgültiges Popup-Fenster angezeigt, in dem Sie nach Ihren [!DNL Salesforce] -Anmeldedaten, Ihrer Sandbox oder Ihrer Produktion gefragt werden. Geben Sie Ihre Informationen ein und klicken Sie auf **[!UICONTROL Autorisieren]** , um das Konto mit [!DNL Marketo Measure] zu verbinden.

>[!NOTE]
>
>[!DNL Marketo Measure] kann jeweils nur mit einer [!DNL Salesforce] -Instanz verbunden werden.
>
>* Eine [!DNL Marketo Measure] -Instanz kann mit einer SFDC-Sandbox-Instanz verbunden werden, um die Integration zu testen, bevor die Verbindung zu Ihrer SFDC-Produktionsinstanz gewechselt wird.
>* Wenn Sie zuerst mit einer SFDC-Sandbox testen, empfehlen wir dringend, einen Test durchzuführen, der eine exakte Replikation Ihrer SFDC-Produktionsinstanz ist, und zwar in Bezug auf die Felder auf den Objekten &quot;Lead&quot;, &quot;Kontakt&quot;, &quot;Konto&quot;, &quot;Chancen&quot;, &quot;Kampagne&quot;und &quot;Case&quot;. Wenn Sie aktive APEX-Trigger in der Produktion haben, die bei Aktualisierungen der Lead-, Kontakt-, Konto-, Opportunity-, Campaign- und Case-Objekte ausgelöst werden, sollten Sie versuchen, diese in Ihrer Sandbox zu aktivieren.
>* Sobald Sie mit dem Testen fertig sind, aktualisieren Sie Ihr [!DNL Marketo Measure]-Konto so, dass es auf Ihre Produktion [!DNL Salesforce] (anstelle von Sandbox [!DNL Salesforce]) verweist. Aufgrund der Art und Weise, wie die Integration erstellt wurde, können Sie nach der Verbindung eines [!DNL Marketo Measure] -Kontos mit der Produktion [!DNL Salesforce] nicht mehr &quot;rückwärts&quot;gehen und keine Verbindung zu einer Sandbox [!DNL Salesforce]-Organisation herstellen.

## Nutzung von API-Anmeldeinformationen {#api-credits-usage}

Marketo Measure verwendet eine CRM-Integrationsaufgabe, um über einen integrierten Benutzer mit der Salesforce eines Kunden zu kommunizieren. Alle Datenaustauschvorgänge über diesen Benutzer verwenden Salesforce-API-Gutschriften. Sie haben die Möglichkeit, einem Integrationsbenutzer ein Kreditkontingent zuzuweisen, das zur Regulierung übermäßiger API-Aufrufe dient. Dieses Kontingent bzw. diese Begrenzung wird alle 24 Stunden zurückgesetzt.

Sie können auf diese Beschränkung in Marketo Measure zugreifen: **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein** > **Tägliches CRM-API-Limit** und sie für Ihre Mandanten konfigurieren.

![](assets/connect-marketo-measure-to-salesforce-4.png)

### Festlegen einer Beschränkung für API-Berechtigungen {#setting-a-limit-for-api-credits}

1. Navigieren Sie zu **Mein Konto** > **Einstellungen**.

1. Klicken Sie unter &quot;CRM&quot;auf **Allgemein**. Sie sehen die Option **Tägliches CRM-API-Limit** .

1. Klicken Sie auf das Sperrsymbol, um es zu bearbeiten.

   ![](assets/connect-marketo-measure-to-salesforce-5.png)

1. Geben Sie eine Grenze von mindestens 100.000 ein. Klicken Sie auf **Speichern**, wenn Sie fertig sind.

   ![](assets/connect-marketo-measure-to-salesforce-6.png)

>[!NOTE]
>
>Wenden Sie sich an Ihren Salesforce-Administrator und verweisen Sie auf [dieses Salesforce-Dokument](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}, um die verfügbaren Salesforce-API-Gutschriften für Ihre verbundene Lösung zu erhöhen.

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
