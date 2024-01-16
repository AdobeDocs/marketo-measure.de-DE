---
unique-page-id: 18874590
description: „[!DNL Marketo Measure]-Cookies – [!DNL Marketo Measure] – Produktdokumentation“
title: „[!DNL Marketo Measure]-Cookies“
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 327daa56fe1b346d067f2e0fb39006b91e6849ee
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 74%

---

# Marketo Measure-Cookies {#marketo-measure-cookies}

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure]-Cookies, die auf Ihre Site geladen werden, wenn Sie [!DNL Marketo Measure]-JavaScript auf Ihren Landingpages anwenden. Diese Informationen können während der Implementierung für das Web-Entwicklungs-Team nützlich sein.

>[!IMPORTANT]
>
>Aus Datenschutzgründen befinden sich Drittanbieter-Cookies auf dem Weg. Die angekündigte Einstellung von Drittanbieter-Cookies im 3. Quartal 2024 durch Google Chrome stellt das Ende dieser Tracking-Form dar. Daher stellt Adobe Marketo Measure-Funktionen, die auf Drittanbieter-Cookies basieren, ein. Dies betrifft insbesondere das domänenübergreifende Tracking und die Durchsichtszuordnung, die das Impressions-Cookie Google/DoubleClick verwenden. Andere Funktionen von Marketo Measure sind davon nicht betroffen. Die Verwendung von Erstanbieter-Cookies ist ebenfalls nicht betroffen. In Anbetracht des Zeitplans von Google wird für die beiden oben genannten Funktionen vom 1.6.2024 erwartet. Zugehörige Daten, die vor diesem Datum erfasst wurden, stehen Adobe-Kunden weiterhin zur Verfügung.

<table>
<thead>
  <tr>
    <th>Cookie-Name</th>
    <th>Cookie-Typ</th>
    <th>Zweck</th>
    <th>Ablaufdatum</th>
    <th>Flag „Sicher“ gesetzt?<br></th>
    <th>Flag „Nur HTTP“ gesetzt?</th>
    <th>Cookie-Setzer</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>Erstanbieter</td>
    <td>Identifizieren Sie eine Benutzerin bzw. einen Benutzer eindeutig in der aktuellen Domain.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>Erstanbieter</td>
    <td>Eine Sequenznummer, die Marketo Measure für alle Anforderungen für die interne Diagnose enthält.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>Erstanbieter</td>
    <td>Ein Cookie, in dem verschiedene Benutzerinformationen gespeichert werden, z. B. Formularübermittlung, Domain-übergreifende Migration, Durchsichts-Pixel, Tracking-Opt-out-Status usw.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>Erstanbieter</td>
    <td>Speichert vorübergehend Analysedaten, bis sie erfolgreich an den Marketo Measure-Server gesendet wurden.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>Erstanbieter</td>
    <td>Liste der Prüfsummen von ABTests-Daten aus Optimizely und Visual Web Optimizer, die bereits gemeldet wurden, was bizible.js daran hindert, erfasste Daten erneut zu senden.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>Erstanbieter</td>
    <td>Liste von Prüfsummen, die von Bizible-Ereignissen gemeldet wurden, um zu verhindern, dass bizible.js erfasste Daten erneut sendet.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>Erstanbieter</td>
    <td>Universelle Benutzer-ID zur Domain-übergreifenden Identifizierung einer Benutzerin oder eines Benutzers, die nur für Mandanten mit Integration unter Umgehung von ITP-Beschränkungen gilt.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Drittanbieter, Domain=.<a href="http://bizible.com/">bizible.com</a></td>
    <td>Universelle Benutzer-ID zur Domain-übergreifenden Identifizierung einer Benutzerin oder eines Benutzers.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Drittanbieter, Domain=.<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>Zuordnung zwischen der Marketo Measure-Cookie-ID in der Domain des Mandanten und der zugehörigen DoubleClick-Impressions-Cookie-ID.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

Wenn während des JavaScript-Setups eine Web Application Firewall(WAF)-Warnung ausgelöst wird, können Benutzende diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/marketo-measure-cookies-1.png)
