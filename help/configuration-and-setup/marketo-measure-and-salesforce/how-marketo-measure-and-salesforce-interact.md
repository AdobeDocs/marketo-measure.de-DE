---
description: Wie [!DNL Marketo Measure] und [!DNL Salesforce] interagieren
title: Wie [!DNL Marketo Measure] und [!DNL Salesforce] interagieren
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 99%

---


# Wie[!DNL Marketo Measure]und[!DNL Salesforce]interagieren {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>Möglicherweise werden in der Dokumentation Anweisungen zu „[!DNL Marketo Measure]“ angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Schauen wir uns einmal die Beziehung zwischen [!DNL Marketo Measure] und Salesforce an.

## Salesforce und [!DNL Marketo Measure]  {#salesforce-and-marketo-measure}

Sobald das [!DNL Marketo Measure] Konto erstellt und [!DNL Salesforce] verbunden ist, beginnt [!DNL Marketo Measure] damit, Marketingdaten in die CRM-Instanz zu pushen, solange das von [!DNL Marketo Measure] verwaltete Paket installiert ist und die Benutzerin bzw. der Benutzer von [!DNL Marketo Measure] Salesforce über Bearbeitungsrechte verfügt.

Wenn Sie das Salesforce-Paket [!DNL Marketo Measure] nicht installiert haben, schreibt [!DNL Marketo Measure] keine Daten in Ihre Salesforce-Instanz.

![ 3](assets/1-3.png)

Standardmäßig exportiert [!DNL Marketo Measure] jedes Mal 200 Einträge pro API-Credit, wenn ein Auftrag Daten an Ihr CRM sendet. Den meisten Kunden bietet dies das optimale Gleichgewicht zwischen den von [!DNL Marketo Measure] verbrauchten API-Credits und den Anforderungen der CPU-Ressourcen im CRM-System. Bei Kundinnen und Kunden mit komplexen CRM-Konfigurationen, wie Workflows und Triggern, kann eine kleinere Batch-Größe die CRM-Leistung möglicherweise jedoch verbessern. Dazu können Kundinnen und Kunden mit [!DNL Marketo Measure] die Batch-Größe für den CRM-Export konfigurieren. Diese Einstellung ist auf der Seite [!UICONTROL Einstellungen] > [!UICONTROL CRM] > [!UICONTROL Allgemein] in der [!DNL Marketo Measure] Web-Anwendung verfügbar. Dort können die Kundinnen und Kunden zwischen Batch-Größen von 200 (Standard), 100, 50 oder 25 wählen.

Einstellung der Exportstapelgröße für ![Marketo Measure CRM in der Web-Anwendung](assets/how-bizible-and-salesforce-interact-2.png)

Beachten Sie bei der Änderung dieser Einstellung, dass kleinere Batch-Größen mehr API-Credits aus Ihrem CRM-System verbrauchen. Es wird empfohlen, die Batch-Größe nur zu reduzieren, wenn in Ihrem CRM-System CPU-Timeouts oder eine hohe CPU-Last auftreten.

## Mit Salesforce verbundene Benutzerberechtigungen {#salesforce-connected-user-permissions}

**Marketo Measure-Administratorberechtigungssatz für dedizierte Benutzende**: Ermöglicht es SFDC-Admins, CRUD-Vorgänge für Marketo Measure-Objekte durchzuführen.

**Berechtigungssatz zum Anzeigen und Bearbeiten konvertierter Leads**: Ermöglicht es Marketo Measure, Leads nach ihrer Konversion in Kontakte zu ergänzen.

**Kontrollkästchen für Salesforce Marketing-Benutzende**: Ermöglicht es Benutzenden, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden.

* Es sind zusätzliche Berechtigungen zum Erstellen und Aktualisieren von Kampagnen in Ihren CRMs erforderlich.

* Wenn ein Touchpoint aus einer Web-Aktivität erstellt wird, muss dieser mit einer Kampagne verknüpft werden. Da Web-Aktivitäten nicht über entsprechende CRM-Kampagnen verfügen, müssen wir eine erstellen, um diese Verknüpfung herzustellen. Dies gilt sowohl für Lead- als auch Opportunity-Touchpoints. Die Berechtigung zum Aktualisieren ist erforderlich, da der von uns verwendete Aufruf „upsert“ lautet. Falls der Eintrag vorhanden ist, wird er aktualisiert, andernfalls wird er erstellt. Dies gilt nur für von uns erstellte Kampagnen.

**Marketo Measure-Standardbenutzende**: Ermöglicht es Benutzenden, Einträge aus Marketo Measure-Objekten zu lesen.

## Salesforce Standard-Objekte und Zugriff {#salesforce-standard-objects-and-access}

Hiermit werden die [!DNL Salesforce]-Standardobjekte, mit denen [!DNL Marketo Measure] interagiert, sowie die benutzerdefinierten Felder aufgelistet, die wir zu diesen Objekten hinzufügen, sobald die Verknüpfung erfolgt und das [!DNL Marketo Measure]-Paket installiert ist. Das vorkonfigurierte [!DNL Marketo Measure] wird NICHT in ein Standard-Objektfeld in [!DNL Salesforce] geschrieben.

**Lead**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>ID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>E-Mail</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Status</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedContactId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ConvertedOpportunityId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsConverted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Website</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Unternehmen</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Account__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**Kontakt**

<table> 
 <tbody> 
  <tr> 
   <th>Felder</th> 
   <th>Standard/Benutzerdefiniert</th> 
   <th>Lesen</th> 
   <th>Schreiben</th> 
  </tr> 
  <tr> 
   <td>Konto</td> 
   <td>Standard</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-Mail</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Erstellungsdatum</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
 </tbody> 
</table>

**Konto**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>ID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Website</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Engagement_Score__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

**Opportunity**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>Name</td>
   <td>Standard</td>
   <td>x</td>
   <td><br></td>
  </tr>
  <tr>
   <td>Konto</td>
   <td>Standard</td>
   <td>x</td>
   <td><br></td>
  </tr>
  <tr>
   <td>ID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsWon</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsClosed</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CloseDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>StageName</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Betrag</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Bizible_Opportunity_Amount__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

**Opportunity – Kontaktrolle**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>ID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>OpportunityId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ContactId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>

<tr>
   <td>IsPrimary</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>Role</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
 </tbody>
</table>

**Kampagne**

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Felder</th> 
   <th>Standard/Benutzerdefiniert</th> 
   <th>Lesen</th> 
   <th>Schreiben</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-Mail</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Status</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDeleted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Unternehmen</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Typ</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>Startdatum</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>EndDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Name</td>
   <td>Standard</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**Kampagnenmitglied**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>ID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CreatedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LastModifiedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsDeleted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>FirstRespondedDate</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>HasResponded</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>ContactId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>LeadID</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>IsConverted</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>CampaignId</td>
   <td>Standard</td>
   <td>x</td>
   <td> </td>
  </tr>
  <tr>
   <td>bizible2__Bizible_Touchpoint_Date__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Date__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Contact__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Leade__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Status_Opportunity__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>Um die Genauigkeit der Erfassung von Löschereignissen durch Marketo Measure innerhalb Ihres Salesforce-Kontos sicherzustellen, sind replizierbare Berechtigungen für die folgenden Objekte erforderlich. Replizierbare Berechtigungen werden standardmäßig mit den folgenden Objekten bereitgestellt:
> Konto
> Kampagne
> Kampagnenmitglied
> Kontakt
> Veranstaltung
> Lead
> Opportunity
> Aufgabe

## Benutzerdefinierte [!DNL Marketo Measure]-Objekte in [!DNL Salesforce]  {#marketo-measure-custom-objects-in-salesforce}

Neben der Erstellung von benutzerdefinierten Feldern in den Standardobjekten von SFDC werden nach der Installation des [!DNL Marketo Measure]-Pakets eine Reihe von benutzerdefinierten Objekten erstellt. Es folgt eine Liste dieser benutzerdefinierten Objekte zusammen mit einer Tabelle, in der die Felder angegeben sind, in die [!DNL Marketo Measure] schreiben wird.

**Buyer Touchpoint**

Der Buyer Touchpoint ist ein benutzerdefiniertes [!DNL Marketo Measure]-Objekt, mit dem die Marketing-Interaktionen für Kontakte, Leads und Fälle eingeschlossen werden können.

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>bizible2__Bizible_Person__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__SF_Campaign__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel_Path__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Type__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Content__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Platform__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Browser__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_City__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Country__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Region__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_MatchType__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Position__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Text__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Medium__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Search_Phrase__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Date__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Source__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Segment__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_First_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Lead_Creation_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_U_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Destination_URL__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Case__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

**[!DNL Marketo Measure]-Person**

Die [!DNL Marketo Measure]-Person ist ein benutzerdefiniertes [!DNL Marketo Measure]-Objekt, das sowohl mit dem Lead- sowie mit dem Kontakt- und dem Fall-Objekt verknüpft ist.

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Lead__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Case__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x </td>
  </tr>
 </tbody>
</table>

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Der Buyer Attribution Touchpoint ist ein benutzerdefiniertes [!DNL Marketo Measure]-Objekt, mit dem der Einfluss des Marketings auf Opportunitys eingeschlossen werden kann.

**Buyer Attribution Touchpoint**

<table>
 <tbody>
  <tr>
   <th>Felder</th>
   <th>Standard/Benutzerdefiniert</th>
   <th>Lesen</th>
   <th>Schreiben</th>
  </tr>
  <tr>
   <td>bizible2__Account__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__SF_Campaign__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Contact__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Opportunity__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__UniqueId__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Marketing_Channel_Path__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Type__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Content__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Group_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Campaign_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Placement_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Site_Name__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Form_URL_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Platform__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Browser__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_City__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Country__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Geo_Region__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Id__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_MatchType__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Position__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Keyword_Text__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Landing_Page_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Medium__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Referrer_Page_Raw__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Search_Phrase__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Date__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Touchpoint_Source__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Segment__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_First_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Lead_Conversion_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_U_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_W_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Custom_Model__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Attribution_Custom_Model_2__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_First_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Lead_Creation_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_U_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_W_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Custom_Model__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Count_Custom_Model_2__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Ad_Destination_URL__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_First_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Lead_Creation_Touch__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_U_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_W_Shaped__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Custom_Model__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
  <tr>
   <td>bizible2__Revenue_Custom_Model_2__c</td>
   <td>Benutzerdefiniert</td>
   <td>x</td>
   <td>x</td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>[Überblick über Integrationsberechtigungen](/help/api-connections/integration-permissions-overview.md){target="_blank"}
