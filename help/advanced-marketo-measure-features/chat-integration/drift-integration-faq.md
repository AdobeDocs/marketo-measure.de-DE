---
unique-page-id: 27656441
description: Häufig gestellte Fragen zur Drift-Integration - [!DNL Marketo Measure]
title: Häufig gestellte Fragen zur Drift-Integration
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Häufig gestellte Fragen zur Drift-Integration {#drift-integration-faq}

Im Rahmen der Integration von [!DNL Marketo Measure] mit Drift finden Sie einige der am häufigsten gestellten Fragen. Wenden Sie sich bei Fragen, die nachfolgend nicht beschrieben werden, an das Adobe Account Team (Ihren Kundenbetreuer) oder an den [Marketo Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**Wie ist die Integration aktiviert?**

Das Drift Chat-Tracking für [!DNL Marketo Measure] ist standardmäßig aktiviert. Wenn Sie sie deaktivieren möchten (und standardmäßig keine Touchpoints aus Drift Chats erstellen möchten), fügen Sie ein zusätzliches Attribut hinzu, das zu Ihrer JavaScript-Implementierung von [!DNL Marketo Measure] hinzugefügt wurde, wie unten dargestellt:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Für diejenigen, die [!DNL Google Tag Manager] verwenden, um das [!DNL Marketo Measure]-Skript zu laden, fügen Sie nach Ihrem [!DNL Marketo Measure]-Skript folgende `<span>` hinzu, wenn Sie Ihre Drift Chats von der Touchpoint-Berechtigung ausschließen möchten:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**Was bewirkt die Integration?**

Durch die Integration kann [!DNL Marketo Measure] nun nachverfolgen, wann ein Endbenutzer seine E-Mail-Adresse in einem Drift-Chat bereitstellt. Von dort aus erstellen wir Touchpoints aus diesen Interaktionen mit dem Touchpoint-Typ &quot;Web-Chat&quot;. Diese Integration ermöglicht es Marketingexperten, die Leistung ihrer Chat-Interaktionen sowie die Kanäle/Unterkanäle/Kampagnen zu verstehen, die die Interaktion mit diesen Chats fördern.

**Was passiert, wenn ich Drift über Kampagnen-Synchronisierungsregeln tracke?**

Wenn es Regeln zur Kampagnensynchronisierung gibt, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, stellen Sie sicher, dass Sie diese speziellen Endbenutzer nicht mehr zur entsprechenden CRM-Kampagne hinzufügen. Wenn die Funktions-Bit-Funktion aktiviert ist, erstellen Sie andernfalls einen CRM-Campaign-Touchpoint und einen digitalen Touchpoint für eine Drift-Chat-Interaktion.

**Was passiert, wenn ich Drift über CRM-Kampagnen nachvollziehe?**

Wenn CRM-Kampagnen vorhanden sind, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, muss für diese spezifischen Kampagnen ein Touchpoint-Enddatum festgelegt werden (das Touchpoint-Enddatum sollte das Datum sein, an dem das Feature Bit für die Web-Chat-Integration aktiviert ist).

**Was passiert, wenn ich Drift über Aktivitäten trage?**

Wenn Aktivitätsregeln vorhanden sind, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, müssen die Regeln um einen zusätzlichen Teil der Logik ergänzt werden. Fügen Sie mithilfe des Felds Task Created Date eine Logik hinzu, um zu verhindern, dass eine Duplizierung von Touchpoints erstellt wird (IE CrmTask.CreatedDate ist kleiner als das Datum, an dem das Feature Bit aktiviert wurde). Siehe Screenshot unten zum Beispiel.

![](assets/activity-rule-drift.png)
