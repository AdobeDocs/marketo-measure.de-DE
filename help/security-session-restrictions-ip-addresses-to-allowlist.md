---
description: Führt Salesforce-IP-Bereiche für die Zulassungsliste auf, damit Marketo Measure eine Verbindung herstellen kann, wenn Sitzungsbeschränkungen erzwungen werden
title: Einschränkungen für Sicherheitssitzungen - IP-Adressen für die Zulassungsliste
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 7%

---

# Sicherheitssitzungsbeschränkungen: IP-Adressen in der Zulassungsliste {#security-session-restrictions-ip-addresses-to-allowlist}

Wenn [Sitzungssicherheitseinstellungen](https://help.salesforce.com/articleView?id=admin_sessions.htm&type=0){target="_blank"} vorhanden sind, die verhindern, dass bestimmte IP-Adressen Daten an Ihre [!DNL Salesforce]-Instanz senden/abrufen, müssen die folgenden IP-Bereiche auf die Zulassungsliste gesetzt werden, damit [!DNL Marketo Measure] Daten an [!DNL Salesforce] senden können:

* 52.162.84.192 – 52.162.84.207
* 23.100.229.112 – 23.100.229.127
* 20.186.163.0 – 20.186.163.15

Um [!DNL Marketo Measure] IP-Adressen zu den vertrauenswürdigen IP-Bereichen in Salesforce hinzuzufügen, klicken Sie auf **[!UICONTROL Setup]** > **[!UICONTROL Administration-]** > **[!UICONTROL Sicherheitssteuerungen]** > **[!UICONTROL Netzwerkzugriff]** > **[!UICONTROL Neu]**.

![So fügen Sie Marketo Measure-IPs zu den vertrauenswürdigen IP-Bereichen in hinzu](assets/compliance-resources-1.png)
