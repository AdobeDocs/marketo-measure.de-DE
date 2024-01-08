---
description: Von JavaScript erfasste Daten –  [!DNL Marketo Measure]  – Produktdokumentation
title: Von JavaScript erfasste Daten
feature: Tracking
source-git-commit: 4953d6c51a87669ced0a13e2a54810d14976585c
workflow-type: ht
source-wordcount: '232'
ht-degree: 100%

---

# Von JavaScript erfasste Daten {#data-collected-by-javascript}

Erfahren Sie mehr über die Daten, die von Marketo Measure JavaScript bei der Bereitstellung erfasst werden.

**Beispielanfrage:**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure erfasst die folgenden allgemeinen Daten für alle Anfragetypen:

<table>
<thead>
  <tr>
    <th>Herkunft</th>
    <th>Name</th>
    <th>Datentyp</th>
    <th>Zweck</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Anfragen-Header</td>
    <td>IP-Adresse</td>
    <td>string</td>
    <td>Der Standort des Benutzers oder der Benutzerin wird durch eine GeoIP-Suche ermittelt. Diese Daten sind temporär und nicht dauerhaft gespeichert.</td>
  </tr>
  <tr>
    <td>Anfragen-Header</td>
    <td>User-Agent-Zeichenfolge:</td>
    <td>string</td>
    <td>Bestimmt, welches Gerät die Person verwendet.</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_u</td>
    <td>string</td>
    <td>Bizible Cookie-ID.</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_l</td>
    <td>string</td>
    <td>URL der aktuellen Seite.</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_t</td>
    <td>long</td>
    <td>Zeitstempel der Aktivität.</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_i</td>
    <td>string</td>
    <td>Aktueller Seitentitel.</td>
  </tr>
</tbody>
</table>

Zusätzlich zu den oben genannten allgemeinen Daten hängt bizible.js auch zusätzliche Daten an, abhängig von den unten spezifizierten Anfragetypen:

<table>
<thead>
  <tr>
    <th>Anfragetyp</th>
    <th>Anfragepfad</th>
    <th>Zusätzlicher Abfrageparameter</th>
    <th>Datentyp</th>
    <th>Zweck</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Seitenansicht</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>string</td>
    <td>URL der Referrer-Seite.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>string</td>
    <td>Die Bildschirmauflösung des Hash-Clients.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>string</td>
    <td>Optionaler Parameter. Wenn dieser Parameter vorhanden ist, zeigt er an, dass der Mandant bizible.js so konfiguriert, dass vor dem Tracking auf das Einverständnis der Person gewartet wird, und dass bizible.js ihr Einverständnis für das Tracking erhalten hat.</td>
  </tr>
  <tr>
    <td>Formularabsendungen</td>
    <td>/frm</td>
    <td>eMail</td>
    <td>string</td>
    <td>E-Mail-Adresse in einfachem Text.</td>
  </tr>
  <tr>
    <td>Benutzer-ID-Zuordnung</td>
    <td>/u</td>
    <td>mapType</td>
    <td>enum</td>
    <td>Welche Art von Benutzer-ID-Zuordnung bizible.js erkannt hat (Marketo Munchkin-ID und Adobe ECID)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>mapValue</td>
    <td>string</td>
    <td>Der tatsächliche Cookie-ID-Wert des Drittanbieters der oben genannten Integration.</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible ist der frühere Name von Marketo Measure.
