---
unique-page-id: 18874749
description: Hinzufügen von [!DNL Marketo Measure] Skript zu [!DNL Uberflip] Forms - [!DNL Marketo Measure]
title: Hinzufügen von [!DNL Marketo Measure] Skript zu [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Hinzufügen von [!DNL Marketo Measure] Skript zu [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Wenn Sie derzeit [!DNL Uberflip] zur Verwaltung Ihres Inhalts verwenden, müssen Sie diese erforderlichen Schritte ausführen, um sicherzustellen, dass [!DNL Marketo Measure] diese Formularübermittlungen verfolgt. Ihr Erfolgsmanager bei [!DNL Uberflip] sollte Ihnen dabei ebenfalls helfen können.

1. Fügen Sie dieses Skript zum Abschnitt [!UICONTROL Benutzerdefinierter Code>HTML] von [!DNL Uberflip] hinzu.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Stellen Sie sicher, dass dieser [!DNL Marketo Measure]-Präambelcode sowohl beim Laden der Seite als auch bei AJAX Seitenänderung ausgelöst wird. Führen Sie dies im Abschnitt [!UICONTROL Benutzerspezifischer Code > JS] aus.

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Fügen Sie diese Präambel sowohl den Hooks für das [!DNL Hubs.onLoad]- als auch den AJAX [!DNL Hubs.onPageChange]-JavaScript-Ereignis hinzu. (Hinweis: Auch in diesen Ereignis-Hooks kann anderer Code enthalten sein. Stellen Sie sicher, dass Sie auch die Präambel einschließen.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Erstellen und definieren Sie eine Funktion, die Daten bei einer Formular-CTA-Übermittlung an Bizible übergibt. Dies wird im Abschnitt [!UICONTROL Benutzerspezifischer Code > JavaScript] erläutert. (Hinweis: Für diese Funktion ist nur der ctaData-Parameter erforderlich, den Uberflip bereitstellt. Sie können jedoch die anderen Parameter ctaId und ctaName einfügen, falls der Benutzer seinen Code anpassen möchte, um diese Daten ebenfalls weiterzugeben.)

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Wenn ein Formular-CTA gesendet wird, stellen Sie sicher, dass Ihre [!DNL Marketo Measure] -Funktion unten ausgeführt wird. Dies erfolgt im Abschnitt [!UICONTROL Benutzerspezifischer Code > JS] . (Hinweis: Möglicherweise enthält der Haken für das JavaScript-Ereignis &quot;Hubs.onCtaFormSubmitSuccess&quot;auch anderen Code. Stellen Sie sicher, dass Sie auch diesen Funktionsaufruf einbeziehen.)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
