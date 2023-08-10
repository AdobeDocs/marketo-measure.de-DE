---
unique-page-id: 18874590
description: „[!DNL Marketo Measure]-Cookies – [!DNL Marketo Measure] – Produktdokumentation“
title: „[!DNL Marketo Measure]-Cookies“
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%

---

# Marketo Measure-Cookies {#marketo-measure-cookies}

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure]-Cookies, die auf Ihre Site geladen werden, wenn Sie [!DNL Marketo Measure]-JavaScript auf Ihren Landingpages anwenden. Diese Informationen können während der Implementierung für das Web-Entwicklungs-Team nützlich sein.

| **Cookie-Name** | **Cookie-Typ** | **Zweck** |
|---|---|---|
| _BUID | Drittanbieter, gespeichert unter der Domain „.bizible.com“ | Universelle Benutzer-ID zur Identifikation derselben Person über mehrere Client-Domains hinweg. |
| _biz_uid | Erstanbieter | Benutzer-ID in der aktuellen Domain. |
| _biz_sid | Erstanbieter | Sitzungs-ID der Benutzerin bzw. des Benutzers |
| _biz_flagsA | Erstanbieter | Ein einzelnes Cookie, das verschiedene Informationen speichert, z. B. ob die Benutzerin oder der Benutzer ein Formular gesendet, eine Domain-übergreifende Migration durchgeführt, ein Viewthrough-Pixel gesendet oder sich vom Tracking abgemeldet hat. |
| _biz_nA | Erstanbieter | Sequenznummer, die von [!DNL Marketo Measure] bei allen Anfragen zu internen Diagnosezwecken eingeschlossen wird |
| _biz_dfsA | Erstanbieter | Speichert vorübergehend Daten zur Formularübermittlung, die erfolgt, bevor [!DNL bizible.js] Konfigurations-JS empfängt, um zu bestimmen, ob das Tracking-Formular in HTTPS aktiviert ist. |
| _biz_pendingA | Erstanbieter | Speichert vorübergehend Analysedaten, die noch nicht erfolgreich an den [!DNL Marketo Measure]-Server gesendet wurden. |

Wenn während des JavaScript-Setups eine Web Application Firewall(WAF)-Warnung ausgelöst wird, können Benutzende diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/marketo-measure-cookies-1.png)
