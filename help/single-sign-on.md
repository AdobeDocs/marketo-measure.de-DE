---
description: Anleitung zum einmaligen Anmelden für Marketo Measure-Benutzende
title: Single Sign-On
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 91%

---

# Single Sign-On {#single-sign-on}

SAML (Security Assertion Markup Language) für SSO (Single Sign-On) ermöglicht es den Benutzenden, sich über den Identitätsanbieter eines Unternehmens zu authentifizieren, wenn sie sich bei der [!DNL Marketo Measure]-App anmelden. SSO ermöglicht es den Benutzenden, sich einmal zu authentifizieren, ohne dass sie sich in verschiedenen Anwendungen authentifizieren müssen. SAML ist eine Notwendigkeit für Kundinnen und Kunden in Unternehmen, da nicht alle Benutzenden über ein [!DNL Salesforce]- oder [!DNL Google]-Konto in ihrer Organisation verfügen. Um zu skalieren, hat [!DNL Marketo Measure] eine SAML-Lösung entwickelt, die Identitätsanbieter von Unternehmen unterstützen kann.

>[!CAUTION]
>
>In diesem Artikel werden das Single Sign-On (SSO) und die erweiterte CRM-Benutzerverwaltung vorgestellt. Wenn Ihr Konto **nach dem 10.09.2020** eingerichtet wurde, beachten Sie diesen Artikel nicht, da SSO und Identitätsmanagement in der [Adobe Admin Console für Ihre [!DNL Marketo Measure] Integration](/help/implementation-guide.md) festgelegt werden.

>[!NOTE]
>
>Es ist wahrscheinlich, dass Unternehmen verschiedene Identitätsanbieter verwenden (z. B. Ping Identity, Okta). Die in den folgenden Einrichtungsanweisungen und in der Benutzeroberfläche verwendeten Begriffe stimmen möglicherweise nicht direkt mit denen Ihres Identitätsanbieters überein.

## Anforderungen {#requirements}

* Benutzende mit AccountAdmin-Rechten in der [!DNL Marketo Measure]-App
* Benutzende mit Adminzugriff auf den Identitätsanbieter der Kundschaft

## Erste Schritte {#getting-started}

Um zu beginnen, navigieren Sie in der [!DNL Marketo Measure]-Anwendung zur Seite „Einstellungen“ > „Sicherheit“ > „Authentifizierung“. Wechseln Sie dann für den Anmeldetyp zu „Benutzerdefiniertes SSO“, um die Konfigurationsoptionen anzuzeigen. Die Änderungen werden erst wirksam, wenn Sie Ihre Authentifizierung testen und auf die Schaltfläche **[!UICONTROL Speichern]** unten auf der Seite klicken.

![Navigieren Sie zunächst zur Seite „Einstellungen Sicherheitsauthentifizierung“ im](assets/compliance-resources-1.png)

## Prozess {#process}

Single Sign-On bei [!DNL Marketo Measure] erfordert die Konfiguration Ihrer Authentifizierungseinstellungen in einer Reihe von Schritten, damit Sie nicht Gefahr laufen, aus Ihrem [!DNL Marketo Measure]-Konto ausgesperrt zu werden.

Richten Sie die [!DNL Marketo Measure]-Anwendung in Ihrem Identitätsanbieter ein. Weitere Informationen finden Sie in der unten aufgeführten externen Dokumentation.

    a. Wenn Sie aufgefordert werden, die Single Sign-On-URL, die Empfänger-URL, die Ziel-URL, oder die SAML Assertion Customer Service-URL (ACS) einzugeben, verwenden Sie [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b. Wenn Sie aufgefordert werden die Zielgruppenbeschränkungs-URL oder die anwendungsdefinierte eindeutige Kennung einzugeben, verwenden Sie [https://BizibleLPM](https://biziblelpm/)

Wechseln zur benutzerdefinierten SSO in der [!DNL Marketo Measure]-Anwendung

    a. Sobald die Abrechnungsgruppe für Ihr Konto aktiviert wurde, können Sie nun zu [!UICONTROL Einstellungen] > [!UICONTROL Sicherheit] > [!UICONTROL Authentifizierung]
    
     navigieren. b. Standardmäßig ist Ihr Login-Typ auf „CRM-Benutzer“ festgelegt.
    
    c. Wechseln Sie für den Anmeldetyp zu „Benutzerdefiniertes SSO“, um den Konfigurationsprozess zu starten.

Ausfüllen der Verbindungseinstellungen für Ihre Identitätsanbieter-Konfiguration

    a. Ihr Identitätsanbieter stellt Ihnen möglicherweise ein XML-Dokument mit den IdP-Metadaten zur Verfügung, aus dem Sie die erforderlichen Konfigurationsfelder entnehmen können. Laden Sie entweder den Inhalt des XML-Dokuments oder füllen Sie die drei folgenden Felder mit den Daten aus, die während des Identitätsanbieter-Konfigurationsprozesses generiert wurden. **Sie brauchen nicht beides durchzuführen.**
    
    i. IdP-URL: Die URL, auf die [!DNL Marketo Measure] verweisen muss, um Ihre Benutzenden in der [!DNL Marketo Measure] -Anwendung zu authentifizieren. Manchmal auch als „Umleitungs-URL“ bezeichnet.
    ii. IdP-Herausgeber: Eine eindeutige Kennung des Identitätsanbieters. Manchmal auch als „externer Schlüssel“ bezeichnet.
    iii. IdP-Zertifikat: Ein öffentlicher Schlüssel, mit dem [!DNL Marketo Measure] die Signatur aller Antworten des Identitätsanbieters überprüfen und validieren kann.

Legen Sie die Gültigkeit des Tokens für Ihre Benutzenden in Minuten fest.

    a. [!DNL Marketo Measure] erlaubt eine ganze Zahl von 1 bis 1440 Minuten. Nachdem die Sitzungszeit einer Person überschritten wurde, wird sie abgemeldet, sobald sie zu einer neuen Seite navigiert.

Richten Sie die Einstellungen für die Benutzerattribute ein und ordnen Sie sie den jeweiligen Vornamen, Nachnamen und E-Mail-Adressen zu.

    a. Wenn Sie die SAML-Attribute eingeben, kann [!DNL Marketo Measure] Ihre Benutzenden anhand der übermittelten Informationen erkennen.
    
    i. E-Mail-Attribut: Geben Sie den Attributnamen an, den Ihr Identitätsanbieter für die E-Mail-Adresse der Person verwendet.
    ii. Vornamen-Attribut: Geben Sie den Attributnamen an, den Ihr Identitätsanbieter für den Vornamen der Person verwendet.
    iii. Nachnamen-Attribut: Geben Sie den Attributnamen an, den Ihr Identitätsanbieter für den Nachnamen der Benutzenden verwendet.
    
    b. Hinweis: Wenn Sie Ihre SAML-Konfiguration jetzt testen, analysieren wir die Attribute „E-Mail“, „Vorname“ und „Nachname“, die Sie für diesen Abschnitt verwenden können.

![ B. Hinweis: Wenn Sie Ihre SAML-Konfiguration jetzt testen, werden wir sie analysieren](assets/discover-control-1.png)

Richten Sie Ihre Benutzerrolleneinstellungen ein und ordnen Sie sie den entsprechenden Rollen oder Gruppen zu, die von Ihrem IdP klassifiziert wurden.

    a. Kundinnen und Kunden verfügen über die Möglichkeit, Benutzerrollen von [!DNL Marketo Measure] auf der Grundlage der in ihrem Identitätsanbieter definierten Gruppen zuzuweisen. Indem Sie Ihre SAML-Attribute eingeben, wird [!DNL Marketo Measure] die Rollen und Gruppen Ihrer Benutzenden den [!DNL Marketo Measure] -Benutzerberechtigungen zuordnen. Wir empfehlen dringend, diese Rollen einzurichten, damit Ihre [!DNL Marketo Measure] -Admins über ausreichende Berechtigungen verfügen, um Ihr Konto zu aktualisieren.
    
    b. Wenn keine Rollen oder Gruppen zugeordnet sind, besteht die Standardeinstellung darin, dass alle Mitarbeitenden im Identitätsanbieter über Standardbenutzerzugriff verfügen.
    
    i. [!DNL Marketo Measure] Standardbenutzer: Geben Sie die Rolle oder den Gruppenwert (von Ihrem SSO-Anbieter) für die Benutzenden an, die über einen schreibgeschützten Zugriff auf die Anwendung [!DNL Marketo Measure] verfügen sollen.
    ii. [!DNL Marketo Measure] -Konto-Admin-Benutzer: Geben Sie die Rolle oder den Gruppenwert (von Ihrem SSO-Anbieter) für die Benutzenden an, die über administrativen Zugriff auf die Anwendung [!DNL Marketo Measure] verfügen sollen. Das bedeutet, dass die Rolle Zugriff auf Konfigurationsänderungen und Einstellungen hat, die sich auf Ihr Konto beziehen.
    iii. Sie müssen in Ihrem IdP über ein Attribut mit dem genauen Namen „Gruppen“ verfügen, das die Werte enthält, die Sie in die Attribute „Bizible-Standardbenutzer“ oder „Bizible-Konto-Admin-Benutzer“ eingeben.
    
    c. Wenn mehrere Rollen oder Gruppen einer Rolle zugeordnet werden sollen, geben Sie jeden Wert durch ein Komma getrennt ein.

![c. Wenn mehrere Rollen oder Gruppen einer Rolle zugeordnet werden sollen,](assets/discover-control-2.png)

Testen der Single Sign-On-Konfiguration

    a. Bevor Sie auf „Speichern“ klicken können, werden Sie aufgefordert, auf die Schaltfläche [!UICONTROL SAML-Authentifizierung testen] zu klicken, um zu überprüfen, ob Ihre Einstellungen richtig konfiguriert wurden.
    
    b. Wenn der Fehler „fehlgeschlagen“ angezeigt wird, folgen Sie der Meldung und versuchen Sie es erneut.

![ B. Wenn der Fehler „Fehler“ angezeigt wird, befolgen Sie die Meldung und versuchen Sie es erneut](assets/discover-control-3.png)

Speichern Sie Ihre Einstellungen und weisen Sie Ihre Kolleginnen und Kollegen an, [!UICONTROL Single Sign-On] mit Ihrer neuen, benutzerdefinierten Anmelde-URL zu verwenden.

    a. Wichtig: Sobald Sie Ihre neuen Authentifizierungseinstellungen gespeichert haben, ist es möglich, dass Ihre Sitzung endet, sobald Sie zu einer neuen Seite navigieren, weil Sie die Anmeldung durch Benutzende eines CRM deaktiviert und benutzerdefiniertes SSO aktiviert haben.

![a. Wichtig: Nachdem Sie Ihre neuen Authentifizierungseinstellungen gespeichert haben, ist dies möglich](assets/discover-control-3.png)

Probieren Sie es aus!

    a. Verwenden Sie Ihre neue, benutzerdefinierte Anmelde-URL und versuchen Sie, sich mit den Anmeldedaten Ihres Identitätsanbieters wieder bei der Anwendung [!DNL Marketo Measure] anzumelden.
    
    b. Das Format sieht wie folgt aus: „https://apps.adobe.com/business/[accountName]“
    
    c. Herzlichen Glückwunsch! Sie haben erfolgreich Single Sign-On in der Anwendung [!DNL Marketo Measure] für Ihr Konto eingerichtet!

![c. Glückwunsch! Sie haben Single Sign-On für erfolgreich eingerichtet](assets/discover-control-3.png)

>[!NOTE]
>
>Nachdem Sie SSO konfiguriert haben, müssen Sie innerhalb der Anwendung[!DNL Marketo Measure]keine Benutzenden mehr hinzufügen. Die Bereitstellung von Benutzenden sollte direkt über Ihren Identitätsanbieter erfolgen.

## Benutzende eines CRM (Erweiterte Einstellungen) {#crm-users-advanced-setup}

Standardmäßig können alle Konten über ihre CRM-Zugangsdaten auf die [!DNL Marketo Measure]-Anwendung zugreifen. Manchmal müssen Kontoinhaberinnen bzw. -inhaber den Zugriff auf bestimmte Rollen beschränken und ihn nicht für alle Benutzenden mit einer aktiven CRM-Lizenz öffnen. Mit der erweiterten Einrichtung können Sie Ihre CRM-Rollen und -Gruppen den [!DNL Marketo Measure]-Benutzerberechtigungen zuordnen.

Wenn keine Rollen oder Gruppen zugeordnet sind, besteht die Standardeinstellung darin, dass alle aktiven Lizenzen in Ihrem CRM-System über Standardbenutzerzugriff verfügen.

* [!DNL Marketo Measure]-Standardbenutzer: Geben Sie den Rollen- oder Gruppenwert für Benutzende an, die über schreibgeschützten Zugriff auf die [!DNL Marketo Measure]-Anwendung verfügen sollen.
* [!DNL Marketo Measure]-Konto-Admin-Benutzer: Geben Sie den Rollen- oder Gruppenwert für Benutzende an, die über Administratorzugriff auf die [!DNL Marketo Measure]-Anwendung verfügen sollen. Das bedeutet, dass die Rolle Zugriff auf Konfigurationsänderungen und Einstellungen hat, die sich auf Ihr Konto beziehen.

Wenn mehrere Rollen oder Gruppen einer Rolle zugeordnet werden sollen, geben Sie jeden Wert durch ein Komma getrennt ein.

**Salesforce-Rollen**

Verwenden Sie für [!DNL Salesforce]-Rollen den Namen jeder Rolle. Alle Rollen finden Sie unter dem Menü [!UICONTROL Einrichtung] >[!UICONTROL Benutzer verwalten] >[!UICONTROL Rollen].

![Verwenden Sie für Salesforce-Rollen den Namen jeder Rolle. Alle Rollen](assets/discover-control-3.png)

**Dynamics-Rollen**

Verwenden Sie für [!DNL Dynamics]-Rollen den Namen jeder Sicherheitsrolle. Alle Sicherheitsrollen finden Sie unter dem Menü [!UICONTROL Einstellungen] >[!UICONTROL Sicherheit] >[!UICONTROL Sicherheitsrollen].

![Für Dynamics-Rollen verwenden Sie den Namen der einzelnen Sicherheitsrollen. Alle](assets/discover-control-3.png)

![Für Dynamics-Rollen verwenden Sie den Namen der einzelnen Sicherheitsrollen. Alle](assets/discover-control-3.png)

**Google-Benutzende**

Sobald das benutzerdefinierte SSO eingerichtet wurde, wird die Seite [!UICONTROL Benutzer] so aktualisiert, dass nur externe Benutzende angezeigt werden, die mit Google-Logins hinzugefügt wurden. Da alle Benutzenden mit Zugriff über die SSO-Konfiguration definiert sind, sind hier weitere externe Benutzende aufgeführt.

![Nachdem das benutzerdefinierte SSO eingerichtet wurde, wird die Seite „Benutzer“ angezeigt](assets/discover-control-3.png)

Nur gültige [!DNL Google]-Konten können hinzugefügt werden und es muss eine Benutzerrolle definiert sein.

## Externe Links {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping Identity](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/de-de/azure/active-directory/active-directory-saas-custom-apps)
