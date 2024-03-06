---
unique-page-id: 35586069
description: Sicherstellen der Zustimmung für die DSGVO in Marketo Measure JS - Marketo Measure - Produktdokumentation
title: Sicherstellen der Zustimmung zur DSGVO in Marketo Measure JS
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Sicherstellen der Zustimmung zur DSGVO in Marketo Measure JS {#ensuring-consent-for-gdpr-in-marketo-measure-js}

Die Datenschutz-Grundverordnung (DSGVO) ist eine EU-Rechtsvorschrift, die am 25. Mai 2018 in Kraft getreten ist.

## Überblick {#overview}

Ziel der DSGVO ist es, die Rechte der betroffenen Personen in der Europäischen Union (EU) und im Europäischen Wirtschaftsraum (EWR) hinsichtlich der Verwendung und des Schutzes ihrer personenbezogenen Daten zu stärken. &quot;Personenbezogene Daten&quot;sind alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gilt für Organisationen innerhalb oder außerhalb der EU, die Waren oder Dienstleistungen für betroffene Personen in der EU und im EWR vermarkten und/oder deren Verhalten verfolgen. Wenn Sie mit Datensubjekten in Europa Geschäfte machen, die die Verarbeitung ihrer personenbezogenen Daten beinhalten, gilt diese Gesetzgebung für Sie. Bei Verstößen gegen die Verordnung werden erhebliche Geldbußen verhängt, wobei die Höchststrafe für einen einzigen Verstoß 20 Millionen Euro oder 4 % des weltweiten Jahresumsatzes beträgt, je nachdem, welcher Betrag höher ist.

Standardmäßig ist [!DNL bizible.js] erfasst die Analysedaten von Benutzern, es sei denn, sie sind so konfiguriert, dass auf die Zustimmung gewartet wird. Wann [!DNL bizible.js] so konfiguriert ist, dass auf die Zustimmung des Benutzers gewartet wird, werden erst Cookies erstellt oder Analysedaten gesendet, nachdem die Zustimmung eingeholt wurde.

## Warten auf Zustimmung {#how-to-wait-for-consent}

Es gibt zwei Möglichkeiten, [!DNL bizible.js] um auf die Zustimmung zu warten.

Option 1 - Standard ersetzen [!DNL bizible.js] Skript-Tag mit:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Wenn Sie [!DNL Google Tag Manager] Skript installieren** Beachten Sie, dass GTM Datenattribute entfernt. Verwenden Sie daher stattdessen das folgende Skript:

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>In diesem Fall [!DNL bizible.js] hängt ein on-click -Ereignis an das HTML-Element mit der ID &quot;ConsentButtonId&quot;an.

Wenn auf dieses HTML-Element geklickt wird, [!DNL bizible.js] erstellt ein Cookie, um sich zu merken, dass die Einwilligung des Benutzers eingegangen ist, und wie gewohnt mit der Erfassung von Analysedaten zu beginnen.

**-or-**

Option 2 - Standard ersetzen [!DNL bizible.js] Skript-Tag mit:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Diese Funktion [!DNL bizible.js] nicht nachverfolgen, bis die Zustimmung eingeholt wurde, was mit der folgenden JS-API erfolgen kann:

*Fenster[&quot;Bizible&quot;] = window[&quot;Bizible&quot;] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };*

*Bizible. Push(&#39;Consent&#39;, true);*

**Wenn Sie [!DNL Google Tag Manager] Skript installieren** Beachten Sie, dass GTM Datenattribute entfernt. Verwenden Sie daher stattdessen das folgende Skript:

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js erstellt ein Cookie, um sich zu merken, dass die Zustimmung des Benutzers einging, und beginnt mit der Erfassung von Analysedaten wie gewohnt erst, nachdem die JS-API aufgerufen wurde.

Im Gegensatz dazu können Kunden diese API auch verwenden, um die Zustimmung des Benutzers zu widerrufen:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Wenn dieser Code ausgeführt wird, löscht er alle Cookies, die [!DNL bizible.js] zuvor erstellt wurde und die Erfassung von Analysedaten nur dann wieder aufnimmt, wenn der Benutzer die Analyse abstimmt.
