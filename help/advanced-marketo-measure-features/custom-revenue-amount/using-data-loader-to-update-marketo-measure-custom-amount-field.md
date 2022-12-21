---
unique-page-id: 18874771
description: Aktualisieren mit Data Loader [!DNL Marketo Measure] Feld für benutzerdefinierten Betrag - [!DNL Marketo Measure] - Produktdokumentation
title: Verwenden von Data Loader zum Aktualisieren des benutzerdefinierten Marketo-Zahlenfelds
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Aktualisieren mit Data Loader [!DNL Marketo Measure] Benutzerdefiniertes Zahlenfeld {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] empfiehlt die Verwendung von Data Loader als praktische Option zur Aktualisierung von Opportunitätswerten bei der Verwendung eines benutzerdefinierten Umsatzfelds (wir verwenden das Feld &quot;Betrag&quot;standardmäßig) in [!DNL Marketo Measure]. Der Datenladevorgang wird gegenüber der Verwendung des [!DNL Marketo Measure] Skript aktualisieren, da Benutzer für das Skript alle Salesforce-Validierungsregeln deaktivieren müssen, während die [!DNL Marketo Measure] -Skript ausgeführt wird.

## Aktualisieren mit Data Loader [!DNL Marketo Measure] Benutzerdefiniertes Zahlenfeld{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Erstellen Sie ein Excel-Blatt mit den folgenden Elementen:

   * Opportunity-ID
   * Feld &quot;Benutzerdefinierter Opportunity-Betrag&quot;(Feld für Ihren bevorzugten Umsatz)
   * [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;

1. Kopieren Sie die Werte aus dem gewünschten Umsatzfeld und fügen Sie sie in das [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] -Feld. Aktualisieren Sie dann diese Optionen mithilfe der CSV-Datei.

**_Alternativ können Sie Salesforce aufrufen und eine benutzerdefinierte Listenansicht verwenden, um alle Möglichkeiten zu bearbeiten..._**

1. Erstellen Sie eine benutzerdefinierte Listenansicht für alle Möglichkeiten.
1. Filter für das Feld &quot;Bevorzugter Umsatz&quot;hinzufügen ist nicht leer _und_ [!UICONTROL Marketo] Feld &quot;Opportunity Amount&quot;messen&quot;ist leer.
1. Klicken **[!UICONTROL Massenbearbeitung]**, aber ändern Sie nichts.
1. Klicken **[!UICONTROL Speichern]**. Dadurch wird der Workflow Trigger, um die [!DNL Marketo Measure] Felder für den Opportunity Amount mit dem Feld Softwareumsatz .
