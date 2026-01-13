---
description: Formularverarbeitung in AJAX - [!DNL Marketo Measure]
title: AJAX-Formularverarbeitung
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 1%

---


# AJAX-Formularverarbeitung {#ajax-form-handling}

Um Kundenkonversionen manuell an [!DNL Marketo Measure] zu melden, gibt es eine einfache API, die Sie verwenden können. Beide JavaScript-APIs sind automatisch auf Ihrer Site verfügbar, wenn Sie Trackingcode darauf haben. Sie müssen nichts Besonderes tun, um darauf zuzugreifen.

## Szenario 1: HTML-Formular mit einer AJAX-Übermittlung {#scenario-html-form-with-an-ajax-submit}

Wenn Sie Formulare verwenden, die AJAX (oder einen anderen Mechanismus), um Konvertierungsdaten vom Client an unsere Server zu senden, ist [!DNL Marketo Measure] möglicherweise nicht über die Kundenkonvertierung auf einem der von uns überwachten Standardpfade informiert. In diesem Szenario können wir eine einfache API verwenden (siehe unten).

Wenn Sie Ihre eigenen Formularübermittlungen bearbeiten, können Sie [!DNL Marketo Measure] explizit über die JavaScript aufrufen. [!DNL Marketo Measure] sammelt alle relevanten Informationen aus dem Formular und sendet sie asynchron an unsere Server.

**Im Folgenden finden Sie ein Codebeispiel unter Verwendung von JQuery (unter der Annahme, dass die ID im Formular „formId“ lautet):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  

// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**Im Folgenden finden Sie ein Codebeispiel, das JQuery nicht verwendet (unter der Annahme, dass die ID im Formular „formId“ ist):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  

// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Szenario 2: In einem Nicht-HTML-Formular erfasste Lead-Informationen {#scenario-lead-information-collected-in-a-non-html-form}

Wenn Informationen von einem konvertierten Lead mithilfe von JavaScript oder einfachen Textfeldern ohne HTML-Formular erfasst werden, funktioniert diese Lösung für Sie. Freigegeben unten ist die API, die in diesem Szenario verwendet werden soll:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  

// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

In diesem Code ist das Feld [!UICONTROL E]Mail) erforderlich. [!DNL Marketo Measure] sendet diese Daten asynchron an unsere Server.

## Szenario 3: Melden Sie Benutzerinformationen auf der Dankeseite {#scenario-report-user-information-from-the-thank-you-page}

Manchmal ist es praktischer, die Lead-Informationen nach dem Übermitteln des Formulars von der Dankeseite an [!DNL Marketo Measure] zu melden. Die einfachste Möglichkeit, diese Informationen zu melden, besteht darin, der Seite ein ausgeblendetes Element hinzuzufügen, das Informationen aus der Formularübermittlung enthält. [!DNL Bizible.js] lesen diese Informationen, wenn die Dankesseite geladen wurde.

**Beispiel:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

Es spielt keine Rolle, ob das ausgeblendete Element ein div, ein script oder ein anderer Tag-Typ ist. [!DNL Marketo Measure] sucht nach „id=„bizible.reportUser“, um die Informationen zu lesen.
