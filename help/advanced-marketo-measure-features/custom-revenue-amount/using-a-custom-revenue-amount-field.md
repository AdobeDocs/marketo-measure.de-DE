---
unique-page-id: 18874793
description: Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag - [!DNL Marketo Measure] - Produktdokumentation
title: Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag {#using-a-custom-revenue-amount-field}

Standardmäßig ziehen die Touchpoints der Käuferzuordnung den Opportunity-Betrag aus einem von zwei Feldern:

* Betrag (SFDC-Standard)
* [!DNL Marketo Measure] Opportunity Amount (Custom)

Wenn Sie ein benutzerdefiniertes Feld &quot;Betrag&quot;für Ihre Möglichkeiten verwenden, müssen wir einen Workflow konfigurieren, um den Umsatz für den Touchpoint des Käufers zu berechnen. Dies erfordert fortgeschrittenere Kenntnisse [!DNL Salesforce], sodass möglicherweise Hilfe von Ihrem SFDC-Administrator benötigt wird.

Zunächst benötigen wir die folgenden Informationen:

* API-Name Ihres Felds &quot;Betrag&quot;

Von hier aus beginnen wir mit der Erstellung des Workflows.

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Erstellen]** > **[!UICONTROL Workflow und Genehmigungen]** > **[!UICONTROL Workflow-Regeln]**.

   ![](assets/1.jpg)

1. Auswählen **[!UICONTROL Neue Regel]**, legen Sie das Objekt als &quot;Opportunity&quot;fest und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. Konfigurieren Sie den Workflow. Legen Sie den Regelnamen auf &quot;Aktualisieren&quot;fest. [!DNL Marketo Measure] Opportunity Amount.&quot; Setzen Sie die Bewertungskriterien auf &quot;Erstellt und jedes Mal, wenn es bearbeitet wird&quot;. Wählen Sie für die Regelkriterien das benutzerdefinierte Feld Betrag aus und wählen Sie den Operator [!UICONTROL als &quot;not equal to&quot;(nicht gleich)] und lassen Sie das Feld &quot;Wert&quot;leer.

   ![](assets/4.jpg)

1. Fügen Sie eine Workflow-Aktion hinzu. Setzen Sie diese Auswahlliste auf &quot;[!UICONTROL Neue Feldaktualisierung].&quot;

   ![](assets/5.jpg)

1. Hier geben Sie die Feldinformationen ein. Im Feld &quot;Name&quot; wird die Verwendung der folgenden Benennung empfohlen: &quot;[!DNL Marketo Measure] Opp Amount.&quot; Der &quot;eindeutige Name&quot;wird automatisch basierend auf dem Feld &quot;Name&quot;aufgefüllt. Wählen Sie in der Auswahlliste &quot;Zu aktualisierendes Feld&quot;die Option[!DNL Marketo Measure] Opportunity Amount.&quot; Nachdem Sie das Feld ausgewählt haben, wählen Sie das Feld &quot;Workflow-Regeln nach Feldänderung neu bewerten&quot;. Wählen Sie unter &quot;Geben Sie den neuen Feldwert an&quot;die Option &quot;Verwenden Sie eine Formel, um den neuen Wert festzulegen&quot;. Legen Sie in das leere Feld den API-Namen des benutzerdefinierten Felds Betrag ab. Klicken **[!UICONTROL Speichern]**.

   ![](assets/6.png)

1. Sie werden auf eine Rollup-Seite für Ihren Workflow zurückgeführt, stellen Sie sicher, dass Sie &quot;Aktivieren&quot;auswählen, und Sie können sofort loslegen. Klicken Sie zur Aktivierung auf **Bearbeiten** neben Ihrem neuen Workflow klicken Sie auf **Aktivieren**.

   Nachdem Sie diese Schritte ausgeführt haben, müssen die Möglichkeiten aktualisiert werden, damit der Workflow Trigger werden kann, sodass der neue Wert aus dem [!UICONTROL benutzerspezifische Chance] -Feld.

   Dies lässt sich erreichen, indem Sie Ihre Möglichkeiten über Data Loader in SFDC ausführen. Weitere Informationen zur Verwendung von Data Loader finden Sie unter [diesem Artikel](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Wenden Sie sich bei weiteren Fragen an Ihren Customer Success Manager oder [[!DNL Marketo] Support](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.
