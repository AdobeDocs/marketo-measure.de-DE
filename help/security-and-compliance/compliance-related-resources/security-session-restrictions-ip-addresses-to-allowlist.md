---
unique-page-id: 18874706
description: Sicherheitssitzungsbeschränkungen - IP-Adressen für die Zulassungsliste - Marketo Measure - Produktdokumentation
title: Sicherheitssitzungsbeschränkungen - IP-Adressen für die Zulassungsliste
exl-id: aaf5190f-893c-4872-8d03-93f516e70a59
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 8%

---

# Sicherheitssitzungsbeschränkungen: IP-Adressen in der Zulassungsliste {#security-session-restrictions-ip-addresses-to-allowlist}

Wenn [Sitzungssicherheitseinstellungen](https://help.salesforce.com/articleView?id=admin_sessions.htm&amp;type=0){target="_blank"} vorhanden sind, die verhindern, dass bestimmte IP-Adressen Daten an Ihre [!DNL Salesforce]-Instanz senden/abrufen, müssen die folgenden IP-Bereiche auf die Zulassungsliste gesetzt werden, damit [!DNL Marketo Measure] Daten an [!DNL Salesforce] senden kann:

* 52.162.84.192 - 52.162.84.207
* 23.10.229.112 - 23.100.229.127
* 20.186.163.0 - 20.186.163.15

Um den vertrauenswürdigen IP-Bereichen in Salesforce [!DNL Marketo Measure] IPs hinzuzufügen, klicken Sie auf **[!UICONTROL Setup]** > **[!UICONTROL Administrationseinstellungen]** > **[!UICONTROL Sicherheitskontrollen]** > **[!UICONTROL Netzwerkzugriff]** > **[!UICONTROL Neu]**.

![](assets/1.png)
