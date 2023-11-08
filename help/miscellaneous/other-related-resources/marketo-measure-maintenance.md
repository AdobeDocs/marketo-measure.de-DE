---
unique-page-id: 18874556
description: "[!DNL Marketo Measure] Wartung - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Wartung"
exl-id: 4e1d53bb-0af8-4774-9f69-6a95516b3d11
feature: Tracking
source-git-commit: b8ea008c594ed114323dedd3762d1265287193c7
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 1%

---

# [!DNL Marketo Measure] Wartung {#marketo-measure-maintenance}

[!DNL Marketo Measure] Ruft täglich fast alles aus Ihrem CRM ab, aber es gibt einige Wartungsaufgaben, die Sie regelmäßig planen sollten, um die [!DNL Marketo Measure] Zusammendrücken und Ausgeben möglichst genauer Informationen.

**Käufer-Touchpoints für neue Offline-Kampagnen synchronisieren (2x/Monat)**

Wie Sie während des Onboarding gelernt haben, [!DNL Marketo Measure] Ruft Informationen zu Ihren Offline-Marketing-Maßnahmen ab, indem Sie sie mit den Kampagnen Ihres CRM-Systems synchronisieren. Wenn Ihr Unternehmen neue Kampagnen startet, stellen Sie sicher, dass Sie die Touchpoints des Käufers für jede Kampagne aktivieren. Checkout [diesem Artikel](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)für weitere Informationen.

**Upload-Ausgaben für alle Kanäle (1x/Monat)**

So nutzen Sie die umfassenden Umsatz- und ROI-Reporting-Funktionen für[!DNL Marketo Measure], müssen Sie [!DNL Marketo Measure] wie viel Sie für die einzelnen Marketing-Kanäle und Unterkanäle ausgeben. Es wird empfohlen, den Eigentümer jedes Kanals/jeden Unterkanals zu bestimmen und die Ausgaben dieser Benutzer monatlich an einen einzigen Anbieter zu melden, der für das Hochladen neuer Kosteninformationen zuständig ist.

Aktualisieren Sie Ihren Speicher, um Informationen zum Hochladen von Kosteninformationen durch Lesen von zu erhalten. [diesem Artikel](/help/marketing-spend/spend-management/marketing-channel-costs.md).

**Liste der nachzuverfolgenden Domänen aktualisieren (1x/Monat)**

Marketo Measure verfolgt alle Seiten und Subdomänen, auf denen unser JavaScript aktiv ist, aber nur für Domänen, über die wir Bescheid wissen. Wenn Sie kürzlich eine neue Domäne deklariert, international erweitert oder Ihre primäre Domäne geändert haben, wenden Sie sich an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} um sicherzustellen, dass wir Ihr Konto entsprechend aktualisieren.

**Überprüfen Sie die Zuordnung benutzerdefinierter Kanäle auf Genauigkeit (1x/Monat).**

Beim Onboarding richten Sie ein benutzerdefiniertes Kanal-Mapping für Ihre Online- und Offline-Marketing-Maßnahmen ein. Wenn sich Ihre Marketing-Strategie und Ihre Verwendung von Marketo Measure weiterentwickeln, sollten Sie diese Zuordnungslogik im Auge behalten, um sicherzustellen, dass alle Touchpoints angemessen kategorisiert werden.

Denken Sie daran, [!DNL Marketo Measure] verarbeitet Ihre Daten bei der Bearbeitung der Zuordnungslogik neu, sodass Sie diese Regeln nicht öfter als alle 7 Tage ändern können.

Referenz [diesem Artikel](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) für die Online-Einrichtung, [diesem Artikel](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md) für die Offline-Einrichtung und diese Liste von Best Practices, die von unseren Kunden kuratiert werden:

* Überprüfen Sie Touchpoints, die derzeit in einen &quot;Sonstige&quot;- oder &quot;NULL&quot;-Kanal fallen, den Sie eingerichtet haben. Aktualisieren Sie gegebenenfalls Ihre Zuordnungslogik, um diese Touchpoints in präzisere Kanäle zu kategorisieren.
* Überprüfen Sie Touchpoints, die derzeit in Ihre direkten Kanäle fallen. Wenn bei einigen Ihrer E-Mail-Marketing-Kampagnen oder anderen Bemühungen UTM-Parameter fehlen, besteht eine gute Wahrscheinlichkeit, dass Traffic unangemessen in einem direkten Kanal zusammengefasst wird. Aktualisieren Sie Ihre UTM-Parameter, um die Referrer-Quelle zu erfassen.

**Einstellungen zur Touchpoint-Unterdrückung bewerten (1x/Quartal)**

Wenn Sie viele Touchpoints sehen, die Sie bevorzugen, werden Sie nicht in Ihrer Attributionsgeschichte berücksichtigt (von einer [!DNL Login] oder [!DNL Unsubscribe forms], einer Karriereseite oder einer internen App), können Sie Ihre vorhandenen Einstellungen für die Touchpoint-Unterdrückung bewerten. Suchen Sie einmal im Quartal alle Gruppen von Touchpoints, die unnötiges Rauschen verursachen, und aktualisieren Sie Ihre Unterdrückungslogik entsprechend. [Hier ist ein hilfreicher Artikel](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)  mit der Anleitung.

**Überprüfen Sie die benutzerdefinierte Staging-Zuordnung auf Genauigkeit (1x/Quartal) (falls zutreffend).**

Wenn Sie eine benutzerdefinierte [!UICONTROL Lead], [!UICONTROL Kontakt]oder [!UICONTROL Chancen] -Bühnen können Sie auch angepasst haben, welchen Teil der Pipeline diese Bühnen zuordnen und ob diese Bühnen in einem benutzerdefinierten Attributionsmodell enthalten sind. Besuchen Sie einmal pro Quartal [diesem Artikel](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md) , um Ihren Speicher bei der benutzerdefinierten Staging-Zuordnung zu aktualisieren und sicherzustellen, dass Sie Ihre benutzerdefinierten Bühnen genau verfolgen.

**Vergleich des Modells für maschinelles Lernen mit der Gewichtung des benutzerdefinierten Modells (1x/Quartal) (falls zutreffend)**

Wenn Sie für die [!DNL Marketo Measure] Benutzerdefiniertes Modell, Sie verfügen auch über Daten aus unserem Machine Learning Model (MLM) in [!UICONTROL Einstellungen] > [!UICONTROL Attributionseinstellungen]. Das MLM berechnet die Wichtigkeit jeder Phase mithilfe von Touchpoint-Daten aus Ihrem Konto und kann Ihnen bei der Entscheidung helfen, die Attributionsgewichtung in Ihrem benutzerdefinierten Modell zuzuweisen. Es wird empfohlen, das MLM einmal pro Quartal mit Ihrem benutzerdefinierten Modell zu vergleichen und die Auswirkungen möglicher Änderungen an Ihrem benutzerdefinierten Modell mit Ihrem SM zu besprechen.

Weitere Informationen zum [!DNL Marketo Measure] Modell für maschinelles Lernen, Checkout [diesem Artikel](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).
