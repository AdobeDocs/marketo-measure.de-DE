---
unique-page-id: 18874652
description: Häufig gestellte Fragen zur [!DNL Marketo Measure] über Attribution - [!DNL Marketo Measure]
title: '[!DNL Marketo Measure] Häufig gestellte Fragen zur Durchsichts-Attribution'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 31%

---

# [!DNL Marketo Measure] Häufig gestellte Fragen zur Durchsichts-Attribution {#marketo-measure-view-through-attribution-faq}

## Was ist View Through Attribution? {#what-is-view-through-attribution}

Die Funktion [!DNL Marketo Measure] [!UICONTROL Durch Attribution anzeigen] bietet die Möglichkeit, Anzeigen-Impressions in das Attributionsmodell aufzunehmen.

>[!IMPORTANT]
>
>Aus Datenschutzgründen werden Drittanbieter-Cookies immer seltener verwendet. Die von Google Chrome angekündigte Einstellung von Drittanbieter-Cookies im 3. Quartal 2024 stellt effektiv das Ende dieser Tracking-Methode dar. Daher stellt Adobe die Marketo Measure-Funktionen, die auf Drittanbieter-Cookies basieren, ein. Dies betrifft insbesondere das Domain-übergreifende Tracking und die Viewthrough-Attribution, die das Impressions-Cookie von Google/DoubleClick verwenden. Andere Funktionen von Marketo Measure sind davon nicht betroffen. Die Verwendung von Erstanbieter-Cookies ist ebenfalls nicht betroffen. In Anbetracht des Zeitplans von Google ist das geplante Einstellungsdatum der beiden oben genannten Funktionen der 1.6.2024. Zugehörige Daten, die vor diesem Datum erfasst wurden, stehen Adobe-Kundinnen und -Kunden weiterhin zur Verfügung.

## Warum ist [!UICONTROL Durch Attribution anzeigen] wichtig? {#why-is-view-through-attribution-important}

Historisch betrachtet war es für Marketing-Experten schwierig, Retargeting oder Impression-Werbung bei der Attributionsanalyse zu berücksichtigen. Potenzielle Kunden werden möglicherweise immer wieder Retargeting-Anzeigen ausgesetzt, aber es ist unwahrscheinlich, dass sie tatsächlich auf eine dieser Anzeigen klicken und ein Formular innerhalb derselben Sitzung ausfüllen. Unsere Lösung View Through Attribution kann jetzt nachvollziehen, ob jemand einer Impression-Anzeige ausgesetzt war oder nicht. Dieser Touchpoint wird an den jeweiligen Datensatz angehängt und wird so lange weitergeführt, bis der Interessent ein Kunde wird. Mit diesen Informationen erhält der Marketing-Experte jetzt einen besseren Einblick in die Leistung seiner Retargeting-Werbung.

## Was ist an der Einrichtung beteiligt? {#what-is-involved-in-setting-this-up}

Damit [!DNL Marketo Measure] mit der Messung der Anzeigenimpressionen beginnen kann, muss ein Impression-Tag in DoubleClick Campaign Manager platziert werden. Sobald das Tag implementiert ist, werden die Impressionen in unseren Logs gespeichert und wir kümmern uns um den Rest. Wenden Sie sich an Ihren Success Manager, wenn Sie daran interessiert sind, die Ansicht über Attribution zu messen.

## Welche Anzeigenplattformen werden unterstützt? {#which-ad-platforms-are-supported}

Derzeit unterstützen wir [!DNL Doubleclick] Campaign Manager.

## Wie wird die Attribution berechnet? {#how-is-the-attribution-calculated}

Wir haben die Impressionsdaten und ihren Einfluss auf Konversionen in allen Stadien und Marketing-Kanälen sorgfältig analysiert. Die Verteilung variiert je nach Modell, wie Sie der folgenden Tabelle entnehmen können:

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
   <td>100 %</td> 
   <td>0 %</td> 
   <td>35 %</td> 
   <td>26,6 %</td> 
   <td>20 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
  <tr> 
   <td><strong>LC</strong></td> 
   <td>0 %</td> 
   <td>100 %</td> 
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
   <td><strong>Zweiter Vorname</strong></td> 
   <td>0 %</td> 
   <td>0 %</td> 
   <td>20 %</td> 
   <td>10 %</td> 
   <td>10 %</td> 
   <td>Benutzerdefiniert</td> 
  </tr> 
 </tbody> 
</table>

## Wie wird das in [!DNL Salesforce?] aussehen? {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] erstellt einen einzelnen Impression-Touchpoint auf jedem Lead, der für die Display-Anzeige verfügbar war. Wir sind in der Lage, den Benutzer auch nach seinem ersten Besuch auf Ihrer Website (FT) abzubilden und ein Formular (LC) auszufüllen. Der Touchpoint enthält Anzeigeninformationen wie Anzeigenkampagnenname/-kennung, Anzeigenkennung, Anzeigeninhalt, Website-Name/-ID, Platzierungsname/-kennung, Marketing-Kanal, Geografie, Referrer-Seite und mehr.

Das Attributionsmodell mit Durchsicht hängt vom Client und seinen Daten ab.
