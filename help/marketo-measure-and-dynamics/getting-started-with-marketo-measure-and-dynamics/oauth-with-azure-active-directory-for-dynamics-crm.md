---
unique-page-id: 37357059
description: OAuth mit  [!DNL Azure Active Directory]  für Dynamics CRM - [!DNL Marketo Measure]
title: OAuth mit  [!DNL Azure Active Directory]  für Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 0%

---

# OAuth mit [!DNL Azure Active Directory] für Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## Wer ist betroffen? {#who-s-affected}

Diese Einrichtung richtet sich an neue [!DNL Marketo Measure], die Dynamics CRM mit einem [!DNL Azure Active Directory] (AAD)-Konto verwenden, oder an Kunden, die von ihrem alten Benutzernamen und Kennwort zu [!DNL Azure Active Directory] mit OAuth migrieren möchten.

>[!NOTE]
>
>Für beide Szenarien wird hier AAD eingerichtet, um als Datenanbieter die Verbindung Ihrer Dynamics-Instanz mit [!DNL Marketo Measure] zu erleichtern.

## Neue Anwendung einrichten {#set-up-new-application}

1. Melden Sie sich bei Ihrem [Azure-Portal](https://portal.azure.com/#home) an.

1. Wählen Sie den Azure AD-Mandanten aus, indem Sie auf Ihr Konto oben rechts auf der Seite klicken, dann auf die Schaltfläche „Verzeichnisnavigation wechseln“ klicken und den entsprechenden Mandanten auswählen. Überspringen Sie diesen Schritt, wenn Sie nur einen Azure AD-Mandanten unter Ihrem Konto haben oder bereits den entsprechenden Azure AD-Mandanten ausgewählt haben.

   ![](assets/setup-2.png)

1. Suchen Sie in der Suchleiste nach &quot;[!DNL Azure Active Directory]&quot; und klicken Sie zum Öffnen auf den Namen.

   ![](assets/setup-3.png)

1. Klicken Sie **[!UICONTROL Menü links auf]** App-Registrierungen“.

   ![](assets/setup-4.png)

1. Klicken Sie **[!UICONTROL oben]** „Neue Registrierung“.

   ![](assets/setup-5.png)

1. Befolgen Sie die Anweisungen und erstellen Sie eine Anwendung. Es spielt keine Rolle, ob es sich um eine Web-Anwendung oder eine öffentliche Client-Anwendung (Mobile und Desktop) handelt, aber wenn Sie spezielle Beispiele für Web-Anwendungen oder öffentliche Client-Anwendungen wünschen, sollten Sie sich die [Schnellstarts](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview) ansehen.\
   a. Name ist der Anwendungsname und beschreibt Ihre Anwendung für Endbenutzer.\
   b. Wählen Sie unter Unterstützte Kontotypen die Option Konten in einem beliebigen Organisationsverzeichnis und persönliche Microsoft-Konten aus.\
   c. Geben Sie den Umleitungs-URI an. Bei Web-Anwendungen ist dies die Basis-URL Ihrer Anwendung, bei der sich Benutzer anmelden können. Beispiel: `http://localhost:12345`. Für öffentliche Clients (Mobile und Desktop) verwendet Azure AD sie, um Token-Antworten zurückzugeben. Geben Sie einen für Ihre Anwendung spezifischen Wert ein. Beispiel: `http://MyFirstAADApp`.

1. Nachdem Sie die Registrierung abgeschlossen haben, weist Azure AD Ihrer Anwendung eine eindeutige Client-Kennung (die Anwendungs-ID) zu. Sie benötigen diesen Wert im nächsten Abschnitt. Kopieren Sie ihn daher von der Anwendungsseite.

1. Um Ihre Anwendung im Azure-Portal zu finden, klicken Sie auf **[!UICONTROL App-Registrierungen]** und dann auf **[!UICONTROL Alle Anwendungen]**. Öffnen Sie das neu erstellte Programm

1. Klicken Sie **[!UICONTROL Menü]** auf „Authentifizierung“.

   ![](assets/setup-9.png)

1. Fügen Sie die [!DNL Marketo Measure] Umleitungs-URLs `https://apps.bizible.com/OAuth2` und `https://apps.bizible.com/OAuth2?identityOnly=true` zur Liste der Umleitungs-URLs hinzu.

   ![](assets/setup-10.png)

1. Navigieren Sie zur Registerkarte API-Berechtigungen und stellen Sie sicher, dass der Anwendung die richtigen Berechtigungen zugewiesen sind.

   ![](assets/setup-10a.png)

1. Geben Sie von hier aus &quot;[!UICONTROL enterprise]&quot; in das Suchfeld ein und klicken Sie auf **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. Suchen Sie Ihr neues Programm erneut in der Liste der Programme und öffnen Sie es.

1. Klicken Sie auf der Registerkarte Berechtigungen auf **[!UICONTROL Administratorzustimmung erteilen für (Instanzname)]**.

   ![](assets/setup-13a.png)

1. Klicken Sie **[!UICONTROL Akzeptieren]**.

   ![](assets/setup-13b.png)

1. Stellen Sie auf der Registerkarte [!UICONTROL Benutzer und &#x200B;]&quot; sicher, dass die gültigen „Benutzer und Gruppen“ der Anwendung zugewiesen sind.

   ![](assets/setup-14.png)

## Programmbenutzer erstellen {#creating-an-application-user}

Nachdem die Registrierung der Anwendung abgeschlossen ist, kann ein Anwendungsbenutzer erstellt werden.

1. Navigieren Sie zu Ihrer Common Data Service-Umgebung (`https://[org].crm.dynamics.com`).

1. Navigieren Sie **[!UICONTROL Einstellungen]** > **[!UICONTROL Sicherheit]** > **[!UICONTROL Benutzer]**.

1. Wählen Sie **[!UICONTROL Anwendungsbenutzer]** im Ansichtsfilter aus.

1. Wählen Sie **[!UICONTROL + Neu]**.

1. Geben Sie im Formular Anwendungsbenutzer die erforderlichen Informationen ein.

   >[!NOTE]
   >
   >* Die Informationen zum Benutzernamen dürfen nicht mit einem Benutzer übereinstimmen, der in der [!DNL Azure Active Directory] vorhanden ist.
   >
   >* Geben Sie im Feld Anwendungs-ID die Anwendungs-ID der App ein, die Sie zuvor in der Azure AD registriert haben.

1. Wenn die Einrichtung korrekt ist, werden nach Auswahl von **[!UICONTROL Speichern]** die Felder **[!UICONTROL Anwendungs-ID-URI]** und **[!UICONTROL Azure AD-Objekt-ID]** automatisch mit den richtigen Werten ausgefüllt.

1. Wählen Sie vor dem Verlassen des Benutzerformulars **[!UICONTROL Rollen verwalten]** und weisen Sie diesem Programmbenutzer eine Sicherheitsrolle zu, damit der Programmbenutzer auf die gewünschten Organisationsdaten zugreifen kann.

## Verbinden Ihrer Dynamics-Instanz über OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Wenn Sie Ihre Dynamics-Verbindung zum ersten Mal einrichten, befolgen Sie die Schritte 1 bis 5 im Abschnitt „CRM als Datenanbieter“ in [diesem Artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. Wenn Sie nach OAuth-Anmeldeinformationen gefragt werden, geben Sie die Client-ID, das Client-Geheimnis und den URI der Anwendungs-ID ein, die im obigen Abschnitt eingerichtet wurden.

a. Die Client-ID ist die ID aus Schritt #7 im obigen Abschnitt. Wenn Sie sie nicht aufgeschrieben haben, wird die Anwendungs-ID in den Einstellungen der App-Registrierung angezeigt.

b. „Client-Geheimnis“ ist das im Azure-Portal für Ihre Anwendung unter „Zertifikate und Geheimnisse“ erstellte Anwendungsgeheimnis.

![](assets/creating-2e.png)

c. Der Anwendungs-ID-URI ist die URL der Ziel-Web-API (gesicherte Ressource). Um die App-ID-URL zu finden, klicken Sie im Azure-Portal auf &quot;[!DNL Azure Active Directory]&quot;, klicken Sie auf „Anwendungsregistrierungen“, öffnen Sie die Seite „Einstellungen“ der Anwendung und klicken Sie dann auf „Eigenschaften“. Es kann sich auch um eine externe Ressource wie `https://graph.microsoft.com` handeln. Dies ist normalerweise die URL der Dynamics-Instanz.

1. Nachdem Sie auf **[!UICONTROL Senden]** geklickt haben, werden Sie aufgefordert, sich mit [!DNL Azure Active Directory] anzumelden. Nach erfolgreicher Authentifizierung wird Ihr Dynamics-Konto als Datenanbieter in [!DNL Marketo Measure] verbunden.

## Erneutes Authentifizieren Ihres Dynamics-Kontos {#re-authenticating-your-dynamics-account}

1. Wechseln Sie in der [!DNL Marketo Measure] zu **[!UICONTROL Meine Einstellungen]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Verbindungen]**.

1. Klicken Sie auf das Schlüsselsymbol im CRM-Abschnitt neben der Dynamics-Verbindung.

1. Wenn Sie auf den -Schlüssel klicken, wird ein Popup angezeigt, und Sie werden aufgefordert, die Client-ID, das Client-Geheimnis und den URI der Anwendungs-ID einzugeben, ähnlich wie beim Registrierungsfluss.

   ![](assets/re-authenticating-3.png)

1. Nachdem Sie auf **[!UICONTROL Senden]** geklickt haben, werden Sie aufgefordert, sich mit [!DNL Azure Active Directory] anzumelden. Nach erfolgreicher Authentifizierung wird Ihr Dynamics-Konto innerhalb von [!DNL Marketo Measure] erneut autorisiert.
