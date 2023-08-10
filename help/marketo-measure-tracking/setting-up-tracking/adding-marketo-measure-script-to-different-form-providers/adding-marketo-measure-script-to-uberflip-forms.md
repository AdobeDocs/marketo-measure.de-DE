---
unique-page-id: 18874749
description: Hinzufügen [!DNL Marketo Measure] Skript für [!DNL Uberflip] FORMS - [!DNL Marketo Measure] - Produktdokumentation
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes für Forms [!DNL Uberflip]
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 3%

---

# Hinzufügen eines[!DNL Marketo Measure]-Skriptes für Forms[!DNL Uberflip] {#adding-marketo-measure-script-to-uberflip-forms}

Wenn Sie derzeit [!DNL Uberflip] Um Ihre Inhalte zu verwalten, müssen Sie diese erforderlichen Schritte ausführen, um sicherzustellen, dass [!DNL Marketo Measure] verfolgt diese Formularübermittlungen. Ihr Erfolgsmanager unter [!DNL Uberflip] sollte Ihnen auch dabei helfen können.

1. Fügen Sie dieses Skript zu [!DNL Uberflip]s [!UICONTROL Benutzerspezifischer Code > HTML] Abschnitt.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Stellen Sie sicher, dass [!DNL Marketo Measure] Präambelcode wird sowohl beim Laden der Seite als auch bei AJAX Seitenänderung ausgelöst. Führen Sie dies innerhalb der [!UICONTROL Benutzerspezifischer Code > JS] Abschnitt

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Sie fügen diese Präambel zu beiden [!DNL Hubs.onLoad] und [!DNL Hubs.onPageChange] AJAX JavaScript-Ereignis-Hooks nach unten. (Hinweis: In diesen Ereignis-Hooks können auch andere Codes enthalten sein. Stellen Sie sicher, dass Sie auch die Präambel einschließen.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Erstellen und definieren Sie eine Funktion, die Daten bei einer Formular-CTA-Übermittlung an Bizible pusst. Das geht in die [!UICONTROL Benutzerspezifischer Code > Javascript] Abschnitt. (Hinweis: Für diese Funktion ist nur der ctaData-Parameter erforderlich, den Uberflip bereitstellt. Sie können jedoch die anderen Parameter ctaId und ctaName einfügen, falls der Benutzer seinen Code anpassen möchte, um diese Daten ebenfalls weiterzugeben.)

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Stellen Sie beim Senden eines Formular-CTA sicher, dass Ihre [!DNL Marketo Measure] -Funktion unten ausgeführt. Dies geschieht innerhalb der [!UICONTROL Benutzerspezifischer Code > JS] Abschnitt. (Hinweis: Möglicherweise enthält der Javascript-Ereignis-Erweiterungspunkt &quot;Hubs.onCtaFormSubmitSuccess&quot;anderen Code. Stellen Sie sicher, dass Sie auch diesen Funktionsaufruf einbeziehen.)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
