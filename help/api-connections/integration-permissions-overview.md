---
description: Übersicht über Integrationsberechtigungen - [!DNL Marketo Measure]
title: Überblick über Integrationsberechtigungen
feature: APIs, Integration
exl-id: c45598fe-0c33-459a-9fde-de7f6906bd0c
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 3%

---


# Überblick über Integrationsberechtigungen {#integration-permissions-overview}

In diesem Handbuch werden die erforderlichen Berechtigungen für eine nahtlose Integration mit Marketo Measure beschrieben, um sicherzustellen, dass jede Integration effektiv und ohne Probleme funktioniert.

<table>
<thead>
  <tr>
    <th style="width:10%">Integration</th>
    <th style="width:25%">Datentyp
    <li>Web-Interaktionsdaten</li>
    <li>B2B-Systemdaten</li>
    <li>Anzeigen von Platform-Daten</li></th>
    <th style="width:25%">Was wir verfolgen</th>
    <th style="width:40%">Berechtigungsanforderungen</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B-Systemdaten  
</td>
    <td>Marketo Measure verfolgt:
    <p>
    <li>Konto</li>
    <li>Kampagne</li>
    <li>Kampagnenmitglied</li>
    <li>Kontakt</li>
    <li>currencyConversionRange</li>
    <li>currencyStatus</li>
    <li>Ereignisse</li>
    <li>FieldHistory (Lead, Kontakt und Opportunity)</li>
    <li>Lead</li>
    <li>Opportunity</li>
    <li>OpportunityContactRole</li>
    <li>OpportunityHistory</li>
    <li>Aufgaben</li>
<p>
Erstellte Touchpoints und andere Daten werden in benutzerdefinierte Bizible-Felder für Konto, Kampagne, Kampagnenmitglied, Fall, Kontakt, Lead und Opportunity geschrieben.</td>
    <td><b>Benutzerberechtigungen für Salesforce Connected (erforderlich)</b>
    <p>
    <b>Marketo Measure-Administratorberechtigungssatz für dedizierten Benutzer: </b> SFDC-Admins ermöglichen, CRUD-Vorgänge für Marketo-Messobjekte durchzuführen.
    <br>
    <b>Berechtigungssatz zum Anzeigen und Bearbeiten konvertierter Leads:</b> Dadurch kann Marketo Measure Leads dekorieren, nachdem sie in Kontakte konvertiert wurden.
    <br>
    <b>Kontrollkästchen für Salesforce-Marketing-Benutzer:</b> Das Kontrollkästchen für Marketing-Benutzer ermöglicht Benutzern das Erstellen von Kampagnen und die Verwendung der Kampagnenimport-Assistenten.
    <br>
    <b>Marketo Measure-Standardbenutzer:</b> Ermöglicht einem Benutzer das Lesen von Datensätzen aus Marketo Measure-Objekten.
    <p>
    <b>Salesforce-Standardfeldberechtigungen</b>
    <br>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce-Standardobjekte und -Zugriff</a>
    <p>
    <b>Benutzerdefinierte Salesforce-Feldberechtigungen</b>
    <br>
    Wir bieten Funktionseinstellungen für benutzerdefinierte Salesforce-Felder, die Kunden verwenden können. Wenn diese Funktionseinstellungen definiert sind, benötigen wir LESEZUGRIFF auf jedes der Salesforce-Felder, die in der Funktionseinstellung gespeichert sind (wenn z. B. der Wert für die Einstellung „CustomLeadSourceField“ gleich „LeadSource__c“ ist, benötigen wir LESEZUGRIFF auf dieses Feld).
    </td>
  </tr>
  <tr>
    <td>Dynamics</td>
    <td>B2B-Systemdaten</td>
    <td>Marketo Measure verfolgt:
    <p>
    <li>Konto
<li>Aktivitätspartei
<li>ActivityPointer
<li>Kampagne
<li>CampaignItem (CampaignList in Ihrem System)
<li>CampaignResponse (CampaignMember in unserem System)
<li>Kontakt
<li>Lead
<li>Liste (MarketingList in Ihrem System)
<li>ListMember (MarketingListMember in unserem System)
<li>Opportunity
<li>Organisation
<li>TransactionCurrency (CurrencyConversionRange und CurrencyStatus in Ihrem System)
<li>Termin, Kampagnenaktivität, E-Mail, Fax, Incident-Lösung, Brief, Telefonanruf, RecurringAppointmentMaster, ServiceAppointment, Aufgabe
<li>bizible2_bizible_abtest
<li>Bizible2_Bizible_Attribution_Touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>Bizible2_Bizible_Touchpoint
<p>
Erstellte Touchpoints und andere Daten werden in benutzerdefinierte Bizible-Felder für Konto, Kampagne, CampaignResponse, Kontakt, Lead, Liste, Opportunity und Telefonanruf geschrieben</td>
    <td><b>Marketo Measure-Benutzerberechtigungen</b>
<br>
Es wird empfohlen, in Dynamics einen dedizierten Marketo Measure-Benutzer zu erstellen, über den Daten exportiert und importiert werden können, um Probleme mit anderen Benutzern in Ihrem CRM zu vermeiden. Notieren Sie sich den Benutzernamen und das Kennwort sowie die Endpunkt-URL, da diese beim Erstellen des Marketo Measure-Kontos verwendet wird.
<p>
<b>Sicherheitsrollen</b>
<br>
Wenn Ihr Unternehmen Dynamics-Sicherheitsrollen verwendet, stellen Sie sicher, dass der verbundene Benutzer oder der dedizierte Marketo Measure-Benutzer über ausreichende Lese-/Schreibberechtigungen für die erforderlichen Entitäten verfügt.
<br>
Sicherheitsrollen befinden sich hier: Einstellungen &gt; Sicherheit &gt; Sicherheitsrollen
<br>
Für benutzerdefinierte Marketo Measure-Entitäten benötigen wir vollständige Berechtigungen für alle unsere Entitäten.
<p>
<b>Dynamics-Standardfeldberechtigungen</b>
<br>
<a href="/help/marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Marketo Measure Dynamics-</a>
<p>
<b>Benutzerdefinierte Dynamics-Feldberechtigungen</b>
<br>
Wir benötigen LESEZUGRIFF für alle Felder in der Lead- oder Kontaktentität, die der Kunde für benutzerdefinierte Regeln zum Unterdrücken/Entfernen von Touchpoint-Einstellungen verwenden möchte.
<br>
Wir benötigen LESEZUGRIFF für jedes Feld in der Lead- oder Opportunity-Entität, das der Kunde für Segmentregeln oder das Staging-Mapping verwenden möchte.
<br>
Wir benötigen LESEZUGRIFF für alle Felder der Entitäten „Kampagne“, „CampaignResponse“ und „Liste“, die der Kunde zum Synchronisieren von Kampagnen-/MarketingList-Mitgliedern verwenden möchte.
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>Anzeigen von Platform-Daten</td>
    <td>Wir integrieren mit Facebook, um:
<p>
<li>Kunden-Anzeigendaten importieren</li>
<li>Importieren von Kostendaten für Kundenanzeigen</li>
<li>Aktualisieren von Client-Anzeigen durch Anhängen von URL-Parametern</li>
<p>
Marketo Measure verfolgt Konten, Kampagnen, Anzeigengruppen, Anzeigen, Filter-IDs und URLs.</td>
    <td><li>Die Berechtigung ads_management ist erforderlich, um Kampagnen zu erstellen, Anzeigen zu verwalten oder Anzeigenmetriken abzurufen.</li>
<li>Die E-Mail-Berechtigung ist erforderlich, damit sich Benutzer bei ihrer Facebook-E-Mail anmelden können.</li>
<p>
<b>Bereiche</b>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/">ads_management</a>
<br>
<li>Programmgesteuertes Erstellen von Kampagnen, Verwalten von Anzeigen und Abrufen von Metriken.</li>
<li>Entwickeln Sie Tools für das Anzeigenmanagement, die innovative Lösungen und einen einzigartigen Mehrwert für Werbetreibende bieten.</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email">email</a>
<br>
<li>Mit Personen kommunizieren und sie sich mit der mit ihrem Facebook-Profil verknüpften E-Mail-Adresse bei Ihrer App anmelden lassen.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>Anzeigen von Platform-Daten
    <p>
    B2B-Systemdaten (Lead-Gen-Formulardaten, einschließlich Formularen und Übermittlungen, die als CRM-Aktivität kategorisiert sind).</td>
    <td>Marketo Measure verfolgt LinkedIn-Werbekampagnen, Kreative und Kostendaten sowie Lead-Gen-Forms und -Antworten. Basierend auf importierten Daten können wir LinkedIn-Touchpoints generieren und Lead-Formular-Antworten für Kunden Leads zuordnen.</td>
    <td><li>Die Rolle des Kampagnen-Managers oder des Konto-Managers ist erforderlich, damit Marketo Measure Kostendaten herunterladen kann. (Scope Row 1)</li>
    <br>
    <li>Für den Zugriff von Marketo Measure auf Lead-Gen-Formulardaten ist ein Superadministrator (Seitenadministratorrolle, Bereichszeile 2) oder Lead-Gen-Forms-Manager (Paid-Media-Administratorrolle, Bereichszeile 3) erforderlich</li>
    <br>
    <li>Superadmin (Seitenadministratorrolle, Bereichszeile 2) oder Sponsored Content Poster (Paid Media-Administratorrolle, Bereichszeile 3) ist erforderlich, damit Marketo Measure das automatische Tagging bearbeiten kann</li>
    <p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts">Benutzerrolle im Portal einrichten (Anmeldung beim LinkedIn-Konto erforderlich)</a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager">Benutzerrollen - Übersicht</a>: Benutzerrolle, Benutzerberechtigung anzeigen und verwalten, Rollen wie Konto-Manager oder Kampagnen-Manager zuweisen
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">Einrichten der Seitenadministratorrolle - <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview">Seitenadministratorrollendefinitionen</a>: Seitenadministratorrolle, auf der gewünschten Administratorseite
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en">Paid-Media-Administratorrolle einrichten (nach Paid-Media-Administrator suchen) - <a href="https://www.linkedin.com/help/linkedin/answer/a554540">Paid-Media-Administratordefinitionen</a>: Paid-Media-Administratorrollen</td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td>Anzeigen von Platform-Daten</td>
    <td>Marketo Measure verfolgt Konten, Werbetreibende, Kampagnen, (benutzerdefinierte) Landingpages, Anzeigen, Kreative, Platzierungen und Websites.</td>
    <td><li>Die primäre E-Mail-Adresse des Google-Kontos des Benutzers ist erforderlich</li>
<li>Für den Zugriff auf das Campaign Manager 360-Konto erforderliche Campaign Manager-Berechtigungen</li>
<ul>
<li>Anzeigen und Verwalten von DoubleClick Advertisers-Berichten</li>
<li>Anzeigen und Verwalten von DoubleClick Campaign Managers Anzeigen-Kampagnen</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: Siehe die E-Mail-Adresse Ihres primären Google-Kontos
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting">https://www.googleapis.com/auth/dfareporting</a>: Anzeigen und Verwalten von DoubleClick für Advertisers-Berichte
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking">https://www.googleapis.com/auth/dfatrafficking</a>: Anzeigen-Anzeigekampagnen des DoubleClick Campaign Managers (DCM) anzeigen und verwalten</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>Anzeigen von Platform-Daten</td>
    <td>Wir integrieren mit AdWords für:
<p>
<li>Kunden-Anzeigendaten importieren</li>
<li>Importieren von Kostendaten für Kundenanzeigen</li>
<li>Aktualisieren von Client-Anzeigen durch Anhängen von URL-Parametern/Aktualisieren von URL-Tracking-Vorlagen</li>
<p>
Marketo Measure verfolgt Kampagnen, Anzeigengruppen, Kreative, Site-Links und Schlüsselwörter.</td>
    <td><li>Die primäre E-Mail-Adresse des Google-Kontos des Benutzers ist erforderlich</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email">https://www.googleapis.com/auth/userinfo.email</a>: Siehe die E-Mail-Adresse Ihres primären Google-Kontos</td>
  </tr>
  <tr>
    <td>Bing</td>
    <td>Anzeigen von Platform-Daten</td>
    <td>Marketo Measure verfolgt Konten, Kampagnen, Anzeigengruppen, Kreative und Schlüsselwörter.</td>
    <td><li>Der Benutzer muss über sein Microsoft-Konto „Offline-Zugriff“ gewähren (wodurch Marketo Measure Zugriff auf die UserInfo des Endbenutzers gewährt wird, auch wenn dieser nicht angemeldet ist). Informationen hierzu finden Sie auf <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access"> Seite von </a>Microsoft.</li>
<p>
    <b>Bereiche</b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access">https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access</a>: Behalten Sie den Zugriff auf Daten bei, denen Sie Zugriff auf die Berechtigung erteilt haben.</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B-Systemdaten</td>
    <td>Durch die Marketo-Integration kann Marketo Measure Aktivitäten, Personen, Programme und Programmmitgliedschaften für Marketo erfassen. Darüber hinaus verfolgt Marketo Measure Marketo-Cookies (Munchkin-IDs), um Marketo-Web-Aktivitäten mit Marketo Measure-Lead-Touchpoints zu verknüpfen <a href="/help/marketo-measure-and-marketo/marketo-engage-programs-integration.md#cookie-mapping">wie hier beschrieben</a>:
    <p>
    <i>Aufgrund der Integration von Marketo Measure mit Marketo wird die Marketo Measure-Cookie-ID jetzt auch der Marketo-Munchkin-ID zugeordnet und mit dieser synchronisiert. Auf diese Weise wird die Lücke geschlossen, sodass der anonyme Erstkontakt einer Web-Sitzung zugeordnet werden kann, anstatt sowohl die FT- als auch die LC-Kontakte einer Marketo-Aktivität zuzuordnen.</i>
    </td>
    <td>Der Kunde muss einen dedizierten Marketo Engage-API-Benutzer erstellen und die Anmeldeinformationen für Marketo Measure bereitstellen. Es ist keine zusätzliche Berechtigungskonfiguration erforderlich. <a href="/help/marketo-measure-and-marketo/set-up-marketo-connection.md#configuring-the-integration">Weitere Informationen</a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B-Systemdaten</td>
    <td>Die Integration von B2B-Kundenattributen ermöglicht es gemeinsamen Benutzenden von Marketo Measure und Adobe Analytics, ihre Adobe Analytics-Benutzerprofile mit wertvollen Metadaten anzureichern, die von der Marketo Measure-Attributionsmaschine und durch ihre Synchronisierungsfunktion mit CRMs (Microsoft Dynamics und Salesforce) abgeleitet wurden. <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Weitere Informationen</a>.</td>
    <td>Der Kunde muss Marketo Measure eine Alias-ID und FTP-Server-Anmeldeinformationen für einen Speicherort bereitstellen, an den Daten in seine Analytics-Instanz hochgeladen werden.
    <p>
    Beachten Sie die folgenden Informationen, da Sie sie für einige der späteren Schritte im Prozess benötigen werden:
    <p>
    <li>Die Alias-ID. Dabei kann es sich um einen beliebigen Wert handeln. Wir empfehlen „marketomeasure_id“</li>
    <li>Der Host-Name und die Anmeldeinformationen des FTP-Servers (Benutzername und Kennwort)</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">Weitere Informationen</a></td>
  </tr>
  <tr>
    <td>Bizible JavaScript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/data-collected-by-javascript.md">Welche Daten erfasst Bizible.js</a>.</td>
    <td></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
