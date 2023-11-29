---
description: „[!DNL Marketo Measure] Ultimate-Datenintegritätsanforderung - [!DNL Marketo Measure] - Produktdokumentation“
title: „[!DNL Marketo Measure] Ultimate-Datenintegritätsanforderung
feature: Integration, Tracking, Attribution
exl-id: 8ad001d0-e9fe-46f5-b808-d6203a55a229
source-git-commit: 034c4639e6054118052524c457995f4caf7a4bf2
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 100%

---

# [!DNL Marketo Measure] Ultimate-Datenintegritätsanforderung {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure] validiert die eingehenden AEP-Datensätze, um sicherzustellen, dass die Daten für die Attribution ausreichend und kohärent sind. Wenn die Datenintegritätsanforderung nicht erfüllt ist, wird der Datensatz vom [!DNL Marketo Measure]-System abgelehnt. In diesem Dokument werden die Datenintegritätsanforderung beschrieben, Beispiele für Abfragen zur Dateninspektion bereitgestellt und eine Lösung für erforderliche Felder mit einem Nullwert empfohlen.

## Entitätsobjekt {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>XDM-Klasse</th>
    <th>XDM-Feldergruppe</th>
    <th>XDM-Pfad</th>
    <th>XDM-Typ</th>
    <th>Datenquellenfeld</th>
    <th>Erforderlich?</th>
    <th>Hinweise</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>Konto</strong> (Konto für Salesforce, Unternehmen und/oder benanntes Konto für Marketo)</td>
    </tr>
    <tr>
      <td rowspan="6">XDM-Geschäftskonto</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>XDM-Geschäftskonto – Details</td>
      <td>accountName</td>
      <td>Zeichenfolge</td>
      <td>Name</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Kampagne</strong> (Kampagne für Salesforce, Programm für Marketo)</td>
    </tr>
    <tr>
      <td rowspan="8">XDM-Geschäftskampagne</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignName</td>
      <td>Zeichenfolge</td>
      <td>Name</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campaignType</td>
      <td>Zeichenfolge</td>
      <td>CampaignType</td>
      <td>Nein</td>
      <td>Für die Kanalzuordnung</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM-Geschäftskampagne – Details</td>
      <td>channelName</td>
      <td>Zeichenfolge</td>
      <td>ChannelName</td>
      <td>Nein</td>
      <td>Für die Kanalzuordnung</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignStartDate</td>
      <td>Datum-Uhrzeit</td>
      <td>Startdatum</td>
      <td>Nein</td>
      <td>Für Kampagnenkosten</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignEndDate</td>
      <td>Datum-Uhrzeit</td>
      <td>EndDate</td>
      <td>Nein</td>
      <td>Für Kampagnenkosten</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>number</td>
      <td>Kosten</td>
      <td>Nein</td>
      <td>Für Kampagnenkosten</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>Zeichenfolge</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>Nein</td>
      <td>Für Kampagnenkosten</td>
    </tr>
    <tr>
      <td colspan="7"><strong>Kampagnenmitglied</strong> (Kampagnenmitglied für Salesforce, Programmmitgliedschaften for Marketo)</td>
    </tr>
    <tr>
      <td rowspan="14">XDM-Geschäftskampagne – Mitglieder</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Lead-ID oder Kontakt-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 333, je nach der Datenquellentabelle ist dies entweder die Lead-ID oder die Kontakt-ID.</p>
        <p>Fremdschlüssel für Lead oder Kontakt</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Kampagnen-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 55555.</p>
        <p>Fremdschlüssel für Kampagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM-Geschäftskampagne – Mitgliederdetails</td>
      <td>b2b.personType</td>
      <td>Zeichenfolge</td>
      <td>„Lead“ oder „Kontakt“</td>
      <td>Ja</td>
      <td>Abhängig von der Datenquellentabelle sollte dies auf „Lead“ oder „Kontakt“ gesetzt werden. Wir empfehlen für die meisten Anwendungsfälle, dies auf „Kontakt“ festzulegen</td>
    </tr>
    <tr>
      <td></td>
      <td>memberStatus</td>
      <td>Zeichenfolge</td>
      <td>Status</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>hasResponded</td>
      <td>boolean</td>
      <td>HasResponded</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>firstRespondedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>FirstRespondedDate</td>
      <td>Nein</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Person</strong> (Kontakt oder Lead für Salesforce, Personen für Marketo)</td>
    </tr>
    <tr>
      <td>XDM-Profil für Einzelpersonen</td>
      <td rowspan="11">XDM-Geschäftsperson – Details</td>
      <td>b2b.personKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 333, je nach Datenquellentabelle ist dies entweder Lead-ID oder Kontakt-ID</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>Zeichenfolge</p>
        <p>E-Mail</p>
      </td>
      <td>E-Mail</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>Zeichenfolge</td>
      <td>Status</td>
      <td>Ja nur für personType „Lead“</td>
      <td>Nur erforderlich, wenn der b2b.personType „Lead“ ist</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>boolean</td>
      <td>IsConverted</td>
      <td>Ja nur für personType „Lead“</td>
      <td>Nur erforderlich, wenn der b2b.personType „Lead“ ist</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>Zeichenfolge</td>
      <td>„Lead“ oder „Kontakt“</td>
      <td>Ja</td>
      <td>Abhängig von der Datenquellentabelle sollte dies auf „Lead“ oder „Kontakt“ gesetzt werden. Wir empfehlen für die meisten Anwendungsfälle, dies auf „Kontakt“ festzulegen</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Nein</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM-Geschäftsperson – Komponenten</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Nein</td>
      <td>
        <p>Zum Beispiel: 123@999-abc-888.Marketo.</p>
        <p>Der Satz von sourceAccountKey-Feldern ist nur für wahre Kontaktdatensätze „erforderlich“, definiert als Personeneinträge, die mit „Konto“ verknüpft sind. Wenn er fehlt, wird der Datensatz nicht zurückgewiesen, aber die Attributionsergebnisse sind deaktiviert.</p>
        <p>personComponents ist ein Array, Marketo Measure verwendet jedoch nur das erste Element „personComponents[0]“</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Konto-ID</td>
      <td>Nein</td>
      <td>
        <p>Zum Beispiel: 123.</p>
        <p>Fremdschlüssel für Konto</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Nein</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Nein</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong>Opportunity</strong> (Opportunity für Salesforce, Opportunities für Marketo)</td>
    </tr>
    <tr>
      <td rowspan="13">XDM-Geschäfts-Opportunity</td>
      <td></td>
      <td>OpportunityKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Konto-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 123.</p>
        <p>Fremdschlüssel für Konto</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityName</td>
      <td>Zeichenfolge</td>
      <td>Name</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityStage</td>
      <td>Zeichenfolge</td>
      <td>Phase</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Nein</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM-Geschäfts-Opportunity – Details</td>
      <td>IsWon</td>
      <td>boolean</td>
      <td>IsWon</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>IsClosed</td>
      <td>boolean</td>
      <td>IsClosed</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>ExpectedCloseDate</td>
      <td>Datum</td>
      <td>CloseDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityAmount.amount</td>
      <td>number</td>
      <td>Betrag</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityAmount.currencyCode</td>
      <td>
        <p>Zeichenfolge</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Die Rolle „Opportunity-Kontakt“ (nur erforderlich, wenn die Rolle „Opportunity-Kontakt“ als die kaufende Gruppe für die Attribution verwendet werden soll)</strong></td>
    </tr>
    <tr>
      <td rowspan="16">XDM-Geschäfts-Opportunity – Personenbeziehung</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Kontakt-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 333.</p>
        <p>Fremdschlüssel für Kontakt</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>boolean</td>
      <td>IsPrimary</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Opportunity-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 77777.</p>
        <p>Fremdschlüssel für Opportunity</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>OpportunityPersonKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personRole</td>
      <td>Zeichenfolge</td>
      <td>Rolle</td>
      <td>Nein</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Konversionsrate (nur bei Verwendung mehrerer Währungen erforderlich; für Marketo Measure kann nur ein Konversionsratendatensatz aktiviert werden)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">Konversion</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Zum Beispiel: 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>Datum-Uhrzeit</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>Datum-Uhrzeit</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>IsDeleted</td>
      <td>boolean</td>
      <td></td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">Währungskonversionsrate – Details</td>
      <td>conversionRate</td>
      <td>number</td>
      <td>ConversionRate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>Datum</td>
      <td>NextStartDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startdate</td>
      <td>Datum</td>
      <td>Startdatum</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOCode</td>
      <td>Zeichenfolge</td>
      <td>ISOCode</td>
      <td>Ja</td>
      <td>Zum Beispiel: EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetISOCode</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Der in Marketo Measure festgelegte Standardwährungscode, z. B. USD</td>
    </tr>
  </tbody>
</table>

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>XDM-Klasse</th>
    <th>XDM-Feldergruppe</th>
    <th>XDM-Pfad</th>
    <th>XDM-Typ</th>
    <th>Datenquellenfeld</th>
    <th>Erforderlich?</th>
    <th>Hinweise</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>Aktivität</strong></td>
    </tr>
    <tr>
      <td rowspan="3">XDM-Erlebnisereignis</td>
      <td></td>
      <td>_ID</td>
      <td>Zeichenfolge</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>eventType</td>
      <td>Zeichenfolge</td>
      <td>Aktivitätstyp</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>Zeitstempel</td>
      <td>Datum-Uhrzeit</td>
      <td>Aktivitätsdatum</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>Personen-ID</td>
      <td>personKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>Zeichenfolge</td>
      <td>Lead-ID oder Kontakt-ID</td>
      <td>Ja</td>
      <td>
        <p>Zum Beispiel: 333, je nach der Datenquellentabelle ist dies entweder die Lead-ID oder die Kontakt-ID.</p>
        <p>Fremdschlüssel für Lead oder Kontakt</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Zu Kampagne hinzufügen</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.addToCampaign</td>
      <td>Zum Beispiel: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>Zeichenfolge</td>
      <td>Kampagnen-ID</td>
      <td>Ja nur für den Typ leadOperation.addToCampaign</td>
      <td>
        <p>Zum Beispiel: 55555.</p>
        <p>Fremdschlüssel für Kampagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.addToCampaign</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.addToCampaign</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Status in Kampagnenfortschritt geändert</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.campaignProgression</td>
      <td>Zum Beispiel: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>Zeichenfolge</td>
      <td>Kampagnen-ID</td>
      <td>Ja nur für den Typ leadOperation.campaignProgression</td>
      <td>
        <p>Zum Beispiel: 55555.</p>
        <p>Fremdschlüssel für Kampagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.campaignProgression</td>
      <td>Zum Beispiel: 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>Zeichenfolge</td>
      <td></td>
      <td>Ja nur für den Typ leadOperation.campaignProgression</td>
      <td>Zum Beispiel: Marketo</td>
    </tr>
  </tbody>
</table>

## Typ ExperienceEvent wird unterstützt {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>Ereignistyp</th>
    <th>XDM-Ereignistyp</th>
    <th>Beschreibung</th>
  </tr>
  <tbody>
    <tr>
      <td>Neuer Lead</td>
      <td>leadOperation.newLead</td>
      <td>Wird verwendet, um die Erstellung und die Details eines neuen Marketing-Leads aufzuzeichnen</td>
    </tr>
    <tr>
      <td>Lead konvertieren</td>
      <td>leadOperation.convertLead</td>
      <td>Wird verwendet, wenn ein Marketing-Lead in einen für den Vertrieb qualifizierten Kontakt umgewandelt wird, der einer Vertriebs-Benutzerin bzw einem -Benutzer zugewiesen ist</td>
    </tr>
    <tr>
      <td>Interessanter Moment</td>
      <td>leadOperation.interestingMoment</td>
      <td>Wird verwendet, um hochwertige Aktivitäten von potenziellen Kundinnen und Kunden nachzuverfolgen</td>
    </tr>
    <tr>
      <td>Formular ausfüllen</td>
      <td>web.formFilledOut</td>
      <td>Wird verwendet, um Details zu erfassen, wenn eine Person ein Formular auf einer Web-Seite ausfüllt</td>
    </tr>
    <tr>
      <td>E-Mail abbestellen</td>
      <td>directMarketing.emailUnsubscribed</td>
      <td>Wird verwendet, um Details zu erfassen, wenn sich eine Person von einer E-Mail abmeldet</td>
    </tr>
    <tr>
      <td>E-Mail öffnen</td>
      <td>directMarketing.emailOpened</td>
      <td>Wird verwendet zum Erfassen von Details, wenn eine Person eine Marketing-E-Mail öffnet</td>
    </tr>
    <tr>
      <td>Klicken auf E-Mail</td>
      <td>directMarketing.emailClicked</td>
      <td>Wird verwendet zum Erfassen von Details, wenn eine Person auf einen Link in einer Marketing-E-Mail klickt</td>
    </tr>
    <tr>
      <td>Status in Entwicklung ändern</td>
      <td>leadOperation.statusInCampaignProgressionChanged</td>
      <td>Wird verwendet, um Details zu erfassen, wenn sich der Status eines Leads in einer Kampagne ändert</td>
    </tr>
    <tr>
      <td>Zum Interaktionsprogramm hinzufügen (Zur Pflege hinzufügen)</td>
      <td>leadOperation.addToCampaign</td>
      <td>Wird verwendet, um eine Person zur jeweiligen Kampagne hinzuzufügen.</td>
    </tr>
  </tbody>
</table>

Der Ereignistyp „Interessanter Moment“ wird für Ereignistypen verwendet, die in der obigen Tabelle nicht unterstützt werden. Fügen Sie ein benutzerdefiniertes Feld hinzu, um den Untertyp „Interessanter Moment“ anzugeben.

## Abfragebeispiele für die Dateninspektion {#query-examples-for-data-inspection}

Im Folgenden finden Sie eine Liste von Abfragebeispielen für die Inspektion von Datensätzen, die in den AEP Data Lake aufgenommen wurden. Um sie für Ihre Datensätze zu verwenden, ersetzen Sie den Tabellennamen in den unten stehenden Abfragebeispielen durch Ihren tatsächlichen Datensatztabellennamen.

Wir gehen davon aus, dass alle Zahlen 0 sind.

Für das Feld „personType“ erwarten wir, dass nur die Werte „Lead“ oder „Kontakt“ vorhanden sind und keine Nullwerte.

Für Personeneinträge des Typs „Kontakt“ erwarten wir, dass es einen Konto-Fremdschlüssel gibt.

Für Personeneinträge des Typs „Lead“ existiert kein Konto-Fremdschlüssel und es ist nicht keiner erforderlich. Wenn Sie Personeneinträge des Typs „Lead“ als Personeneinträge des Typs „Kontakt“ aufnehmen möchten (was empfohlen wird), ist kein Konto-Fremdschlüssel für diese Personeneinträge erforderlich.

### XDM-Geschäftskonto {#xdm-business-account}

```
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM-Geschäftskampagne {#xdm-business-campaign}

```
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM-Geschäftskampagne – Mitglied {#xdm-business-campaign-member}

```
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM-Geschäftsperson {#xdm-business-person}

```
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM-Geschäfts-Opportunity {#xdm-business-opportunity}

```
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM-Erlebnisereignis {#xdm-experienceevent}

```
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.campaignProgression.campaignKey.sourceKey' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### Konversion {#conversion}

```
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

## Empfohlene Lösung für erforderliche Felder mit Nullwert {#recommended-solution-for-required-fields-with-a-null-value}

Es wird empfohlen, ein berechnetes Feld in der Feldzuordnung zu verwenden, um das Feld standardmäßig auf einen Wert ungleich null zu setzen. Im Folgenden finden Sie zwei Beispiele:

* Wenn opportunityName für einige Opportunity-Datensätze null ist, erstellen und verwenden Sie das folgende berechnete Feld in der Feldzuordnung
   * `iif(name != null && name != "", name, "Unknown")`

* Wenn die leadOperation.campaignProgression.campaignID einiger Erlebnisereigniseinträge null ist, erstellen und verwenden Sie das folgende berechnete Feld in der Feldzuordnung
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`
