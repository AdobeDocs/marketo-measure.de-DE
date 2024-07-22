---
unique-page-id: 18874779
description: Benutzerdefiniertes Attributionsmodell und Einrichtung - [!DNL Marketo Measure]
title: Benutzerdefiniertes Attributionsmodell und Einrichtung
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---

# Benutzerdefiniertes Attributionsmodell und Einrichtung {#custom-attribution-model-and-setup}

Unten finden Sie einen Überblick über das benutzerdefinierte Attributionsmodell [!DNL Marketo Measure] und dessen Einrichtung.

## Benutzerdefiniertes Attributionsmodell {#custom-attribution-model}

Mit dem Modell [!DNL Marketo Measure] Benutzerdefinierte Zuordnung können Benutzer auswählen, welche Touchpoints oder benutzerdefinierten Bühnen in das Modell aufgenommen werden sollen. Benutzer können den Prozentsatz der Umsatzgutschriften steuern, die diesen Touchpoints und Bühnen zugeordnet werden, oder die vom Modell für maschinelles Lernen empfohlenen Attributionsprozentwerte verwenden.[!DNL Marketo Measure]

## Einrichten Ihres benutzerdefinierten Attributionsmodells {#how-to-set-up-your-custom-attribution-model}

1. Bestimmen Sie, welche Phasen Sie in Ihr benutzerdefiniertes Modell aufnehmen möchten.

   Um mit der Erstellung Ihres benutzerdefinierten Attributionsmodells zu beginnen, müssen Sie auswählen, welche Phasen für Ihr Marketing-Team wichtig sind. Zusätzlich zu den [!DNL Marketo Measure] Meilensteinen (FT, LC, OC, Closed) können Sie bis zu sechs weitere Lead-/Kontaktstatus- oder Opportunity-Phasen in Ihrem benutzerdefinierten Modell hinzufügen. Beispielsweise ist es üblich, dass die MQL-Bühne in das benutzerdefinierte Modell aufgenommen wird. Marketing-Teams möchten häufig wissen, welche Bemühungen oder Kanäle den Übergang zur MQL-Phase vorantreiben.

   Anmelden bei [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Wechseln Sie zu [!UICONTROL Mein Konto] > [!UICONTROL Einstellungen] > und wählen Sie im Abschnitt &quot;CRM&quot;die Option **[!UICONTROL Staging-Zuordnung]** aus.

   Wählen Sie als Nächstes aus, welche Leads/Kontakte und Opportunity-Phasen eingeschlossen werden sollen, indem Sie das Feld **[!UICONTROL In Modell einschließen]** auswählen.

   >[!NOTE]
   >
   >Sie können bis zu sechs benutzerdefinierte Phasen ausführen (ohne die Standardeinstellungen: FT, LC, OC, Closed).

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_Alle_ Leads/Kontakte und Opportunity-Phasen werden hier angezeigt, auch wenn die Bühne inaktiv ist oder nicht mehr in [!DNL Salesforce] verwendet wird. Wenn Sie diese Bühnen entfernen möchten, müssen Sie sie in [!DNL Salesforce] löschen.

   Wenn Sie Ihre Bühnen ausgewählt haben, klicken Sie unten auf der Seite auf die Schaltfläche **[!UICONTROL Speichern und verarbeiten]** . Die Phasen werden jetzt auf der Registerkarte **[!UICONTROL Attributionseinstellungen]** angezeigt und Sie können jedem Schritt Zuordnungsprozentsätze zuweisen. Benutzerdefinierte Bühnen werden auch in der Marketing Performance Suite als Lead- oder Opportunity-Phase im Demand Waterfall angezeigt.

   Wenn es andere Phasen gibt, die Sie in das Modell einbeziehen möchten, die jedoch nicht in der Liste [!UICONTROL Lead-/Kontaktstatus] oder [!UICONTROL Opportunity Stage] enthalten sind, können Sie eine eigene benutzerdefinierte Phase anhand von Feldern in Ihrem CRM-System definieren.

   Im folgenden Beispiel wird eine benutzerdefinierte MQL-Phase mithilfe eines Datumsfelds definiert. In der Regel wird lediglich festgelegt, dass das Feld MQL-Datum, wenn es nicht leer ist, als MQL betrachtet werden und in das benutzerdefinierte Modell aufgenommen werden sollte. Es ist auch wichtig, die benutzerdefinierten Phasen nach deren Erstellung zu sortieren, damit sie dem Fortschritt Ihres Verkaufszyklus folgen.

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >Vergessen Sie nicht, die Verlaufsverfolgung für benutzerdefinierte Felder zu aktivieren.

Wenn in Ihrem benutzerdefinierten Modell ein benutzerdefiniertes Feld verwendet wird, MUSS das Feldverlauf-Tracking im CRM aktiviert werden. Anweisungen zum Aktivieren der Verfolgung des Feldverlaufs finden Sie unter [Einrichten des benutzerdefinierten Modells: Verfolgung des Feldverlaufs aktivieren](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. Bestimmen Sie die Attributionsprozentsätze für das benutzerdefinierte Modell.

   Navigieren Sie zu &quot;**[!UICONTROL Attributionseinstellungen]**&quot;in &quot;[!DNL Marketo Measure] Apps&quot;. Die benutzerdefinierten Phasen werden hier in der Attributionstabelle angezeigt. Die Attributionstabelle enthält alle [!DNL Marketo Measure] -Attributionsmodelle und die Attributionsgewichtung der einzelnen Modelle. Die Attributionsprozentsätze der ersten fünf Modelle sind fest und können nicht geändert werden.

   In der Spalte ganz rechts mit der Bezeichnung &quot;**[!UICONTROL Benutzerdefiniert]**&quot; können Sie die Prozentgewichtung für jede Phase in Ihrem benutzerdefinierten Attributionsmodell festlegen. Geben Sie die Werte für jede Phase in die Spalte &quot;Benutzerdefiniert&quot;ein und klicken Sie nach Abschluss auf **[!UICONTROL Speichern und erneut verarbeiten]** .

   Links neben der Spalte _Benutzerdefiniert_ befindet sich das Modell **[!DNL Marketo Measure]Machine Learning**. Das Modell für maschinelles Lernen berechnet die Zuordnungsgewichtung anhand der relativen Bedeutung für den Gewinn eines Deals, je nachdem, was in jeder benutzerdefinierten Phase passiert ist. Weitere Informationen zum Modell für maschinelles Lernen finden Sie unter [FAQ zum Modell für maschinelles Lernen](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## Touchpoint-Positionen {#touchpoint-positions}

Nachdem die Attributionsprozentsätze gespeichert und verarbeitet wurden, werden die Touchpoints aktualisiert und erhalten ihre neuen Bühnen und Positionen. Der Touchpoint, der zuletzt vor einer Staging-Transition aufgetreten ist, erhält die Gutschrift für diese Phase (wie unten dargestellt). Auch die benutzerdefinierte Gewichtung und der Umsatz werden umverteilt.

![](assets/4.png)

## Der Unterschied zwischen Trichterphasen und benutzerdefinierten Modellphasen {#the-difference-between-funnel-stages-and-custom-model-stages}

Sie können jetzt benutzerdefinierte Bühnen in Ihrem Marketing-Trichter sehen, selbst wenn Sie kein benutzerdefiniertes Modell aktiviert haben. Dies würde durch die Verwendung unserer Trichterschrittfunktion erfolgen. Trichterschritte ermöglichen es Ihnen jetzt, dem Trichter Bühnen hinzuzufügen, aber keine Attribution für sie zu sehen.

Trichterphasen werden weiterhin als Touchpoints verfolgt und in Ihrem CRM weiterhin als Touchpoint-Positionen angezeigt. Ohne benutzerdefiniertes Modell erhalten diese Touchpoints weiterhin die mittlere Touchzuordnung, wenn ein Formular ausgefüllt wird (10 % für Mittelkontakt), aber keine Attribution, wenn es nur ein Webbesuch ist.

Wie Sie unten sehen können, haben wir die Phase der Sorgfalt als Teil unserer Trichterphasen aufgenommen. Das bedeutet, dass wir Touchpoints haben, bei denen die Position &quot;Sorgfalt&quot;enthält. Diese Touchpoints erhalten jedoch nur dann eine Attribution-Gutschrift für den Nahen Kontakt, wenn das benutzerdefinierte Modell nicht aktiviert ist (höchstens 10 %).

![](assets/5.png)

>[!NOTE]
>
>Das Verhalten BAT benutzerdefinierten Modelle besteht darin, den mittleren Touch-Prozentsatz des benutzerdefinierten Modells gleichmäßig auf andere Phasen zu unterteilen, sofern es keine mittleren Touches gibt.
