---
unique-page-id: 18874590
description: „[!DNL Marketo Measure]-Cookies – [!DNL Marketo Measure] – Produktdokumentation“
title: „[!DNL Marketo Measure]-Cookies“
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 69304dddf3569cd92c95a50e9a2e346acdad0f43
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 42%

---

# Marketo Measure-Cookies {#marketo-measure-cookies}

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure]-Cookies, die auf Ihre Site geladen werden, wenn Sie [!DNL Marketo Measure]-JavaScript auf Ihren Landingpages anwenden. Diese Informationen können während der Implementierung für das Web-Entwicklungs-Team nützlich sein.

<table>
<thead>
  <tr>
    <th>Cookie-Name</th>
    <th>Cookie-Typ</th>
    <th>Zweck</th>
    <th>Ablaufdatum</th>
    <th>Hat sicheres Flag gesetzt?<br></th>
    <th>Hat nur HTTP-Flag gesetzt?</th>
    <th>Cookie-Setter</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>Erstanbieter</td>
    <td>Identifizieren Sie einen Benutzer eindeutig in der aktuellen Domäne.</td>
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
    <td>Ein Cookie, in dem verschiedene Benutzerinformationen gespeichert werden, z. B. Formularübermittlung, domänenübergreifende Migration, Durchsichts-Pixel, Tracking-Opt-out-Status usw.</td>
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
    <td>Liste der Prüfsummen aus "Optimizely"und "Visual Web Optimizer"ABTests von Daten, die bereits gemeldet wurden, verhindern, dass bizible.js erfasste Daten erneut sendet.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>Erstanbieter</td>
    <td>Liste der von Bizible-Ereignissen gemeldeten Prüfsummen, um zu verhindern, dass bizible.js erfasste Daten erneut sendet.</td>
    <td>1 Jahr</td>
    <td>Nein</td>
    <td>Nein</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>Erstanbieter</td>
    <td>Universelle Benutzer-ID zur domänenübergreifenden Identifizierung eines Benutzers, die nur für Mandanten mit Integration unter Umgehung von ITP-Beschränkungen gilt.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Drittanbieter, Domäne=.<a href="http://bizible.com/">bizible.com</a></td>
    <td>Universelle Benutzer-ID zur domänenübergreifenden Identifizierung eines Benutzers.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Drittanbieter, Domäne=.<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>Mapping zwischen der Marketo Measure-Cookie-ID in der Domäne des Mandanten und der zugehörigen DoubleClick-Impressions-Cookie-ID.</td>
    <td>1 Jahr</td>
    <td>Ja</td>
    <td>Nein</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

Wenn während des JavaScript-Setups eine Web Application Firewall(WAF)-Warnung ausgelöst wird, können Benutzende diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/marketo-measure-cookies-1.png)
