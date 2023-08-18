---
description: ROI-Dashboard - [!DNL Marketo Measure] - Produkt
title: ROI-Dashboard
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 18%

---

# ROI-Dashboard {#roi-dashboard}

Das ROI-Dashboard bietet Marketing-Experten einen detaillierten Überblick über die Investitionsrenditen über Kanäle, Unterkanäle und Kampagnen hinweg. Sie schlüsselt Kosten- und Umsatzmuster sorgfältig auf und zeigt gleichzeitig Metriken wie Kosten-pro-Interessent-, Deal- und Opportunities auf, um ein umfassendes Verständnis der Marketing-Attribution zu gewährleisten.

Fragen, die die Pinnwand beantwortet:

* Wie hoch waren die ROI-Werte für jeden Kanal, jeden Unterkanal und jede Kampagne?
* Wie wurden die Kosten und Einnahmen auf die einzelnen Kanäle, Unterkanäle und Kampagnen verteilt?
* Was waren die Kosten pro Lead, Kosten pro Deal und Kosten pro Opportunity?

<table style="table-layout:auto"> 
<tbody>
 <tr> 
   <th>Komponente</th> 
   <th>Beschreibung</th>
   <th>Datumstyp</th>
   <th>Durchsuchen von Feldern</th>
   <th>Filter</th>
  </tr>
  <tr>
    <td>Kostenkachel</td>
    <td>Gesamtkosten</td>
    <td>Datum der Kostenanrechnung</td>
    <td><li>Kampagnen-ID</li>
<li>Kampagnenname</li>
<li>Kanal</li>
<li>Unterkanal</li>
<li>Datum</li>
<li>Ausgaben</li></td>
    <td rowspan="15"><li>Datum</li>
<li>Attributionsmodell (Einstellung)</li>
<li>Kanal</li>
<li>Unterkanal</li>
<li>Kampagne</li></td>
  </tr>
  <tr>
    <td>Zugewiesene Umsatzkachel</td>
    <td>Gesamter zugewiesener Umsatz</td>
    <td>Abschlussdatum</td>
    <td><li>Opportunity-ID</li>
<li>Opportunity-Name</li>
<li>Opportunity-Erstellungsdatum</li>
<li>Opportunity Closed Date</li>
<li>Ist geschlossen (J/N)</li>
<li>Is Won (Y/N)</li>
<li>Attributionsmodell</li>
<li>Attributierter Umsatz</li>
<li>Erzielter Umsatz</li></td>
  </tr>
  <tr>
    <td>Einfache ROI-Kachel</td>
    <td>Legacy-ROI: Umsatz dividiert durch Kosten in einem bestimmten Zeitraum. 
    <li>Kosten: Kosten, die im gefilterten Datumszeitraum anfallen.</li>
    <li>Umsatz: Umsatz aus "geschlossenen Gewinnen"-Chancen in diesem Zeitraum.</li></td>
    <td>Abschlussdatum</td>
    <td>n.z</td>
  </tr>
  <tr>
    <td>Realisierte ROI-Kachel</td>
    <td>Realized ROI: Stellt die greifbaren Ergebnisse von Touchpoints dar, die von Kampagnen innerhalb eines bestimmten Zeitraums generiert wurden.
    <li>Kosten: Kosten, die im gefilterten Datumszeitraum anfallen.</li>
    <li>Umsatz: Erzielter Umsatz aus allen "geschlossenen Gewinnen"-Angeboten, insbesondere jenen, die innerhalb des festgelegten Zeitrahmens von Touchpoints beeinflusst werden.</li>
    <br/><img src="assets/roi-dashboard-1.png" width="600"></td>
    <td>Datum der Kostenanrechnung</td>
    <td>n.z</td>
  </tr>
  <tr>
    <td>Neuer Lead-Bereich gesamt</td>
    <td>Gesamtzahl neuer Leads (Gesamtanzahl), die innerhalb eines bestimmten Zeitraums generiert wurden, einschließlich sowohl berührter als auch unberührter Leads.</td>
    <td>Erstellungsdatum</td>
    <td rowspan="2">
    <li>Lead-ID</li>
    <li>Lead-E-Mail</li>
    <li>LC-Datum</li></td>
  </tr>
  <tr>
    <td>Kosten pro neuer Leadbereich</td>
    <td>Gesamtzahl der neuen Leads (Gesamtanzahl) dividiert durch Kosten.</td>
    <td>Erstellungsdatum</td>
  </tr>
  <tr>
    <td>Kachel "Neue Möglichkeiten"gesamt</td>
    <td>Gesamtzahl neuer Möglichkeiten (Gesamtanzahl), die innerhalb eines bestimmten Zeitraums generiert wurden, einschließlich sowohl berührter als auch unberührter Leads.</td>
    <td>Erstellungsdatum</td>
    <td rowspan="2">
    <li>Opportunity-ID</li>
    <li>Opportunity-Name</li>
    <li>Opportunity-Erstellungsdatum</li>
    <li>Opportunity Closed Date</li>
    <li>Ist geschlossen (J/N)</li>
    <li>Is Won (Y/N)</li>
    <li>Aktuelles Stadium</li></td>
  </tr>
  <tr>
    <td>Kachel "Kosten pro neuer Chance"</td>
    <td>Gesamtzahl der neuen Möglichkeiten (Gesamtanzahl) dividiert durch Kosten.</td>
    <td>Erstellungsdatum</td>
  </tr>
  <tr>
    <td>Kachel "Angebote insgesamt"</td>
    <td>Gesamtzahl der innerhalb eines bestimmten Zeitraums abgeschlossenen Angebote, einschließlich der Angebote ohne zugehörige Touchpoints.</td>
    <td>Abschlussdatum</td>
    <td><li>Opportunity-ID</li>
<li>Opportunity-Name</li>
<li>Opportunity-Erstellungsdatum</li>
<li>Opportunity Closed Date</li>
<li>Ist geschlossen (J/N)</li>
<li>Is Won (Y/N)</li>
<li>Aktuelles Stadium</li>
<li>Währung</li>
<li>Attributionsmodell</li>
<li>Attributierter Umsatz</li>
<li>Erzielter Umsatz</li></td>
  </tr>
  <tr>
    <td>Kosten und Umsatz nach Kanaldiagramm</td>
    <td>Balkendiagramm, das sowohl Kosten als auch Umsatz anzeigt und eine vergleichende Sicht auf deren Größenordnung in Bezug auf verschiedene Kanäle, Unterkanäle und Kampagnen bietet.
    <br/><img src="assets/roi-dashboard-2.png" width="600"></td>
    <td>Abschlussdatum</td>
    <td>Kosten:
<br/>
<li>Kampagnen-ID</li>
<li>Kampagnenname</li>
<li>Kanal</li>
<li>Unterkanal</li>
<li>Datum der Kostenanrechnung</li>
<li>Währung</li>
<li>Ausgaben</li>
<p>
Umsatz:
<br/>
<li>Opportunity-ID</li>
<li>Opportunity-Name</li>
<li>Opportunity-Erstellungsdatum</li>
<li>Opportunity Closed Date</li>
<li>Ist geschlossen (J/N)</li>
<li>Is Won (Y/N)</li>
<li>Attributierter Umsatz</li>
<li>Attributionsmodell</li>
<li>Attributierter Umsatz</li>
<li>Erzielter Umsatz</li></td>
  </tr>
  <tr>
    <td>Realisierter und einfacher ROI im Zeitverlauf</td>
    <td>Zeitreihenliniendiagramm, das den Vergleich zwischen realisiertem und einfachem ROI anzeigt und deren Fortschritt im Zeitverlauf verfolgt.
    <br/><img src="assets/roi-dashboard-3.png" width="600"></td>
    <td>Einfacher ROI: Kosten für Datum und Datum der Beendigung
    <p>Realisierter ROI: Kosten für Datum und Touchpoint-Datum</td>
    <td>n.z</td>
  </tr>
  <tr>
    <td>Zeitverlaufsdiagramm</td>
    <td>Gestapeltes Balkendiagramm mit vierteljährlichen/monatlichen Gesamtkosten, segmentiert nach einzelnen Kanälen für eine detaillierte Aufschlüsselung.
    <br/><img src="assets/roi-dashboard-4.png" width="600"></td>
    <td>Datum der Kostenanrechnung</td>
    <td rowspan="2"><li>Kampagnen-ID</li>
<li>Kampagnenname</li>
<li>Kanal</li>
<li>Unterkanal</li>
<li>Datum der Kostenanrechnung</li>
<li>Währung</li>
<li>Ausgaben</li></td>
  </tr>
  <tr>
    <td>Kosten nach Kanaldiagramm</td>
    <td>Balkendiagramm mit nach Kanälen segmentierten Marketingausgaben.
    <br/><img src="assets/roi-dashboard-5.png" width="600"></td>
    <td>Datum der Kostenanrechnung</td>
  </tr>
  <tr>
    <td>ROI-Zusammenfassungstabelle</td>
    <td>Tabelle mit zurechenbaren Einnahmen, Kosten und ROI, segmentiert nach einzelnen Kanälen, für eine detaillierte Aufschlüsselung.
<p>
<b>Spalten:</b>
<p>
<li>Kanal/Subkanal/Kampagne</li>
<li>Kosten</li>
<li>Attributierter Umsatz</li>
<li>Einfacher ROI</li>
<li>Realisierter ROI</li>
<li>Nicht realisierte Pipeline</li>
<ul style="padding-left: 30px;"><li>Pipeline von Touchpoints (Open Opportunities), die Kampagnen in einem bestimmten Zeitraum zugeordnet sind</li></ul></td>
    <td>Einfacher ROI: Kosten für Datum und Datum der Beendigung
    <p>Realisierter ROI: Kosten für Datum und Touchpoint-Datum</td>
    <td>n.z</td>
  </tr>
  <tr>
    <td>Tabelle der Marketing-Ausgaben</td>
    <td>Tabelle mit den Kosten, neuen Leads, Chancen und Angeboten, die nach einzelnen Kanälen segmentiert sind, für eine detaillierte Aufschlüsselung.
<p>
<b>Spalten:</b>
<p>
<li>Kanal/Subkanal/Kampagne</li>
<li>Kosten</li>
<li>Neue Leads</li>
<li>Kosten pro neuem Lead</li>
<li>Neue Chancen</li>
<li>Kosten pro neuer Chance</li>
<li>Geschlossene Angebote</li>
<li>Kosten pro abgeschlossenem Geschäft</li></td>
    <td><li>Kosten: Entstehungsdatum der Kosten</li>
<li>Neue Leads: Erstellungsdatum</li>
<li>Neue Möglichkeiten: Erstellungsdatum</li>
<li>Geschlossene Angebote: Geschlossenes Datum</li></td>
    <td>n.z</td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[Dashboard-Grundlagen](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
