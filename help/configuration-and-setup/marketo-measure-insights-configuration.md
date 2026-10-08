---
description: '[!DNL Marketo Measure] Insights-Konfiguration - [!DNL Marketo Measure]'
title: Konfiguration von [!DNL Marketo Measure]-Insights
exl-id: f6fe296b-d22a-43f2-b124-5d4b2f74d67a
feature: Reporting
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: d24e0b99-7796-5c7d-831d-d71a1d725f01
    internal-label: Reporting
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 4%
---
# Konfiguration von [!DNL Marketo Measure]-Insights {#marketo-measure-insights-configuration}

Die [!DNL Marketo Measure] Insights Canvas-App sollte zum Lead-Seiten-Layout hinzugefügt werden, erfordert jedoch eine zusätzliche Einrichtung im Abschnitt „Verbundene Apps“ Ihrer [!DNL Salesforce]. Befolgen Sie diese Anweisungen, um sicherzustellen, dass die Canvas-App über die entsprechenden Berechtigungen verfügt.

1. Navigieren Sie zu [!DNL Salesforce] Setup und klicken Sie auf **[!UICONTROL Verbundene Apps]** auf der Registerkarte [!UICONTROL Apps verwalten].

1. Wählen Sie die [!DNL Marketo Measure Insights] aus der Liste aus, die mit Werten gefüllt wird.

1. Ändern Sie im Abschnitt [!UICONTROL OAuth]-Richtlinien die Einstellung Zulässige Benutzer in „Admin-genehmigte Benutzer sind vorautorisiert“. Ein Popup wird angezeigt, klicken Sie auf **[!UICONTROL OK]** und dann auf **[!UICONTROL Speichern]**.

   ![1. Ändern Sie im Abschnitt OAuth-Richtlinien die Einstellung Zulässige Benutzer &#x200B;](assets/marketo-app-1.png)

1. Nachdem die Seite gespeichert wurde, können Sie auf die Schaltfläche **[!UICONTROL Profile verwalten]** klicken.

   ![1. Nachdem die Seite gespeichert wurde, können Sie auf die Schaltfläche](assets/marketo-app-2.png)

1. Wählen Sie alle Profile aus, die Zugriff auf [!DNL Marketo Measure] Insights haben sollen, und klicken Sie auf **[!UICONTROL Speichern]**.
