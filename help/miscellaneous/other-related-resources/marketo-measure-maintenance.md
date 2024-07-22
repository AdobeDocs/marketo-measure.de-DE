---
unique-page-id: 18874556
description: „[!DNL Marketo Measure]-Wartung – [!DNL Marketo Measure]“
title: „[!DNL Marketo Measure]-Wartung“
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: fca2db86611d16f4e74467405521a89dd5d825ab
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---

# [!DNL Marketo Measure]-Wartung {#marketo-measure-maintenance}

[!DNL Marketo Measure] ruft fast alles, was es braucht, täglich aus Ihrem CRM ab. Es gibt jedoch ein paar Wartungsaufgaben, die Sie regelmäßig einplanen sollten, damit [!DNL Marketo Measure] glatt weiterläuft und möglichst genaue Informationen ausgibt.

**Synchronisieren von Buyer Touchpoints für neue Offline-Kampagnen (2x/Monat)**

Wie Sie beim Onboarding erfahren haben, erhält [!DNL Marketo Measure] durch die Synchronisierung mit den Kampagnen Ihres CRM Informationen über Ihre Offline-Marketing-Maßnahmen. Wenn Ihr Unternehmen neue Kampagnen startet, stellen Sie sicher, dass Sie die Buyer Touchpoints für jede Kampagne aktivieren.

**Hochladen der Ausgaben für alle Kanäle (1x/Monat)**

Um die Vorteile der vollständigen Umsatz- und ROI-Reporting-Funktionen für [!DNL Marketo Measure] zu nutzen, müssen Sie [!DNL Marketo Measure] mitteilen, wie viel Sie für jeden Ihrer Marketing-Kanäle und -Unterkanäle ausgeben. Bestimmen Sie die Inhaberin bzw. den Inhaber jedes Kanals und Unterkanals und lassen Sie diese die Ausgaben an eine einzige Person melden, die für das monatliche Hochladen neuer Kosteninformationen verantwortlich ist.

Frischen Sie Ihr Gedächtnis auf, indem Sie [diesen Artikel](/help/marketing-spend/spend-management/marketing-channel-costs.md) lesen, um zu erfahren, wie Sie Kosteninformationen hochladen.

**Aktualisieren der Liste der zu verfolgenden Domains (1x/Monat)**

Marketo Measure verfolgt alle Seiten und Subdomains, auf denen unser JavaScript aktiv ist, aber nur für Domains, die uns bekannt sind. Wenn Sie kürzlich eine neue Domain eingeführt, international erweitert oder Ihre primäre Domain geändert haben, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}, um sicherzustellen, dass wir Ihr Konto entsprechend aktualisieren.

**Überprüfen der Zuordnung der benutzerdefinierten Kanäle auf Genauigkeit (1x/Monat)**

Während des Onboardings richten Sie eine benutzerdefinierte Kanalzuordnung für Ihre Online- und Offline-Marketing-Maßnahmen ein. Wenn sich Ihre Marketing-Strategie und Ihre Verwendung von Marketo Measure weiterentwickeln, sollten Sie diese Zuordnungslogik im Auge behalten, um sicherzustellen, dass alle Touchpoints angemessen kategorisiert werden.

Denken Sie daran, dass [!DNL Marketo Measure] Ihre Daten neu verarbeitet, wenn Sie die Zuordnungslogik bearbeiten. Sie können diese Regeln also nicht mehr als einmal alle sieben Tage ändern.

Lesen Sie [diesen Artikel](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) für die Online-Einrichtung, [diesen Artikel](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) für die Offline-Einrichtung und die folgende von Kundenseite erstellte Liste mit Best Practices:

* Überprüfen Sie die Touchpoints, die derzeit unter „Andere“ oder „NULL“ Kanäle fallen, die Sie möglicherweise eingerichtet haben. Aktualisieren Sie gegebenenfalls Ihre Zuordnungslogik, um diese Touchpoints in präzisere Kanäle zu kategorisieren.
* Überprüfen Sie Touchpoints, die derzeit in Ihre direkten Kanäle fallen. Wenn bei einigen Ihrer E-Mail-Marketing-Kampagnen oder anderen Bemühungen UTM-Parameter fehlen, besteht eine gewisse Wahrscheinlichkeit, dass Traffic unangemessen in einem direkten Kanal zusammengefasst wird. Erwägen Sie, Ihre UTM-Parameter zu aktualisieren, um die verweisende Quelle zu erfassen.

**Evaluieren der Einstellungen für die Touchpoint-Unterdrückung (1x/Quartal)**

Wenn Sie viele Touchpoints sehen, die Sie lieber nicht in Ihrer Attributionshistorie berücksichtigen möchten (z. B. von einem [!DNL Login] oder [!DNL Unsubscribe forms], einer Karriereseite oder einer internen App), sollten Sie Ihre bestehenden Einstellungen zur Unterdrückung von Touchpoints überprüfen. Ermitteln Sie einmal im Quartal die Gruppen von Touchpoints, die unnötiges Rauschen verursachen, und aktualisieren Sie Ihre Unterdrückungslogik entsprechend. [Hier finden Sie einen hilfreichen Artikel](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) mit der Anleitung dazu.

**Überprüfen der benutzerdefinierten Phasenzuordnung auf Genauigkeit (1x/Quartal) (falls anwendbar)**

Wenn Sie benutzerdefinierte [!UICONTROL Lead]-, [!UICONTROL Kontakt]- oder [!UICONTROL Opportunitys]-Phasen verwenden, haben Sie möglicherweise auch angepasst, welchem Teil der Pipeline diese Phasen zugeordnet sind und ob diese Phasen in einem benutzerdefinierten Attributionsmodell enthalten sind. Lesen Sie einmal im Quartal [diesen Artikel](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md), um Ihr Gedächtnis bezüglich der Zuordnung von benutzerdefinierten Phasen aufzufrischen und sicherzustellen, dass Sie Ihre benutzerdefinierten Phasen genau verfolgen.

**Vergleichen des Machine Learning-Modells mit der Gewichtung des benutzerdefinierten Modells (1x/Quartal) (falls anwendbar)**

Wenn Sie für das benutzerdefinierte Modell [!DNL Marketo Measure] lizenziert sind, stehen Ihnen auch Daten aus unserem Machine Learning-Modell (MLM) in [!UICONTROL Einstellungen] > [!UICONTROL Attributionseinstellungen] zur Verfügung. Das MLM berechnet die Wichtigkeit jeder Phase mithilfe von Touchpoint-Daten aus Ihrem Konto und kann Ihnen bei der Entscheidung helfen, die Attributionsgewichtung in Ihrem benutzerdefinierten Modell zuzuweisen. Es wird empfohlen, das MLM einmal pro Quartal mit Ihrem benutzerdefinierten Modell zu vergleichen und die Auswirkungen möglicher Änderungen an Ihrem benutzerdefinierten Modell mit Ihrem SM zu besprechen.

Weitere Informationen über das [!DNL Marketo Measure]-Machine Learning-Modell finden Sie in [diesem Artikel](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
