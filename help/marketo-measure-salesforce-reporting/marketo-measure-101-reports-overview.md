---
description: Übersicht über [!DNL Marketo Measure] 101-Berichte - [!DNL Marketo Measure]
title: '[!DNL Marketo Measure] 101 Berichte - Überblick'
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 5%

---

# [!DNL Marketo Measure] 101 Berichte - Überblick {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Alle [!DNL Marketo Measure] Kunden, die [!DNL Marketo Measure] und [!DNL Salesforce] verwenden, haben in ihrer SFDC-Instanz Zugriff auf den Ordner „Buyer Touchpoints Reports“. Dieser Ordner enthält eine Reihe vordefinierter Berichte, die Ihnen bei den ersten Schritten mit dem Reporting mit Buyer Touchpoint-Daten helfen können.

![Alle Marketo Measure-Kunden, die Marketo Measure und Salesforce verwenden](assets/bizible-guide-1.png)

Während viele dieser Berichte bereits spezifische Berichtsziele haben, gibt es sechs &quot;_[!DNL Marketo Measure]101…_&quot;, die durch drei wichtige Berichtstypen repräsentiert werden, die einen Großteil des Berichtsbedarfs decken.

* Leads mit Käufer-Touchpoints
* Personen mit Kunden-Touchpoints [!DNL Marketo Measure]
* Attribution-Touchpoints des Käufers mit Opportunities

![Attribution-Touchpoints des Käufers mit Opportunities](assets/bizible-guide-2.png)

Diese Berichte liefern die grundlegenden Felder und die Infrastruktur, die für jeden [!DNL Marketo Measure] Bericht, den Sie erstellen möchten, erforderlich sind. Wir empfehlen allen Kundinnen und Kunden, ob neu oder alt, diese Berichte bei der Untersuchung von Fragen zur Marketing-Attribution zu verwenden. Nachstehend finden Sie eine Erläuterung jedes der sechs &quot;_[!DNL Marketo Measure]101…_&quot;-Berichte.

_Wenn Sie den Ordner mit dem Käufer-Touchpoint-Bericht oder die sechs &quot;_[!DNL Marketo Measure] 101…_&quot;-Berichte in diesem Ordner nicht finden können, wenden Sie sich an den Support, um Hilfe zu erhalten._

**Leads mit Käufer-Touchpoints** | Die folgenden beiden Varianten enthalten Berichte zu Leads und ihren Buyer Touchpoints. Obwohl sie denselben Basisberichtstyp verwenden, werden sie nach verschiedenen Metriken gruppiert, Lead-ID vs. Marketing-Kanal, um zwei wichtige Ansichten der Daten bereitzustellen. Dieser Berichtstyp wurde für die Erstellung von Berichten über funnel entwickelt und eignet sich ideal, um zu untersuchen, wie Ihre Leads mit Ihren Marketing-Maßnahmen interagieren. Vor jeder Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Leads nach Kanal** | Eine allgemeine Übersicht darüber, wie Ihre Marketing-Kanäle die Erstellung von Leads und deren zusätzliche Interaktionen beeinflussen.
**[!DNL Marketo Measure]101: Leads nach ID** | Dieser Bericht zeigt die Leads-Story an und ist wesentlich detaillierter. Er zeigt jeden einzelnen Lead und die zugehörigen Buyer Touchpoints an.

**Leads/Kontakte mit Käufer-Touchpoints** | Diese Berichte werden im Allgemeinen als Berichte zu [!DNL Marketo Measure] Personen bezeichnet. Sie verwenden das [!DNL Marketo Measure] benutzerdefinierte Objekt _[!DNL Marketo Measure]Person_ das Lead-Objekt in den oben genannten Berichten.

Das Objekt „[!DNL Marketo Measure]-Person“ verknüpft die Lead- und Kontaktobjekte miteinander. Vorkonfiguriert bietet [!DNL Salesforce] keine Möglichkeit, Berichte mit dem Lead- und Kontaktobjekt im selben Bericht zu erstellen. Indem er sich mit dem Lead- und Kontaktobjekt über die eindeutige Kennung einer Person, ihre E-Mail, verbindet, kann die [!DNL Marketo Measure] Person innerhalb desselben Berichts sowohl Lead- als auch Kontakt-bezogene Käufer-Touchpoints melden. Dieser Berichtstyp ist ideal, wenn Sie eine Ihrer [!DNL Marketo Measure] Kontoeinstellungen überprüfen möchten, da dies die umfassendste Ebene des Touchpoint-Reportings ist.

Die folgenden beiden Berichtsvarianten verwenden denselben Berichtstyp, sind jedoch nach verschiedenen Metriken gruppiert, nämlich Personen-ID (E-Mail) vs. Marketing-Kanal. Dies sind die Top-Berichte von funnel/Middle of funnel. Sie eignen sich hervorragend, wenn Sie untersuchen möchten, wie Ihre Leads und Kontakte mit Ihren Marketing-Maßnahmen interagieren. Vor jeder Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Lead/Kontakte nach Kanal** | Eine allgemeine Übersicht darüber, wie Ihre Marketing-Kanäle die Erstellung von Leads oder Kontakten und deren zusätzliche Interaktionen beeinflussen. Dieser Bericht ist ideal, wenn Sie wissen möchten, wie die gesamte Interaktion über Ihre Marketing-Kanäle hinweg verläuft und welche Marketing-Kanäle neue Namen in Ihrer Salesforce-Instanz auslösen.
**[!DNL Marketo Measure]101: Lead/Kontakte nach ID** | Dies zeigt die Geschichte jeder [!DNL Marketo Measure] Person an und ist ein wesentlich detaillierterer Bericht, der jede Person und ihre Käufer-Touchpoints zeigt, unabhängig davon, ob der Touchpoint während ihrer Lead- oder als Kontakt-Person aufgetreten ist.

**Opportunities mit Käufer-Attribution-Touchpoints** | Die letzten beiden &quot;_[!DNL Marketo Measure]101…_&quot;-Berichte sind die unteren Berichte von funnel, die die Buyer Attribution Touchpoint-Daten zu Opportunities anzeigen. Das wichtigste Unterscheidungsmerkmal dieser Berichte besteht darin, dass sie auf Touchpoints der _-Attribution basieren_ die sich auf Daten auf Opportunity- und Opportunity-Ebene beziehen, z. B. Umsatz. Wenn Sie einen Bericht zu Opportunitys oder zugeordneten Einnahmen erstellen möchten, sollte dieser Berichtstyp verwendet werden. Die beiden folgenden Berichte verwenden denselben Berichtstyp, sind jedoch nach verschiedenen Metriken gruppiert, Opportunity-ID vs. Marketing-Kanal. Vor jeder Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Opportunities nach Kanal** | Eine allgemeine Übersicht darüber, wie Ihre Marketing-Kanäle die zugeordneten Umsätze in Ihren Opportunities beeinflussen und fördern.
**[!DNL Marketo Measure]101: Opportunities nach ID** | Diese granulare Berichtsversion zeigt Ihnen die vollständige Journey Ihrer Opportunities. In diesem Bericht können Sie jede Buyer Attribution Touchpoint sehen, die mit einer Opportunity verbunden ist, und ihren zugeordneten Umsatz durch die verschiedenen Attributionsmodelle.

Es gilt als Best Practice, die Berichte &quot;_[!DNL Marketo Measure]101…_&quot; als Vorlagen für Ihre Reporting-Anforderungen zu behandeln. Wenn Sie mit einem der oben genannten Berichte beginnen, sparen Sie Zeit und stellen sicher, dass Sie mit den richtigen Feldern arbeiten, die sich auf [!DNL Marketo Measure] Daten beziehen. Achten Sie immer darauf, „Speichern unter“ zu wählen, wenn Sie die Vorlagen von &quot;_[!DNL Marketo Measure]101…_&quot; anpassen, um die ursprüngliche Variante des Berichts beizubehalten.

Der Ordner &quot;Buyer Touchpoint-Berichte“ soll Ihnen bei den ersten Schritten im [!DNL Marketo Measure]-Reporting helfen. Für umsetzbare Berichte müssen Sie diese Berichte so anpassen, dass sie auf Ihre Reporting-Anforderungen zugeschnitten sind. Sie müssen die erforderlichen Filter hinzufügen, um sicherzustellen, dass die Datensätze im Bericht (und die zugehörigen Touchpoints) mit Ihrem Berichtsziel übereinstimmen.

Wenn Sie mit den Berichten &quot;_[!DNL Marketo Measure]101…_&quot; vertraut sind, empfiehlt es sich möglicherweise, sie aus benutzerdefinierten Berichtstypen neu zu erstellen, um benutzerdefiniertes Reporting zu ermöglichen. Durch die Erstellung [[!DNL Marketo Measure] benutzerdefinierten Berichtstypen](/help/marketo-measure-salesforce-reporting/creating-report-types.md) können Sie benutzerdefinierte Felder abrufen, die Sie häufig in anderen CRM-Berichten verwenden. Dies hilft Ihnen, [!DNL Marketo Measure] Reporting auf die nächste Stufe zu bringen!
