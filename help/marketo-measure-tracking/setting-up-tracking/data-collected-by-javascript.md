---
description: Von JavaScript erfasste Daten - [!DNL Marketo Measure] - Produktdokumentation
title: Von JavaScript erfasste Daten
feature: Tracking
source-git-commit: 2be08b96fb9f6d027e80751db64f16a7f2893764
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 8%

---

# Von JavaScript erfasste Daten {#data-collected-by-javascript}

Erfahren Sie mehr über die von Marketo Measure JavaScript bei der Bereitstellung erfassten Daten.

**Beispielanfrage:**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure erfasst die folgenden allgemeinen Daten für alle Anforderungstypen:

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
    <td>Anforderungs-Header</td>
    <td>IP-Adresse</td>
    <td>Zeichenfolge</td>
    <td>Der Standort des Benutzers wird durch die GeoIP-Suche ermittelt. Diese Daten sind temporär und nicht dauerhaft gespeichert.</td>
  </tr>
  <tr>
    <td>Anforderungs-Header</td>
    <td>Benutzeragenten-Zeichenfolge</td>
    <td>Zeichenfolge</td>
    <td>Bestimmt, welches Gerät der Benutzer verwendet.</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_u</td>
    <td>Zeichenfolge</td>
    <td>Bizible-Cookie-ID</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_l</td>
    <td>Zeichenfolge</td>
    <td>Aktuelle Seiten-URL</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_t</td>
    <td>long</td>
    <td>Aktivitätszeitstempel</td>
  </tr>
  <tr>
    <td>Abfrageparameter</td>
    <td>_biz_i</td>
    <td>Zeichenfolge</td>
    <td>Aktueller Seitentitel</td>
  </tr>
</tbody>
</table>

Zusätzlich zu den oben genannten allgemeinen Daten hängt bizible.js auch zusätzliche Daten an, die von den unten spezifizierten Anfragetypen abhängen:

<table>
<thead>
  <tr>
    <th>Anforderungstyp</th>
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
    <td>Zeichenfolge</td>
    <td>URL der Referrer-Seite</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>Zeichenfolge</td>
    <td>Die Bildschirmauflösung des Hash-Clients.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>Zeichenfolge</td>
    <td>Optionaler Parameter. Wenn dieser Parameter vorhanden ist, zeigt er an, dass der Mandant bizible.js so konfiguriert, dass vor dem Tracking auf die Zustimmung der Benutzer gewartet wird, und dass bizible.js die Zustimmung des Benutzers erhalten hat, verfolgt zu werden.</td>
  </tr>
  <tr>
    <td>Formularübermittlungen</td>
    <td>/form</td>
    <td>eMail</td>
    <td>Zeichenfolge</td>
    <td>Einfache Text-E-Mail-Adresse.</td>
  </tr>
  <tr>
    <td>Benutzer-ID-Zuordnung</td>
    <td>/u</td>
    <td>mapType</td>
    <td>enum</td>
    <td>Welche Art von Benutzer-ID-Mapping bizible.js erkannt hat (Marketo Munchkin-ID und Adobe ECID)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>mapValue</td>
    <td>Zeichenfolge</td>
    <td>Der tatsächliche Drittanbieter-Cookie-ID-Wert der oben genannten Integration.</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible ist der frühere Name von Marketo Measure.
