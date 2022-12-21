---
unique-page-id: 34406495
description: Kacheln für Marketing Ops - [!DNL Marketo Measure] - Produktdokumentation
title: Kacheln für Marketing Ops
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 10%

---

# Kacheln für Marketing Ops {#marketing-ops-tiles}

Marketing Ops ermöglicht Ihnen die Validierung und Diagnose von [!DNL Marketo Measure] Daten mit vollständiger Sichtbarkeit einzelner Kontaktpunkte pro Leads, Kontakte, Konten, Kampagnen und Chancen.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><br></td> 
   <td><p><strong>Konto-ID</strong></p></td> 
   <td><p><strong>Kontoname</strong></p></td> 
   <td><p><strong>Opt-in-ID</strong></p></td> 
   <td><p><strong>Opt-in-Name</strong></p></td> 
   <td><p><strong>Lead- oder Kontakt-ID</strong></p></td> 
   <td><p><strong>Lead- oder Kontakt-E-Mail-Adresse</strong></p></td> 
   <td><p><strong>Kampagnen-ID</strong></p></td> 
   <td><p><strong>Opportunity gewonnen</strong></p></td> 
   <td><p><strong>Erstellungsdatum der Opt-in</strong></p></td> 
   <td><p><strong>Opt-in-Schließdatum</strong></p></td> 
   <td><p><strong>Touchpoint-Datum</strong></p></td> 
   <td><p><strong>Attributionsmodell</strong></p></td> 
  </tr> 
  <tr> 
   <td><p><strong>Konten</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Chance</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Kontakte</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Leads</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Kampagnen</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
 </tbody> 
</table>

## Kachel &quot;Konto&quot; {#account-tile}

![](assets/one-1.png)

Zeigt die folgenden Daten zu den angegebenen Konten an.

**Konten müssen über Touchpoint-Daten verfügen (nur anwendbar, wenn ABM aktiviert ist)**

-Konto-ID: Konto-ID in CRM

-Kontoname: Kontoname in CRM

-Erstellungsdatum: Erstellungsdatum des Kontos im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Website: Wert im Feld Website im Konto

-Interaktionsbewertung: Prädiktive Interaktionsbewertung (PES), gefüllt durch [!DNL Marketo Measure]^1

-Möglichkeiten: Anzahl der mit dem Konto verbundenen Möglichkeiten

* Drilldown: Siehe Details zu den damit verbundenen Möglichkeiten

-Ansprechpartner: Anzahl der auf diesem Konto aufgeführten Kontakte

* Drilldown: Siehe Details für die zugehörigen Kontakte.

-Leads: Anzahl der Leads, die diesem Konto zugeordnet sind, durch die Kontozuordnung^1

* Drilldown: Siehe Details zu den Leads, die dem Konto zugeordnet wurden.

-Attributions-Touchpoints: Anzahl der Touchpoints der Käuferzuordnung für das Konto

* Drilldown: Siehe Details zum Touchpoint der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchpoint-Typ, Attributionsmodell)

-Touchpoints: Anzahl der Touchpoints, die die Kontakte auf diesem Konto haben^2

* Drilldown: Siehe Touchpoints in den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchtyp).

>[!NOTE]
>
>Wenn Sie über ABM verfügen, werden Touchpoints angezeigt, die sich auf die Leads beziehen, die über die Zuordnung von Lead zu Konto zugeordnet wurden.

## Opportunity-Kachel {#opportunity-tile}

![](assets/two-1.png)

Zeigt die folgenden Daten im Zusammenhang mit den angegebenen Möglichkeiten an.

-Opportunity ID: Chancen-ID in CRM

-Opportunity Name: Opportunity name in CRM

-Kontoname: Kontoname, der der Gelegenheit zugeordnet ist

-Erstellungsdatum: Erstellungsdatum der Opportunity im CRM

Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Datum schließen: Abschlussdatum der Chance im CRM

Drilldown: Siehe Datum nach Stunde, Minute und Zeit schließen .

-Betrag: Die Gesamtanzahl der Möglichkeiten

-Ansprechpartner: Anzahl der Kontakte, die mit der Gelegenheit in Verbindung stehen

Drilldown: Siehe Details für die zugehörigen Kontakte.

-Attributions-Touchpoints: Anzahl der zugehörigen Touchpoints der Käuferzuordnung

Drilldown: Siehe Details zum Touchpoint der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchpoint-Typ, Attributionsmodell)

## Kontaktbereich {#contacts-tile}

![](assets/three-1.png)

Zeigt die folgenden Daten zu den angegebenen Kontakten an.

-Kontakt-ID: Kontakt-ID in CRM

-Email: E-Mail-Adresse des Kontaktdatensatzes

-Erstellungsdatum: Erstellungsdatum des Kontakts im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Kontoname: Kontoname des Kontakts

-Attributions-Touchpoints: Anzahl der Touchpoints der Käuferzuordnung für den Kontakt

* Drilldown: Siehe Details zum Touchpoint der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchpoint-Typ, Attributionsmodell)

-Touchpoints: Anzahl der Touchpoints des Käufers für den Kontakt

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch-Typ).

## Lead-Kachel {#leads-tile}

![](assets/four-1.png)

Zeigt die folgenden Daten zu den angegebenen Leads an.

-Lead-ID: Lead-ID in CRM

-Email: E-Mail-Adresse des Lead-Datensatzes

-Erstellungsdatum: Zeitpunkt der Erstellung des Leads im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Unternehmen (Lead): Das Unternehmen, das im Datensatz im CRM aufgeführt ist, der vom Kunden ausgefüllt wird

-Kontoname: Der Kontoname [!DNL Marketo Measure] füllt basierend auf unserer &quot;Lead to Account Mapping&quot;

-Touchpoints: Die Anzahl der Touchpoints, die mit dem Lead (den Leads) verknüpft sind

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch-Typ).

## Kampagnenkachel {#campaigns-tile}

![](assets/five-1.png)

Zeigt die folgenden Daten bezüglich der angegebenen Kampagne(n) an.

-Kampagnen-ID: Kampagnen-ID in CRM

-Kampagnenname: Kampagnenname in CRM

-Kampagnenausgaben: Ausgaben [!DNL Marketo Measure] hat mit der Kampagne verknüpfte Datensätze aufgezeichnet

-Attributionsmodell: Dadurch wird die entsprechende Attribution basierend auf dem ausgewählten Modell angezeigt.

-Attributions-Touchpoints: Die Anzahl der mit der Kampagne(n) verknüpften Touchpoints der Käuferzuordnung

* Drilldown: Siehe Details zum Touchpoint der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchpoint-Typ, Attributionsmodell)

-Touchpoints: Die Anzahl der Touchpoints, die mit der Kampagne(n) verknüpft sind

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch-Typ).
