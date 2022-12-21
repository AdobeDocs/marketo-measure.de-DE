---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Cookies"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
source-git-commit: 3a13ab3e497652d1975e69280a3d224ac95504aa
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Cookies in Marketo messen {#marketo-measure-cookies}

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure] Cookies, die auf Ihre Site geladen werden, wenn Sie die [!DNL Marketo Measure] JavaScript auf Ihren Landingpages. Diese Informationen können dem Webentwicklungsteam während der Implementierung als nützlich dienen.

| **Cookie-Name** | **Cookie-Typ** | **Zweck** |
|---|---|---|
| _BUID | Drittanbieter, gespeichert unter der Domäne .bizible.com | Universelle Benutzer-ID zur Identifikation desselben Benutzers über die Domänen mehrerer Kunden hinweg. |
| _biz_uid | Erstanbieter | Benutzer-ID in der aktuellen Domäne. |
| _biz_sid | Erstanbieter | Sitzungs-ID des Benutzers. |
| _biz_flagsA | Erstanbieter | Ein einzelnes Cookie, das mehrere Informationen speichert, z. B. ob der Benutzer ein Formular gesendet hat, eine domänenübergreifende Migration durchgeführt, einen Viewthrough-Pixel gesendet, von der Verfolgung ausgeschlossen usw. |
| _biz_nA | Erstanbieter | Sequenznummer, die [!DNL Marketo Measure] umfasst für alle Anforderungen, zu internen Diagnosezwecken |
| _biz_dfsA | Erstanbieter | Speichert temporär Daten zur Formularübermittlung, die vor [!DNL bizible.js] empfängt eine Konfigurations-JS, um zu bestimmen, ob das Tracking-Formular in HTTPS aktiviert ist. |
| _biz_pendingA | Erstanbieter | Speichert vorübergehend Analysedaten, die nicht erfolgreich an gesendet wurden [!DNL Marketo Measure] -Server. |

Wenn während des JavaScript-Setups eine WAF-Warnung (Web Application Firewall) ausgelöst wird, können Benutzer diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/marketo-measure-cookies-1.png)
