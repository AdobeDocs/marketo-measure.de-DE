---
unique-page-id: 18874688
description: CRM-Kampagnenkosten - [!DNL Marketo Measure]
title: Kosten für CRM-Kampagnen
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 0%

---

# Kosten für CRM-Kampagnen {#crm-campaign-costs}

Am meisten [!DNL Marketo Measure] -Kunden verwenden CRM-Kampagnen zur Verfolgung von Offline-Marketingaktivitäten. Marketingexperten, die diese Kampagnen nutzen, überwachen auch die Kosten im CRM-System. Diese Funktion erleichtert Marketingexperten die Arbeit, indem sie [!DNL Marketo Measure] , um diese Kosten zu lesen und sie auf die gemeldeten Marketing-Ausgaben in [!DNL Marketo Measure]. Bisher mussten die Kunden die Kosten für jede Kampagne pro Monat manuell eingeben, jedoch mit den erforderlichen Informationen, die uns zur Verfügung gestellt wurden. [!DNL Marketo Measure] kann diesen Prozess automatisieren, sodass Marketing-Experten mehr Zeit für die Analyse ihrer Ausgaben und ihres ROI verbringen können.

## Verfügbarkeit {#availability}

Diese Funktion ist für alle [!DNL Salesforce] und Dynamics-Kunden.

## Funktionsweise {#how-it-works}

[!DNL Marketo Measure] sucht zunächst nach Kampagnen, die für Touchpoints &quot;aktiviert&quot;wurden. Es wurde also entweder eine passende Kampagnensynchronisierungsregel erstellt oder der Wert &quot;Käufer-Touchpoints aktivieren&quot;lautet &quot;Alle Kampagnenmitglieder einschließen&quot;oder &quot;Respondierte Kampagnenmitglieder einschließen&quot;. Darüber hinaus [!DNL Marketo Measure] die richtigen Werte importieren und wissen müssen, wie die Kosten verteilt werden, sodass die folgenden Felder einen Wert enthalten müssen:

**[!DNL Salesforce]**: ActualCost, StartDate, EndDate

**[!DNL Microsoft Dynamics]**: totalactualcost, actualstart, tatsächliche

Wenn in einem der 3 Felder ein Wert fehlt, [!DNL Marketo Measure] nicht die Kosten importieren. Korrigieren Sie dies, indem Sie den Campaign-Datensatz im CRM aktualisieren. Wichtig ist auch, dass wir die Kosten nicht importieren, wenn sie explizit auf 0 USD gesetzt sind, da [!DNL Salesforce] behandelt leer und $0 gleich.

Zur [!DNL Marketo Measure] Um die monatliche Verteilung einer Kampagne zu bestimmen, verwenden wir das Start- und Enddatum der Kampagne und verteilen den Betrag gleichmäßig pro Tag.

![](assets/1.jpg)

In diesem Beispiel haben wir also eine Kampagne, die 109 Tage dauert. Mit Gesamtkosten von 18.000 US-Dollar beläuft sich die tägliche Ausgabe also auf ~ 165,14 US-Dollar.

Basierend auf der Anzahl der Tage pro Monat erhalten wir diese monatlichen Summen, wie Sie in der Tabelle sehen können:

Juli 2018: ($18.000/109) x 31 = 5.119,27 $

August 2018: ($18.000/109) x 31 = 5.119,27 $

Sep 2018: ($18.000/109) x 30 = $4.954.13

Okt. 2018: ($18.000/109) x 17 = $2.807.34

## Historische Ausgaben in Berichten {#historical-reported-spend}

Mach dir keine Sorgen! Wenn Sie Ausgaben für Kampagnen eingegeben haben, die wir in der Vergangenheit verfolgt und einer CRM-Kampagne zugeordnet haben, werden keine der eingegebenen Kosten überschrieben. Wenn dieselbe Kampagne im CRM geändert wird, wird sie dennoch ignoriert und den Änderungen, die Sie zuvor im CSV-Upload vorgenommen haben, Priorität eingeräumt.

Wenn Sie es vorziehen würden, die Kosten der CRM-Kampagne fortzuführen, können Sie den Wert in der CSV-Datei auf 0 USD ändern, wodurch der Eintrag annulliert wird. Wenn wir dann das nächste Mal unsere Aufträge zum Importieren der Kosten ausführen, werden wir nach allen Datensätzen suchen, die zuvor bearbeitet wurden, und diese abrufen.

## Kampagnen ohne Touchpoints {#campaigns-with-no-touchpoints}

Viele Marketingexperten melden Marketingausgaben für CRM-Kampagnen, die nicht zufällig Touchpoints generiert haben, oder haben wissentlich keine Campaign-Mitglieder, um Ausgaben verfolgen zu können. Solange die drei Felder ausgefüllt sind (Startdatum, Enddatum, Kosten) und die Kampagne für Touchpoints aktiviert ist, [!DNL Marketo Measure] berücksichtigt diese Kosten immer noch, unabhängig davon, ob Touchpoints zugeordnet sind oder nicht.

Dies könnte hilfreich sein, um Ausgaben für überschüssige Marketing-Kosten oder Tools zu verfolgen, die diese in Ihre ROI-Berechnungen einfließen lassen.

## Marketo-Programmsynchronisierung {#marketo-program-sync}

Wenn Sie Marketo-Programme als Kampagnen in das CRM-System integrieren, sollten Sie sicherstellen, dass die Zuordnung von Startdatum, Enddatum und Period Cost zu den erforderlichen CRM-Feldern eingerichtet ist. Da es keine Zuordnung zum Feld &quot;Käufer-Touchpoints aktivieren&quot;gibt, müssen Sie diese Kampagnen weiterhin aktivieren, damit wir wissen, dass wir die Kosten für sie übernehmen können.

## Bearbeiten der Kosten {#editing-the-costs}

Nachdem eine Kampagne aus dem CRM importiert wurde, wird sie einem API-Anzeigenanbieter ähnlich behandelt und nicht in der CSV angezeigt, um Kostenänderungen vorzunehmen.

Änderungen an Kosten oder Verteilung müssen im CRM vorgenommen werden, damit wir auf einen einzigen Punkt der Wahrheit verweisen können.

## FAQs {#faq}

**Ich habe eine Änderung an meiner Kampagne vorgenommen - wann sollte ich mit den Änderungen in der Tabelle Marketing-Ausgaben oder in meinem Bericht rechnen?**

3-4 Stunden

**Ich habe das Start- und Enddatum sowie die Kosten ausgefüllt, aber warum werden meine Kosten immer noch nicht angezeigt? [!DNL Marketo Measure]?**

Vergewissern Sie sich, dass entweder der Wert &quot;Käufer-Touchpoint aktivieren&quot;auf &quot;Alle Kampagnenmitglieder einschließen&quot;oder zumindest auf &quot;Respondierte Kampagnenmitglieder einschließen&quot;gesetzt ist oder dass Sie eine benutzerdefinierte Kampagnensynchronisierungsregel erstellt haben, die diese Kampagne enthält. Wenn Sie dies bestätigt haben und die Kampagne trotzdem nicht sehen, wenden Sie sich an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} damit wir überprüfen können, ob Ihre Kampagnen ordnungsgemäß importiert werden.

**Ich muss die Verteilung meiner Kampagne ändern, damit ich sie in bestimmten Monaten schwerer wiegen kann. Wie mache ich das?**

Die Kostenverteilung basiert ausschließlich auf einer gleichmäßigen Verteilung vom Startdatum bis zum Enddatum. Leider können wir es nicht ändern, sodass Ihre Kosten eine andere Gewichtung haben als die festgelegten Daten. Sie können dies steuern, indem Sie das Start- und Enddatum Ihrer Kampagne anpassen, da es auf jeden Tag im Monat ankommt.

**Ich habe in meiner übergeordneten Kampagne Kosten eingerichtet - wie werden die Kinderkampagnen von der übergeordneten Kampagne zugewiesen?**

Tatsächlich wird die Art und Weise, wie Kosten einbezogen werden, direkt von einer einzigen Kampagne übernommen, unabhängig von einer übergeordneten oder untergeordneten Beziehung. Wir empfehlen, die Kosten auf die Kinderkampagnen sowie die Daten der Kampagne zu übertragen und dann die Übergeordnete Kampagne als Dachkampagne zu verwenden, bei der die übergeordnete Kampagne nicht für Touchpoints aktiviert wurde.

**Wie ändere ich die Kosten für einen Monat in [!DNL Marketo Measure]?**

Da wir uns auf das CRM als einzige &quot;Source of Truth&quot; verlassen, müssen alle Änderungen im CRM vorgenommen werden. Nachdem die Kampagne importiert wurde von [!DNL Marketo Measure], sind die Kampagnenwerte in [!DNL Marketo Measure] oder in der CSV-Datei.

**In welchem Szenario würde eine Kampagne in der Tabelle Marketing-Ausgaben angezeigt und dann nicht mehr angezeigt?**

Es wird weiterhin erforderlich sein, dass alle drei Schlüsselfelder einen Wert aufweisen: Startdatum, Enddatum und Kosten. Unser Standardverhalten ist, dass wir nur Kampagnen mit einem Wert von mehr als 0 USD importieren. Im Idealfall würden wir Kampagnen importieren, bei denen explizit 0 USD vorhanden ist, und nicht leere Kampagnen importieren. Die Salesforce-API importiert sie jedoch unabhängig vom Wert als 0 USD. Wenn sich der Wert &quot;Käufer-Touchpoint aktivieren&quot;von &quot;Alle einschließen&quot;oder &quot;Antwort einschließen&quot;in &quot;Alle ausschließen&quot;ändert, werden die Kampagne und die Kosten aus der Tabelle Marketing-Ausgaben entfernt.

**Welche Kosten wären vorrangig, wenn eine Zeile bereits aus dem CRM-System heruntergeladen wurde und ich eine andere Zeile in die CSV-Datei mit derselben Kampagnen-ID eingegeben habe?**

Obwohl Sie die Datei möglicherweise erfolgreich hochladen können, [!DNL Marketo Measure] verwendet diese Zeile nicht, da wir bereits über eine Kampagnen-ID mit demselben Wert verfügen, der automatisch aus der Integration abgerufen wurde.

**Wie würden Sie vorschlagen, dass wir Kosten aus unseren im CRM-System eingerichteten digitalen Kampagnen übernehmen?**

weil unsere [!DNL Marketo Measure] JavaScript verfolgt bereits Web-Aktivitäten von Ihrer Site aus. Wir empfehlen, keine Kampagnen zu synchronisieren, die Campaign-Mitglieder über Webformulare oder andere Site-Aktivitäten verfolgen, da dies die Touches verdoppeln wird. Daher können Sie die Option CSV-Upload in Marketing Spend weiterhin verwenden, um diese Online-/Digitalkosten zu verfolgen, wenn wir noch nicht mit dieser Plattform integriert sind (d. h. Twitter, Adroll).
