---
description: Ausgabenverwaltungsmethoden - [!DNL Marketo Measure]
title: Ausgabenverwaltungsmethoden
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Ausgabenverwaltungsmethoden {#spend-management-methods}

Ausgabedaten sind der Schlüssel zum Erfolg der ROI-Berichterstellung mit [!DNL Marketo Measure]. Um eine genaue und umfassende ROI-Berichterstellung für alle Kanäle und Unterkanäle zu erhalten, müssen Sie sicherstellen, dass die entsprechenden Ausgabedaten in [!DNL Marketo Measure] abgerufen werden.

Es gibt drei Möglichkeiten, Ausgabedaten in [!DNL Marketo Measure] zu übertragen. Jede Methode ist so konzipiert, dass Ausgabedaten aus bestimmten Dateneingaben abgerufen werden.

**1 API Connected Accounts**

Bei jedem Anzeigenkonto, das Sie über eine API mit [!DNL Marketo Measure] verbunden haben, werden die Ausgaben für die ROI-Berichterstellung automatisch in [!DNL Marketo Measure] eingezogen. Um zu überprüfen, welche Konten Sie verbunden haben und daher Ausgaben abholen, gehen Sie zu Ihrer [!DNL Marketo Measure]-App und wählen Sie die Registerkarte [!UICONTROL Verbindungen] unter dem Abschnitt [!UICONTROL Integrationen] aus. Weitere Informationen zum Einrichten Ihrer API-Verbindungen finden Sie unter [Integrierte Anzeigenplattformen](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 CRM-Kampagnenkostensynchronisierung**

Jedes [!DNL Marketo Measure] -Konto hat Zugriff auf eine Funktion namens [CRM-Kampagnenkosten synchronisieren](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). Standardmäßig ist dieses Feature-Bit auf &quot;Nein&quot;gesetzt, kann jedoch jederzeit aktiviert werden.

![](assets/spend-management-methods-1.png)

Wenn diese Funktion aktiviert ist, ruft sie automatisch Ausgaben von jeder CRM-Kampagne/-Programm ab, die die folgenden Kriterien erfüllt:

i. [!DNL Marketo Measure] prüft zunächst, ob die Kampagne/das Programm Touchpoints erstellt, entweder aus einer übereinstimmenden [Kampagnensynchronisierungsregel](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) , die erstellt wurde, oder einer entsprechenden [Programmsynchronisierungsregel](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md), oder der Wert [Käufer-Touchpoints aktivieren](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) lautet &quot;Alle Kampagnenmitglieder einschließen&quot;oder &quot;Respondierte Kampagnenmitglieder einschließen&quot;.

ii. Ein Startdatum muss in der Kampagne/dem Programm angegeben werden.

iii. Für die Kampagne/das Programm muss ein Enddatum angegeben werden.

iv. Die tatsächlichen Kosten (für Kampagnen in SFDC) oder die Periodentaugen (für Programme in Marketo) müssen angegeben werden.

**3 Manueller Upload der Kosten**

Mit dieser Methode können Sie [ Ausgabedaten manuell hochladen](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) für die Kanäle und den Unterkanal, die nicht von API Connected Accounts (API Connected Accounts) oder der CRM Campaign-Kostensynchronisierung abgedeckt sind. Wenn Sie in Ihren [!DNL Marketo Measure] -Einstellungen zum Abschnitt Marketing-Ausgaben navigieren, können Sie Daten über eine CSV-Datei für jeden Ihrer Kanäle hochladen.

Kunden können je nach der spezifischen Einrichtung von [!DNL Marketo Measure] eine Kombination aus allen drei dieser Methoden verwenden, um ihre Ausgaben zu verwalten. Da es drei Methoden zum Importieren von Ausgaben in [!DNL Marketo Measure] gibt, empfehlen wir dringend, Ihre Marketing-Ausgabedarstellung in Discover zu verwenden, um einen umfassenden Überblick über alle Ausgabedaten zu erhalten. Diese Pinnwand ist der einzige Ort, an dem Sie alle Ihre Kanäle und die damit verbundenen Ausgaben sehen können. Mit dem Marketing Spend-Forum können Sie schnell ermitteln, wo Lücken in Ihren Ausgabedaten auftreten können und wie Sie Ihre ROI-Berichte verbessern können.
