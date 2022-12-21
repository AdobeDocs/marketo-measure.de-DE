---
unique-page-id: 18874604
description: Benutzerdefinierte Segmentierung - [!DNL Marketo Measure] - Produktdokumentation
title: Benutzerdefinierte Segmentierung
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 0%

---

# Benutzerdefinierte Segmentierung {#custom-segmentation}

Segmente bieten die Möglichkeit, Daten im [!DNL Marketo Measure] ROI-Dashboard , um einen weiteren Drilldown für einen bestimmten Datensatz durchzuführen. Beispielsweise könnte ein Segment nach geografischem Gebiet oder einem Klassifizierungssystem definiert werden.

**Warum benutzerdefinierte Segmentierung?**

Mit der Funktion Benutzerdefinierte Segmentierung können Sie Touchpoints nach einer Kategorie und nach bis zu fünf Segmenten filtern. Je nachdem, auf welches Objekt Ihr ROI-Dash verweist (Lead oder Kontakt), können Sie Segmente basierend auf den Feldern erstellen, die im Lead-/Kontaktobjekt gefunden werden. Außerdem können Sie Segmente basierend auf Feldern erstellen, die im Opportunity-Objekt gefunden wurden.

**Wann ist die Funktion zur benutzerspezifischen Segmentierung hilfreich?**

Benutzerdefinierte Segmentierung kann verwendet werden, um Daten für einen bestimmten Datensatztyp anzuzeigen. Nachdem Sie die Filterlogik zugeordnet haben, sollten Sie in der [!DNL Marketo Measure] Die Demand Waterfall-Ansicht des Dashboards - dieselben Daten, die Sie in Ihrem CRM-System sehen würden.

**Wie richte ich es ein?**

Schritt 1: Bestimmen Sie, welche Informationen Sie sehen möchten.

Bevor Sie diese Funktion verwenden, sollten Sie herausfinden, nach welchen Touchpoint-Informationen Sie filtern möchten. Denken Sie daran, die exakten Werte in Ihrem CRM-System für Ihre Datensatztypen zu verwenden. Durch das Setup werden Touchpoints von oben nach unten im Marketing-Trichter gefiltert.

Schritt 2: Anmelden und Suchen Sie die Funktion Segmente .

* Navigieren Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} und sich anmelden
* Unter dem [!UICONTROL Mein Konto] Registerkarte, wählen Sie [!UICONTROL Einstellungen]
* Auswählen [!UICONTROL Segmente] aus den Optionen auf der Seitenleiste nach links, unter der [!UICONTROL Berichterstellung] Abschnitt

Schritt 3: Grundlegendes zu den Komponenten.

* Verwenden Sie diese Legende, um die verschiedenen Symbole auf dieser Seite zu verstehen.

![](assets/1.png)

Schritt 4: Hinzufügen von Filterregeln

* Geben Sie zunächst den Kategorienamen ein. Geschäftstyp ist ein Beispiel. Klicken Sie auf das Häkchen, wenn Sie fertig sind. Sie müssen einen Kategorienamen eingeben, bevor Sie Segmente hinzufügen können
* Klicken Sie auf das Pluszeichen, um ein Segment hinzuzufügen.
* Geben Sie einen Segmentnamen ein. Sie könnten beispielsweise ein Segment für &quot;New Business&quot;, &quot;Partners&quot;, &quot;Renewal&quot;oder &quot;Upsell&quot;haben.

![](assets/2.png)

* Klicken Sie auf das Pluszeichen, um die Regeleingabefelder anzuzeigen. Die Optionen in der Feldauswahl beziehen Felder direkt aus Ihrem CRM-System

![](assets/3.png)

>[!NOTE]
>
>Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, [!DNL Marketo Measure] kann nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.

* Die Option Wert ist keine Dropdown-Liste und der Wert muss manuell eingegeben werden. Überprüfen Sie die Werte in Ihrer Salesforce-Organisation.
* Wiederholen Sie diesen Vorgang für die Segmentregeln &quot;Chancen&quot;.
* Die Kategorie &quot;Sonstige&quot;ist ein Standardsegment, das alle nicht definierten Touchpoints erfasst. Sie können den Namen des Standardsegments ändern
* Klicken Sie auf das Papierkorbsymbol, um eine ganze Kategorie oder eine einzelne Regel innerhalb einer Kategorie zu löschen. Alternativ können Sie auf das Stiftsymbol klicken, um die Kategorie oder Regel zu bearbeiten
* Sie werden feststellen, dass Sie über eine &quot;Speichern&quot;-Schaltfläche und eine &quot;Speichern und Verarbeiten&quot;-Schaltfläche verfügen. Verwenden Sie die Schaltfläche Speichern , um Ihre Arbeit und Änderungen im Laufe der Zeit zu speichern. Verwenden Sie die Schaltfläche Speichern und verarbeiten NUR, wenn Sie Folgendes sichergestellt haben:

   * Ihre Zuordnung ist korrekt
   * Sie haben alle Segmente hinzugefügt, die Sie innerhalb einer Kategorie verfolgen möchten
   * Die Trigger der Schaltfläche &quot;Speichern und verarbeiten&quot; [!DNL Marketo Measure] um alle Touchpoints zu synchronisieren und die von Ihnen hinzugefügten neuen Informationen anzuwenden. Dieser Vorgang dauert 7 Tage und Regeln können während dieses Zeitraums nicht geändert werden

**_Zusätzliche Hinweise:_**

Wenn keine Regeln für Leads/Kontakte und Chancen eingerichtet sind, sehen Sie nur einen Teil Ihrer Daten. Wenn Sie also nicht die Angebotsregeln einrichten, sehen Sie nur Lead-/Kontaktdaten ohne die damit verbundenen Möglichkeiten. Dasselbe gilt, wenn Sie keine Regeln für Leads/Kontakte einrichten - Sie sehen nur Chancen ohne die zugehörigen Leads/Kontakte.

Wenn Sie fertig sind, klicken Sie auf [!UICONTROL Speichern] Überprüfen Sie zunächst alles, und klicken Sie dann auf [!UICONTROL Speichern und verarbeiten]. Denken Sie daran, dass Sie Ihre Einstellungen sieben Tage lang nicht bearbeiten können, wenn Sie speichern und verarbeiten, wie [!DNL Marketo Measure] Formatiert Ihre Daten während dieser Zeit neu.

**Wie speichere ich die generierten Berichte?**

Die erstellten Berichte können nicht direkt in der Benutzeroberfläche gespeichert werden. Allerdings [!DNL Marketo Measure] speichert die Segmentnamen in der URL, damit Sie die einzelnen Berichte mit einem Lesezeichen auf der Seite speichern können.
