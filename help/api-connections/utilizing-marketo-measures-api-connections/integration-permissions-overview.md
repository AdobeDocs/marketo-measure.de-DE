---
description: Übersicht über Integrationsberechtigungen - [!DNL Marketo Measure]
title: Überblick über Integrationsberechtigungen
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Überblick über Integrationsberechtigungen {#integration-permissions-overview}

In diesem Handbuch werden die erforderlichen Berechtigungen für die nahtlose Integration mit Marketo Measure beschrieben, um sicherzustellen, dass jede Integration effektiv und problemlos funktioniert.

<table>
<thead>
  <tr>
    <th style="width:10%">Integration</th>
    <th style="width:25%">Datentyp
    <li>Web-Interaktionsdaten</li>
    <li>B2B-Systemdaten</li>
    <li>Anzeigenplattformdaten</li></th>
    <th style="width:25%">Was wir verfolgen</th>
    <th style="width:40%">Berechtigungsanforderungen</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B-Systemdaten    
</td>
    <td>Marketo Measure verfolgt Folgendes:
    <p>
    <li>Konto</li>
    <li>Kampagne</li>
    <li>CampaignMember</li>
    <li>Kontakt</li>
    <li>CurrencyConversionRange</li>
    <li>CurrencyStatus</li>
    <li>Ereignisse</li>
    <li>FieldHistory (Lead, Kontakt und Chancen)</li>
    <li>Lead</li>
    <li>Opportunity</li>
    <li>OpportunityContactRole</li>
    <li>OpportunityHistory</li>
    <li>Aufgaben</li>
<p>
Die erstellten Touchpoints und andere Daten werden in benutzerdefinierte bizible Felder in Konto, Kampagne, CampaignMember, Case, Contact, Lead und Opportunity geschrieben.</td>
    <td><b>Salesforce Connected User Permissions (erforderlich)</b>
    <p>
    <b>Marketo Measure-Administratorberechtigungssatz für dedizierte Benutzer:</b> Erlauben Sie dem SFDC-Administrator, CRUD-Vorgänge auf Marketo durchzuführen, um Objekte zu messen.
    <br>
    <b>Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten:</b> Dadurch kann Marketo Measure Leads dekorieren, nachdem sie in Kontakte konvertiert wurden.
    <br>
    <b>Salesforce Marketing User Checkbox:</b> Über das Kontrollkästchen Marketing-Benutzer können Benutzer Kampagnen erstellen und die Assistenten zum Importieren von Kampagnen verwenden.
    <br>
    <b>Marketo Measure Standard-Benutzer:</b> Ermöglicht dem Benutzer das Lesen von Datensätzen aus Marketo Measure-Objekten.
    <p>
    <b>Salesforce Standard-Feldberechtigungen</b>
    <br>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce-Standardobjekte und Zugriff</a>
    <p>
    <b>Berechtigungen für benutzerdefinierte Salesforce-Felder</b>
    <br>
    Wir bieten Funktionseinstellungen für benutzerdefinierte Salesforce-Felder, die Kunden verwenden können. Wenn diese Funktionseinstellungen definiert sind, benötigen wir READ-Zugriff auf jedes Salesforce-Feld, das in der Funktionseinstellung gespeichert wurde (wenn z. B. der Wert der Einstellung CustomLeadSourceField gleich "LeadSource__c"ist, benötigen wir READ-Zugriff auf dieses Feld).
    </td>
  </tr>
  <tr>
    <td>Dynamics</td>
    <td>B2B-Systemdaten</td>
    <td>Marketo Measure verfolgt Folgendes:
    <p>
    <li>Konto
<li>ActivityParty
<li>ActivityPointer
<li>Kampagne
<li>CampaignItem (CampaignList in unserem System)
<li>CampaignResponse (CampaignMember in unserem System)
<li>Kontakt
<li>Lead
<li>List (MarketingList in unserem System)
<li>ListMember (MarketingListMember in unserem System)
<li>Opportunity
<li>Organisation
<li>TransactionCurrency (CurrencyConversionRange und CurrencyStatus in unserem System)
<li>Termin, CampaignActivity, E-Mail, Fax, IncidentResolution, Brief, PhoneCall, RecurringAppointingMaster, ServiceAppointing, Task
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
Die erstellten Touchpoints und andere Daten werden in benutzerdefinierte bizible Felder in Konto, Kampagne, CampaignResponse, Kontakt, Lead, Liste, Chancen und PhoneCall geschrieben.</td>
    <td><b>Marketo Measure-Benutzerberechtigungen</b>
<br>
Es wird empfohlen, in Dynamics einen dedizierten Marketo Measure-Benutzer zu erstellen, über den Daten exportiert und importiert werden können, um Probleme mit anderen Benutzern in Ihrem CRM-System zu vermeiden. Notieren Sie sich den Benutzernamen und das Kennwort sowie die Endpunkt-URL, da diese bei der Erstellung des Marketo Measure-Kontos verwendet wird.
<p>
<b>Sicherheitsrollen</b>
<br>
Wenn Ihr Unternehmen Dynamics-Sicherheitsrollen verwendet, stellen Sie sicher, dass der verbundene Benutzer oder der dedizierte Marketo Measure-Benutzer über ausreichende Lese-/Schreibberechtigungen für die erforderlichen Entitäten verfügt.
<br>
Sicherheitsrollen finden Sie hier: Einstellungen &gt; Sicherheit &gt; Sicherheitsrollen .
<br>
Für benutzerdefinierte Marketo Measure-Entitäten benötigen wir vollständige Berechtigungen für alle unsere Entitäten.
<p>
<b>Feldberechtigungen in Dynamics Standard</b>
<br>
<a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Marketo Measure Dynamics-Schema</a>
<p>
<b>Benutzerdefinierte Feldberechtigungen in Dynamics</b>
<br>
Wir benötigen LESE-Zugriff für jedes Feld in der Lead- oder Kontaktentität, das der Kunde für benutzerdefinierte Regeln für die Unterdrücken/Entfernen von Touchpoint-Einstellungen verwenden möchte.
<br>
Wir benötigen LESE-Zugriff für jedes Feld in der Lead- oder Opportunity-Entität, das der Kunde für Segmentregeln oder Staging-Mapping verwenden möchte.
<br>
Wir benötigen LESE-Zugriff für jedes Feld in den Kampagnen-, CampaignResponse- und List-Entitäten, die der Kunde für die Synchronisierung von Campaign-/MarketingList-Mitgliedern verwenden möchte.
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>Anzeigenplattformdaten</td>
    <td>Die Integration mit Facebook erfolgt in:
<p>
<li>Importieren von Kundenanzeigendaten</li>
<li>Importieren von Kundenwerbungskosten</li>
<li>Aktualisieren der Anzeigen des Kunden durch Anhängen von URL-Parametern</li>
<p>
Marketo Measure verfolgt Konten, Kampagnen, Anzeigengruppen, Anzeigen, Filter-IDs und URLs.</td>
    <td><li>Die Berechtigung ads_management ist erforderlich, um Kampagnen zu erstellen, Anzeigen zu verwalten oder Anzeigenmetriken abzurufen.</li>
<li>Die E-Mail-Berechtigung ist erforderlich, damit sich Benutzer in ihrer Facebook-E-Mail anmelden können.</li>
<p>
<b>Bereiche</b>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>Programmgesteuerte Erstellung von Kampagnen, Verwaltung von Anzeigen und Abrufen von Metriken.</li>
<li>Erstellen Sie Tools für das Anzeigen-Management, die innovative Lösungen und einen differenzierten Nutzen für Advertiser bieten.</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email">email</a>
<br>
<li>Kommunikation mit Personen und deren Anmeldung bei der App mit der mit ihrem Facebook-Profil verknüpften E-Mail-Adresse.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>Anzeigenplattformdaten
    <p>
    B2B-Systemdaten (Lead Gen-Formulardaten, einschließlich Formularen und Übermittlungen, die als CRM-Aktivität kategorisiert sind).</td>
    <td>Marketo Measure verfolgt LinkedIn Ads-Kampagnen, Kreative und Kostendaten sowie Lead Gen Forms und Antworten. Basierend auf importierten Daten können wir LinkedIn-Touchpoints generieren und Lead-Formular-Antworten für Kunden mit Leads verknüpfen.</td>
    <td><li>Die Rolle "Kampagnenmanager"oder "Kundenbetreuer"ist erforderlich, damit Marketo Measure Kostendaten herunterladen kann. (Zeile 1 des Anwendungsbereichs)</li>
    <br>
    <li>Für den Zugriff auf Lead-Generieren-Formulardaten ist "Super Admin"(Seitenadministratorrolle, Tabellenzeile 2) oder "Lead Gen Forms Manager"(Paid Media-Administratorrolle, Scopes-Zeile 3) erforderlich, damit Marketo Measure auf Lead-Forms-Daten zugreifen kann</li>
    <br>
    <li>Für die Bearbeitung des automatischen Tagging durch Marketo Measure ist "Super Admin"(Seitenadministratorrolle, Scopes-Zeile 2) oder "Sponsored Content Poster"(Paid Media-Administratorrolle, Scopes-Zeile 3) erforderlich.</li>
    <p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts">Einrichten der Benutzerrolle im Portal (Anmeldung beim LinkedIn-Konto erforderlich)</a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager">Überblick über Benutzerrollen</a>: Benutzerrolle, Benutzerberechtigungen anzeigen und verwalten, Rollen wie Kundenbetreuer oder Kampagnenmanager zuweisen
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">Einrichten der Seitenadministratorrolle - <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview">Seitenadministratorrollendefinitionen</a>: Seitenadmin-Rolle auf der gewünschten Admin-Seite
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">Paid Media-Administratorrolle einrichten (suchen Sie nach Paid Media-Admin ) - <a href="https://www.linkedin.com/help/linkedin/answer/a554540">Definitionen für gebührenpflichtige Medien</a>: Paid Media-Administratorrollen</td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td>Anzeigenplattformdaten</td>
    <td>Marketo Measure verfolgt Konten, Advertiser, Kampagnen, (benutzerdefinierte) Landingpages, Anzeigen, Kreative, Platzierungen und Sites.</td>
    <td><li>Die primäre E-Mail-Adresse des Google-Kontos ist erforderlich.</li>
<li>Für den Zugriff auf das Campaign Manager 360-Konto erforderliche Campaign Manager-Berechtigungen</li>
<ul>
<li>Anzeigen und Verwalten von DoubleClick-Advertiser-Berichten</li>
<li>Anzeigen und Verwalten von Display-Anzeigenkampagnen für DoubleClick Campaign-Manager</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: Siehe Ihre primäre Google-Konto-E-Mail-Adresse
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting">https://www.googleapis.com/auth/dfareporting</a>: Anzeigen und Verwalten von DoubleClick for Advertisers-Berichten
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking">https://www.googleapis.com/auth/dfatrafficking</a>: Zeigen Sie die Display-Anzeigenkampagnen (DCM) Ihres DoubleClick Campaign Managers an und verwalten Sie sie.</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>Anzeigenplattformdaten</td>
    <td>Die Integration mit AdWords erfolgt in:
<p>
<li>Importieren von Kundenanzeigendaten</li>
<li>Importieren von Kundenwerbungskosten</li>
<li>Aktualisieren der Anzeigen des Kunden durch Anhängen von URL-Parametern/Aktualisieren von URL-Tracking-Vorlagen</li>
<p>
Marketo Measure verfolgt Kampagnen, Anzeigengruppen, Kreative, Site-Links und Suchbegriffe.</td>
    <td><li>Die primäre E-Mail-Adresse des Google-Kontos ist erforderlich.</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: Siehe Ihre primäre Google-Konto-E-Mail-Adresse</td>
  </tr>
  <tr>
    <td>Bing</td>
    <td>Anzeigenplattformdaten</td>
    <td>Marketo Measure verfolgt Konten, Kampagnen, Anzeigengruppen, Kreative und Suchbegriffe.</td>
    <td><li>Der Benutzer muss über sein Microsoft-Konto "Offline-Zugriff"gewähren (das Marketo Measure Zugriff auf die UserInfo des Endbenutzers gewährt, auch wenn er nicht angemeldet ist). Siehe <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">Microsoft-Seite</a> wie dies zu tun ist.</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access</a>: Beibehalten des Zugriffs auf die Daten, die Sie ihm Zugriff auf die Berechtigung gewährt haben.</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B-Systemdaten</td>
    <td>Durch die Marketo-Integration kann Marketo Measure Marketo-Aktivitäten, Personen, Programme und Programmmitgliedschaften erfassen. Darüber hinaus verfolgt Marketo Measure Marketo-Cookies (Munchkin-IDs), um Marketo-Web-Aktivitäten mit Lead-Touchpoints von Marketo Measure zu verknüpfen. <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#cookie-mapping">wie hier beschrieben</a>:
    <p>
    <i>Aufgrund der Marketo Measure-Integration mit Marketo wird jetzt auch die Marketo Measure-Cookie-ID zugeordnet und mit der Marketo Munchkin-ID synchronisiert. Dies hilft, die Lücke zu schließen, um den anonymen Erstkontakt einer Web-Sitzung zuzuordnen, anstatt sowohl FT- als auch LC-Touches einer Marketo-Aktivität zuzuordnen.</i>
    </td>
    <td>Der Kunde muss einen dedizierten Marketo Engage-API-Benutzer erstellen und die Anmeldeinformationen an Marketo Measure übermitteln. Es ist keine zusätzliche Berechtigungskonfiguration erforderlich. <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md#configuring-the-integration">Weitere Infos</a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B-Systemdaten</td>
    <td>Die Integration von B2B-Kundenattributen ermöglicht es den Anwendern von Marketo Measure und Adobe Analytics, ihre Adobe Analytics-Benutzerprofile mit wertvollen Metadaten anzureichern, die von der Marketo Measure-Attributionsmodul abgeleitet wurden, sowie über die Synchronisierungsfunktion mit CRMs (Microsoft Dynamics und Salesforce). <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Weitere Infos</a>.</td>
    <td>Der Kunde muss Marketo Measure die Anmeldedaten für Alias-ID und FTP-Server an einem Speicherort bereitstellen, an den Daten in seine Analytics-Instanz hochgeladen werden.
    <p>
    Beachten Sie die folgenden Informationen, da Sie sie für einige der späteren Schritte im Prozess benötigen:
    <p>
    <li>Die Alias-ID, bei der es sich um einen beliebigen Wert handeln kann, den Sie benötigen. Wir empfehlen "marketomeasure_id"</li>
    <li>Der Hostname und die Anmeldeinformationen des FTP-Servers (Benutzername und Kennwort)</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">Weitere Informationen</a></td>
  </tr>
  <tr>
    <td>Bizible JavaScript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/setting-up-tracking/data-collected-by-javascript.md">Welche Daten werden von bizible.js erfasst?</a>.</td>
    <td></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
