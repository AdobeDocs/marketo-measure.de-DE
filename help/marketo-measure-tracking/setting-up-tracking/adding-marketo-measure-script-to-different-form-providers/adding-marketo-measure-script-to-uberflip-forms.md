---
unique-page-id: 18874749
description: ' [!DNL Marketo Measure]  zu  [!DNL Uberflip] Forms hinzufügen - [!DNL Marketo Measure]'
title: ' [!DNL Marketo Measure]  zu  [!DNL Uberflip] Forms hinzufügen'
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Hinzufügen [!DNL Marketo Measure] Skripts [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Wenn Sie [!DNL Uberflip] derzeit zur Verwaltung Ihrer Inhalte verwenden, ist es wichtig, dass Sie diese erforderlichen Schritte ausführen, um sicherzustellen, dass [!DNL Marketo Measure] diese Formularübermittlungen nachverfolgt. Auch Ihr Success Manager bei [!DNL Uberflip] sollte Ihnen dabei behilflich sein können.

1. Fügen Sie dieses Skript zum Abschnitt [!UICONTROL Benutzerdefinierter Code>HTML&quot; von [!DNL Uberflip] &#x200B;].

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Stellen Sie sicher, dass dieser [!DNL Marketo Measure] Präambelcode sowohl beim Laden der Seite als auch beim Ändern der AJAX-Seite ausgelöst wird. Gehen Sie dazu im Abschnitt [!UICONTROL Benutzerdefinierter Code>JS] vor

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Fügen Sie diese Präambel den [!DNL Hubs.onLoad] und den [!DNL Hubs.onPageChange] AJAX JavaScript-Ereignis-Hooks gemäß unten hinzu. (Hinweis: In diesen Ereignis-Hooks kann auch anderer Code enthalten sein. Stellen Sie sicher, dass Sie auch die Präambel einbeziehen.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Erstellen und definieren Sie eine Funktion, die bei Übermittlung eines Formulars an CTA Daten an Bizible überträgt. Dies geht in den Abschnitt [!UICONTROL Benutzerdefinierter Code>JavaScript] ein. (Hinweis: Diese Funktion erfordert nur den von Uberflip bereitgestellten ctaData-Parameter, Sie können jedoch die anderen Parameter ctaId und ctaName einbeziehen, falls der Benutzer seinen Code anpassen möchte, um auch diese Daten zu übergeben).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Vergewissern Sie sich beim Übermitteln eines Formular-CTA, dass Ihre [!DNL Marketo Measure] wie unten beschrieben ausgeführt wird. Dies geschieht im Abschnitt [!UICONTROL Benutzerdefinierter Code>JS] . (Hinweis: Möglicherweise befinden sich andere Codes im JavaScript-Ereignis-Hook „Hubs.onCtaFormSubmitSuccess“. Stellen Sie sicher, dass Sie auch diesen Funktionsaufruf einbeziehen).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
