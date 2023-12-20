---
description: Übersicht über Integrationsberechtigungen - [!DNL Marketo Measure] - Produktdokumentation
title: Übersicht über Integrationsberechtigungen
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 9196877384140d60a22012b43ea960017528f4d5
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 4%

---

# Übersicht über Integrationsberechtigungen {#integration-permissions-overview}

In diesem Handbuch werden die erforderlichen Berechtigungen für die nahtlose Integration mit Marketo Measure beschrieben, um sicherzustellen, dass jede Integration effektiv und problemlos funktioniert.

<table>
<thead>
  <tr>
    <th style="width:10%">Integration</th>
    <th style="width:20%">Datentyp
    <li>Web-Interaktionsdaten</li>
    <li>B2B-Systemdaten</li>
    <li>Anzeigenplattformdaten</li></th>
    <th style="width:30%">Was wir verfolgen</th>
    <th style="width:40%">Berechtigungsanforderungen</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B-Systemdaten    
</td>
    <td>Marketo Measure verfolgt Folgendes:
    <br>
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
<br>
Die erstellten Touchpoints und andere Daten werden in benutzerdefinierte bizible Felder in Konto, Kampagne, CampaignMember, Case, Contact, Lead und Opportunity geschrieben.</td>
    <td><b>Salesforce-Benutzerberechtigungen (erforderlich)</b>
    <br>
    <b>Marketo Measure-Administratorberechtigungssatz für dedizierte Benutzer:</b> Erlauben Sie dem SFDC-Administrator, CRUD-Vorgänge auf Marketo durchzuführen, um Objekte zu messen.
    <br>
    <b>Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten:</b> Dadurch kann Marketo Measure Leads dekorieren, nachdem sie in Kontakte konvertiert wurden.
    <br>
    <b>Salesforce Marketing User Checkbox:</b> Über das Kontrollkästchen Marketing-Benutzer können Benutzer Kampagnen erstellen und die Assistenten zum Importieren von Kampagnen verwenden.
    <br>
    <b>Marketo Measure Standard-Benutzer:</b> Ermöglicht dem Benutzer das Lesen von Datensätzen aus Marketo Measure-Objekten.
    <p>
    <b>Salesforce Standard-Feldberechtigungen</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce-Standardobjekte und Zugriff</a>
    <p>
    <b>Berechtigungen für benutzerdefinierte Salesforce-Felder</b>
    <br>
    Wir bieten Funktionseinstellungen für benutzerdefinierte Salesforce-Felder, die Kunden verwenden können. Wenn diese Funktionseinstellungen definiert sind, benötigen wir READ-Zugriff auf jedes Salesforce-Feld, das in der Funktionseinstellung gespeichert wurde (wenn z. B. der Wert der Einstellung CustomLeadSourceField gleich "LeadSource__c"ist, benötigen wir READ-Zugriff auf dieses Feld).
    </td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
