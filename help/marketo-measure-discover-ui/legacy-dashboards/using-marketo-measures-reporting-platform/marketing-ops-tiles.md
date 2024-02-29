---
unique-page-id: 34406495
description: Kacheln für Marketing Ops - [!DNL Marketo Measure]
title: Kacheln für Marketing Ops
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 4%

---

# Kacheln für Marketing Ops {#marketing-ops-tiles}

Marketing Ops ermöglicht Ihnen die Validierung und Diagnose von [!DNL Marketo Measure] Daten mit vollständiger Sichtbarkeit einzelner Touchpoints pro Leads, Kontakte, Konten, Kampagnen und Chancen.

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
   <td><p><strong>Opportunity</strong></p></td> 
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

## Kachel Konto {#account-tile}

![](assets/one-1.png)

Zeigt die folgenden Daten zu den angegebenen Konten an.

**Konten müssen über Touchpoint-Daten verfügen (nur bei aktiviertem ABM)**

-Konto-ID: Konto-ID in CRM

-Kontoname: Kontoname in CRM

-Erstellungsdatum: Erstellungsdatum des Kontos im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Website: Wert im Feld Website im Konto

- Interaktionsbewertung: Prädiktive Interaktionsbewertung (PES), ausgefüllt von [!DNL Marketo Measure]^1

-Möglichkeiten: Anzahl der mit dem Konto verbundenen Möglichkeiten

* Drilldown: Details zu den damit verbundenen Möglichkeiten finden Sie unter

- Kontakte: Anzahl der auf diesem Konto aufgeführten Kontakte

* Drilldown: Details zu den zugehörigen Kontakten anzeigen

-Leads: Anzahl der Leads, die diesem Konto durch Lead-Zuordnung zugeordnet sind^1

* Drilldown: Details zu den Leads anzeigen, die dem Konto zugeordnet wurden

-Attributions-Touchpoints: Anzahl der Touchpoints der Käuferzuordnung für das Konto

* Drilldown: Siehe Details zu Touchpoints der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch Type, Attributionsmodell)

-Touchpoints: Anzahl der Touchpoints, die die Kontakte auf diesem Konto haben^2

* Drilldown: Siehe Touchpoints in den Konto-Touchpoint-Details (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch-Typ).

>[!NOTE]
>
>Wenn Sie über ABM verfügen, werden Touchpoints angezeigt, die sich auf die Leads beziehen, die über die Zuordnung von Lead zu Konto zugeordnet wurden.

## Opportunity-Bereich {#opportunity-tile}

![](assets/two-1.png)

Zeigt die folgenden Daten im Zusammenhang mit den angegebenen Möglichkeiten an.

-Opportunity ID: Opportunity ID in CRM

-Opportunity Name (Angebotsname) in CRM

-Kontoname: Kontoname, der der Gelegenheit zugeordnet ist

-Erstellungsdatum: Erstellungsdatum der Opportunity im CRM

Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Datum schließen: Geschlossenes Datum der Möglichkeit im CRM

Drilldown: Siehe Datum nach Stunde, Minute, Zeit schließen .

-Betrag: Der Gesamtbetrag der Chancen

- Kontakte: Anzahl der Kontakte, die mit der Möglichkeit in Verbindung stehen

Drilldown: Details zu den zugehörigen Kontakten anzeigen

-Attributions-Touchpoints: Anzahl der zugehörigen Touchpoints der Käuferzuordnung

Drilldown: Siehe Details zu Touchpoints der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch Type, Attributionsmodell)

## Kontaktbereich {#contacts-tile}

![](assets/three-1.png)

Zeigt die folgenden Daten zu den angegebenen Kontakten an.

-Kontakt-ID: Kontakt-ID im CRM

-E-Mail: E-Mail-Adresse des Kontaktdatensatzes

-Erstellungsdatum: Erstellungsdatum des Kontakts im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Kontoname: Kontoname, der dem Kontakt zugeordnet ist

-Attributions-Touchpoints: Anzahl der Touchpoints der Käuferzuordnung für den Kontakt

* Drilldown: Siehe Details zu Touchpoints der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch Type, Attributionsmodell)

-Touchpoints: Anzahl der Touchpoints des Käufers für den Kontakt

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchtyp).

## Lead-Kachel {#leads-tile}

![](assets/four-1.png)

Zeigt die folgenden Daten zu den angegebenen Leads an.

-Lead-ID: Lead-ID in CRM

-E-Mail: Lead-Datensatz-E-Mail-Adresse

-Erstellungsdatum: Zeitpunkt der Erstellung des Leads im CRM

* Drilldown: Siehe Erstellungsdatum nach Stunde, Minute, Zeit .

-Unternehmen (aus Lead): Das Unternehmen, das im Datensatz im CRM aufgeführt ist, der vom Kunden ausgefüllt wurde.

-Kontoname: Der Kontoname [!DNL Marketo Measure] füllt basierend auf unserer &quot;Lead to Account Mapping&quot;

-Touchpoints: Die Anzahl der Touchpoints, die mit dem (den) Lead(s) verknüpft sind.

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchtyp).

## Kampagnenkachel {#campaigns-tile}

![](assets/five-1.png)

Zeigt die folgenden Daten bezüglich der angegebenen Kampagne(n) an.

-Kampagnen-ID: Kampagnen-ID in CRM

-Kampagnenname: Kampagnenname im CRM

- Kampagnenausgaben: Die Ausgaben [!DNL Marketo Measure] hat mit der Kampagne verknüpfte Datensätze aufgezeichnet

-Attributionsmodell: Zeigt die entsprechende Attribution basierend auf dem ausgewählten Modell an

-Attributions-Touchpoints: Die Anzahl der mit der Kampagne(n) verbundenen Touchpoints der Käuferzuordnung.

* Drilldown: Siehe Details zu Touchpoints der Käuferzuordnung (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subchannel, Marketing Touch Type, Attributionsmodell)

-Touchpoints: Die Anzahl der Touchpoints, die mit der/den Kampagne(n) verknüpft sind

* Drilldown: Siehe Kontakte zu den Touchpoint-Details des Kontos (ID, E-Mail, Touchpoint-Datum, Kontoname, Kampagne, Kanal, Subkanal, Marketing-Touchtyp).
