---
description: Von JavaScript erfasste Daten für Marketo Measure-Benutzende
title: Von JavaScript erfasste Daten
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 77%

---

# Von JavaScript erfasste Daten {#data-collected-by-javascript}

Erfahren Sie mehr über die Daten, die von Marketo Measure JavaScript bei der Bereitstellung erfasst werden.

**Beispielanfrage:**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure erfasst die folgenden allgemeinen Daten für alle Anfragetypen:

| Herkunft | Name | Datentyp | Zweck |
| --- | --- | --- | --- |
| Anfragen-Header | IP-Adresse | string | Der Standort des Benutzers oder der Benutzerin wird durch eine GeoIP-Suche ermittelt. Diese Daten sind temporär und nicht dauerhaft gespeichert. |
| Anfragen-Header | User-Agent-Zeichenfolge: | string | Bestimmt, welches Gerät die Person verwendet. |
| Abfrageparameter | `_biz_u` | string | Bizible Cookie-ID. |
| Abfrageparameter | `_biz_l` | string | URL der aktuellen Seite. |
| Abfrageparameter | `_biz_t` | long | Zeitstempel der Aktivität. |
| Abfrageparameter | `_biz_i` | string | Aktueller Seitentitel. |

Zusätzlich zu den oben genannten allgemeinen Daten hängt bizible.js auch zusätzliche Daten an, abhängig von den unten spezifizierten Anfragetypen:

| Anfragetyp | Anfragepfad | Zusätzlicher Abfrageparameter | Datentyp | Zweck |
| --- | --- | --- | --- | --- |
| Seitenansicht | `/ipv` | `_biz_r` | string | URL der Referrer-Seite. |
|  |  | `_biz_h` | string | Die Bildschirmauflösung des Hash-Clients. |
|  |  | `_biz_c` | string | Optionaler Parameter. Wenn dieser Parameter vorhanden ist, zeigt er an, dass der Mandant `bizible.js` so konfiguriert, dass er auf das Einverständnis des Benutzers wartet, bevor er das Tracking durchführt, und dass `bizible.js` das Einverständnis des Benutzers zur Nachverfolgung erhalten hat. |
| Formularabsendungen | `/frm` | `eMail` | string | E-Mail-Adresse in einfachem Text. |
| Benutzer-ID-Zuordnung | `/u` | `mapType` | enum | Welche Art von Benutzer-ID-Zuordnung erkannt `bizible.js` (Marketo Munchkin ID und Adobe ECID) |
|  |  | `mapValue` | string | Der tatsächliche Cookie-ID-Wert des Drittanbieters der oben genannten Integration. |

>[!NOTE]
>
>Bizible ist der frühere Name von Marketo Measure.
