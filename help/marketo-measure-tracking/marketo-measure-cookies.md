---
description: '[!DNL Marketo Measure] Cookies - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Cookies'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 85%

---

# Marketo Measure-Cookies {#marketo-measure-cookies}

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure]-Cookies, die auf Ihre Site geladen werden, wenn Sie [!DNL Marketo Measure]-JavaScript auf Ihren Landingpages anwenden. Diese Informationen können während der Implementierung für das Web-Entwicklungs-Team nützlich sein.

>[!IMPORTANT]
>
>Aus Datenschutzgründen werden Drittanbieter-Cookies immer seltener verwendet. Die von Google Chrome angekündigte Einstellung von Drittanbieter-Cookies im 3. Quartal 2024 stellt effektiv das Ende dieser Tracking-Methode dar. Daher stellt Adobe die Marketo Measure-Funktionen, die auf Drittanbieter-Cookies basieren, ein. Dies betrifft insbesondere das Domain-übergreifende Tracking und die Viewthrough-Attribution, die das Impressions-Cookie von Google/DoubleClick verwenden. Andere Funktionen von Marketo Measure sind davon nicht betroffen. Die Verwendung von Erstanbieter-Cookies ist ebenfalls nicht betroffen. In Anbetracht des Zeitplans von Google ist das geplante Einstellungsdatum der beiden oben genannten Funktionen der 1.6.2024. Zugehörige Daten, die vor diesem Datum erfasst wurden, stehen Adobe-Kundinnen und -Kunden weiterhin zur Verfügung.

| Cookie-Name | Cookie-Typ | Zweck | Ablaufdatum | Flag „Sicher“ gesetzt? | Flag „Nur HTTP“ gesetzt? | Cookie-Setzer |
| --- | --- | --- | --- | --- | --- | --- |
| `_biz_uid` | Erstanbieter | Identifizieren Sie eine Benutzerin bzw. einen Benutzer eindeutig in der aktuellen Domain. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_nA` | Erstanbieter | Eine Sequenznummer, die Marketo Measure für alle Anforderungen für die interne Diagnose enthält. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_flagsA` | Erstanbieter | Ein Cookie, in dem verschiedene Benutzerinformationen gespeichert werden, z. B. Formularübermittlung, Domain-übergreifende Migration, Durchsichts-Pixel, Tracking-Opt-out-Status usw. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_pendingA` | Erstanbieter | Speichert vorübergehend Analysedaten, bis sie erfolgreich an den Marketo Measure-Server gesendet wurden. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_ABTestA` | Erstanbieter | Liste der bereits gemeldeten Prüfsummen aus AB-Testdaten von Optimizely und Visual Web Optimizer, die `bizible.js` daran hindern, die erfassten Daten erneut zu senden. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_EventA` | Erstanbieter | Liste der von Bizible Events gemeldeten Prüfsummen, um zu verhindern, dass `bizible.js` erfasste Daten erneut senden. | 1 Jahr | Nein | Nein | `bizible.js` |
| `_biz_su` | Erstanbieter | Universelle Benutzer-ID zur Domain-übergreifenden Identifizierung einer Benutzerin oder eines Benutzers, die nur für Mandanten mit Integration unter Umgehung von ITP-Beschränkungen gilt. | 1 Jahr | Ja | Nein | Edgecast |
| `_BUID` | Drittanbieter, domain=.bizible.com | Universelle Benutzer-ID zur Domain-übergreifenden Identifizierung einer Benutzerin oder eines Benutzers. | 1 Jahr | Ja | Nein | Edgecast |
| `_BUID` | Drittanbieter, domain=.bizibly.com | Zuordnung zwischen der Marketo Measure-Cookie-ID in der Domain des Mandanten und der zugehörigen DoubleClick-Impressions-Cookie-ID. | 1 Jahr | Ja | Nein | Edgecast |

Wenn während der JavaScript-Einrichtung eine Web Application Firewall-Warnung (WAF) ausgelöst wird, können Benutzende diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![Wenn während der JavaScript eine Warnung bezüglich Web Application Firewall (WAF) ausgelöst wird](assets/adding-script-1.png)
