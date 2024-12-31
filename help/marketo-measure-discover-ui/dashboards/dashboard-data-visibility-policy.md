---
description: Richtlinie für die Sichtbarkeit von Dashboard-Daten - [!DNL Marketo Measure] - Produkt
title: Richtlinie zur Dashboard-Datentransparenz
feature: Reporting
exl-id: 5f6f7173-617e-459d-992f-8a8b6c2db7cb
source-git-commit: 2bfa2923119f8ece18ec68408f8098bfa6778ccf
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 14%

---

# Richtlinie zur Dashboard-Datentransparenz {#dashboard-data-visibility-policy}

Um in unseren Dashboards ein besseres Erlebnis zu bieten, haben wir Richtlinien zur Datensichtbarkeit für Objekte festgelegt, über die wir berichten. Beachten Sie Folgendes: Wenn Sie sich mit unseren neuen Discover-Dashboards vertraut machen, werden Sie möglicherweise niedrigere Zahlen im Vergleich zu den alten Dashboards feststellen. Dies ist auf eine Änderung unserer Datendarstellungsmethode zurückzuführen, bei der die neuen Dashboards jetzt über spezifische Richtlinien für die Sichtbarkeit verfügen. Im Gegensatz zu unseren alten Discover Dashboards, die alle verfügbaren Daten anzeigen, zeigt die neue Version nur die Daten gemäß der Sichtbarkeitsrichtlinie an. In diesem Artikel soll klargestellt werden, wie Sichtbarkeitsrichtlinien für verschiedene Datenobjekte funktionieren, und es soll sichergestellt werden, dass die Berichte transparent und präzise interpretiert werden.

<table>
<thead>
  <tr>
    <th>Objekt</th>
    <th>Sichtbarkeit</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Konto</td>
    <td>Dauerhaft</td>
  </tr>
  <tr>
    <td>Kontakt</td>
    <td>Dauerhaft</td>
  </tr>
  <tr>
    <td>Lead</td>
    <td>Dauerhaft</td>
  </tr>
  <tr>
    <td>User Touchpoints</td>
    <td>Letzte 5 Jahre, basierend auf dem Touchpoint-Datum</td>
  </tr>
  <tr>
    <td>Kosten</td>
    <td>Letzte 2 Jahre</td>
  </tr>
  <tr>
    <td>Konversionsraten</td>
    <td>Letzte 2 Jahre</td>
  </tr>
  <tr>
    <td>Opportunity</td>
    <td>Letzte 2 Jahre, basierend auf Opportunity-Abschlussdatum</td>
  </tr>
  <tr>
    <td>Stadienübergänge (Lead und Opportunity)</td>
    <td>Letzte 5 Jahre, basierend auf Übergang im Datum</td>
  </tr>
  <tr>
    <td>Kampagne</td>
    <td>Dauerhaft </td>
  </tr>
  <tr>
    <td>Kampagnenmitglieder</td>
    <td>Letzte 5 Jahre, basierend auf dem Erstellungsdatum des Kampagnenmitglieds</td>
  </tr>
  <tr>
    <td>CRM-Aufgaben</td>
    <td>Letzte 5 Jahre, basierend auf dem Erstellungsdatum der Aufgabe</td>
  </tr>
  <tr>
    <td>CRM-Ereignisse</td>
    <td>Letzte 5 Jahre, basierend auf dem Startdatum des Ereignisses</td>
  </tr>
  <tr>
    <td>Aktivitäten (Marketo und AEP)</td>
    <td>Letzte 5 Jahre, basierend auf dem Ereignisdatum</td>
  </tr>
  <tr>
    <td>Sessions </td>
    <td>Letzte 5 Jahre, basierend auf dem Ereignisdatum</td>
  </tr>
  <tr>
    <td>Seitenansichten</td>
    <td>Letzte 5 Jahre, basierend auf dem Ereignisdatum</td>
  </tr>
  <tr>
    <td>Formularsendungen</td>
    <td>Letzte 5 Jahre, basierend auf dem Ereignisdatum</td>
  </tr>
</tbody>
</table>
