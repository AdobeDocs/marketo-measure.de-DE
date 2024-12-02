---
description: '[!DNL Marketo Measure] 101 Berichte - Überblick - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] 101 Berichte - Überblick'
exl-id: 83977b81-8055-47fd-8a6b-5ef32d280269
feature: Reporting
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 5%

---

# [!DNL Marketo Measure] 101 Berichte - Überblick {#marketo-measure-101-reports-overview}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Alle [!DNL Marketo Measure] -Kunden, die [!DNL Marketo Measure] und [!DNL Salesforce] verwenden, haben Zugriff auf den Ordner &quot;Buyer Touchpoints-Berichte&quot;in ihrer SFDC-Instanz. Dieser Ordner enthält eine Reihe vordefinierter Berichte, die Ihnen bei den ersten Schritten mit der Berichterstellung für Buyer Touchpoint-Daten helfen können.

![](assets/bizible-101-reports-overview-1.png)

Während für viele dieser Berichte bereits spezifische Berichtsziele festgelegt wurden, gibt es sechs &quot;_[!DNL Marketo Measure]101..._&quot;, die durch drei wichtige Berichtstypen repräsentiert werden, die den Großteil der Berichtserfordernisse abdecken.

* Leads mit Käufer-Touchpoints
* [!DNL Marketo Measure] Personen mit Touchpoints des Käufers
* Touchpoints der Käuferzuordnung mit Chancen

![](assets/bizible-101-reports-overview-2.png)

Diese Berichte liefern Ihnen die grundlegenden Felder und die Infrastruktur, die für jeden [!DNL Marketo Measure] verwandten Bericht benötigt werden, den Sie erstellen möchten. Wir empfehlen allen neuen und alten Kunden, mit diesen Berichten zu beginnen, wenn sie Fragen zur Marketing-Attribution untersuchen. Unten finden Sie eine Erklärung zu jedem der sechs &quot;_[!DNL Marketo Measure]101..._&quot; Berichte.

_Wenn Sie den Ordner &quot;Touchpoints-Bericht des Käufers&quot;oder die sechs &quot;_[!DNL Marketo Measure] 101..._&quot;-Berichte in diesem Ordner nicht finden können, wenden Sie sich an den Support für Unterstützung._

**Leads mit Käufer-Touchpoints** | Die folgenden beiden Varianten zeigen Leads und ihre Käufer-Touchpoints an. Obwohl sie denselben Basisberichtstyp verwenden, werden sie nach verschiedenen Metriken gruppiert: Lead-ID vs. Marketing-Kanal, um zwei wichtige Ansichten der Daten bereitzustellen. Dieser Berichtstyp wurde als Grundlage für Trichterberichte konzipiert und eignet sich ideal als Ausgangspunkt, um zu untersuchen, wie Ihre Leads mit Ihren Marketing-Maßnahmen interagieren. Vor einer Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Leads nach Kanal** | Ein Überblick darüber, wie Ihre Marketingkanäle die Erstellung von Leads und deren zusätzlichen Interaktionen beeinflussen.
**[!DNL Marketo Measure]101: Leads nach ID** | Daraufhin wird die Leads-Meldung angezeigt. Es handelt sich um einen detaillierteren Bericht, in dem jeder Lead und die zugehörigen Käufer-Touchpoints angezeigt werden.

**Leads/Kontakte mit Kunden-Touchpoints** | Diese Berichte werden häufig als [!DNL Marketo Measure] Persons -Berichte bezeichnet. Sie verwenden das benutzerdefinierte Objekt [!DNL Marketo Measure] _[!DNL Marketo Measure]Person_ im Gegensatz zum Lead-Objekt in den oben genannten Berichten.

Das Objekt „[!DNL Marketo Measure]-Person“ verknüpft die Lead- und Kontaktobjekte miteinander. Standardmäßig bietet [!DNL Salesforce] nicht die Möglichkeit, Berichte mit dem Lead- und Kontaktobjekt im selben Bericht zu erstellen. Indem sie sich auf das Lead- und Kontaktobjekt bezieht, das die eindeutige Kennung einer Person verwendet, deren E-Mail, kann die [!DNL Marketo Measure] Person innerhalb desselben Berichts sowohl über Interessenten- als auch über Kontaktkontakt-Kontaktpunkte von Käufern berichten. Dieser Berichtstyp eignet sich ideal zur Überprüfung Ihrer [!DNL Marketo Measure] -Kontoeinstellungen, da er die integrativste Ebene für die Touchpoint-Berichterstellung ist.

Die folgenden beiden Berichtsvarianten verwenden denselben Berichtstyp, werden jedoch nach verschiedenen Metriken gruppiert: Personen-ID (E-Mail) oder Marketing-Kanal. Dies sind die wichtigsten Trichterberichte bzw. Trichterberichte, mit denen Sie herausfinden können, wie Ihre Leads und Kontakte mit Ihren Marketing-Maßnahmen interagieren. Vor einer Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Lead/Kontakte nach Kanal** | Ein Überblick darüber, wie Ihre Marketingkanäle die Erstellung von Leads oder Kontakten und deren zusätzlichen Interaktionen beeinflussen. Dieser Bericht ist ideal, um die Gesamtinteraktion über Ihre Marketingkanäle hinweg zu verstehen und herauszufinden, welche Marketingkanäle innerhalb Ihrer Salesforce-Instanz zu neuen Netznamen führen.
**[!DNL Marketo Measure]101: Lead/Kontakte nach ID** | Dadurch wird die Geschichte jeder [!DNL Marketo Measure] Person angezeigt und es handelt sich um einen wesentlich detaillierteren Bericht, in dem jede Person und ihre Touchpoints des Käufers angezeigt werden, unabhängig davon, ob der Touchpoint als Lead oder als Kontakt auftrat.

**Möglichkeiten für Touchpoints der Käuferzuordnung** | Die letzten beiden &quot;_[!DNL Marketo Measure]101..._&quot;-Berichte sind der untere Teil der Trichterberichte, in denen die Buyer Attribution Touchpoint-Daten zu Opportunities angezeigt werden. Der Hauptunterschied für diese Berichte besteht darin, dass sie aus _Touchpoints der Käuferzuordnung_ erstellt wurden, die sich auf die Daten auf der Ebene der Chancen und Chancen beziehen, z. B. auf den Umsatz. Wann immer Sie Berichte über Chancen oder zurechenbare Einnahmen erstellen möchten, sollte dieser Berichtstyp verwendet werden. Die beiden folgenden Berichte verwenden denselben Berichtstyp, werden jedoch nach verschiedenen Metriken gruppiert: Chancen-ID vs. Marketing-Kanal. Vor einer Anpassung zeigen die beiden folgenden Berichte Folgendes an:

**[!DNL Marketo Measure]101: Chancen nach Kanal** | Ein Überblick darüber, wie Ihre Marketing-Kanäle in Ihren Opportunities beeinflussen und Umsatz mit Attributen generieren.
**[!DNL Marketo Measure]101: Chancen nach ID** | Diese granulare Berichtsversion zeigt Ihnen die vollständige Journey Ihrer Möglichkeiten. In diesem Bericht können Sie jede Buyer Attribution Touchpoint sehen, die einer Chance zugeordnet ist, sowie den zugeordneten Umsatz über die verschiedenen Attributionsmodelle.

Es wird als Best Practice erachtet, die &quot;_[!DNL Marketo Measure]101..._&quot;-Berichte als Vorlagen für Ihre Berichtsanforderungen zu behandeln. Wenn Sie mit einem der oben genannten Berichte beginnen, sparen Sie Zeit und stellen Sie sicher, dass Sie mit den korrekten Feldern arbeiten, die sich auf [!DNL Marketo Measure] -Daten beziehen. Achten Sie immer darauf, &quot;Speichern unter&quot;jedes Mal, wenn Sie Anpassungen an den Vorlagen &quot;_[!DNL Marketo Measure]101..._&quot;vornehmen, um die ursprüngliche Variante des Berichts beizubehalten.

Der Ordner &quot;Buyer Touchpoint-Berichte&quot;soll Ihnen bei den ersten Schritten mit der Berichterstellung [!DNL Marketo Measure] helfen. Für umsetzbare Berichte müssen Sie diese Berichte so anpassen, dass sie auf Ihre Berichterstattungsanforderungen zugeschnitten sind. müssen Sie die erforderlichen Filter hinzufügen, um sicherzustellen, dass die Datensätze im Bericht (und die zugehörigen Touchpoints) mit Ihrem Berichterstellungsziel übereinstimmen.

Wenn Sie mit den Berichten &quot;_[!DNL Marketo Measure]101..._&quot; vertraut sind, sollten Sie sie für benutzerspezifischere Berichtsanforderungen möglicherweise aus benutzerdefinierten Berichtstypen neu erstellen. Durch Erstellen der [[!DNL Marketo Measure] benutzerdefinierten Berichtstypen](/help/marketo-measure-salesforce-reporting/new-report-types/creating-custom-marketo-measure-report-types.md) können Sie benutzerdefinierte Felder abrufen, die Sie normalerweise in anderen CRM-Berichten verwenden. Auf diese Weise können Sie die [!DNL Marketo Measure] -Berichterstellung auf die nächste Stufe bringen!
