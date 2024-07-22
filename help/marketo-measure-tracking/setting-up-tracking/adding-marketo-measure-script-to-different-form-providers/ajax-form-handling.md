---
unique-page-id: 18874745
description: AJAX Form Handling - [!DNL Marketo Measure]
title: AJAX-Formularverarbeitung
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 1%

---

# AJAX-Formularverarbeitung {#ajax-form-handling}

Um Kundenkonversionen manuell auf [!DNL Marketo Measure] zu melden, gibt es eine einfache API, die Sie verwenden können. Beide dieser JavaScript-APIs sind automatisch auf Ihrer Site verfügbar, wenn Sie Trackingcode darauf haben. Es ist nicht erforderlich, etwas Besonderes zu tun, um darauf zuzugreifen.

## Szenario 1: HTML-Formular mit AJAX Senden {#scenario-html-form-with-an-ajax-submit}

Wenn Sie Formulare mit AJAX (oder einem anderen Mechanismus) verwenden, um Konversionsdaten vom Client an unsere Server zu senden, ist [!DNL Marketo Measure] möglicherweise nicht über die Kundenkonvertierung über einen der von uns überwachten Standardpfade informiert. In diesem Szenario können wir eine einfache API verwenden (siehe unten).

Wenn Sie Ihre eigenen Formularübermittlungen verarbeiten, können Sie [!DNL Marketo Measure] explizit über die JavaScript aufrufen. [!DNL Marketo Measure] erfasst alle relevanten Informationen aus dem Formular und veröffentlicht sie asynchron auf unseren Servern.

**Nachfolgend finden Sie ein Codebeispiel, das JQuery verwendet (vorausgesetzt, die ID im Formular lautet &quot;formId&quot;):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**Nachfolgend finden Sie ein Codebeispiel, das JQuery nicht verwendet (vorausgesetzt, die ID im Formular lautet &quot;formId&quot;):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Szenario 2: Lead-Informationen, die in einem Nicht-HTML-Formular erfasst werden {#scenario-lead-information-collected-in-a-non-html-form}

Wenn Informationen aus einem konvertierten Lead mit JavaScript oder einfachen Textfeldern ohne HTML-Formular erfasst werden, funktioniert diese Lösung für Sie. Im Folgenden finden Sie die API, die in diesem Szenario verwendet werden soll:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

In diesem Code ist das Feld [!UICONTROL email] erforderlich. [!DNL Marketo Measure] sendet diese Daten asynchron an unsere Server.

## Szenario 3 - Bericht zu Benutzerinformationen von der Dankeseite {#scenario-report-user-information-from-the-thank-you-page}

Manchmal ist es praktischer, die Lead-Informationen von der Dankeseite an [!DNL Marketo Measure] zu melden, nachdem das Formular gesendet wurde. Die einfachste Möglichkeit, diese Informationen zu melden, besteht darin, der Seite ein ausgeblendetes Element hinzuzufügen, das Informationen aus der Formularübermittlung enthält. [!DNL Bizible.js] liest diese Informationen, wenn die Dankeseite geladen wurde.

**Beispiel:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

Es spielt keine Rolle, ob das ausgeblendete Element ein div-, script- oder ein anderer Tag-Typ ist. [!DNL Marketo Measure] sucht nach id=&quot;bizible.reportUser&quot;, um die Informationen zu lesen.
