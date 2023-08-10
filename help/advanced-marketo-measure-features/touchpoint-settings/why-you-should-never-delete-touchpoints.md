---
unique-page-id: 18874560
description: Warum sollten Touchpoints nie löschen? [!DNL Marketo Measure] - Produktdokumentation
title: Warum Sie Touchpoints nie löschen sollten
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Warum Sie Touchpoints nie löschen sollten {#why-you-should-never-delete-touchpoints}

Wenn Sie feststellen, dass es einen Touchpoint auf einer Gelegenheit gibt, der fälschlicherweise Attributionsgutschriften zugewiesen wird, wenden Sie sich an Ihren Kundenbetreuer, um die nächsten Schritte zu bestimmen. In diesen Situationen empfehlen wir die Verwendung der Touchpoint-Unterdrückungsfunktion des Käufers, um den Touchpoint aus SFDC und dem ROI-Dashboard zu entfernen. Ihr Kundenbetreuer kann Ihnen bei der Erstellung dieser Regeln helfen. Bitte löschen Sie diese Touchpoints nicht manuell selbst.

Die [!DNL Marketo Measure] Das Verarbeitungssystem registriert nicht, dass ein Touchpoint manuell aus SFDC gelöscht wurde. Bis heute gibt es keinen Trigger, der an unser System signalisiert, Daten anzupassen. [!DNL Marketo Measure] wird nicht automatisch ein anderer Touchpoint per Push ersetzt, um den gelöschten zu ersetzen, und die Touchpoint-Position oder -Attribution wird auch nicht dem nachfolgenden Touchpoint neu zugewiesen.

Wenn ein Touchpoint gelöscht wird, entsteht ein Loch in den Attributionsdaten. In der Regel wird dies in den Attributions-Touchpoints einer Gelegenheit angezeigt. In der Abbildung unten wurde der Touchpoint gelöscht, der den Kontakt &quot;Opportunity Creation&quot;erhalten hätte. Daher fehlt bei dieser Gelegenheit der OC-Touchpoint, und der Attributionsprozentsatz für diesen Opp wird nicht auf 100 % ansteigen.

![](assets/1.png)

Wenn Touchpoints aus Ihrem SFDC gelöscht wurden, wenden Sie sich an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} , um einen erneuten Import Ihrer Daten anzufordern.
