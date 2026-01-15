---
description: Anleitung zum Verbinden von Marketo Measure mit Salesforce für Marketo Measure-Benutzende
title: Marketo Measure mit Salesforce verbinden
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 2%

---

# Marketo Measure mit Salesforce verbinden {#connect-marketo-measure-to-salesforce}

Dieser Artikel bietet einen Überblick darüber, wie Sie Ihr [!DNL Salesforce]-Konto mit Ihrem [!DNL Marketo Measure]-Konto verbinden.

## Verbinden von [!DNL Marketo Measure] mit [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Verwenden Sie einen Inkognito-Browser, um sich bei [!DNL Marketo Measure] anzumelden.

1. Navigieren Sie in der Menüleiste am oberen Bildschirmrand zu **[!UICONTROL Mein Konto]** und klicken Sie auf die Option **[!UICONTROL Einstellungen]**.

1. Klicken Sie in der Spalte mit den Einstellungsoptionen auf der linken Seite **[!UICONTROL Verbindungen]** im Abschnitt [!UICONTROL Integrationen].

   ![1. Klicken Sie in der Spalte mit den Einstellungsoptionen auf der linken Seite auf](assets/bizible-full-1.png)

1. Klicken Sie unter dem CRM-Abschnitt in Verbindungen auf **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![1. Klicken Sie unter dem CRM-Abschnitt in Verbindungen auf Neu einrichten &#x200B;](assets/bizible-taxonomy-1.png)

1. Ein Popup-Fenster erscheint, in dem Sie aufgefordert werden, die CRM-Verbindung auszuwählen. Klicken Sie **[!UICONTROL Verbinden]** neben dem [!DNL Salesforce].

   ![1. Ein Popup-Fenster erscheint, in dem Sie aufgefordert werden, die CRM-Verbindung auszuwählen. Klicken](assets/connect-salesforce-1.png)

1. Ein letztes Popup-Fenster wird angezeigt, in dem Sie nach Ihren [!DNL Salesforce], Sandbox oder Ihrer Produktion gefragt werden. Geben Sie Ihre Informationen ein und klicken Sie auf **[!UICONTROL Autorisieren]**, um das Konto mit [!DNL Marketo Measure] zu verbinden.

>[!NOTE]
>
>[!DNL Marketo Measure] kann jeweils nur mit einer [!DNL Salesforce] verbunden werden.
>
>* Eine [!DNL Marketo Measure] kann mit einer SFDC Sandbox-Instanz verbunden werden, um die Integration zu testen, bevor die Verbindung zu Ihrer SFDC-Produktionsinstanz gewechselt wird.
>* Wenn Sie zuerst mit einer SFDC-Sandbox testen, empfehlen wir dringend, mit einer zu testen, die eine exakte Replikation Ihrer SFDC-Produktionsinstanz in Bezug auf Felder in den Objekten Lead, Kontakt, Konto, Opportunity, Kampagne und Fall ist. Wenn Sie aktive APEX-Trigger in der Produktion haben, die bei Aktualisierungen der Lead-, Kontakt-, Konto-, Opportunity-, Kampagnen- und Fallobjekte ausgelöst werden, sollten Sie versuchen, diese in Ihrer Sandbox zu aktivieren.
>* Wenn Sie mit dem Testen fertig sind, aktualisieren Sie Ihr [!DNL Marketo Measure]-Konto, sodass es auf Ihre Produktions-[!DNL Salesforce] verweist (anstelle von Sandbox-[!DNL Salesforce]). Aufgrund der Art und Weise, wie die Integration erstellt wurde, können Sie, sobald ein [!DNL Marketo Measure]-Konto mit [!DNL Salesforce] verbunden ist, nicht „rückwärts“ gehen und eine Verbindung zu einer Sandbox-[!DNL Salesforce]-Organisation herstellen.

## Verwendung von API-Guthaben {#api-credits-usage}

Marketo Measure verwendet eine CRM-Integrationsaufgabe, um über einen integrierten Benutzer eine Verbindung zur Salesforce eines Kunden herzustellen. Für den Datenaustausch über diesen Benutzer werden Salesforce-API-Credits verwendet. Sie haben die Möglichkeit, einem Integrationsbenutzer ein Kreditkontingent zuzuweisen, was dazu dient, übermäßige API-Aufrufe zu regulieren. Dieses Kontingent oder Limit wird alle 24 Stunden zurückgesetzt.

Sie können auf dieses Limit in Marketo Measure zugreifen über: **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein** > **Tägliches CRM-API-Limit** und es für Ihre Mandanten konfigurieren.

![Sie können auf dieses Limit in Marketo Measure zugreifen über: Meine Kontoeinstellungen](assets/connect-salesforce-2.png)

### Festlegen eines Limits für API-Credits {#setting-a-limit-for-api-credits}

1. Navigieren Sie zu **Mein Konto** > **Einstellungen**.

1. Klicken Sie unter CRM auf **Allgemein**. Die Option **Tägliches CRM-API-Limit** wird angezeigt.

1. Klicken Sie auf das Schlosssymbol, um es zu bearbeiten.

   ![1. Klicken Sie auf das Schlosssymbol, um es zu bearbeiten.](assets/connect-salesforce-3.png)

1. Geben Sie ein gewünschtes Limit von mindestens 100.000 ein. Klicken Sie auf **Speichern**, wenn Sie fertig sind.

   ![1. Geben Sie ein gewünschtes Limit von mindestens 100.000 ein. Klicken](assets/connect-salesforce-1.png)

>[!NOTE]
>
>Um die verfügbaren Salesforce-API-Credits für Ihre Connected Solution zu erhöhen, wenden Sie sich an Ihren Salesforce-Administrator und lesen Sie [dieses Salesforce-Dokument](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}.

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/error-notifications.md){target="_blank"}
