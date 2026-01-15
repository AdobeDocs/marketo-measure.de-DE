---
description: Verwenden eines benutzerdefinierten Felds für Umsatzbeträge für Marketo Measure-Benutzende
title: Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 3%

---

# Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag {#using-a-custom-revenue-amount-field}

Standardmäßig ziehen Attributions-Touchpoints des Käufers den Opportunity-Betrag aus einem von zwei Feldern:

* Betrag (SFDC-Standard)
* Opportunity-Betrag [!DNL Marketo Measure] (benutzerdefiniert)

Wenn Sie ein benutzerdefiniertes Summenfeld für Ihre Opportunities verwenden, müssen wir einen Workflow konfigurieren, um den Buyer Touchpoint-Umsatz zu berechnen. Dies erfordert etwas fortgeschrittenere [!DNL Salesforce], sodass Sie möglicherweise die Unterstützung Ihres SFDC-Administrators benötigen.

Zunächst benötigen wir die folgenden Informationen:

* API-Name Ihres Betragsfelds

Von hier aus beginnen wir mit der Erstellung des Workflows.

## Erstellen des Workflows in Salesforce Lightning {#create-the-workflow-in-salesforce-lightning}

Die folgenden Schritte sind für Benutzende von Salesforce Lightning vorgesehen. Wenn Sie Salesforce Classic weiterhin verwenden, [&#x200B; diese Schritte unten &#x200B;](#create-the-workflow-in-salesforce-classic).

1. Geben Sie bei der Einrichtung „Flüsse“ in das Feld „Schnellsuche“ ein und wählen Sie &quot;**[!UICONTROL &quot;,]** Flow Builder zu starten. Klicken Sie im rechten Bedienfeld auf die Schaltfläche **[!UICONTROL Neuer Fluss]**.

   ![1. Geben Sie bei der Einrichtung „Flüsse“ in das Feld „Schnellsuche“ ein und wählen Sie Folgendes aus](assets/custom-amount-1.png)

1. Wählen Sie **[!UICONTROL Datensatzausgelöster Fluss]** und klicken Sie unten **[!UICONTROL auf]** Erstellen“.

   ![1. Wählen Sie einen durch einen Datensatz ausgelösten Fluss aus und klicken Sie unten auf Erstellen &#x200B;](assets/custom-amount-10.png)

1. Wählen Sie im Fenster Start konfigurieren das Objekt Opportunity aus. Wählen Sie im [!UICONTROL Trigger konfigurieren] die Option **[!UICONTROL Ein Datensatz wird erstellt oder aktualisiert]** aus.

   ![1. Wählen Sie im Fenster Start konfigurieren das Objekt Opportunity aus. Vom &#x200B;](assets/custom-amount-11.png)

1. Wählen Sie im Abschnitt Einstiegsbedingungen festlegen unter [!UICONTROL Bedingungsanforderungen] die Option **[!UICONTROL Benutzerdefinierte Bedingungslogik ist erfüllt]**.
   * Wählen Sie im Suchfeld Ihr benutzerdefiniertes Betragsfeld aus.
   * Legen Sie den Operator als **Is Null** und den Wert als **[!UICONTROL False]** fest.
   * Legen Sie die Auswertungskriterien auf **[!UICONTROL Jedes Mal, wenn ein Datensatz aktualisiert wird und die Bedingungsanforderungen erfüllt]** fest.

   ![Legen Sie die Auswertungskriterien auf Jedes Mal fest, wenn ein Datensatz aktualisiert wird](assets/custom-amount-12.png)

1. Wählen Sie im Abschnitt „Fluss optimieren für“ die Option **[!UICONTROL Schnelle Feldaktualisierungen]**. Klicken **[!UICONTROL unten]** auf „Fertig“.

   ![1. Wählen Sie im Abschnitt „Fluss optimieren für“ die Option Schnellfeld aus](assets/custom-amount-13.png)

1. Um das Element hinzuzufügen, klicken Sie auf das Pluszeichen (+) und wählen Sie **[!UICONTROL Auslösenden Datensatz aktualisieren]**.

   ![1. Um das Element hinzuzufügen, klicken Sie auf das Pluszeichen (+) und wählen Sie Folgendes aus](assets/custom-amount-14.png)

1. Geben Sie im Fenster Neue Datensätze aktualisieren Folgendes ein:

   * Titel eingeben - der API-Name wird automatisch generiert
   * Wählen Sie unter „Suchen nach Datensätzen zum Aktualisieren und Festlegen ihrer Werte“ die Option **[!UICONTROL Verwenden des Opportunity-Datensatzes, der den Fluss ausgelöst hat]**.
   * Wählen Sie im Abschnitt [!UICONTROL Filterbedingungen festlegen] die Option **[!UICONTROL Datensatz immer aktualisieren]** als Bedingungsanforderung zum Aktualisieren des Datensatzes aus.
   * Wählen Sie [!UICONTROL &#x200B; Feld „Feldwerte für den Kampagnensatz festlegen] den Marketo Measure-Opportunity-Betrag und den Ab-Wert aus. Wählen Sie dann Ihr benutzerdefiniertes Betragsfeld aus.
   * Klicken Sie auf **[!UICONTROL Fertig]**.

   ![Klicken Sie auf Fertig.](assets/custom-amount-15.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**. Ein Popup-Fenster wird angezeigt. Geben Sie im Fenster Fluss speichern „Flow Label“ ein (der Name der Flow API wird automatisch generiert). Klicken Sie **[!UICONTROL erneut auf]** Speichern“.

   ![1. Klicken Sie auf Speichern. Ein Popup-Fenster wird angezeigt. Geben Sie „Fluss-Bezeichnung“ in ein](assets/custom-amount-2.png)

1. Klicken Sie auf die **[!UICONTROL Aktivieren]**-Schaltfläche, um den Fluss zu aktivieren.

   ![1. Klicken Sie auf die Schaltfläche Aktivieren , um den Fluss zu aktivieren.](assets/custom-amount-3.png)

## Erstellen des Workflows in Salesforce Classic {#create-the-workflow-in-salesforce-classic}

Die folgenden Schritte sind für Salesforce Classic-Benutzer vorgesehen. Wenn Sie zu Salesforce Lightning gewechselt haben, [&#x200B; Sie diese Schritte oben](#create-the-workflow-in-salesforce-lightning).

1. Navigieren Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Erstellen]** > **[!UICONTROL Workflow und Genehmigungen]** > **[!UICONTROL Workflow-Regeln]**.

   ![1. Navigieren Sie zu Einrichtung Workflow erstellen und Genehmigungen](assets/custom-amount-4.png)

1. Wählen Sie **[!UICONTROL Neue Regel]**, legen Sie das Objekt als „Opportunity“ fest und klicken Sie auf **[!UICONTROL Weiter]**.

   ![1. Wählen Sie Neue Regel , legen Sie das Objekt als „Opportunity“ fest und klicken Sie auf](assets/custom-amount-5.png)

   ![1. Wählen Sie Neue Regel , legen Sie das Objekt als „Opportunity“ fest und klicken Sie auf](assets/custom-amount-6.png)

1. Konfigurieren Sie den Workflow. Legen Sie den Regelnamen als „Opportunity-Betrag [!DNL Marketo Measure].“ fest. Legen Sie die Auswertungskriterien auf „Erstellt und jedes Mal, wenn sie bearbeitet werden“ fest. Wählen Sie für die Regelkriterien Ihr benutzerdefiniertes Betragsfeld aus und wählen Sie den Operator [!UICONTROL als „Ungleich“] und lassen Sie das Feld „Wert“ leer.

   ![1. Konfigurieren Sie den Workflow. Legen Sie den Regelnamen als &quot;Marketo aktualisieren“ &#x200B;](assets/custom-amount-7.png)

1. Eine Workflow-Aktion hinzufügen. Wählen Sie für diese Auswahlliste &quot;[!UICONTROL Neues Feld aktualisieren] aus.
   ![1. Eine Workflow-Aktion hinzufügen. Diese Auswahlliste auf „Neues Feld“ &#x200B;](assets/custom-amount-8.png)

1. Hier geben Sie die Feldinformationen ein. Im Feld „Name“ empfehlen wir die Verwendung der folgenden Bezeichnung: &quot;[!DNL Marketo Measure] Opportunity-Betrag“. Der „Eindeutige Name“ wird automatisch basierend auf dem Feld „Name“ ausgefüllt. Wählen Sie in der Auswahlliste „Zu aktualisierendes Feld“ die Option „Opportunity-Betrag [!DNL Marketo Measure]&quot;. Aktivieren Sie nach Auswahl des Felds das Kontrollkästchen „Workflow-Regeln nach Feldänderung neu auswerten“. Wählen Sie unter „Neuen Feldwert angeben“ die Option „Formel zum Festlegen des neuen Werts verwenden“ aus. Legen Sie den API-Namen Ihres benutzerdefinierten Betragsfelds in das leere Feld. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![1. Hier geben Sie die Feldinformationen ein. Im Feld „Name“](assets/custom-amount-9.png)

1. Sie werden auf eine Rollout-Seite für Ihren Workflow zurückgeleitet. Stellen Sie sicher, dass Sie auf „Aktivieren“ klicken und schon können Sie loslegen. Klicken Sie zum Aktivieren **[!UICONTROL Bearbeiten]** neben Ihrem neuen Workflow und dann auf **[!UICONTROL Aktivieren]**.

   Trigger Nachdem Sie diese Schritte abgeschlossen haben, müssen die Opportunitys aktualisiert werden, damit der Workflow den neuen Wert aus dem Feld [!UICONTROL Benutzerdefinierte Opportunity] erhält.

   Dies können Sie erreichen, indem Sie Ihre Opportunitys über den Data Loader in SFDC ausführen. Weitere Informationen zur Verwendung des Datenladers finden Sie in [diesem Artikel](/help/channel-tracking-and-setup/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Bei Fragen wenden Sie sich bitte an das Adobe Account Team (Ihren Account Manager) oder an den [[!DNL Marketo] Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
