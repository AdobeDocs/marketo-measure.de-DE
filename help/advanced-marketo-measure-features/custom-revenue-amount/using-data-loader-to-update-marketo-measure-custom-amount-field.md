---
unique-page-id: 18874771
description: Verwenden des Datenladers zum Aktualisieren  [!DNL Marketo Measure]  benutzerdefinierten Betragsfelds - [!DNL Marketo Measure]
title: Verwenden des Datenladers zum Aktualisieren des benutzerdefinierten Marketo Measure-Betragsfelds
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 2%

---

# Verwenden des Datenladers zum Aktualisieren [!DNL Marketo Measure] benutzerdefinierten Betragsfelds {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] empfiehlt die Verwendung von Data Loader als praktische Option, um Opportunity-Werte zu aktualisieren, wenn ein benutzerdefiniertes Umsatzfeld in [!DNL Marketo Measure] verwendet wird (wir verwenden das Feld „Betrag“ standardmäßig). Data Loader wird gegenüber der Verwendung des [!DNL Marketo Measure]-Aktualisierungsskripts bevorzugt, da die Benutzenden für das Skript alle Salesforce-Validierungsregeln deaktivieren müssen, während das [!DNL Marketo Measure] ausgeführt wird.

## Verwenden des Datenladers zum Aktualisieren [!DNL Marketo Measure] benutzerdefinierten Betragsfelds{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Erstellen Sie ein Excel-Arbeitsblatt mit:

   * Opportunity-ID
   * Benutzerdefiniertes Feld für Opportunity-Betrag (Feld für den bevorzugten Umsatz)
   * [!DNL Marketo Measure] Feld Opportunity-Betrag

1. Kopieren Sie die Werte aus dem Feld Bevorzugter Umsatz und fügen Sie sie in das Feld [!UICONTROL [!DNL Marketo Measure] Opportunity-] ein. Aktualisieren Sie dann diese Opportunities mithilfe der CSV-Datei .

**_Alternativ können Sie zu Salesforce wechseln und eine benutzerdefinierte Listenansicht verwenden, um alle Opportunities massenweise zu bearbeiten…_**

1. Erstellen Sie eine benutzerdefinierte Listenansicht für alle Opportunities.
1. Filter für das Feld „Bevorzugter Umsatz“ hinzufügen ist nicht leer _und das Feld_ 2}Marketo[!UICONTROL  Opportunity-Betrag messen ist leer.]
1. Klicken Sie **[!UICONTROL Massenbearbeitung]** ändern Sie jedoch nichts.
1. Klicken Sie auf **[!UICONTROL Speichern]**. Dadurch wird der Workflow so Trigger, dass die Felder für den Betrag der [!DNL Marketo Measure] Opportunity mit dem Feld „Software-Umsatz“ ausgefüllt werden.
