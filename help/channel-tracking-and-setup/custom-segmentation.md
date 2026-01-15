---
description: Benutzerdefinierte Segmentierungsleitfäden für Marketo Measure-Benutzende
title: Benutzerdefinierte Segmentierung
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Benutzerdefinierte Segmentierung {#custom-segmentation}

Segmente bieten die Möglichkeit, Daten im Dashboard &quot;[!DNL Marketo Measure]-ROI“ zu filtern, um einen bestimmten Datensatz weiter aufzuschlüsseln. Beispielsweise kann ein Segment durch ein geografisches Gebiet oder ein Benotungssystem definiert werden.

**Warum benutzerdefinierte Segmentierung?**

Mit der benutzerdefinierten Segmentierung können Sie Touchpoints nach Kategorien (Filtername) und Regeln (Filterwerte) filtern. Tier 1-Kunden erhalten ein Segment, Tier 2 und höher zehn. Je nachdem, auf welches Objekt Ihr ROI-Strich verweist (Lead oder Kontakt), können Sie Segmente basierend auf den Feldern im Lead/Kontakt-Objekt erstellen. Außerdem können Sie Segmente basierend auf allen Feldern erstellen, die im Objekt Opportunity gefunden wurden.

**Wann ist die Funktion „Benutzerdefinierte Segmentierung“ hilfreich?**

Benutzerdefinierte Segmentierung kann verwendet werden, um Daten für einen bestimmten Datensatztyp anzuzeigen. Nachdem Sie die Filterlogik zugeordnet haben, sollten Sie in der Demand Waterfall-Ansicht des [!DNL Marketo Measure]-Dashboards dieselben Daten sehen können, die Sie auch in Ihrem CRM sehen würden.

**Wie richte ich das ein?**

>[!NOTE]
>
>Durch die Aktualisierung der Segmentregeln werden historische Daten erneut verarbeitet.

Schritt 1: Bestimmen Sie, welche Informationen angezeigt werden sollen.

Bevor Sie diese Funktion verwenden, sollten Sie herausfinden, nach welchen Touchpoint-Informationen Sie filtern möchten. Denken Sie daran, die genauen Werte in Ihrem CRM für Ihre Datensatztypen zu verwenden. Die Einrichtung filtert Touchpoints von oben nach unten in der Marketing-funnel.

Schritt 2: Melden Sie sich an und suchen Sie die Funktion [!UICONTROL Segmente].

* Wechseln Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und melden Sie sich an
* Wählen Sie auf der [!UICONTROL Mein Konto] die Option [!UICONTROL Einstellungen]
* Wählen [!UICONTROL Segmente] aus den Optionen in der Seitenleiste links unter dem Abschnitt [!UICONTROL Berichte] aus

Schritt 3: Komponenten verstehen.

* Diese Legende zeigt die verschiedenen Symbole auf dieser Seite

![Verwenden Sie diese Legende, um die verschiedenen Symbole auf dieser Seite zu verstehen](assets/custom-segmentation-1.png)

Schritt 4: Filterregeln hinzufügen.

* Geben Sie zunächst den Kategorienamen ein. [!UICONTROL Geschäftstyp] ist ein Beispiel. Klicken Sie auf das Häkchen, wenn Sie fertig sind. Sie müssen einen Kategorienamen eingeben, bevor Sie Segmente hinzufügen können
* Klicken Sie auf das Pluszeichen, um ein Segment hinzuzufügen
* Geben Sie einen Segmentnamen ein. Beispielsweise könnte es ein Segment für Neues Unternehmen, Partner, Erneuerung oder Upsell geben

![Geben Sie einen Segmentnamen ein. Beispielsweise könnte ein Segment für Folgendes vorhanden sein](assets/custom-segmentation-2.png)

* Klicken Sie auf das Pluszeichen, um die Regeleingabefelder anzuzeigen. Mit den Optionen in der Feldauswahlliste können Sie Felder direkt aus Ihrem CRM abrufen

![Klicken Sie auf das Pluszeichen, um die Regeleingabefelder anzuzeigen. Die Optionen](assets/custom-segmentation-3.png)

>[!NOTE]
>
>Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, können [!DNL Marketo Measure] nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.

* Die [!UICONTROL Wert]-Option ist keine Dropdown-Liste und ihr Wert muss manuell eingegeben werden. Überprüfen Sie unbedingt die Werte in Ihrer Salesforce-Organisation
* Wiederholen Sie diesen Vorgang für die Segmentregeln für Opportunities .
* Die Kategorie „Sonstige“ ist ein Standardsegment, das alle nicht definierten Touchpoints erfasst. Sie können den Namen des Standardsegments ändern
* Klicken Sie auf das Papierkorbsymbol, um eine ganze Kategorie oder eine einzelne Regel innerhalb einer Kategorie zu löschen. Alternativ können Sie zum Bearbeiten der Kategorie oder Regel auf das Stiftsymbol klicken
* Beachten Sie, dass Sie die Schaltfläche &quot;[!UICONTROL Speichern] und „Speichern und Verarbeiten“ haben. Klicken Sie auf die Schaltfläche Speichern , um Ihre Änderungen zu speichern. Verwenden Sie die Schaltfläche Speichern und Verarbeiten NUR, nachdem Sie Folgendes sichergestellt haben:

   * Ihre Zuordnung ist korrekt
   * Sie haben alle Segmente hinzugefügt, die Sie innerhalb einer Kategorie nachverfolgen möchten
   * Mit den Triggern der Schaltfläche Speichern und verarbeiten [!DNL Marketo Measure] Sie alle Touchpoints synchronisieren und die neu hinzugefügten Informationen anwenden. Dieser Vorgang dauert 7 Tage, und die Regeln können während dieses Zeitraums nicht geändert werden

**_Zusätzliche Hinweise:_**

Wenn keine Regeln für Leads/Kontakte und Opportunities eingerichtet sind, wird nur ein Teil der Daten angezeigt. Wenn Sie die Opportunities-Regeln nicht einrichten, sehen Sie jetzt Lead-/Kontaktdaten, aber nicht die damit verbundenen Opportunities. Dasselbe gilt, wenn Sie keine Regeln für Leads/Kontakte einrichten. Es werden nur Opportunities ohne die zugehörigen Leads/Kontakte angezeigt.

Wenn Sie fertig sind, klicken Sie zuerst auf [!UICONTROL Speichern], überprüfen Sie alles und klicken Sie dann auf [!UICONTROL Speichern und verarbeiten]. Beachten Sie, dass Sie Ihre Einstellungen nach dem Speichern und Verarbeiten sieben Tage lang nicht bearbeiten können, da [!DNL Marketo Measure] Ihre Daten während dieser Zeit neu formatiert.

Wenn Sie Marketo Measure Ultimate-Kunde sind und Ihr standardmäßiges Dashboard-Objekt als Kontakt festgelegt haben, verwenden Sie nicht die beiden folgenden Lead-spezifischen Felder ([ mehr dazu](/help/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**Wie speichere ich die generierten Berichte?**

Die generierten Berichte können nicht direkt in der Benutzeroberfläche gespeichert werden. [!DNL Marketo Measure] speichert jedoch die Segmentnamen in der URL, damit Sie jeden Bericht durch Setzen eines Lesezeichens auf der Seite erfassen können.
