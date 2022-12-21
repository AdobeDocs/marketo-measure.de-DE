---
unique-page-id: 30082018
description: Verzögerte Cookie-Synchronisierung - [!DNL Marketo Measure] - Produktdokumentation
title: Verzögerte Cookie-Synchronisierung
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Verzögerte Cookie-Synchronisierung {#delayed-cookie-sync}

Diese Änderung an der Standardeinstellung [!DNL Marketo Measure] JavaScript stellt Folgendes bereit [!DNL bizible.js] API-Unterstützung, sodass Sie die JS so konfigurieren können, dass die Benutzeraktivitäten der Besucher vorübergehend gespeichert werden, die Informationen jedoch nicht an die [!DNL Marketo Measure] -Server, bis der Benutzer seine Zustimmung dazu erteilt.

## Anleitung {#how-to}

Standard ersetzen [!DNL bizible.js] Skript-Tag mit folgendem Inhalt:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

Das Attribut data-consent-button-id=&quot;ConsentButtonId&quot; gibt folgende Informationen an: [!DNL bizible.js] , damit keine Analysedaten gesendet werden, bis auf ein HTML-Element mit dieser ID geklickt wird.

Alternativ können Kunden die Variable [!UICONTROL data-consent-button-id] nicht vorhanden sein (z. B. &quot;foobar&quot;) und die folgende API verwenden, um [!DNL bizible.js] dass der Benutzer Folgendes zugestimmt hat:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>Die Benutzereinwilligung wird im Cookie gespeichert, d. h., nachdem der Benutzer seine Einwilligung gegeben hat, muss dieser Aufruf auf allen nachfolgenden Seiten nicht mehr ausgeführt werden.

## Einschränkung {#limitation}

weil [!DNL bizible.js] speichert nicht gesendete Web-Aktivitäten vorübergehend in Erstanbieter-Cookies von Kunden und die Größe von Erstanbieter-Cookies ist begrenzt. Es können immer nur drei nicht gesendete Anfragen gespeichert werden.

Wenn bereits drei ausstehende Anforderungen vorliegen, werden alle nachfolgenden Aktivitäten ignoriert. Dadurch wird die erste Seitenansicht beibehalten, die wertvolle Referrer-Informationen enthält.
