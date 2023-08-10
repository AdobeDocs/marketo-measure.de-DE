---
unique-page-id: 27656441
description: Häufig gestellte Fragen zur Drift-Integration - [!DNL Marketo Measure] - Produktdokumentation
title: Häufig gestellte Fragen zur Drift-Integration
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 3%

---

# Häufig gestellte Fragen zur Drift-Integration {#drift-integration-faq}

Als Teil der [!DNL Marketo Measure] Integration mit Drift, haben wir einige der am häufigsten gestellten Fragen beschrieben. Wenden Sie sich bei Fragen, die nachfolgend nicht erläutert werden, an das Kundenbetreuungsteam von Adobe (Ihren Kundenbetreuer) oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**Wie ist die Integration aktiviert?**

Drilldown-Chat-Tracking für [!DNL Marketo Measure] ist standardmäßig aktiviert. Wenn Sie es aus irgendeinem Grund deaktivieren möchten (und keine Touchpoints standardmäßig aus Drift Chats erstellen), benötigen wir ein zusätzliches Attribut, das zu Ihrem [!DNL Marketo Measure] JavaScript-Implementierung, unten hervorgehoben:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Für Benutzer, die [!DNL Google Tag Manager] , um die [!DNL Marketo Measure] Skript: Wenn Sie Ihre Drift Chats davon ausschließen möchten, Touchpoint-berechtigt zu sein, müssen Sie Folgendes hinzufügen `<span>` direkt nach dem [!DNL Marketo Measure] Script:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**Was bewirkt die Integration?**

Die Integration ermöglicht jetzt [!DNL Marketo Measure] , um zu verfolgen, wann ein Endbenutzer seine E-Mail-Adresse in einem Drift-Chat bereitstellt. Von dort aus erstellen wir Touchpoints aus diesen Interaktionen mit dem Touchpoint-Typ &quot;Web-Chat&quot;. Diese Integration ermöglicht es Marketingexperten, die Leistung ihrer Chat-Interaktionen sowie die Kanäle/Unterkanäle/Kampagnen zu verstehen, die die Interaktion mit diesen Chats fördern.

**Was passiert, wenn ich Drift über Kampagnen-Synchronisierungsregeln tracke?**

Wenn es Regeln zur Kampagnensynchronisierung gibt, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, müssen Sie sicherstellen, dass Sie diese speziellen Endbenutzer nicht mehr zur entsprechenden CRM-Kampagne hinzufügen. Andernfalls erstellen wir nach Aktivierung der Feature-Bit-Funktion einen CRM-Campaign-Touchpoint und einen digitalen Touchpoint für eine Drift-Chat-Interaktion.

**Was passiert, wenn ich Drift über CRM-Kampagnen nachvollziehe?**

Wenn CRM-Kampagnen vorhanden sind, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, muss für diese spezifischen Kampagnen ein Touchpoint-Enddatum festgelegt werden (das Touchpoint-Enddatum sollte das Datum sein, an dem das Feature-Bit für die Web-Chat-Integration aktiviert ist).

**Was passiert, wenn ich Drift über Aktivitäten tracke?**

Wenn es Aktivitätsregeln gibt, mit denen Touchpoints für Drift-Chat-Interaktionen erstellt werden, müssen die Regeln um einen zusätzlichen Teil der Logik ergänzt werden. Sie müssen mithilfe des Felds Task Created Date eine Logik hinzufügen, um zu verhindern, dass eine Duplizierung von Touchpoints erstellt wird (IE CrmTask.CreatedDate ist kleiner als das Datum, an dem das Feature Bit aktiviert wurde). Siehe Screenshot unten zum Beispiel.

![](assets/activity-rule-drift.png)
