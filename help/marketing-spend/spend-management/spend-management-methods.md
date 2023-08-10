---
description: Ausgabenverwaltungsmethoden - [!DNL Marketo Measure] - Produktdokumentation
title: Ausgabenverwaltungsmethoden
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 3df1bd288ebd65f75a2ed52d7c8a6faf50c7ff1f
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# Ausgabenverwaltungsmethoden {#spend-management-methods}

Ausgabedaten sind der Schlüssel zum Erfolg der ROI-Berichterstellung mit [!DNL Marketo Measure]. Um eine genaue und umfassende ROI-Berichterstellung über alle Kanäle und Subkanäle hinweg zu erhalten, müssen Sie sicherstellen, dass die entsprechenden Ausgabedaten in [!DNL Marketo Measure].

Es gibt drei Möglichkeiten, Ausgabedaten in [!DNL Marketo Measure]. Jede Methode ist so konzipiert, dass Ausgabedaten aus bestimmten Dateneingaben abgerufen werden.

**1) API-Connected Accounts**

Jedes Anzeigenkonto, mit dem Sie verbunden sind [!DNL Marketo Measure] über eine API automatisch in [!DNL Marketo Measure] für ROI-Berichte. Gehen Sie zu Ihrem [!DNL Marketo Measure] App und wählen Sie die [!UICONTROL Verbindungen] Registerkarte unter [!UICONTROL Integrationen] Abschnitt. Weitere Informationen zum Einrichten Ihrer API-Verbindungen finden Sie in der [Integrierte Anzeigenplattformen](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) Artikel.

**2) CRM-Kampagnenkostensynchronisierung**

Alle [!DNL Marketo Measure] -Konto hat Zugriff auf eine Funktion namens [CRM-Kampagnenkosten synchronisieren](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). Standardmäßig ist dieses Feature-Bit auf &quot;Nein&quot;gesetzt, kann jedoch jederzeit aktiviert werden.

![](assets/spend-management-methods-1.png)

Nach Aktivierung dieser Funktion werden Ausgaben automatisch von jeder CRM-Kampagne/-Programm abgerufen, die die folgenden Kriterien erfüllt

i. [!DNL Marketo Measure] prüft zunächst, ob die Kampagne/das Programm Touchpoints erstellt, entweder aus einer übereinstimmenden [Kampagnensynchronisierungsregel](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) , der erstellt wurde, oder eine [Regel zur Programmsynchronisierung](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) , das erstellt wurde, oder [Käufer-Touchpoints-Wert aktivieren](/help/channel-tracking-and-setup/offline-channels/deprecated-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) ist &quot;Alle Campaign-Mitglieder einschließen&quot;oder &quot;Respondierte Kampagnenmitglieder einschließen&quot;.

ii. Ein Startdatum muss in der Kampagne/dem Programm angegeben werden.

iii. Ein Enddatum muss auch in der Kampagne/dem Programm angegeben werden.

iv. Schließlich müssen die tatsächlichen Kosten (für Kampagnen in SFDC) oder die Periodentaugen (für Programme in Marketo) angegeben werden.

**3) Manueller Kosten-Upload**

Mit dieser Methode können Sie [manuelles Hochladen von Ausgabedaten](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) für die Kanäle und Unterkanäle, die nicht von API Connected Accounts oder der CRM Campaign Cost Sync abgedeckt werden. Navigieren Sie zum Abschnitt Marketingausgaben in Ihrer [!DNL Marketo Measure] -Einstellungen können Sie Ausgabedaten über eine CSV-Datei für jeden Ihrer Kanäle hochladen.

Kunden können eine Kombination aus allen drei dieser Methoden verwenden, um ihre Ausgaben zu verwalten, und hängen von der spezifischen Einrichtung der [!DNL Marketo Measure]. Da es drei Methoden gibt, Ausgaben in zu importieren [!DNL Marketo Measure]Wir empfehlen Ihnen dringend, Ihre Marketing-Ausgabenplatine in Discover zu verwenden, um einen umfassenden Überblick über alle Ausgabedaten zu erhalten. Diese Pinnwand ist der einzige Ort, an dem Sie alle Ihre Kanäle und die damit verbundenen Ausgaben sehen können. Mit dem Marketing Spend-Forum können Sie schnell ermitteln, wo Lücken in Ihren Ausgabedaten auftreten können und wie Sie Ihre ROI-Berichte verbessern können.
