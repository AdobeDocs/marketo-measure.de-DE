---
description: Benutzerdefiniertes Attributionsmodell und Einrichtungshandbuch für Marketo Measure-Benutzende
title: Benutzerdefiniertes Attributionsmodell und Einrichtung
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 1%

---

# Benutzerdefiniertes Attributionsmodell und Einrichtung {#custom-attribution-model-and-setup}

Unten finden Sie einen Überblick über das [!DNL Marketo Measure] benutzerdefinierte Attributionsmodell und dessen Einrichtung.

## Benutzerdefiniertes Attributionsmodell {#custom-attribution-model}

Mit dem [!DNL Marketo Measure] benutzerdefinierten Attributionsmodell können Benutzer auswählen, welche Touchpoints oder benutzerdefinierten Stadien in das Modell aufgenommen werden sollen. Benutzer können den Prozentsatz des Umsatzguthabens steuern, der diesen Touchpoints und Stadien zugeordnet ist, oder die prozentualen Zuordnungswerte verwenden, die vom Modell des [!DNL Marketo Measure] maschinellen Lernens vorgeschlagen werden.

## Einrichten des benutzerdefinierten Attributionsmodells {#how-to-set-up-your-custom-attribution-model}

1. Bestimmen Sie, welche Stadien Sie in Ihr benutzerdefiniertes Modell aufnehmen möchten.

   Um mit der Erstellung Ihres benutzerdefinierten Attributionsmodells zu beginnen, müssen Sie auswählen, welche Stadien für Ihr Marketing-Team wichtig sind. Zusätzlich zu den [!DNL Marketo Measure] Meilensteinphasen (FT, LC, OC, Closed) können Sie in Ihrem benutzerdefinierten Modell bis zu sechs zusätzliche Lead-/Kontaktstatus- oder Opportunity-Phasen hinzufügen. Beispielsweise ist es üblich, dass der SQL-Schritt im benutzerdefinierten Modell enthalten ist. Marketing-Teams möchten oft wissen, welche Bemühungen oder Kanäle den Übergang zur MQL-Phase fördern.

   Anmelden bei [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Gehen Sie zu [!UICONTROL Mein Konto] > [!UICONTROL Einstellungen] > und wählen Sie im Abschnitt CRM die Option **[!UICONTROL Stadienzuordnung]**.

   Wählen Sie als Nächstes aus, welche Leads/Kontakte und Opportunity-Stadien einbezogen werden sollen, indem Sie das Feld **[!UICONTROL In Modell einbeziehen]** auswählen.

   >[!NOTE]
   >
   >Es sind bis zu sechs benutzerdefinierte Phasen zulässig (ohne die Standardwerte: FT, LC, OC, Closed).

   ![Es sind bis zu sechs benutzerdefinierte Phasen zulässig (ohne die Standardwerte:](assets/custom-models-1.png)

   >[!NOTE]
   >
   >_Alle_ Leads/Kontakte und Opportunity-Phasen werden hier angezeigt, auch wenn die Phase inaktiv ist oder nicht mehr in [!DNL Salesforce] verwendet wird. Wenn Sie diese Stadien entfernen möchten, müssen Sie sie in [!DNL Salesforce] schwer löschen.

   Klicken Sie nach der Auswahl der Stadien auf die Schaltfläche **[!UICONTROL Speichern und verarbeiten]** unten auf der Seite. Die Stadien werden jetzt auf der Registerkarte **[!UICONTROL Attributionseinstellungen]** angezeigt und Sie können jedem Stadium Attributionsprozentsätze zuweisen. Benutzerdefinierte Stadien werden auch in der Marketing Performance Suite als Lead- oder Opportunity-Phase im Demand Waterfall angezeigt.

   Wenn Sie andere Phasen in das Modell aufnehmen möchten, diese aber nicht in der Liste [!UICONTROL Lead-/Kontaktstatus] oder [!UICONTROL Opportunity-] aufgeführt sind, können Sie Ihr eigenes benutzerdefiniertes Stadium basierend auf Feldern in Ihrem CRM definieren.

   Im folgenden Beispiel wird eine benutzerdefinierte „MQL“-Phase mithilfe eines Datumsfelds definiert. Die Regel besagt einfach, dass das Feld „MQL-Datum“, wenn es nicht leer ist, als MQL betrachtet und in das benutzerdefinierte Modell aufgenommen werden sollte. Es ist auch wichtig, die benutzerdefinierten Stadien nach ihrer Erstellung zu sortieren, damit sie dem Verlauf Ihres Verkaufszyklus folgen.

   ![Im folgenden Beispiel wird eine benutzerdefinierte „MQL“-Phase mithilfe eines definiert](assets/custom-models-10.png)

   >[!CAUTION]
   >
   >Vergessen Sie nicht, die Verlaufsverfolgung für benutzerdefinierte Felder zu aktivieren.

Wenn ein benutzerdefiniertes Feld in Ihrem benutzerdefinierten Modell verwendet wird, MUSS das Tracking des Feldverlaufs im CRM aktiviert sein. Anweisungen zum Aktivieren der Feldverlaufsverfolgung finden Sie unter [Benutzerdefinierte Modelleinrichtung: Feldverlaufsverfolgung aktivieren](/help/channel-tracking-and-setup/custom-model-setup-enable-field-history-tracking.md).

1. Bestimmen Sie die Prozentsätze der Attribution für das benutzerdefinierte Modell.

   Navigieren Sie zu **[!UICONTROL Attributionseinstellungen]** in [!DNL Marketo Measure] Apps. Die benutzerdefinierten Stadien werden hier in der Attributionstabelle angezeigt. Die Attributionstabelle zeigt alle [!DNL Marketo Measure] Attributionsmodelle und die Attributionsgewichtung jedes Modells an. Die Attributionsprozentsätze der ersten fünf Modelle sind fest und können nicht geändert werden.

   In der Spalte ganz rechts mit der Beschriftung **[!UICONTROL Benutzerdefiniert]** können Sie die prozentuale Gewichtung für jede Phase in Ihrem benutzerdefinierten Attributionsmodell festlegen. Geben Sie die Werte für jedes Stadium unter der Spalte Benutzerdefiniert ein und klicken Sie **[!UICONTROL Speichern und erneut verarbeiten]** wenn Sie fertig sind.

   Links neben der Spalte _Benutzerdefiniert_ befindet sich das **[!DNL Marketo Measure]Modell für maschinelles Lernen**. Das Modell für maschinelles Lernen berechnet die Attributionsgewichtung basierend auf der relativen Bedeutung des Gewinns eines Angebots in Abhängigkeit davon, was in jeder benutzerdefinierten Phase passiert ist. Weitere Informationen zum Modell für maschinelles Lernen finden Sie unter [Häufig gestellte Fragen zum Modell für maschinelles Lernen](/help/channel-tracking-and-setup/machine-learning-model-faq.md).

   ![Links neben der benutzerdefinierten Spalte befindet sich die Marketo Measure](assets/custom-models-2.png)

## Touchpoint-Positionen {#touchpoint-positions}

Nachdem die Attributionsprozentsätze gespeichert und verarbeitet wurden, werden die Touchpoints aktualisiert und erhalten ihre neuen Stadien und Positionen. Der Touchpoint, der zuletzt vor einem Stadienübergang aufgetreten ist, erhält eine Gutschrift für dieses Stadium (wie unten gezeigt). Die benutzerdefinierte Gewichtung und der Umsatz werden ebenfalls neu verteilt.

![Nachdem die Prozentsätze der Attribution gespeichert und verarbeitet wurden, werden die Touchpoints](assets/custom-models-3.png)

## Der Unterschied zwischen Funnel-Stadien und benutzerdefinierten Modellstadien {#the-difference-between-funnel-stages-and-custom-model-stages}

Sie können jetzt benutzerdefinierte Stadien in Ihrer Marketing-Funnel sehen, auch wenn Sie das benutzerdefinierte Modell nicht aktiviert haben. Dies geschieht durch die Verwendung unserer Funnel-Staging-Funktion. Funnel-Stadien bieten Ihnen jetzt die Möglichkeit, der funnel Stadien hinzuzufügen, aber keine Attribution dafür zu sehen.

Funnel-Stadien werden weiterhin als Touchpoints verfolgt und erscheinen weiterhin als Touchpoint-Positionen in Ihrem CRM. Ohne benutzerdefiniertes Modell erhalten diese Touchpoints möglicherweise weiterhin die Attribution „Middle Touch“, wenn ein Formular ausgefüllt ist (10 % für Middle Touches), aber keine Attribution, wenn es sich nur um einen Web-Besuch handelt.

Wie Sie unten sehen können, haben wir die Diligence-Phase als Teil unserer Funnel-Stadien einbezogen. Dies bedeutet, dass wir Touchpoints haben, bei denen die Position Sorgfalt enthält, aber diese Touchpoints erhalten nur dann eine Attribution auf mittlere Berührung, wenn das benutzerdefinierte Modell nicht aktiviert ist (höchstens 10 %).

![Wie Sie unten sehen können, haben wir die Diligence-Phase als separate Phase einbezogen](assets/custom-models-7.png)

>[!NOTE]
>
>Bei benutzerdefinierten BAT-Modellen gilt es, den Prozentsatz der mittleren Berührung eines benutzerdefinierten Modells gleichmäßig auf andere Stadien zu verteilen, sofern keine mittleren Berührungen vorhanden sind.
