---
unique-page-id: 18874761
description: Single Sign-On - [!DNL Marketo Measure]
title: Single Sign-On
exl-id: a328e9cb-8352-4693-8a44-533e08f1a29c
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---

# Single Sign-On {#single-sign-on}

SAML (Security Assertion Markup Language) für SSO (Single Sign-on) ermöglicht Benutzern die Authentifizierung über den Identitäts-Provider eines Unternehmens bei der Anmeldung beim [!DNL Marketo Measure] App. SSO ermöglicht es einem Benutzer, sich einmal zu authentifizieren, ohne separate Apps authentifizieren zu müssen. SAML ist für Unternehmenskunden erforderlich, da nicht alle Benutzer über eine [!DNL Salesforce] oder [!DNL Google] -Konto in ihrer Organisation. Skalierung, [!DNL Marketo Measure] hat eine SAML-Lösung entwickelt, die Identitätsanbieter des Unternehmens unterstützen kann.

>[!CAUTION]
>
>In diesem Artikel werden Single Sign-On (SSO) und die erweiterte CRM-Benutzerverwaltung vorgestellt. Wenn Ihr Konto bereitgestellt wurde **nach dem 10.9.2020**, da SSO und Identity Management innerhalb der [Adobe Admin Console für Ihre [!DNL Marketo Measure] Integration](/help/configuration-and-setup/getting-started-with-marketo-measure/marketo-measure-quick-start.md).

>[!NOTE]
>
>Es ist wahrscheinlich, dass Unternehmen verschiedene Identitäts-Provider verwenden (z. B. Ping Identity, Okta). Die in den folgenden Einrichtungsanweisungen und in der Benutzeroberfläche verwendeten Begriffe stimmen möglicherweise nicht direkt mit denen Ihres Identitäts-Providers überein.

## Anforderungen {#requirements}

* Benutzer mit Konto-Admin-Berechtigungen in der [!DNL Marketo Measure] App
* Benutzer mit Administratorzugriff auf den Identitätsanbieter des Kunden

## Erste Schritte {#getting-started}

Navigieren Sie zu Einstellungen > Sicherheit > Authentifizierung in der [!DNL Marketo Measure] Anwendung. Wechseln Sie dann den Anmeldetyp zu Benutzerdefiniertes SSO , um die Konfigurationsoptionen anzuzeigen. Änderungen werden erst wirksam, wenn Sie Ihre Authentifizierung testen und auf **[!UICONTROL Speichern]** -Schaltfläche unten auf der Seite.

![](assets/single-sign-on-1.png)

## Prozess {#process}

[!DNL Marketo Measure] Single Sign-On erfordert die Konfiguration Ihrer Authentifizierungseinstellungen in einer Reihe von Schritten, damit Sie nicht riskieren, Ihre [!DNL Marketo Measure] -Konto.

Richten Sie die [!DNL Marketo Measure] Anwendung in Ihrem Identitätsanbieter. Weitere Informationen finden Sie in der unten aufgeführten externen Dokumentation.

    a. Wenn Sie nach der Single Sign-On-URL, der Empfänger-URL oder der Ziel-URL, der SAML Assertion Customer Service (ACS)-URL gefragt werden, verwenden Sie [https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest](https://apps.bizible.com/BizibleSAML2/ReceiveSSORequest)
    
    b. Wenn Sie zur URL der Zielgruppenbeschränkung oder zur anwendungsdefinierten eindeutigen Kennung aufgefordert werden, verwenden Sie [https://BizibleLPM](https://biziblelpm/)

Wechseln Sie zur benutzerdefinierten einmaligen Anmeldung im [!DNL Marketo Measure] Anwendung

    a. Sobald die Abrechnungsgruppe für Ihr Konto aktiviert wurde, können Sie jetzt zu [!UICONTROL Einstellungen] >>[!UICONTROL Sicherheit] >> [!UICONTROL Authentifizierung]
    
    b. Standardmäßig ist Ihr Anmeldetyp auf &quot;CRM-Benutzer&quot;eingestellt.
    
    c. Wechseln Sie den Anmeldetyp zu &quot;Benutzerdefinierte SSO&quot;, um den Konfigurationsprozess zu starten.

Füllen Sie die Verbindungseinstellungen für Ihre Identity Provider-Konfiguration aus.

    a. Ihr Identitäts-Provider kann ein IdP-Metadaten-XML-Dokument bereitstellen, das die erforderlichen Konfigurationsfelder abruft. Laden Sie entweder den Inhalt des XML-Dokuments oder füllen Sie die drei unten stehenden Felder aus der Ausgabe aus, die Sie während des Identity Provider-Konfigurationsprozesses erhalten haben. **Sie müssen beide Schritte nicht ausführen.**
    
    i. IdP-URL: Die URL, die [!DNL Marketo Measure] muss auf verweisen, um Ihre Benutzer bei der [!DNL Marketo Measure] Anwendung. Manchmal als &quot;Umleitungs-URL&quot;bezeichnet.
    ii. IdP-Herausgeber: Eine eindeutige Kennung des Identitäts-Providers. Manchmal als &quot;externer Schlüssel&quot;bezeichnet.
    iii. IdP-Zertifikat: ein öffentlicher Schlüssel, der Folgendes ermöglicht: [!DNL Marketo Measure] um die Signatur aller Identity Provider-Antworten zu überprüfen und zu validieren.

Legen Sie die Gültigkeit des Tokens für Ihre Benutzer in Minuten fest.

    a. [!DNL Marketo Measure] erlaubt eine ganze Zahl von 1 bis 1440 Minuten. Nachdem die Sitzungszeit eines Benutzers überschritten wurde, wird der Benutzer abgemeldet, sobald er zu einer neuen Seite navigiert.

Richten Sie Ihre Benutzerattributeinstellungen ein und ordnen Sie sie dem jeweiligen Vornamen, Nachnamen und E-Mail-Adresse zu.

    a. durch Eingabe der SAML-Attribute, [!DNL Marketo Measure] können Ihre Benutzer anhand der weitergeleiteten Informationen erkennen.
    
    i. E-Mail-Attribut: Geben Sie den Attributnamen an, den Ihr Identitäts-Provider für die E-Mail-Adresse des Benutzers verwendet.
    ii. Vorname Attribut: Geben Sie den Attributnamen an, den Ihr Identitätsanbieter für den Vornamen des Benutzers verwendet.
    iii. Nachname-Attribut: Geben Sie den Attributnamen an, den Ihr Identitätsanbieter für den Nachnamen des Benutzers verwendet.
    
    b. Hinweis: Wenn Sie Ihre SAML-Konfiguration jetzt testen, analysieren wir die Attribute E-Mail, Vorname und Nachname , die Sie für diesen Abschnitt verwenden können.

![](assets/single-sign-on-2.png)

Richten Sie Ihre Benutzerrolleneinstellungen ein und ordnen Sie sie den entsprechenden Rollen oder Gruppen zu, die von Ihrem IdP klassifiziert wurden.

    a. Kunden können [!DNL Marketo Measure] Benutzerrollen basierend auf Gruppen, die in ihrem Identitätsanbieter definiert sind. durch Eingabe Ihrer SAML-Attribute, [!DNL Marketo Measure] kann die Rollen und Gruppen Ihres Benutzers [!DNL Marketo Measure] Benutzerberechtigungen. Wir empfehlen dringend, diese Rollen einzurichten, damit Ihre [!DNL Marketo Measure] -Administrator verfügt über ausreichende Berechtigungen, um Ihr Konto zu aktualisieren.
    
    b. Wenn keine Rollen oder Gruppen zugeordnet sind, besteht die Standardeinstellung darin, dass alle Mitarbeiter im Identitätsanbieter über Standardbenutzerzugriff verfügen.
    
    i. [!DNL Marketo Measure] Standardbenutzer: Geben Sie den Rollen- oder Gruppenwert (von Ihrem SSO-Anbieter) für Benutzer an, die schreibgeschützten Zugriff auf die [!DNL Marketo Measure] Anwendung.
    ii. [!DNL Marketo Measure] Kontoadministratorbenutzer: Geben Sie den Rollen- oder Gruppenwert (von Ihrem SSO-Anbieter) für Benutzer an, die Administratorzugriff auf die [!DNL Marketo Measure] Anwendung. Das bedeutet, dass die Rolle Zugriff auf Konfigurationsänderungen und Einstellungen hat, die sich auf Ihr Konto beziehen.
    iii. Sie müssen in Ihrem IdP über ein Attribut mit dem genauen Namen &quot;Gruppen&quot;verfügen, das die Werte enthält, die Sie in den Attributen &quot;Bizible Standard User&quot;oder &quot;Bizible Account Admin User&quot;eingegeben haben.
    
    c. Wenn einer Rolle mehrere Rollen oder Gruppen zugeordnet werden sollen, geben Sie jeden durch ein Komma getrennten Wert ein.

![](assets/single-sign-on-3.png)

Testen der Single Sign-On-Konfiguration

    a. Bevor Sie auf Speichern klicken können, müssen Sie auf die [!UICONTROL SAML-Authentifizierung testen] -Schaltfläche, um zu überprüfen, ob Ihre Einstellungen ordnungsgemäß konfiguriert wurden.
    
    b. Wenn der Fehler &quot;fehlgeschlagen&quot; angezeigt wird, folgen Sie der Nachricht und versuchen Sie es erneut.

![](assets/single-sign-on-4.png)

Speichern Sie Ihre Einstellungen und weisen Sie Ihre Kollegen an, [!UICONTROL Single Sign-On] mit Ihrer neuen benutzerdefinierten Anmelde-URL.

    a. Wichtig: Sobald Sie Ihre neuen Authentifizierungseinstellungen gespeichert haben, kann die Sitzung beendet werden, sobald Sie zu einer neuen Seite navigieren, da Sie die Anmeldung durch CRM-Benutzer deaktiviert und die benutzerdefinierte einmalige Anmeldung aktiviert haben.

![](assets/single-sign-on-5.png)

Probier es aus!

    a. Verwenden Sie Ihre neue benutzerdefinierte Anmelde-URL und versuchen Sie, sich wieder bei der [!DNL Marketo Measure] Anwendung mit Ihren Identity Provider-Anmeldeinformationen.
    
    b. Das Format sieht wie folgt aus: &quot;https://apps.adobe.com/business/[accountName]&quot;
    
    c. Herzlichen Glückwunsch! Sie haben Single Sign-On erfolgreich in der [!DNL Marketo Measure] Bewerbung für Ihr Konto!

![](assets/single-sign-on-6.png)

>[!NOTE]
>
>Nachdem Sie SSO konfiguriert haben, müssen Sie keine Benutzer mehr im [!DNL Marketo Measure] Anwendung. Die Benutzerbereitstellung sollte direkt in Ihrem Identitäts-Provider erfolgen.

## CRM-Benutzer (Erweiterte Einstellungen) {#crm-users-advanced-setup}

Standardmäßig können alle Konten auf die [!DNL Marketo Measure] Anwendung unter Verwendung ihrer CRM-Anmeldeinformationen. Manchmal müssen Kontoinhaber den Zugriff auf bestimmte Rollen beschränken und nicht für alle Benutzer mit einer aktiven CRM-Lizenz öffnen. Das erweiterte Setup ermöglicht die Zuordnung Ihrer CRM-Rollen und -Gruppen zu [!DNL Marketo Measure] Benutzerberechtigungen.

Wenn keine Rollen oder Gruppen zugeordnet sind, besteht die Standardeinstellung darin, dass alle aktiven Lizenzen in Ihrem CRM-System über Standardbenutzerzugriff verfügen.

* [!DNL Marketo Measure] Standardbenutzer: Geben Sie den Rollen- oder Gruppenwert für Benutzer an, die schreibgeschützten Zugriff auf die [!DNL Marketo Measure] Anwendung.
* [!DNL Marketo Measure] Kontoadministratorbenutzer: Geben Sie den Rollen- oder Gruppenwert für Benutzer an, die Administratorzugriff auf die [!DNL Marketo Measure] Anwendung. Das bedeutet, dass die Rolle Zugriff auf Konfigurationsänderungen und Einstellungen hat, die sich auf Ihr Konto beziehen.

Wenn einer Rolle mehrere Rollen oder Gruppen zugeordnet werden sollen, geben Sie jeden Wert durch ein Komma getrennt ein.

**Salesforce-Rollen**

Für [!DNL Salesforce] Rollen, verwenden Sie den Namen jeder Rolle. Alle Rollen finden Sie unter der [!UICONTROL Einrichtung] >[!UICONTROL Benutzer verwalten] >[!UICONTROL Rollen] Menü.

![](assets/6.png)

**Dynamics-Rollen**

Für [!DNL Dynamics] Rollen verwenden Sie den Namen jeder Sicherheitsrolle. Alle Sicherheitsrollen finden Sie unter der [!UICONTROL Einstellungen] >[!UICONTROL Sicherheit] >[!UICONTROL Sicherheitsrollen] Menü.

![](assets/7.png)

![](assets/8.png)

**Google-Benutzer**

Sobald die benutzerdefinierte einmalige Anmeldung eingerichtet wurde, wird die [!UICONTROL Benutzer] -Seite wird aktualisiert und zeigt nur externe Benutzer an, die mit Google-Anmeldungen hinzugefügt wurden. Da alle Benutzer mit Zugriff über die SSO-Konfiguration definiert sind, sind hier weitere externe Benutzer aufgeführt.

![](assets/9.png)

Nur gültig [!DNL Google] -Konten können hinzugefügt werden und müssen eine Benutzerrolle definieren.

## Externe Links {#external-links}

* [Okta](https://developer.okta.com/standards/SAML/setting_up_a_saml_application_in_okta)
* [Ping-Identität](https://docs.pingidentity.com:443/bundle/p1_enterpriseConfigSsoSaml_cas/page/enableAppWithoutURL.html)
* [OneLogin](https://onelogin.service-now.com/support?id=kb_article&amp;sys_id=b2c91143db109700d5505eea4b9619d5)
* [Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-saas-custom-apps)
