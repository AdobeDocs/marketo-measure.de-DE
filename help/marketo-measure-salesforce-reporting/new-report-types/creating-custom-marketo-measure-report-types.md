---
unique-page-id: 18874539
description: Benutzerdefiniert erstellen [!DNL Marketo Measure] Berichtstypen - [!DNL Marketo Measure]
title: Erstellen benutzerdefinierter  [!DNL Marketo Measure] Berichtstypen
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 5%

---

# Benutzerdefiniert erstellen [!DNL Marketo Measure] Berichtstypen {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber weiterhin &quot;[!DNL Bizible]&quot; in Ihrem CRM-System. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Erfahren Sie, wie Sie benutzerdefinierte [!DNL Marketo Measure] [!DNL Salesforce] Berichtstypen. Es gibt drei verschiedene Berichtstypen, die wir empfehlen zu erstellen: Leads mit Käufer-Touchpoints (benutzerdefiniert), [!DNL Marketo Measure] Person mit Käufer-Touchpoints (benutzerdefiniert), Chancen mit Käufer-Attribution-Touchpoint (benutzerdefiniert).

## Leads mit Käufer-Touchpoints (benutzerdefiniert) {#leads-with-buyer-touchpoints-custom}

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Build]** > **[!UICONTROL Berichtstypen]** > **[!UICONTROL Neue benutzerdefinierte Berichtstypen]**.

   ![](assets/1.png)

1. Definieren Sie den benutzerdefinierten Berichtstyp.

   * [!UICONTROL Berichtstyp Fokus] > [!UICONTROL [!UICONTROL Primäres Objekt]]: Lead
   * Identifizierung > [!UICONTROL Berichtstyp-Bezeichnung]: Leads mit Käufer-Touchpoints (benutzerdefiniert)
   * [!UICONTROL Store in Category]: Andere Berichte
   * [!UICONTROL Implementierung] > [!UICONTROL Bereitstellungsstatus]: bereitgestellt

   ![](assets/2.png)

1. Definieren Sie die Objektbeziehungen.

   * Verknüpfen Sie das Lead-Objekt (A) mit dem [!DNL Marketo Measure] Personen-Objekt (B) und anschließend zum Touchpoint-Objekt (C) des Käufers
   * Stellen Sie sicher, dass[!UICONTROL Jeder A/B-Datensatz muss mindestens eine B/C aufweisen]&quot; Datensatz ausgewählt ist
   * [!UICONTROL Speichern]

   ![](assets/3.png)

## [!DNL Marketo Measure] Person mit Käufer-Touchpoints (benutzerdefiniert) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Build]** > **[!UICONTROL Berichtstypen]** > **[!UICONTROL Neue benutzerdefinierte Berichtstypen]**.

   ![](assets/4.png)

1. Definieren Sie den benutzerdefinierten Berichtstyp.

   * [!UICONTROL Berichtstyp Fokus] > [!UICONTROL Primäres Objekt]: [!DNL Marketo Measure] Personen
   * [!UICONTROL Bezeichnung] > [!UICONTROL Berichtstyp-Bezeichnung]: [!DNL Marketo Measure] Person mit Käufer-Touchpoints (benutzerdefiniert)
   * [!UICONTROL Store in Category]: Andere Berichte
   * [!UICONTROL Implementierung] > [!UICONTROL Bereitstellungsstatus]: bereitgestellt

   ![](assets/5.png)

1. Definieren Sie die Objektbeziehungen.

   * Relieren Sie die [!DNL Marketo Measure] Personen-Objekt (A) zum Touchpoint-Objekt des Käufers (B)
   * Stellen Sie sicher, dass[!UICONTROL Jeder A-Datensatz muss mindestens eine B aufweisen]&quot; Datensatz ausgewählt ist
   * [!UICONTROL Speichern]

   ![](assets/6.png)

## Möglichkeiten mit dem Touchpoint der Käuferzuordnung (benutzerdefiniert) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Build]** > **[!UICONTROL Berichtstypen]** > **[!UICONTROL Neue benutzerdefinierte Berichtstypen]**.

   ![](assets/7.png)

1. Definieren Sie den benutzerdefinierten Berichtstyp.

   * [!UICONTROL Berichtstyp Fokus] > [!UICONTROL Primäres Objekt]: Chancen
   * [!UICONTROL Bezeichnung] > [!UICONTROL Berichtstyp-Bezeichnung]: Möglichkeiten mit dem Touchpoint der Käuferzuordnung (benutzerdefiniert)
   * [!UICONTROL Store in Category]: Andere Berichte
   * [!UICONTROL Implementierung] > [!UICONTROL Bereitstellungsstatus]: bereitgestellt

   ![](assets/8.png)

1. Definieren Sie die Objektbeziehungen.

   * Verknüpfen des Opportunities -Objekts (A) mit dem Touchpoint-Objekt &quot;Buyer Attribution&quot;(B)
   * Stellen Sie sicher, dass[!UICONTROL Jeder A-Datensatz muss mindestens eine B aufweisen]&quot; Datensatz ausgewählt ist
   * [!UICONTROL Speichern]

   ![](assets/9.png)

## Hinzufügen benutzerdefinierter Felder zu benutzerdefinierten Berichtstypen {#adding-custom-fields-to-custom-report-types}

1. Nach der Erstellung der Berichte gelangen Sie zu einer Übersicht über den Berichtstyp. Klicks **[!UICONTROL Layout bearbeiten]**.

   ![](assets/10.png)

1. Stellen Sie sicher, dass die benutzerdefinierten Felder, die Sie zum Bericht hinzufügen möchten, im Abschnitt Feldlayout-Eigenschaften angezeigt werden. Wenn Sie weitere Felder hinzufügen möchten, verwenden Sie den[!UICONTROL Felder für die Suche hinzufügen]&quot;.

   ![](assets/11.png)
