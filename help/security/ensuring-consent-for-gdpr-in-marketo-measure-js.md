---
description: Sicherstellen der Zustimmung für die DSGVO in Marketo Measure JS
title: Sicherstellen der Zustimmung für die DSGVO in Marketo Measure JS
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 100%

---


# Sicherstellen der Zustimmung für die DSGVO in Marketo Measure JS {#ensuring-consent-for-gdpr-in-marketo-measure-js}

Die Datenschutz-Grundverordnung (DSGVO) ist eine EU-Rechtsvorschrift, die am 25. Mai 2018 in Kraft getreten ist.

## Überblick {#overview}

Ziel der DSGVO ist es, die Rechte der betroffenen Personen in der Europäischen Union (EU) und im Europäischen Wirtschaftsraum (EWR) hinsichtlich der Verwendung und des Schutzes ihrer personenbezogenen Daten zu stärken. „Personenbezogene Daten“ sind alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gilt für alle Organisationen innerhalb oder außerhalb der EU, die Waren oder Dienstleistungen für betroffene Personen in der EU und im EWR vermarkten und/oder deren Verhalten nachverfolgen. Wenn Sie mit betroffenen Personen in Europa Geschäfte machen, die die Verarbeitung ihrer personenbezogenen Daten beinhalten, gilt diese Gesetzgebung für Sie. Bei Verstößen gegen die Verordnung werden erhebliche Geldbußen verhängt, wobei die Höchststrafe für einen einzigen Verstoß 20 Millionen Euro oder 4 % des weltweiten Jahresumsatzes beträgt, je nachdem, welcher Betrag höher ist.

Standardmäßig sammelt [!DNL bizible.js] die Analysedaten der Benutzenden, es sei denn, es ist so konfiguriert, dass es auf die Zustimmung wartet. Wenn [!DNL bizible.js] so konfiguriert ist, dass es auf die Zustimmung der Benutzenden wartet, erstellt es keine Cookies und sendet keine Analysedaten, bis die Zustimmung erteilt wurde.

## Warten auf Zustimmung {#how-to-wait-for-consent}

Es gibt zwei Möglichkeiten, [!DNL bizible.js] so einzustellen, dass auf die Zustimmung gewartet wird.

Option 1: Ersetzen des Standard-Skript-Tags [!DNL bizible.js] durch:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Wenn Sie [!DNL Google Tag Manager] verwenden, um das Skript zu installieren**, denken Sie daran, dass GTM die Datenattribute entfernt. Verwenden Sie stattdessen das folgende Skript:

```html
<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async></script>
```

>[!NOTE]
>In diesem Fall fügt [!DNL bizible.js] dem HTML-Element mit der ID „ConsentButtonId“ ein On-Click-Ereignis zu.

Wenn dieses HTML-Element angeklickt wird, erstellt [!DNL bizible.js] ein Cookie zur Erinnerung daran, dass die Benutzenden ihr Einverständnis gegeben haben, und beginnt wie gewohnt mit der Erfassung von Analysedaten.

**– oder –**

Option 2: Ersetzen des Standard-Skript-Tags [!DNL bizible.js] durch:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Damit wird [!DNL bizible.js] angewiesen, nichts nachzuverfolgen, bis eine Zustimmung vorliegt, was mit der folgenden JS-API geschehen kann:

*window[&#39;Bizible&#39;] = window[&#39;Bizible&#39;] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };*

*Bizible. Push(&#39;Consent&#39;, true);*

**Wenn Sie [!DNL Google Tag Manager] verwenden, um das Skript** zu installieren, denken Sie daran, dass GTM die Datenattribute entfernt. Verwenden Sie stattdessen das folgende Skript:

```html
<span id="bizible-settings" data-requires-user-consent="true"></span>
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async></script>
```

>[!NOTE]
>bizible.js erstellt ein Cookie zur Erinnerung daran, dass die Zustimmung der Benutzerin bzw. des Benutzers eingegangen ist, und beginnt mit der Erfassung von Analysedaten wie gewohnt erst, nachdem die JS-API aufgerufen wurde.

Im Gegensatz dazu können Kundinnen und Kunden diese API auch verwenden, um die Zustimmung der Person zu widerrufen:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Wenn dieser Code ausgeführt wird, löscht er alle Cookies, die [!DNL bizible.js] zuvor erstellt hat, und nimmt die Sammlung von Analysedaten nur dann wieder auf, wenn die Person erneut zustimmt.
