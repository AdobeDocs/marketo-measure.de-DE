---
description: Passport-Dashboard - [!DNL Marketo Measure] - Produkt
title: Passport-Dashboard
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 8%

---

# Passport-Dashboard {#passport-dashboard}

Das Passport-Dashboard bietet Marketing-Experten eine dynamische Ansicht von Leads, Kontakten und Möglichkeiten, während sie innerhalb eines bestimmten Zeitraums verschiedene Phasen durchlaufen. Durch Filterung nach einem bestimmten Datum können Benutzer auch eine Momentaufnahme der Datensätze für diesen Tag abrufen.

Fragen, die die Pinnwand beantwortet:

* Wie viele Leads, Kontakte oder Möglichkeiten gab es an einem beliebigen Tag in jeder Phase ohne Terminalfenster?
* Wie viele verschiedene Leads oder Kontakte sind während eines bestimmten Zeitraums durch die einzelnen Phasen der Transition fortgeschritten?
   * _Beispiel_: Wäre Lead A am 1.1.2023 in Phase 1 gewesen und bis zum 31.3.2023 auf Stufe 5 erweitert worden, würde die Passport-Analyse Q1 2023 Lead A in den Stufen 1 bis 5 zählen.
* Wie viele einmalige Möglichkeiten während eines bestimmten Zeitraums durch die einzelnen Übergangsphasen geleitet wurden?

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
    <td>Gelegenheiten</td>
    <td><li>Jede Phase zeigt die Anzahl der Möglichkeiten für BVT-Merkblätter, die innerhalb eines bestimmten Zeitraums durch sie vergangen sind.</li>
<ul style="padding-left: 30px;"><li>Wenn eine Gelegenheit innerhalb dieses Zeitraums mehrere Phasen durchläuft, werden sie in jeder Phase gezählt, in der sie bestanden hat.</li></ul>
<li>Terminalphasen wie "Geschlossene Gewinne"und "Geschlossene Verluste"sind ausgeschlossen.</li>
<li>Sowohl das Start- als auch das Enddatum sind inklusive.</li>
<br/><img src="assets/passport-dashboard-1.png" width="600"></td>
    <td rowspan="2">Übergangsdatum</td>
    <td></td>
    <td rowspan="2"><li>Datum</li>
<li>Kanal</li>
<li>Unterkanal</li>
<li>Kampagne</li>
<li>Segmente</li></td>
  </tr>
  <tr>
    <td>Leads/Kontakte</td>
    <td><li>Jede Phase zeigt die Anzahl der Leads oder Kontakte mit BTs an, die innerhalb eines bestimmten Zeitraums durch sie geleitet wurden.</li>
<ul style="padding-left: 30px;"><li>Ob "Lead"oder "Kontakt"angezeigt werden soll, hängt von der in den Einstellungen &gt; Attributionseinstellungen &gt; Standard-Dashboard-Objekt festgelegten Voreinstellung ab.</li></ul>
<li>Terminalphasen wie "Geschlossene Gewinne"und "Geschlossene Verluste"sind ausgeschlossen.</li>
<li>Sowohl das Start- als auch das Enddatum sind inklusive.</li>
<br/><img src="assets/passport-dashboard-2.png" width="600"></td>
    <td><li>Lead-/Kontaktkennung</li>
<li>Lead-/Kontakt-E-Mail</li>
<li>Erstellungsdatum</li>
<li>Aktuelles Stadium</li>
<li>Übertragung eingehend Datum</li>
<li>Übertragung ausgehend Datum</li></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[Dashboard-Grundlagen](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
