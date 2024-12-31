---
unique-page-id: 18874690
description: Erneutes Autorisieren von verbundenen Konten - [!DNL Marketo Measure]
title: Erneutes Autorisieren von Connected Accounts
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
feature: APIs, Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 3%

---

# Erneutes Autorisieren von Connected Accounts {#reauthorizing-connected-accounts}

Wenn ein Konto von Ihrem [!DNL Marketo Measure]-Konto getrennt wird, ändert sich der Status der Plattform in „Autorisierung erforderlich“ und es wird ein rotes Schlüsselsymbol angezeigt.

Wenn die Verbindung Ihrer Werbeplattform unterbrochen wird, können [!DNL Marketo Measure] keine Kostendaten herunterladen oder, falls Sie das automatische Tagging aktiviert haben, die [!DNL Marketo Measure] UTM-Parameter an neu erstellte Anzeigen anhängen. [!DNL Marketo Measure] können die UTM-Parameter nicht rückwirkend an Touchpoints anhängen, die von der Anzeigenplattform erstellt wurden, während das Konto getrennt wurde.

Wenn Ihre CRM-Plattform getrennt wird, können [!DNL Marketo Measure] keine [!DNL Marketo Measure] Daten aktualisieren oder neue Touchpoints in Ihre Organisation übertragen. Sobald die CRM-Verbindung wiederhergestellt wurde, überträgt [!DNL Marketo Measure] alle Daten, die während der Trennung des Kontos fehlten.

![](assets/1-1.png)

## Erneutes Autorisieren von getrennten Konten {#re-authorizing-disconnected-accounts}

1. Wechseln Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und melden Sie sich an.
1. Wählen Sie **[!UICONTROL Einstellungen]** auf der Registerkarte [!UICONTROL Mein Konto] in der oberen linken Ecke aus.
1. Suchen Sie den Abschnitt Integrationen auf der linken Seite und klicken Sie auf **[!UICONTROL Verbindungen]**.
1. Wählen Sie das Symbol Roter Schlüssel neben dem Konto, mit dem die Verbindung wiederhergestellt werden soll.
1. Ein Popup-Fenster wird angezeigt, in dem Sie aufgefordert werden, die Anmeldedaten für das Konto anzugeben.
