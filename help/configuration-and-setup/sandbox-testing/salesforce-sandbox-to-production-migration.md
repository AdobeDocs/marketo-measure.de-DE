---
unique-page-id: 18874694
description: Salesforce-Sandbox zur Produktionsmigration [!DNL Marketo Measure] - Produktdokumentation
title: Salesforce-Sandbox zur Betreibungsmigration
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: ad658a513b01dc7a51299abcb7313ff1877e49f3
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 4%

---

# Salesforce-Sandbox zur Betreibungsmigration {#salesforce-sandbox-to-production-migration}

Wenn Sie ausgewählt haben, [!DNL Marketo Measure] in einer [!DNL Salesforce] Sandbox-Umgebung verwenden, befolgen Sie diese Anweisungen, um zur Produktion zu migrieren, sobald Sie bereit sind. Bei den folgenden Anweisungen wird davon ausgegangen, dass Sie die [!DNL Marketo Measure] in Ihre Sandbox-Organisation verpacken, die erforderlichen Tests durchführen und bereit sind, Push-Benachrichtigungen durchzuführen [!DNL Marketo Measure] in die Produktion.

## Schritt 1: Installieren Sie die [!DNL Marketo Measure] Package in Ihrer Produktion [!DNL Salesforce] Instanz

* Installieren Sie die [!DNL Marketo Measure] -Paket in die Produktion mit &quot;[!UICONTROL Alle Benutzer]&quot;-Einstellung

   * [Basispaket](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* Weitere Informationen zum [!DNL Marketo Measure] Beziehung zu [!DNL Salesforce], sehen Sie sich [diesem Artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* Ein bisschen [!DNL Salesforce] -Konfiguration erforderlich ist. Die spezifischen Aktionselemente werden im Folgenden beschrieben unter [Schritt 4 unten](#salesforce-configuration)

## Schritt 2: Löschen der aktuellen Sandbox-CRM-Verbindung in [!DNL Marketo Measure] App {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Melden Sie sich bei [!DNL Marketo Measure] Anwendung unter experience.adobe.com/marketo-measure
* Navigieren Sie zu Mein Konto >[!UICONTROL Einstellungen] >[!UICONTROL Verbindungen]
* Klicken Sie auf das Papierkorbsymbol neben Ihrer SFDC-Verbindung, um sie zu löschen.
* Sie werden aufgefordert, den Löschvorgang zu bestätigen. Bitte lesen Sie die Informationen sorgfältig durch und verstehen Sie die Folgen der Löschung.

  ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * Geben Sie den Namen des Unternehmens ein, wie im Bestätigungsmodell angezeigt, und klicken Sie auf &quot;Ich verstehe die Konsequenzen, löschen Sie diese Verbindung&quot;.
* Dadurch wird der Löschvorgang Trigger und es dauert einige Zeit, bis er abgeschlossen ist.

## Schritt 3: Verbinden der Produktions-CRM-Instanz in [!DNL Marketo Measure] App {#connect-the-production-crm-instance-in-marketo-measure-app}

* Melden Sie sich bei [!DNL Marketo Measure] Anwendung unter experience.adobe.com/marketo-measure
* Navigieren Sie zu [!UICONTROL Mein Konto] >[!UICONTROL Einstellungen] > [!UICONTROL Verbindungen]
* Sobald das Löschen der Sandbox-Verbindung erfolgreich gelöscht wurde, wird die Verbindung von der Seite verschwinden. Andernfalls ist die Verbindung weiterhin mit dem Status &quot;Löschung in Bearbeitung&quot;
* Klicken Sie auf &quot;[!UICONTROL Einrichten einer neuen CRM-Verbindung]&quot;
* Im[!UICONTROL CRM-Verbindung auswählen]&quot; modales Dialogfeld, klicken Sie auf &quot;[!UICONTROL Verbinden]&quot; Aktion neben dem [!DNL Salesforce] Plattform: Wählen Sie &quot;[!UICONTROL Produktion]&quot; option
* Sie werden aufgefordert, Ihre Anmeldeinformationen einzugeben. Geben Sie dazu die Anmeldedaten für die Produktion ein.

## Schritt 4: Salesforce-Konfiguration {#salesforce-configuration}

[Seiten-Layouts](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Berechtigungssätze](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[Berichte freigeben](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[Ausblenden unnötiger Berichtstypen](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Benutzerdefinierter Workflow ggf.](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
