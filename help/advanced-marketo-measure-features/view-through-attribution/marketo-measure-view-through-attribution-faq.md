---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] FAQ zur Durchsicht der Attribution - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Überblick über die Attribution - FAQ"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 13%

---

# [!DNL Marketo Measure] Häufig gestellte Fragen zur Durchsichts-Attribution {#marketo-measure-view-through-attribution-faq}

## Was ist &quot;View Through Attribution&quot;? {#what-is-view-through-attribution}

Die [!DNL Marketo Measure] [!UICONTROL Durchsicht Attribution] -Funktion bietet die Möglichkeit, Anzeigenimpressionen in das Attributionsmodell aufzunehmen.

## Warum ist [!UICONTROL Durchsicht Attribution] Wichtig? {#why-is-view-through-attribution-important}

In der Vergangenheit war es für Marketingexperten schwierig, die Neuausrichtung von Targeting oder Impression-Werbung in der Attributionsanalyse zu berücksichtigen. Potenzielle Kunden können von Zeit zu Zeit erneut Targeting-Anzeigen erhalten, es ist jedoch unwahrscheinlich, dass sie tatsächlich auf eine dieser Anzeigen klicken und ein Formular innerhalb derselben Sitzung ausfüllen. Unsere Lösung &quot;Durch Attribution anzeigen&quot;bietet jetzt die Möglichkeit nachzuverfolgen, ob jemand einer Impressions-Anzeige ausgesetzt war oder nicht. Dieser Touchpoint wird an den einzelnen Datensatz angehängt und so lange ausgeführt, bis der Interessent zum Kunden wird. Mit diesen Informationen erhält der Marketing-Experte jetzt bessere Einblicke in die Leistung seiner Retargeting-Werbung.

## Was ist an der Einrichtung dieses Systems beteiligt? {#what-is-involved-in-setting-this-up}

Zur [!DNL Marketo Measure] Um die Anzeigenimpressionen zu messen, muss ein Impressions-Tag im Kampagnen-Manager von Doubleclick platziert werden. Sobald das Tag implementiert ist, werden die Impressionen in unseren Logs gespeichert und wir kümmern uns um den Rest. Wenden Sie sich an Ihren Success Manager, wenn Sie die Ansicht durch Attribution messen möchten.

## Welche Anzeigenplattformen werden unterstützt? {#which-ad-platforms-are-supported}

Wir unterstützen derzeit [!DNL Doubleclick] Kampagnen-Manager.

## Wie wird die Attribution berechnet? {#how-is-the-attribution-calculated}

Wir haben eine sorgfältige Analyse von Impressionsdaten und deren Einfluss auf Konversionen in allen Phasen und Marketingkanälen durchgeführt. Die Verteilung variiert je nach Modell, wie Sie aus der folgenden Tabelle sehen können:

<table> 
 <colgroup> 
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
   <th><br></th> 
   <th>First Touch</th> 
   <th>Leaderstellung</th> 
   <th>U-förmig</th> 
   <th>W-förmig</th> 
   <th>Vollständiger Pfad</th> 
   <th>Benutzerdefiniertes Modell</th> 
  </tr> 
  <tr> 
   <td><strong>Impressions</strong></td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>10 %</td> 
   <td>10 %</td> 
   <td>10 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>FT</strong></td> 
   <td>100 Prozent</td> 
   <td>0 %</td> 
   <td>35 %</td> 
   <td>26,6 %</td> 
   <td>20 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0 %</td> 
   <td>100 Prozent</td> 
   <td>35 %</td> 
   <td>26,6 %</td> 
   <td>20 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>OC</strong></td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>26,6 %</td> 
   <td>20 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>Geschlossen</strong></td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>20 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>Mitte</strong></td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>20 %</td> 
   <td>10 %</td> 
   <td>10 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
 </tbody> 
</table>

## Wie sieht dies aus in [!DNL Salesforce?] {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] erstellt einen einzelnen Impression-Touchpoint auf jedem Lead, das der Display-Anzeige angezeigt wurde. Wir können den Benutzer auch dann zuordnen, wenn er zum ersten Mal auf Ihre Website (FT) gelangt ist und ein Formular (LC) ausfüllt. Der Touchpoint enthält Anzeigeninformationen wie Anzeigenkampagnenname/-ID, Anzeigen-ID, Anzeigeninhalt, Site-Name/ID, Platzierungsname/-ID, Marketing-Kanal, Geo, Referrer-Seite und mehr.

Das Viewthrough-Attributionsmodell hängt vom Client und den zugehörigen Daten ab.
