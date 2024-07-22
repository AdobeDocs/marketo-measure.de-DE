---
unique-page-id: 18874688
description: CRM-Kampagnenkosten - [!DNL Marketo Measure]
title: Kosten für CRM-Kampagnen
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 0%

---

# Kosten für CRM-Kampagnen {#crm-campaign-costs}

Die meisten [!DNL Marketo Measure] -Kunden verwenden CRM-Kampagnen, um Offline-Marketingaktivitäten zu verfolgen. Marketer, die diese Kampagnen verwenden, überwachen auch die Kosten im CRM. Diese Funktion erleichtert Marketingexperten die Lektüre dieser Kosten durch [!DNL Marketo Measure] und ihre Anwendung auf die gemeldeten Marketing-Ausgaben innerhalb von [!DNL Marketo Measure]. Bisher mussten Kunden die Kosten für jede Kampagne pro Monat manuell eingeben. Mit den erforderlichen Informationen an[!DNL Marketo Measure] können Benutzer diesen Prozess jedoch automatisieren, sodass Marketing-Experten mehr Zeit mit der Analyse ihrer Ausgaben und des ROI verbringen können.

## Verfügbarkeit {#availability}

Diese Funktion ist für alle Kunden von [!DNL Salesforce] und Dynamics verfügbar.

## Funktionsweise {#how-it-works}

[!DNL Marketo Measure] sucht zunächst nach Kampagnen, die für Touchpoints &quot;aktiviert&quot;wurden. Es wurde also entweder eine passende Kampagnensynchronisierungsregel erstellt oder der Wert &quot;Touchpoints des Käufers aktivieren&quot;lautet &quot;Alle Kampagnenmitglieder einschließen&quot;oder &quot;Respondierte Kampagnenmitglieder einschließen&quot;. Außerdem muss [!DNL Marketo Measure] die richtigen Werte importieren und wissen, wie die Kosten verteilt werden. Daher müssen die folgenden Felder einen Wert enthalten:

**[!DNL Salesforce]**: `ActualCost`, `StartDate`, `EndDate`

**[!DNL Microsoft Dynamics]**: `totalactualcost`, `actualstart`, `actualend`

Wenn in einem der drei Felder ein Wert fehlt, importiert [!DNL Marketo Measure] die Kosten nicht. Korrigieren Sie dies, indem Sie den Campaign-Datensatz im CRM aktualisieren. Kosten werden nicht importiert, wenn sie auf 0 USD gesetzt sind, da [!DNL Salesforce] leer und 0 USD gleich behandelt.

Damit [!DNL Marketo Measure] die Verteilung einer Kampagne über Monate bestimmt, wird das Start- und Enddatum der Kampagne verwendet, um den Betrag gleichmäßig pro Tag zu verteilen.

![](assets/1.jpg)

In diesem Beispiel dauert eine Kampagne 109 Tage. Mit Gesamtkosten von 18.000 US-Dollar belaufen sich die Ausgaben pro Tag also auf ~ 165,14 US-Dollar.

Basierend auf der Anzahl der Tage pro Monat erhalten wir diese monatlichen Summen, wie Sie in der Tabelle sehen können:

Juli 2018: ($18.000/109) x 31 = 5.119,27 $

August 2018: ($18.000/109) x 31 = 5.119,27 $

Sep 2018: ($18.000/109) x 30 = $4.954.13

Okt. 2018: ($18.000/109) x 17 = $2.807.34

## Historische Ausgaben in Berichten {#historical-reported-spend}

Wenn Sie Ausgaben für Kampagnen eingegeben haben, die in der Vergangenheit verfolgt und einer CRM-Kampagne zugeordnet wurden, werden keine der eingegebenen Kosten überschrieben. Wenn dieselbe Kampagne im CRM geändert wird, wird sie ignoriert und den Änderungen, die Sie zuvor beim CSV-Upload vorgenommen haben, wird Vorrang eingeräumt.

Wenn Sie es vorziehen möchten, die Kosten der CRM-Kampagne von jetzt an zu berücksichtigen, ändern Sie den Wert in der CSV-Datei in $0 , wodurch der Eintrag annulliert wird. Wenn die Aufträge das nächste Mal zum Importieren der Kosten ausgeführt werden, werden zuvor bearbeitete Berichte abgerufen.

## Kampagnen ohne Touchpoints {#campaigns-with-no-touchpoints}

Viele Marketing-Experten melden Marketingausgaben für CRM-Kampagnen, die keine Touchpoints generiert haben oder über keine Campaign-Mitglieder verfügen, um Ausgaben verfolgen zu können. Solange die drei Felder ausgefüllt sind (Startdatum, Enddatum, Kosten) und die Kampagne für Touchpoints aktiviert ist, ruft [!DNL Marketo Measure] diese Kosten ab, selbst wenn keine Touchpoints damit verknüpft sind.

Dies könnte hilfreich sein, um Ausgaben für überschüssige Marketing-Kosten oder Tools zu verfolgen, die diese in Ihre ROI-Berechnungen einfließen lassen.

## Marketo-Programmsynchronisierung {#marketo-program-sync}

Wenn Sie Marketo-Programme als Kampagnen in das CRM-System integrieren, stellen Sie sicher, dass Sie die Zuordnung von Startdatum, Enddatum und Period Cost in die erforderlichen CRM-Felder eingerichtet haben. Da es keine Zuordnung zum Feld &quot;Käufer-Touchpoints aktivieren&quot;gibt, müssen Sie diese Kampagnen dennoch aktivieren, damit die Kosten abgerufen werden können.

## Bearbeiten der Kosten {#editing-the-costs}

Nachdem eine Kampagne aus dem CRM importiert wurde, wird sie ähnlich wie ein API Ads Provider behandelt und nicht in der CSV angezeigt, um Kostenänderungen vorzunehmen.

Änderungen an Kosten oder Verteilung müssen im CRM vorgenommen werden, damit wir auf einen einzigen Punkt der Wahrheit verweisen können.

## FAQs {#faq}

**Ich habe eine Änderung an meiner Kampagne vorgenommen - wann sollte ich mit den Änderungen in der Tabelle Marketing-Ausgaben oder in meinem Bericht rechnen?**

3-4 Stunden

**Ich habe das Start- und Enddatum sowie die Kosten ausgefüllt, aber warum werden meine Kosten immer noch nicht in [!DNL Marketo Measure] angezeigt?**

Vergewissern Sie sich, dass entweder der Wert &quot;Buyer Touchpoint aktivieren&quot;auf &quot;Alle Campaign-Mitglieder einschließen&quot;oder zumindest &quot;Respondierte Kampagnenmitglieder einschließen&quot;gesetzt ist oder dass Sie eine benutzerdefinierte Kampagnensynchronisierungsregel erstellt haben, die diese Kampagne enthält. Wenn Sie dies bestätigt haben und die Kampagne immer noch nicht sehen, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} , damit wir überprüfen können, ob Ihre Kampagnen ordnungsgemäß importiert werden.

**Ich muss die Verteilung meiner Kampagne ändern, damit ich sie in bestimmten Monaten schwerer wiegen kann. Wie mache ich das?**

Die Kostenverteilung basiert ausschließlich auf einer gleichmäßigen Verteilung vom Startdatum bis zum Enddatum. Leider können wir es nicht ändern, sodass Ihre Kosten eine andere Gewichtung haben als die festgelegten Daten. Sie können dies steuern, indem Sie das Start- und Enddatum Ihrer Kampagne anpassen, da es auf jeden Tag im Monat ankommt.

**Ich habe in meiner übergeordneten Kampagne Kosten eingerichtet - wie werden die Kinderkampagnen von der übergeordneten Kampagne zugewiesen?**

Tatsächlich wird die Art und Weise, wie Kosten einbezogen werden, direkt von einer einzigen Kampagne übernommen, unabhängig von einer übergeordneten oder untergeordneten Beziehung. Wir empfehlen, die Kosten auf die Kinderkampagnen sowie die Daten der Kampagne zu übertragen und dann die Übergeordnete Kampagne als Dachkampagne zu verwenden, bei der die übergeordnete Kampagne nicht für Touchpoints aktiviert wurde.

**Wie ändere ich die Kosten für einen Monat in [!DNL Marketo Measure]?**

Da wir uns auf das CRM als einzige &quot;Source of Truth&quot; verlassen, müssen alle Änderungen im CRM vorgenommen werden. Sobald die Kampagne von [!DNL Marketo Measure] importiert wurde, können die Kampagnenwerte nicht mehr in [!DNL Marketo Measure] oder der CSV-Datei bearbeitet werden.

**In welchem Szenario würde eine Kampagne in der Tabelle der Marketing-Ausgaben angezeigt und dann nicht mehr angezeigt?**

Es ist weiterhin erforderlich, dass alle drei Schlüsselfelder einen Wert aufweisen: Startdatum, Enddatum und Kosten. Unser Standardverhalten ist, dass wir nur Kampagnen mit einem Wert von mehr als 0 USD importieren. Im Idealfall würden wir Kampagnen importieren, bei denen explizit 0 USD vorhanden ist, und nicht leere Kampagnen importieren. Die Salesforce-API importiert sie jedoch unabhängig vom Wert als 0 USD. Wenn sich der Wert &quot;Buyer Touchpoint aktivieren&quot;von &quot;Alle einschließen&quot;oder &quot;Antwort einschließen&quot;in &quot;Alle ausschließen&quot;ändert, werden die Kampagne und die Kosten aus der Tabelle Marketingausgaben entfernt.

**Welche Kosten würden Vorrang haben, wenn eine Zeile bereits aus dem CRM heruntergeladen wurde und ich eine andere Zeile in die CSV-Datei mit derselben Kampagnen-ID eingegeben habe?**

Obwohl Sie die Datei möglicherweise erfolgreich hochladen können, verwendet [!DNL Marketo Measure] diese Zeile nicht, da wir bereits über eine Kampagnen-ID mit demselben Wert verfügen, der automatisch aus der Integration abgerufen wurde.

**Wie würden Sie vorschlagen, dass wir Kosten aus unseren im CRM-System eingerichteten digitalen Kampagnen übernehmen?**

Da unser JavaScript [!DNL Marketo Measure] bereits die Webaktivität von Ihrer Site verfolgt, empfehlen wir, keine Kampagnen zu synchronisieren, die Campaign-Mitglieder aus Webformularen oder anderen Site-Aktivitäten verfolgen, da dies die Touches verdoppeln wird. Daher können Sie die Option CSV-Upload in Marketing Spend weiterhin verwenden, um diese Online-/Digitalkosten zu verfolgen, wenn wir noch nicht mit dieser Plattform integriert sind (d. h. Twitter, Adroll).
