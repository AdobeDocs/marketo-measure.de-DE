---
unique-page-id: 18874688
description: CRM-Kampagnenkosten - [!DNL Marketo Measure]
title: Kosten für CRM-Kampagnen
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 1%

---

# Kosten für CRM-Kampagnen {#crm-campaign-costs}

Die meisten [!DNL Marketo Measure]-Kunden verwenden CRM-Kampagnen zur Verfolgung von Offline-Marketing-Aktivitäten. Marketer, die diese Kampagnen verwenden, überwachen auch die Kosten innerhalb des CRM. Diese Funktion erleichtert es Marketing-Fachleuten, da [!DNL Marketo Measure] diese Kosten lesen und auf die gemeldeten Marketingausgaben innerhalb von [!DNL Marketo Measure] anwenden können. Bisher mussten Kunden die Kosten für jede Kampagne pro Monat manuell eingeben. Mit den erforderlichen Informationen für [!DNL Marketo Measure] können Benutzer diesen Prozess jedoch automatisieren, sodass Marketing-Experten mehr Zeit mit der Analyse ihrer Ausgaben und ihres ROI verbringen können.

## Verfügbarkeit {#availability}

Diese Funktion ist für alle Kunden von [!DNL Salesforce] und Dynamics verfügbar.

## Funktionsweise {#how-it-works}

[!DNL Marketo Measure] sucht zunächst nach Kampagnen, die für Touchpoints „aktiviert“ wurden, sodass entweder eine entsprechende Kampagnensynchronisierungsregel erstellt wurde oder der Wert „Käufer-Touchpoints aktivieren“ „Alle Kampagnenmitglieder einschließen“ oder „Responded“-Kampagnenmitglieder einschließen“ lautet. Darüber hinaus müssen [!DNL Marketo Measure] die richtigen Werte importieren und wissen, wie die Kosten verteilt werden. Daher müssen die folgenden Felder einen Wert enthalten:

**[!DNL Salesforce]**: `ActualCost`, `StartDate`, `EndDate`

**[!DNL Microsoft Dynamics]**: `totalactualcost`, `actualstart`, `actualend`

Wenn in einem der drei Felder ein Wert fehlt, importiert [!DNL Marketo Measure] die Kosten nicht. Sie können dies korrigieren, indem Sie den Campaign-Datensatz im CRM aktualisieren. Kosten werden nicht importiert, wenn sie auf 0 $ eingestellt sind, da [!DNL Salesforce] leere und 0 $ gleich behandelt.

[!DNL Marketo Measure] die Verteilung einer Kampagne auf mehrere Monate zu bestimmen, wird das Start- und Enddatum der Kampagne verwendet, um den Betrag gleichmäßig pro Tag zu verteilen.

![](assets/1.jpg)

In diesem Beispiel dauert eine Kampagne 109 Tage, sodass die Gesamtkosten von 18.000 US-Dollar die Ausgaben pro Tag auf ~ 165,14 US-Dollar betragen.

Basierend auf der Anzahl der Tage pro Monat erhalten wir diese monatlichen Gesamtwerte, wie Sie in der Tabelle sehen können:

Juli 2018: ($18.000/109) x 31 = $5.119,27

Aug 2018: ($18.000/109) x 31 = $5.119.27

Sep 2018: ($18.000/109) x 30 = $4.954,13

Okt. 2018: ($18.000/109) x 17 = $2.807.34

## Historisch gemeldete Ausgaben {#historical-reported-spend}

Wenn Sie Ausgaben für Kampagnen eingegeben haben, die in der Vergangenheit verfolgt wurden und einer CRM-Kampagne zugeordnet wurden, werden keine der eingegebenen Kosten überschrieben. Wenn dieselbe Kampagne im CRM geändert wird, wird sie ignoriert und den Änderungen, die Sie zuvor im CSV-Upload vorgenommen haben, Priorität eingeräumt.

Wenn Sie es vorziehen würden, dass wir ab jetzt die CRM-Kampagnenkosten nehmen, ändern Sie den Wert in der CSV auf $0, wodurch der Eintrag ungültig wird. Wenn die Aufträge das nächste Mal ausgeführt werden, um die Kosten zu importieren, werden zuvor bearbeitete Berichte abgerufen.

## Kampagnen ohne Touchpoints {#campaigns-with-no-touchpoints}

Viele Marketing-Fachleute melden Marketing-Ausgaben für CRM-Kampagnen, die keine Touchpoints generiert haben oder über keine Kampagnenmitglieder verfügen, um Ausgaben zu verfolgen. Solange die drei Felder ausgefüllt sind (Startdatum, Enddatum, Kosten) und die Kampagne für Touchpoints aktiviert ist, ruft [!DNL Marketo Measure] diese Kosten ab, auch wenn keine Touchpoints damit verknüpft sind.

Dies kann hilfreich sein, um Ausgaben für überschüssige Marketing-Kosten oder Tools zu verfolgen, die in Ihre ROI-Berechnungen einfließen.

## Marketo-Programmsynchronisierung {#marketo-program-sync}

Wenn Sie Marketo-Programme als Kampagnen in das CRM einbinden, stellen Sie sicher, dass Sie das Startdatum, Enddatum und das Periodenkosten-Mapping für die erforderlichen CRM-Felder eingerichtet haben. Da es keine Zuordnung zum Feld Käufer-Touchpoints aktivieren gibt, müssen Sie diese Kampagnen dennoch aktivieren, damit die Kosten ermittelt werden können.

## Kosten bearbeiten {#editing-the-costs}

Nachdem eine Kampagne aus dem CRM importiert wurde, wird sie ähnlich wie ein API-Werbeanbieter behandelt und nicht mehr in der CSV-Datei angezeigt, um Änderungen an den Kosten vorzunehmen.

Alle Änderungen an den Kosten oder der Verteilung müssen im CRM vorgenommen werden, damit wir auf einen einzigen Punkt der Wahrheit verweisen können.

## FAQs {#faq}

**Ich habe eine Änderung an meiner Kampagne vorgenommen. Wann sollte ich die Änderungen in der Tabelle der Marketingausgaben oder in meinen Berichten erwarten?**

3-4 Stunden

**Ich habe das Start- und Enddatum sowie die Kosten ausgefüllt, aber warum werden meine Kosten immer noch nicht in [!DNL Marketo Measure] angezeigt?**

Vergewissern Sie sich, dass Sie entweder den Wert &quot;Buyer Touchpoint aktivieren“ auf „Alle Kampagnenmitglieder einschließen“ oder zumindest „Respondierte Kampagnenmitglieder einschließen“ gesetzt haben oder dass Sie eine benutzerdefinierte Kampagnensynchronisierungsregel erstellt haben, die diese Kampagne enthält. Wenn Sie dies bestätigt haben und die Kampagne immer noch nicht angezeigt wird, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} damit wir überprüfen können, ob Ihre Kampagnen ordnungsgemäß importiert werden.

**Ich muss die Verteilung meiner Kampagne ändern, damit ich sie in bestimmten Monaten schwerer wiegen kann. Wie mache ich das?**

Die Verteilung der Kosten basiert ausschließlich auf einer gleichmäßigen Verteilung vom Start- bis zum Enddatum. Leider können wir es nicht ändern, sodass Ihre Kosten abgesehen von den festgelegten Terminen eine andere Gewichtung haben. Sie können dies steuern, indem Sie das Start- und Enddatum Ihrer Kampagne anpassen, da jeder Tag im Monat wichtig ist.

**Ich habe die Kosten für meine übergeordnete Kampagne eingerichtet. Wie werden die Kosten für die untergeordneten Kampagnen der übergeordneten Kampagne zugeordnet?**

Tatsächlich werden die Kosten direkt aus einer einzelnen Kampagne abgeleitet, unabhängig von einer Eltern- oder Kinderbeziehung. Wir empfehlen, die Kosten für die Kampagnen für untergeordnete Elemente zusammen mit den Daten der Kampagne zu übernehmen und dann die übergeordnete Kampagne als Überlagerungskampagne zu verwenden, bei der die übergeordnete Kampagne nicht für Touchpoints aktiviert wird.

**Wie ändere ich die Kosten für einen Monat in [!DNL Marketo Measure]?**

Da wir uns auf das CRM als zentrale Datenquelle verlassen, müssen alle Änderungen im CRM vorgenommen werden. Nachdem die Kampagne von [!DNL Marketo Measure] importiert wurde, können die Kampagnenwerte in [!DNL Marketo Measure] oder in der CSV-Datei nicht mehr bearbeitet werden.

**In welchem Szenario würde eine Kampagne in der Tabelle „Marketingausgaben“ angezeigt und dann nicht mehr?**

Wir fordern weiterhin, dass alle drei Schlüsselfelder einen Wert aufweisen: Startdatum, Enddatum und Kosten. Unser Standardverhalten ist, dass wir nur Kampagnen mit einem Wert größer als 0 $ importieren. Idealerweise importieren wir Kampagnen mit einem expliziten $0-Wert und nicht solche, die leer gelassen werden. Die Salesforce-API importiert jedoch beide als $0, unabhängig vom Wert. Wenn sich der Wert Buyer Touchpoint aktivieren von „Alle einschließen“ oder „Beantwortet einschließen“ in „Alle ausschließen“ ändert, entfernen wir außerdem die Kampagne und die Kosten aus der Tabelle Marketing-Ausgaben .

**Welche Kosten hätten Vorrang, wenn bereits eine Zeile aus dem CRM heruntergeladen wurde und ich eine weitere Zeile mit derselben Kampagnen-ID in die CSV-Datei eingegeben hätte?**

Obwohl Sie die Datei möglicherweise erfolgreich hochladen können, verwendet [!DNL Marketo Measure] diese Zeile nicht, da wir bereits über eine Kampagnen-ID mit demselben Wert verfügen, der automatisch aus der Integration abgerufen wurde.

**Wie würden Sie vorschlagen, dass wir die IT-Kosten aus unseren digitalen Kampagnen übernehmen, die wir im CRM eingerichtet haben?**

Da unser [!DNL Marketo Measure] JavaScript bereits Web-Aktivitäten von Ihrer Site aus verfolgt, raten wir davon ab, Kampagnen zu synchronisieren, die Kampagnenmitglieder von Web-Formularen oder anderen Site-Aktivitäten verfolgen, da dies die Anzahl der Kontakte verdoppelt. Aus diesem Grund sollten Sie die CSV-Upload-Option in den Marketingausgaben weiterhin verwenden, um diese Online-/Digitalkosten zu verfolgen, wenn wir noch nicht mit dieser Plattform integriert sind (d. h. Twitter, Adroll).
