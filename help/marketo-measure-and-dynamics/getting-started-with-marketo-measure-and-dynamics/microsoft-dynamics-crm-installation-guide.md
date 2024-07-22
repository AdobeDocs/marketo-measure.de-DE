---
unique-page-id: 18874763
description: „[!DNL Microsoft Dynamics]-CRM-Installationsanleitung – Marketo Measure – Produktdokumentation“
title: „[!DNL Microsoft Dynamics]-CRM-Installationsanleitung“
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 100%

---

# [!DNL Microsoft Dynamics]-CRM-Installationsanleitung {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in unserer Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

## Unterstützte Versionen {#supported-versions}

[!DNL Marketo Measure] unterstützt die folgenden [!DNL Microsoft Dynamics CRM]-Versionen:

* [!DNL Microsoft Dynamics 2016] (Online und On-Premise)
* [!DNL Microsoft Dynamics 365] (Online und On-Premise)

Für die Verbindung und Authentifizierung unterstützt [!DNL Marketo Measure] die folgenden Active Directory Federated Services-Versionen (ADFS):

* ADFS 4.0 – [!DNL Windows Server 2016]
* ADFS 5.0 – [!DNL Windows Server 2019]

## Installieren der verwalteten Lösung {#install-the-managed-solution}

[Laden Sie die Zip-Datei herunter und installieren](assets/marketo-measure-dynamics-extension.zip) Sie sie in Dynamics CRM.

**[!UICONTROL Einstellungen]** > **[!UICONTROL Anpassungen]** > **[!UICONTROL Lösungen]** > **[!UICONTROL Importieren]** (Schaltfläche) > **[!UICONTROL Datei auswählen]**.

![](assets/1.png)

>[!NOTE]
>
>Die folgenden beiden Screenshots können geringfügig von Ihren abweichen, da sie während einer Lösungsaktualisierung erstellt wurden.

![](assets/2.png)

![](assets/3.png)

## Erstellen einer Benutzerin bzw. eines Benutzers von [!DNL Marketo Measure] {#creating-a-marketo-measure-user}

Es wird empfohlen, einen speziellen Marketo Measure-Benutzer oder eine spezielle Marketo Measure-Benutzerin als „Anwender“ in Dynamics anzulegen, um über diese „Person“ Daten exportieren und importieren zu können und Probleme mit anderen Benutzenden in Ihrem CRM zu vermeiden. Notieren Sie sich den Benutzernamen und das Kennwort sowie die Endpunkt-URL, da diese bei der Erstellung des [!DNL Marketo Measure]-Kontos verwendet werden.

## Sicherheitsrollen {#security-roles}

Wenn Ihr Unternehmen Sicherheitsrollen von Dynamics verwendet, vergewissern Sie sich, dass die verbundenen Benutzenden oder die dedizierten [!DNL Marketo Measure]-Benutzenden über ausreichende Lese-/Schreibberechtigungen für die erforderlichen Entitäten verfügen.

Sicherheitsrollen finden Sie hier: **[!UICONTROL Einstellungen]** > **[!UICONTROL Sicherheit]** > **[!UICONTROL Sicherheitsrollen]**.

Für benutzerdefinierten Entitäten von [!DNL Marketo Measure] benötigen wir vollständige Berechtigungen für alle unsere Entitäten.

>[!NOTE]
>
>Benutzende, die Opportunitys schließen, benötigen ebenfalls die volle Berechtigung.

![](assets/4.png)

Für Dynamics-Standardentitäten lesen Sie bitte das Dynamics-Schema-Dokument von [!DNL Marketo Measure]. Im Großen und Ganzen liest [!DNL Marketo Measure] bestimmte Entitäten ein, um die entsprechenden Daten zu sammeln und in benutzerdefinierte Felder zu schreiben, die mit der verwalteten Lösung installiert sind. Standardeinträge werden nicht erstellt und Standardfelder werden nicht aktualisiert.

## So schließen Sie Touchpoints in Seiten-Layouts ein: {#include-touchpoints-on-page-layouts}

1. Navigieren Sie für jede Entität zum Formulareditor. Sie finden dies unter **[!UICONTROL Einstellungen]** > **[!UICONTROL Anpassungen]** > **[!UICONTROL System anpassen]** > `[Entity]` > **[!UICONTROL Formulare]**. Alternativ finden Sie ihn auch in den Einstellungen, während Sie einen Eintrag ansehen.

   * Die zu konfigurierenden Entitäten: Konto, Opportunity, Kontakt, Lead und Kampagne.

   * Um Kampagnen zu konfigurieren, müssen Sie die Option „Kampagnensynchronisierung“ unter **[!UICONTROL CRM]** > **[!UICONTROL Kampagnen]** aktivieren.

   ![](assets/5.png)

1. Seiten-Layouts: Fügen Sie zunächst eine „[!UICONTROL Einspaltig]“-Kachel in dem Bereich ein, in dem die Touchpoints untergebracht werden sollen. In dieser neuen Spalte benötigen wir ein Teilraster, das zu jedem Formular in Ihren Konto-, Opportunity-, Kontakt- und Lead-Entitäten hinzugefügt wird.

   ![](assets/6.png)

   ![](assets/7.png)

1. Wählen Sie das Objekt (Buyer Attribution Touchpoints oder Buyer Touchpoints) aus, das im Unterraster dargestellt werden soll, was von der Objektbeziehung abhängt. Ändern Sie optional die angezeigten Spalten, indem Sie auf die Schaltfläche „Bearbeiten“ klicken. Das Standard-Layout wird von der verwalteten Lösung festgelegt.

   Buyer Attribution Touchpoint-Subgrid – Konten, Opportunitys und Kontakt\
   Buyer Touchpoint-Subgrid – Leads und Kontakte

   ![](assets/8.png)

1. Nachdem Sie die Aktualisierung des Formulars abgeschlossen haben, veröffentlichen Sie die Änderungen und speichern Sie sie.

## Schema-bezogene Aspekte {#schema-related-considerations}

**Umsatz**

[!DNL Marketo Measure] verweist standardmäßig auf das Standardfeld „Tatsächlicher Umsatz“. Wenn Sie diese Option nicht verwenden, erläutern Sie, wie Sie Ihre Fachkraft für Lösungstechnik oder Ihre Erfolgs-Managerin bzw. Ihren Erfolgs-Manager über den Umsatz in Berichten informieren, da ein benutzerdefinierter Workflow erforderlich ist.

**Abschlussdatum**

[!DNL Marketo Measure] verweist standardmäßig auf das Feld „Datum des tatsächlichen Abschlusses“. Wenn Sie dies nicht verwenden oder auch das Feld „Geschätztes Abschlussdatum“ verwenden, erläutern Sie Ihren Prozess Ihrer Fachkraft für Lösungstechnik oder Ihrer Erfolgs-Managerin bzw. Ihrem Erfolgs-Manager. Möglicherweise ist ein benutzerdefinierter Workflow erforderlich, um beide Felder zu berücksichtigen.

## Konfigurieren von Verbindungen und Datenanbietern {#configuring-your-connections-and-data-providers}

Nachdem Sie sich bei der [!DNL Marketo Measure]-Anwendung angemeldet haben und in der Adobe Admin Console als Benutzerin bzw. Benutzer festgelegt wurden, müssen Sie als nächstes Ihre verschiedenen Datenverbindungen einrichten.

**CRM als Datenanbieter**

1. Klicken Sie in Ihrem [!DNL Marketo Measure]-Konto auf das Dropdown-Menü **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. Klicken Sie unter [!UICONTROL Integrationen] in der linken Navigationsleiste auf **[!UICONTROL Verbindungen]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. Klicken Sie neben [!UICONTROL Microsoft Dynamics CRM] auf die Schaltfläche **[!UICONTROL Verbinden]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. Wählen Sie [!UICONTROL Zugangsdaten] oder [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >Weitere Informationen zu OAuth finden Sie in [diesem Artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). Wenn Sie Fragen zu diesem Vorgang haben, wenden Sie sich an Ihre [!DNL Marketo Measure]-Kundenbetreuung.

1. In diesem Beispiel haben wir Zugangsdaten ausgewählt. Geben Sie Ihre Zugangsdaten ein und klicken Sie auf **[!UICONTROL Weiter]**.

Nach der Verbindung werden die Details Ihrer Dynamics-Verbindung in der Liste der CRM/MAP-Verbindungen angezeigt.

**Verbindungen von Werbekonten**

Um Ihre Werbekonten mit [!DNL Marketo Measure] zu verbinden, besuchen Sie zunächst die Registerkarte [!UICONTROL Verbindungen] in der [!DNL Marketo Measure]-Anwendung.

1. Führen Sie die Schritte 1 und 2 aus dem obigen Abschnitt _CRM als Datenanbieter_ aus.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Neue CRM-Verbindung einrichten]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. Wählen Sie die gewünschte Plattform aus.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]-Javascript**

Damit [!DNL Marketo Measure] Ihre Web-Aktivitäten verfolgen kann, sind mehrere Schritte zur Einrichtung erforderlich.

1. Klicken Sie auf das Dropdown-Menü **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Kontenkonfiguration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. Geben Sie Ihre Telefonnummer ein. Geben Sie für Website Ihre primäre Stamm-Domain ein, die für das [!DNL Marketo Measure]-Tracking auf Ihrer Website verwendet wird. Klicken Sie auf **[!UICONTROL Speichern]**, wenn Sie fertig sind.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >Um mehrere Stamm-Domains hinzuzufügen, kontaktieren Sie Ihre [!DNL Marketo Measure]-Kundenbetreuung.

1. Das [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) muss dann auf der gesamten Website und den Landingpages platziert werden. Wir empfehlen, für das Skript im Kopfteil Ihrer Landingpages eine Hartkodierung durchzuführen oder es über ein Tag-Management-System wie [Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md) hinzuzufügen.

   >[!NOTE]
   >
   >Standardmäßig exportiert [!DNL Marketo Measure] jedes Mal 200 Einträge pro API-Credit, wenn ein Vorgang Daten an Ihr CRM sendet. Den meisten Kunden bietet dies das optimale Gleichgewicht zwischen den von [!DNL Marketo Measure] verbrauchten API-Credits und den Anforderungen der CPU-Ressourcen im CRM-System. Bei Kundinnen und Kunden mit komplexen CRM-Konfigurationen, wie Workflows und Triggern, kann eine kleinere Batch-Größe die CRM-Leistung möglicherweise jedoch verbessern. Dazu können Kundinnen und Kunden mit [!DNL Marketo Measure] die Batch-Größe für den CRM-Export konfigurieren. Diese Einstellung ist auf der Seite „Einstellungen“ > „CRM“ > „Allgemein“ in der [!DNL Marketo Measure]-Web-Anwendung verfügbar. Dort kann die Kundschaft zwischen Batch-Größen von 200 (Standard), 100, 50 oder 25 wählen.
   >
   >Beachten Sie bei der Änderung dieser Einstellung, dass kleinere Batch-Größen mehr API-Credits aus Ihrem CRM-System verbrauchen. Es wird empfohlen, die Batch-Größe nur zu reduzieren, wenn in Ihrem CRM-System CPU-Timeouts oder eine hohe CPU-Last auftreten.

   >[!NOTE]
   >
   >Wenn Sie den Marketo Measure-Export von Daten in Dynamics deaktivieren, werden keine vorhandenen Daten entfernt. Hilfe zum Entfernen vorhandener Daten erhalten Sie beim Dynamics-Support.

   >[!MORELIKETHIS]
   >
   >[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
