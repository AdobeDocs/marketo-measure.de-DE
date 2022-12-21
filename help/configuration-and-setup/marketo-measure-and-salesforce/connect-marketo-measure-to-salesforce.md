---
unique-page-id: 18874580
description: Marketo-Maßnahme mit Salesforce verbinden - [!DNL Marketo Measure] - Produktdokumentation
title: Marketo-Maßnahme mit Salesforce verbinden
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Marketo-Maßnahme mit Salesforce verbinden {#connect-marketo-measure-to-salesforce}

Dieser Artikel bietet einen Überblick darüber, wie Sie Ihre [!DNL Salesforce] -Konto [!DNL Marketo Measure] -Konto.

## Verbinden [!DNL Marketo Measure] mit [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Anmelden über einen Inkognito-Browser bei [!DNL Marketo Measure].

1. Navigieren Sie in der Menüleiste am oberen Bildschirmrand zu **[!UICONTROL Mein Konto]** und klicken Sie auf [!UICONTROL Einstellungen] -Option.

1. Klicken Sie in der Spalte mit den Einstellungsoptionen auf der linken Seite auf [!UICONTROL Verbindungen] unter dem [!UICONTROL Integrationen] Abschnitt.

   ![](assets/1.png)

1. Klicken Sie im Abschnitt CRM unter Verbindungen auf **[!UICONTROL Einrichten einer neuen CRM-Verbindung]**.

   ![](assets/2.png)

1. Es wird ein Popup-Fenster mit der Aufforderung angezeigt, die CRM-Verbindung auszuwählen. Klicken Sie auf [!UICONTROL Verbinden] Schaltfläche neben [!DNL Salesforce] Logo.

   ![](assets/3.png)

1. Daraufhin wird ein abschließendes Popup-Fenster angezeigt, in dem Sie nach Ihrer [!DNL Salesforce] Anmeldeinformationen, Sandbox oder Produktion. Geben Sie Ihre Informationen ein und klicken Sie auf **[!UICONTROL Autorisieren]** , um das Konto mit [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] kann nur mit einer [!DNL Salesforce] -Instanz zu einer bestimmten Zeit.
>
>* A [!DNL Marketo Measure] -Instanz kann mit einer SFDC-Sandbox-Instanz verbunden werden, um die Integration zu testen, bevor die Verbindung zu Ihrer SFDC-Produktionsinstanz gewechselt wird.
>* Wenn Sie zuerst mit einer SFDC-Sandbox testen, empfehlen wir dringend, einen Test durchzuführen, der eine exakte Replikation Ihrer SFDC-Produktionsinstanz ist, und zwar in Bezug auf die Felder auf den Objekten &quot;Lead&quot;, &quot;Kontakt&quot;, &quot;Konto&quot;, &quot;Chancen&quot;, &quot;Kampagne&quot;und &quot;Case&quot;. Wenn Sie aktive APEX-Trigger in der Produktion haben, die bei Aktualisierungen der Lead-, Kontakt-, Konto-, Opportunity-, Campaign- und Case-Objekte ausgelöst werden, sollten Sie versuchen, diese in Ihrer Sandbox zu aktivieren.
>* Sobald Sie mit dem Testen fertig sind, aktualisieren Sie Ihre [!DNL Marketo Measure] -Konto auf Ihre Produktion zu verweisen [!DNL Salesforce] (anstelle von Sandbox [!DNL Salesforce]). Aufgrund der Art und Weise, wie die Integration erstellt wurde, einmal pro [!DNL Marketo Measure] -Konto mit Produktion verbunden ist [!DNL Salesforce], können Sie nicht &quot;rückwärts&quot;gehen und eine Verbindung zu einer Sandbox herstellen [!DNL Salesforce] org.


