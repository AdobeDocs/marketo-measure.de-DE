---
unique-page-id: 37357059
description: OAuth mit  [!DNL Azure Active Directory] für Dynamics CRM - [!DNL Marketo Measure]
title: OAuth mit [!DNL Azure Active Directory] für Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 0%

---

# OAuth mit [!DNL Azure Active Directory] für Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## Betroffene Personen {#who-s-affected}

Diese Einrichtung richtet sich an neue [!DNL Marketo Measure] -Kunden, die Dynamics CRM mit einem [!DNL Azure Active Directory] -Konto (AAD) verwenden, oder an Kunden, die mit OAuth von ihrem alten Benutzernamen und Passwort zu [!DNL Azure Active Directory] migrieren möchten.

>[!NOTE]
>
>Für beide Szenarien ist AAD hier eingerichtet, um die Verbindung Ihrer Dynamics-Instanz mit [!DNL Marketo Measure] als Datenanbieter zu erleichtern.

## Einrichten einer neuen Anwendung {#set-up-new-application}

1. Melden Sie sich bei Ihrem [Azure Portal](https://portal.azure.com/#home) an.

1. Wählen Sie den Azure AD-Mandanten aus, indem Sie auf Ihr Konto in der oberen rechten Ecke der Seite klicken, dann auf die Navigation Switch Directory klicken und dann den entsprechenden Mandanten auswählen. Überspringen Sie diesen Schritt, wenn Sie nur einen Azure AD-Mandanten unter Ihrem Konto haben oder wenn Sie bereits den entsprechenden Azure AD-Mandanten ausgewählt haben.

   ![](assets/setup-2.png)

1. Suchen Sie in der Suchleiste nach &quot;[!DNL Azure Active Directory]&quot; und klicken Sie auf den Namen, um ihn zu öffnen.

   ![](assets/setup-3.png)

1. Klicken Sie im linken Menü auf **[!UICONTROL App-Registrierungen]** .

   ![](assets/setup-4.png)

1. Klicken Sie oben auf **[!UICONTROL Neue Registrierung]** .

   ![](assets/setup-5.png)

1. Befolgen Sie die Anweisungen und erstellen Sie eine Anwendung. Es spielt keine Rolle, ob es sich um eine Webanwendung oder eine öffentliche Client-Anwendung (Mobil- und Desktop-Programm) handelt. Wenn Sie jedoch bestimmte Beispiele für Webanwendungen oder öffentliche Clientanwendungen wünschen, sehen Sie sich die [quickstarts](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview) an.\
   a. Name ist der App-Name und beschreibt Ihre Anwendung für Endbenutzer.\
   b. Wählen Sie unter &quot;Unterstützte Kontotypen&quot;Konten in einem beliebigen Organisationsverzeichnis und persönlichen Microsoft-Konten aus.\
   c. Geben Sie den Umleitungs-URI an. Bei Webanwendungen ist dies die Basis-URL Ihrer App, an der sich Benutzer anmelden können. Beispiel: `http://localhost:12345`. Für öffentliche Clients (mobile und Desktopgeräte) verwendet Azure AD diese, um Token-Antworten zurückzugeben. Geben Sie einen anwendungsspezifischen Wert ein. Beispiel: `http://MyFirstAADApp`.

1. Nachdem Sie die Registrierung abgeschlossen haben, weist Azure AD Ihrer Anwendung eine eindeutige Client-Kennung (die Anwendungs-ID) zu. Sie benötigen diesen Wert im nächsten Abschnitt. Kopieren Sie ihn daher von der Anwendungsseite.

1. Um Ihre Anwendung im Azure-Portal zu finden, klicken Sie auf **[!UICONTROL App-Registrierungen]** und dann auf **[!UICONTROL Alle Anwendungen]**. Öffnen Sie die neu erstellte Anwendung

1. Klicken Sie im linken Menü auf **[!UICONTROL Authentifizierung]** .

   ![](assets/setup-9.png)

1. Fügen Sie die Umleitungs-URLs [!DNL Marketo Measure]: `https://apps.bizible.com/OAuth2` und `https://apps.bizible.com/OAuth2?identityOnly=true` zur Liste der Umleitungs-URLs hinzu.

   ![](assets/setup-10.png)

1. Navigieren Sie zur Registerkarte API-Berechtigungen und stellen Sie sicher, dass der Anwendung die richtigen Berechtigungen zugewiesen sind.

   ![](assets/setup-10a.png)

1. Geben Sie hier &quot;[!UICONTROL enterprise]&quot;in das Suchfeld ein und klicken Sie auf **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. Suchen und öffnen Sie erneut Ihre neue Anwendung in der Liste der Anwendungen.

1. Klicken Sie auf der Registerkarte &quot;Berechtigungen&quot;auf **[!UICONTROL Admin-Zustimmung erteilen für (Instanzname)]**.

   ![](assets/setup-13a.png)

1. Klicken Sie auf **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. Vergewissern Sie sich auf der Registerkarte &quot;[!UICONTROL Benutzer und Gruppen]&quot;, dass der Anwendung die gültigen &quot;Benutzer und Gruppen&quot;zugewiesen sind.

   ![](assets/setup-14.png)

## Anwendungsbenutzer erstellen {#creating-an-application-user}

Sobald die Registrierung der Anwendung abgeschlossen ist, kann ein Anwendungsbenutzer erstellt werden.

1. Navigieren Sie zu Ihrer allgemeinen Datendienstumgebung (`https://[org].crm.dynamics.com`).

1. Navigieren Sie zu **[!UICONTROL Einstellungen]** > **[!UICONTROL Sicherheit]** > **[!UICONTROL Benutzer]**.

1. Wählen Sie **[!UICONTROL Anwendungsbenutzer]** im Ansichtsfilter aus.

1. Wählen Sie **[!UICONTROL + Neu]** aus.

1. Geben Sie im Formular &quot;Application User&quot;die erforderlichen Informationen ein.

   >[!NOTE]
   >
   >* Die Benutzernameninformationen dürfen nicht mit einem Benutzer übereinstimmen, der in der [!DNL Azure Active Directory] vorhanden ist.
   >
   >* Geben Sie im Feld Anwendungs-ID die Anwendungs-ID der App ein, die Sie zuvor in der Azure AD registriert haben.

1. Wenn die Einrichtung korrekt ist, werden nach Auswahl von **[!UICONTROL Speichern]** die Felder **[!UICONTROL Anwendungs-ID URI]** und **[!UICONTROL Azure AD Object Id]** automatisch mit den richtigen Werten ausgefüllt.

1. Wählen Sie vor dem Beenden des Benutzerformulars **[!UICONTROL Rollen verwalten]** und weisen Sie diesem Anwendungsbenutzer eine Sicherheitsrolle zu, damit der Anwendungsbenutzer auf die gewünschten Organisationsdaten zugreifen kann.

## Verbinden Ihrer Dynamics-Instanz über OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Führen Sie beim erstmaligen Einrichten Ihrer Dynamics-Verbindung die Schritte 1 bis 5 des Abschnitts &quot;CRM as a Data Provider&quot;in [diesem Artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md) aus.

1. Wenn Sie nach OAuth-Anmeldeinformationen gefragt werden, geben Sie die Client-ID, das Client-Geheimnis und den Anwendungs-ID-URI ein, die im obigen Abschnitt eingerichtet wurden.

a. Die Client-ID ist die ID aus Schritt 7 im obigen Abschnitt. Wenn Sie es nicht notiert haben, wird die Anwendungs-ID in den Einstellungen der App-Registrierung angezeigt.

b. Client Secret ist das Anwendungsgeheimnis, das im Azure Portal für Ihre Anwendung unter Zertifikate und Geheimnisse erstellt wurde.

![](assets/creating-2e.png)

c. Der Anwendungs-ID-URI ist die URL der Ziel-Web-API (gesicherte Ressource). Um die App-ID-URL zu finden, klicken Sie im Azure Portal auf &quot;[!DNL Azure Active Directory]&quot;, klicken Sie auf &quot;App-Registrierungen&quot;, öffnen Sie die Einstellungsseite der Anwendung und klicken Sie auf &quot;Eigenschaften&quot;. Es kann sich auch um eine externe Ressource wie `https://graph.microsoft.com` handeln. Dies ist normalerweise die URL der Dynamics-Instanz.

1. Nachdem Sie auf **[!UICONTROL Senden]** geklickt haben, werden Sie aufgefordert, sich mit [!DNL Azure Active Directory] anzumelden. Wenn die Authentifizierung erfolgreich ist, ist Ihr Dynamics-Konto als Datenanbieter innerhalb von [!DNL Marketo Measure] verbunden.

## Reauthentifizieren Ihres Dynamics-Kontos {#re-authenticating-your-dynamics-account}

1. Wenn Sie sich in der Anwendung [!DNL Marketo Measure] befinden, gehen Sie zu **[!UICONTROL Meine Einstellungen]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Verbindungen]**.

1. Klicken Sie auf das Schlüsselsymbol im Abschnitt CRM neben der Dynamics-Verbindung.

1. Wenn auf den Schlüssel geklickt wird, wird ein Popup-Fenster angezeigt, in dem Sie aufgefordert werden, die Client-ID, das Client-Geheimnis und den Anwendungs-ID-URI einzugeben, ähnlich dem Anmeldefluss.

   ![](assets/re-authenticating-3.png)

1. Nachdem Sie auf **[!UICONTROL Senden]** geklickt haben, werden Sie aufgefordert, sich mit [!DNL Azure Active Directory] anzumelden. Wenn die Authentifizierung erfolgreich ist, wird Ihr Dynamics-Konto innerhalb von [!DNL Marketo Measure] erneut autorisiert.
