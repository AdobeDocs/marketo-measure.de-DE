---
description: Führt Salesforce-IP-Bereiche für die Zulassungsliste auf, damit Marketo Measure eine Verbindung herstellen kann, wenn Sitzungsbeschränkungen erzwungen werden
title: Einschränkungen für Sicherheitssitzungen - IP-Adressen für die Zulassungsliste
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 12%
---
# Einschränkungen für Sicherheitssitzungen: IP-Adressen zur Allowlist hinzufügen {#security-session-restrictions-ip-addresses-to-allowlist}

Wenn [Sitzungssicherheitseinstellungen](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"} vorhanden sind, die verhindern, dass bestimmte IP-Adressen Daten an Ihre [!DNL Salesforce]-Instanz senden/abrufen, müssen die folgenden IP-Bereiche auf die Zulassungsliste gesetzt werden, damit [!DNL Marketo Measure] Daten an [!DNL Salesforce] senden können:

* 52.162.84.192 – 52.162.84.207
* 23.100.229.112 – 23.100.229.127
* 20.186.163.0 – 20.186.163.15

Um [!DNL Marketo Measure] IP-Adressen zu den vertrauenswürdigen IP-Bereichen in Salesforce hinzuzufügen, klicken Sie auf **[!UICONTROL Setup]** > **[!UICONTROL Administration-]** > **[!UICONTROL Sicherheitssteuerungen]** > **[!UICONTROL Netzwerkzugriff]** > **[!UICONTROL Neu]**.

![So fügen Sie Marketo Measure-IPs zu den vertrauenswürdigen IP-Bereichen in hinzu](assets/compliance-resources-1.png)
