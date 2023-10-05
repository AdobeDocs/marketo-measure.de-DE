---
unique-page-id: 35586105
description: Interaktionspfad - [!DNL Marketo Measure] - Produktdokumentation
title: Interaktionsverlauf
exl-id: 104d803f-9f40-4ab6-872d-6432f8c087e9
feature: Reporting
source-git-commit: e24e01a03218252c06c9a776e0519afbddbe2b8c
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 9%

---

# Interaktionsverlauf {#engagement-path}

Interaktionspfad ermöglicht es Ihnen, eine vollständige Ansicht der Interaktionen mit Lead, Kontakt, Konto und Chancen von Erstkontakt bis zum Schließen anzuzeigen.

![](assets/one-2.png)

## Kachelbeschreibung {#tile-description}

**Ereignistyp:** Der Typ des Touchpoints (Sitzung, CRM-Kampagne, CRM-Ereignis, CRM-Aufgabe, Impression)

**Touchpoint-Position des Kunden:** Touchpoint-Position des Leads/Kontakts

**Touchpoint-Position der Käuferzuordnung:** Touchpoint-Position der Käuferzuordnung

**Touchpoint-Datum:** Für Online-Quellen: Datum und Uhrzeit der Interaktion. Für Offline-Ereignisse: Datum und Uhrzeit in der Salesforce-Kampagne festgelegt. Bei Aktivitäten Touchpoint: Touchpoint-Datumsfeld, auf das in der Aktivitätskonfiguration verwiesen wird

**E-Mail:** Die der Interaktion zugeordnete E-Mail

**Marketing-Touch-Typ:** Art der Interaktion (Webbesuch, Webformular, Webchat, CRM, Aktivitätstypen)

**Kanal:** Marketing-Kanal, der die Interaktion angetrieben hat

**Mittel:** Interaktionsmittel

* Wenn die Interaktion von einer API-verbundenen Plattform (Adwords/BingAds) erfolgt, ist das Medium CPC
* Wenn die Einstiegsseite der Interaktion utm_medium enthält, werden wir analysieren
* Wenn die Interaktion von einer CRM-Kampagne stammt, stammt das Medium aus dem Feld Typ der CRM-Kampagne.

**Webquelle:** In dieser Spalte wird die Quelle der Interaktion angezeigt

* Wenn die Interaktion von einer mit einer API verbundenen Plattform erfolgt, zeigt die Webquelle den Namen der Anzeigenplattform an
* Wenn der Touchpoint aus einer organischen Suche stammt, zeigt dieses Feld den Namen der Suchmaschine an
* Wenn weder #1 noch #2 zutreffen und der Wert von utm_source in der URL der Landingpage für den Touchpoint vorhanden ist, wird dieser Wert hier angezeigt
* Wenn nicht #1 oder #2 und kein utm_source -Wert vorhanden ist, wird hier die Stammdomäne der verweisenden URL angezeigt.
* Wenn keine der oben genannten Optionen angezeigt wird, wird Web Direct oder Web

**Erste Interaktion mit der Person:** Diese Spalte zeigt Ja oder Nein an, wenn dieser Touchpoint die erste Interaktion der Kontakte war.

**Zugewiesener Umsatz:** Diese Spalte zeigt den diesem Touchpoint zugeordneten Umsatz basierend auf dem ausgewählten Attributionsmodell an

## Filterbeschreibung {#filter-description}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Filtername</th> 
   <th>Beschreibung</th> 
  </tr> 
  <tr> 
   <td><p>Kontoname/ID</p></td> 
   <td><p>Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Mehrere Filterwerte weisen die Beziehung "Entweder"oder auf, d. h. die Kachel zeigt Ergebnisse für beide Filterwerte an. Wenn einer der Filterwerte ungültig ist, liefert das Dashboard keine Ergebnisse für den ungültigen Wert, filtert aber trotzdem nach den gültigen Filterwerten. Nicht zwischen Groß- und Kleinschreibung unterscheiden.</p></td> 
  </tr> 
  <tr> 
   <td><p>Opportunity Name/ID</p></td> 
   <td><p>Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Mehrere Filterwerte weisen die Beziehung "Entweder"oder auf, d. h. die Kachel zeigt Ergebnisse für beide Filterwerte an. Wenn einer der Filterwerte ungültig ist, liefert das Dashboard keine Ergebnisse für den ungültigen Wert, filtert aber trotzdem nach den gültigen Filterwerten. Nicht zwischen Groß- und Kleinschreibung unterscheiden.</p></td> 
  </tr> 
  <tr> 
   <td><p>Lead-ID/E-Mail</p></td> 
   <td><p>Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Mehrere Filterwerte weisen die Beziehung "Entweder"oder auf, d. h. die Kachel zeigt Ergebnisse für beide Filterwerte an. Wenn einer der Filterwerte ungültig ist, liefert das Dashboard keine Ergebnisse für den ungültigen Wert, filtert aber trotzdem nach den gültigen Filterwerten. Nicht zwischen Groß- und Kleinschreibung unterscheiden.</p></td> 
  </tr> 
  <tr> 
   <td><p>Kontakt-ID/E-Mail</p></td> 
   <td><p>Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Mehrere Filterwerte weisen die Beziehung "Entweder"oder auf, d. h. die Kachel zeigt Ergebnisse für beide Filterwerte an. Wenn einer der Filterwerte ungültig ist, liefert das Dashboard keine Ergebnisse für den ungültigen Wert, filtert aber trotzdem nach den gültigen Filterwerten. Nicht zwischen Groß- und Kleinschreibung unterscheiden.</p><p>Kontoname/ID, Lead-ID/E-Mail, Kontakt-ID/E-Mail-Filter sind eine "Entweder-Oder-Beziehung. Wenn also sowohl der Lead-Filter als auch der Kontaktfilter einen Wert haben, werden alle Datensätze für eine der IDs angezeigt.</p></td> 
  </tr> 
  <tr> 
   <td><p>Attributionsmodell</p></td> 
   <td><p>Geben Sie an, mit welchem Modell der zugeordnete Umsatz berechnet werden soll. Zulässige Werte: "Vollständige Pfadzuordnung", "Erstkontakt-Zuordnung", "Benutzerdefinierte Modellzuordnung", "Lead-Erstellung-Zuordnung", "U-förmige Zuordnung", "W-förmige Zuordnung".</p></td> 
  </tr> 
  <tr> 
   <td><p>Ereignistyp</p></td> 
   <td><p>Filtern Sie die Journey nach Ereignistyp, auf dem der Benutzer-Touchpoint basiert. Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Zulässige Werte: "Sitzung", "CRM-Kampagne", "CRM-Ereignis", "CRM-Aufgabe", "Impression".</p></td> 
  </tr> 
  <tr> 
   <td><p>Lead-Stadien</p></td> 
   <td><p>Filtern Sie Journey nach Lead-Bühne, auf der der Benutzer-Touchpoint basiert. Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Filter default zu "ist gleich"zeigt Vorschläge zur Auswahl an, empfiehlt jedoch die Verwendung von "enthält"als Filterkriterium für mehrere Filter auf Bühnen.</p></td> 
  </tr> 
  <tr> 
   <td><p>Chancen-Stadien</p></td> 
   <td><p>Filtern Sie Journey nach Opportunity, auf der der User-Touchpoint basiert. Ermöglicht mehrere Werte durch Hinzufügen von Filtern über das Pluszeichen "+"rechts. Filter default zu "ist gleich"zeigt Vorschläge zur Auswahl an, empfiehlt jedoch die Verwendung von "enthält"als Filterkriterium für mehrere Filter auf Bühnen.</p></td> 
  </tr> 
  <tr> 
   <td><p>Touchpoint-Datum</p></td> 
   <td><p>Filtern Sie die Journey nach Datum/Uhrzeit des Touchpoints.</p></td> 
  </tr> 
  <tr> 
   <td><p>E-Mail-Adresse des User Touchpoint</p></td> 
   <td><p>Filtern Sie Journey per E-Mail nach Benutzer-Touchpoint. Dies ermöglicht das Filtern von E-Mails, die nicht mit einem Lead/Kontakt/Konto verknüpft sind.</p></td> 
  </tr> 
  <tr> 
   <td><p>Marketing-Kontakttyp</p></td> 
   <td><p>Filtern Sie Journey nach Marketing-Touchtyp.</p></td> 
  </tr> 
  <tr> 
   <td><p>Kanal</p></td> 
   <td><p>Journey nach Kanal filtern.</p></td> 
  </tr> 
  <tr> 
   <td><p>Medium</p></td> 
   <td><p>Journey nach Medium filtern.</p></td> 
  </tr> 
  <tr> 
   <td><p>Webquelle</p></td> 
   <td><p>Journey nach Webquelle filtern.</p></td> 
  </tr> 
  <tr> 
   <td><p>Erste Interaktion mit der Person</p></td> 
   <td><p>Filtern Sie die Journey nach der Spalte "Ist Erstkontakt"in der Tabelle der Benutzer-Touchpoints.</p></td> 
  </tr> 
  <tr> 
   <td><p>Attributierter Umsatz</p></td> 
   <td><p>Filtern Sie die Journey nach dem zugeordneten Umsatzwert.</p></td> 
  </tr> 
 </tbody> 
</table>
