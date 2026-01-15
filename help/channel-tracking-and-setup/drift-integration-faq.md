---
description: Häufig gestellte Fragen zur Drift-Integration für Marketo Measure-Benutzende
title: Häufig gestellte Fragen zur Drift-Integration
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Häufig gestellte Fragen zur Drift-Integration {#drift-integration-faq}

Im Rahmen der [!DNL Marketo Measure] Integration mit Drift finden Sie hier einige der am häufigsten gestellten Fragen. Wenn Sie Fragen haben, die unten nicht aufgeführt sind, wenden Sie sich an das Adobe Account Team (Ihren Account Manager) oder an den [Marketo Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**Wie ist die Integration aktiviert?**

Das Tracking von Drift-Chats für [!DNL Marketo Measure] ist standardmäßig aktiviert. Wenn Sie sie deaktivieren möchten (und standardmäßig keine Touchpoints aus Drift-Chats erstellen möchten), fügen Sie Ihrer [!DNL Marketo Measure] JavaScript-Implementierung ein zusätzliches Attribut hinzu, das unten fett gedruckt ist:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Wenn Sie [!DNL Google Tag Manager] zum Laden des [!DNL Marketo Measure] verwenden und Ihre Drift-Chats von der Touchpoint-Berechtigung ausschließen möchten, fügen Sie direkt nach Ihrem `<span>`-Skript zu den folgenden [!DNL Marketo Measure] hinzu:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**Was bewirkt die Integration?**

Durch die Integration können [!DNL Marketo Measure] jetzt verfolgen, wann ein Endbenutzer seine E-Mail-Adresse in einem Drift-Chat angegeben hat. Von dort aus erstellen wir Touchpoints aus diesen Interaktionen mit dem Touchpoint-Typ „Webchat“. Diese Integration ermöglicht es Marketing-Experten, die Leistung ihrer Chat-Interaktionen zusammen mit den Kanälen/Unterkanälen/Kampagnen zu verstehen, die die Benutzer zur Interaktion mit diesen Chats antreiben.

**Was passiert, wenn ich Drift über Kampagnensynchronisierungsregeln nachverfolge?**

Wenn es Regeln für die Kampagnensynchronisierung gibt, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, stellen Sie sicher, dass Sie diese bestimmten Endbenutzer nicht mehr zur entsprechenden CRM-Kampagne hinzufügen. Andernfalls müssen Sie, sobald das Feature Bit aktiviert ist, einen CRM-Campaign-Touchpoint und einen digitalen Touchpoint für eine Drift-Chat-Interaktion erstellen.

**Was passiert, wenn ich Drift über CRM-Kampagnen nachverfolge?**

Wenn es CRM-Kampagnen gibt, um Touchpoints für Interaktionen mit Drift-Chat zu erstellen, muss für diese spezifischen Kampagnen ein Touchpoint-Enddatum festgelegt werden (das Touchpoint-Enddatum sollte das Datum sein, an dem das Feature Bit für die Web-Chat-Integration aktiviert wird).

**Was passiert, wenn ich Drift über Aktivitäten nachverfolge?**

Wenn es Aktivitätsregeln gibt, um Touchpoints für Drift-Chat-Interaktionen zu erstellen, muss eine zusätzliche Logik zu den Regeln hinzugefügt werden. Fügen Sie mithilfe des Datumsfelds für die Aufgabenerstellung eine Logik hinzu, um zu verhindern, dass doppelte Touchpoints erstellt werden (d. h. CrmTask.CreatedDate ist kleiner als das Datum, an dem das Funktionsbit aktiviert wurde). Siehe Screenshot unten, zum Beispiel.

![Wenn es Aktivitätsregeln gibt, um Touchpoints für Drift zu erstellen](assets/chat-integration-1.png)
