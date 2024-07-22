---
unique-page-id: 18874771
description: Verwenden von Data Loader zum Aktualisieren des Felds  [!DNL Marketo Measure] Benutzerdefinierter Betrag - [!DNL Marketo Measure]
title: Verwenden von Data Loader zum Aktualisieren des benutzerdefinierten Marketo Measure-Zahlenfelds
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 2%

---

# Verwenden von Data Loader zum Aktualisieren des Felds [!DNL Marketo Measure] benutzerspezifischer Betrag {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] empfiehlt die Verwendung von Data Loader als praktische Option zum Aktualisieren von Opportunitätswerten bei der Verwendung eines benutzerdefinierten Umsatzfelds (wir verwenden das Feld &quot;Betrag&quot;standardmäßig) in [!DNL Marketo Measure]. Data Loader wird gegenüber dem Update-Skript [!DNL Marketo Measure] bevorzugt, da für das Skript Benutzer alle Salesforce-Validierungsregeln deaktivieren müssen, während das Skript [!DNL Marketo Measure] ausgeführt wird.

## Verwenden von Data Loader zum Aktualisieren des Felds [!DNL Marketo Measure] benutzerspezifischer Betrag{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Erstellen Sie ein Excel-Blatt mit den folgenden Elementen:

   * Opportunity-ID
   * Feld &quot;Benutzerdefinierter Opportunity-Betrag&quot;(Feld für Ihren bevorzugten Umsatz)
   * [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;

1. Kopieren Sie die Werte aus Ihrem bevorzugten Umsatzfeld und fügen Sie sie in das Feld [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] ein. Aktualisieren Sie dann diese Optionen mithilfe der CSV-Datei.

**_Alternativ können Sie Salesforce aufrufen und eine benutzerdefinierte Listenansicht verwenden, um alle Möglichkeiten massenweise zu bearbeiten..._**

1. Erstellen Sie eine benutzerdefinierte Listenansicht für alle Möglichkeiten.
1. Das Feld &quot;Filter für das bevorzugte Umsatzfeld hinzufügen&quot;ist nicht leer _und das Feld_ [!UICONTROL Marketo] &quot;Wert für die Mglichkeitsbewertung&quot;ist leer.
1. Klicken Sie auf **[!UICONTROL Massenbearbeitung]**, aber ändern Sie nichts.
1. Klicken Sie auf **[!UICONTROL Speichern]**. Dadurch wird der Workflow Trigger, die Felder [!DNL Marketo Measure] &quot;Opportunity Amount&quot;mit dem Feld Softwareumsatz zu füllen.
