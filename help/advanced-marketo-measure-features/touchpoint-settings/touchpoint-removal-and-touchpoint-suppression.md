---
unique-page-id: 18874710
description: Touchpoint-Entfernung und Touchpoint-Unterdrückung - [!DNL Marketo Measure]
title: Entfernen von Touchpoints und Unterdrückung von Touchpoints
exl-id: 201af648-6525-4a80-a7e5-3cbeeb1670b6
feature: Touchpoints
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Entfernen von Touchpoints und Unterdrückung von Touchpoints {#touchpoint-removal-and-touchpoint-suppression}

Erfahren Sie, wie Sie Touchpoints, die bestimmte Kriterien erfüllen, aus Ihrem CRM entfernen oder unterdrücken können. Dies kann hilfreich sein, um Speicherplatz freizugeben, wenn Sie [!DNL Salesforce] Datenspeicherungsbeschränkungen haben.

Es gibt einen wichtigen Unterschied zwischen Regeln zum Entfernen von Touchpoints und Regeln zur Touchpoint-Unterdrückung:

* Touchpoint-Entfernung - [!DNL Marketo Measure] löscht (d. h. entfernt) alle Touchpoints aus Ihrem CRM, die den Regelkriterien entsprechen. Die Daten _können_ im [!DNL Marketo Measure] ROI-Dashboard gemeldet werden, nicht mehr im CRM.
* Touchpoint-Unterdrückung - Ähnlich wie beim Entfernen eines Touchpoints, aber die Daten können nicht im ROI-Dashboard gemeldet werden.

Bevor Sie mit der Erstellung von Regeln zum Entfernen/Unterdrücken von Touchpoints beginnen, empfehlen wir, Ihren Implementierungsplan mit Ihrem Marketing- und Vertriebs-Team zu teilen. Sie sollten bereits eine Vorstellung davon haben, welche Typen oder Werte Sie entfernen möchten. Einige der gängigen Anwendungsfälle sind:

* Löschen von Touchpoints aus abgeschlossenen verlorenen Opportunities
* Touchpoints aus sehr alten Leads löschen
* Löschen von Touchpoints aus nicht qualifizierten Leads

Nachdem die Regeln gespeichert wurden, bereinigen [!DNL Marketo Measure] Ihr Attributionsmodell und verteilen es neu. Dies bedeutet, dass sich die Meilensteine und Positionen ändern und sich die Attribution-Credits Ihres Kanals ändern werden! Dadurch werden Ihre Daten geändert. Wenden Sie sich bei Bedarf an Ihren Success Manager.

`1)` Es gibt zwei Abschnitte für Entfernungs-/Unterdrückungseinstellungen. Sie haben die Möglichkeit, sie für Käufer-Touchpoints (Leads und Kontakte) oder Käufer-Attribution-Touchpoints (Kontakte, Opportunities und Konten) einzurichten.

Beginnen Sie mit dem Hinzufügen einer Regel und der Auswahl des Felds, das Ihre Kriterien definiert.

Wählen Sie aus einer Liste von Operatoren aus, die sich auf den nächsten Wertesatz beziehen, den Sie in der nächsten Spalte hinzufügen.

![](assets/1-1.png)

>[!TIP]
>
>Um mehrere Werte in einem Feld hinzuzufügen, verwenden Sie den Operator „stimmt überein mit“, wobei die einzelnen Werte durch Kommas voneinander getrennt sind.

>[!TIP]
>
>Um einen leeren oder NULL-Wert in einem Feld zu berücksichtigen, lassen Sie einfach das Feld [!UICONTROL Wert] leer. Hierbei werden Szenarien berücksichtigt, wie z. B. die Bewertung anhand eines Touchpoints ohne Formular-URL.

>[!NOTE]
>
>Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, können [!DNL Marketo Measure] nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.

`2)` Fügen Sie Regeln innerhalb derselben Gruppe hinzu, um die Logik „AND“ in Ihrer Anweisung zu verwenden.
Oder fügen Sie neue Anweisungen außerhalb der Gruppe hinzu, um die Logik „OR“ in Ihrer Anweisung zu verwenden.

![](assets/2.png)

`3)` Wenn Ihre Regeln komplex werden und Sie Gruppen neu erstellen und kleine Änderungen an jeder Anweisung vornehmen müssen, verwenden Sie die Option [!UICONTROL Klonen], um die Dinge zu vereinfachen.

![](assets/3.png)

Machen Sie sich keine Sorgen, wenn Sie einen Fehler machen. Sie können auch einzelne Zeilen Ihrer Anweisung oder vollständige Gruppen löschen.

![](assets/4.png)

`4)` Richten Sie Regeln für die Attributions-Touchpoints des Käufers ein, wenn sie auf beide Objekte angewendet werden sollen. Unsere Flexibilität ermöglicht es Ihnen, Regeln für ein oder beide Objekte festzulegen und sie für beide einzurichten, wenn sie zutreffen.

![](assets/5.png)

Zum Fertigstellen [!UICONTROL &#x200B; Sie Ihre Regeln &#x200B;] und verarbeiten. Wenn Sie viele Änderungen vornehmen, sollten Sie sicherstellen, dass Sie Ihre Änderungen dabei speichern. [!DNL Marketo Measure] werden Ihre Touchpoints erst entfernen, wenn Sie auf klicken
[!UICONTROL **Speichern und Verarbeiten**].

| **Operator** | **Anwendungsfall** |
|---|---|
| ist gleich | Einzelwert - exakte Übereinstimmung |
| Enthält | Einzelwert - enthält Wert |
| Entspricht allen | Mehrere Werte - Exakte Übereinstimmung |
| stimmt überein mit „any“ (enthält) | Mehrere Werte - &#42;value&#42;, &#42;value, &#42;value&#42; |

Für Kunden, die Dynamics verwenden und Unterdrückungsregeln basierend auf Status und/oder Status-Code einrichten möchten, ist beim Einrichten der Regel die folgende Formatierung erforderlich: `[Object].Statecode` ist gleich/nicht gleich `[Status Value]`. Wenn beispielsweise der Statuscode in Dynamics „1“ auf einem Kontakt liest und der Status „Inaktiv“ lautet und Sie alle diese Kontakte unterdrücken möchten, wäre das folgende Format für Ihre Unterdrückungsregel falsch: Kontakt.Statuscode ist gleich 1. Stattdessen sollten Sie das folgende Format verwenden: Da Statecode und Status als Paar funktionieren, liest [!DNL Marketo Measure] den Wert aus Status in unserer Abfrage: Kontakt.Statecode ist gleich Inaktiv.
