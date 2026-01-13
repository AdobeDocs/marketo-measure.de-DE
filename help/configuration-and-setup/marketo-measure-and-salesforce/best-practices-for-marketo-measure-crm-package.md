---
description: Best Practices für das  [!DNL Marketo Measure] -CRM-Paket - [!DNL Marketo Measure]
title: Best Practices für [!DNL Marketo Measure] CRM-Package
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 7%

---


# Best Practices für [!DNL Marketo Measure] CRM-Paket {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Das wird aktualisiert und das Rebranding wird bald in Ihrem CRM widergespiegelt.

## Überblick {#overview}

[!DNL Marketo Measure] sowohl mit [!DNL Salesforce] als auch mit [!DNL Microsoft Dynamics] integriert, konzentriert sich dieses Dokument auf die [!DNL Marketo Measure] Best Practices für die für [!DNL Salesforce] entworfenen CRM-Pakete.

Während der Implementierung wären die beiden folgenden Pakete in Ihre [!DNL Salesforce]-Instanz installiert worden.

Basispaket : Dies ist das Basispaket, das benutzerdefinierte Objekte und Felder enthält. Es wird empfohlen, die Installation in der Produktionsumgebung für alle Benutzer durchzuführen.
Dashboard-Erweiterungspaket: Dies ist unser Dashboard-Erweiterungspaket, das drei vordefinierte Dashboards enthält. Es wird empfohlen, die Installation in der Produktionsumgebung für alle Benutzer durchzuführen. Dies ist optional, aber wir empfehlen Kunden, Folgendes zu installieren.

Mit diesen Paketen können Ihre [!DNL Marketo Measure] Benutzer einfach auf Touchpoint-Daten in ihrer gesamten [!DNL Salesforce] zugreifen. Um sicherzustellen, dass diese Pakete korrekt konfiguriert sind, müssen Sie sicherstellen, dass Seiten-Layouts, Berechtigungssätze, Berichte und Dashboards den [!DNL Marketo Measure] Benutzern wie erwartet angezeigt werden.

## Best Practices {#best-practice}

Beachten Sie bei der Implementierung und Verwaltung Ihres [!DNL Marketo Measure] [!DNL Salesforce]-Pakets die folgenden Best Practices.

* Vergewissern Sie sich, dass jedes erforderliche Teammitglied Zugriff auf die [!DNL Marketo Measure] Berichtsordner hat. Es sollten 1-3 [!DNL Marketo Measure] vorhanden sein (diese werden unten erläutert). Um den Zugriff zu öffnen, muss die Person, die die Pakete installiert hat, die Berichtsordner für die entsprechenden Benutzer oder Rollen freigeben.
   * **Buyer Touchpoint-Berichte** - für alle verfügbar
   * **[!DNL Marketo Measure]Account-Based Marketing Reports** - Berichte werden nur an Kunden mit Stufe 2 und höher ausgefüllt
   * **Buyer Touchpoint-Dashboards** - für alle verfügbar, dieses Paket ist jedoch optional.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Während die Einrichtung Ihres CRM-Pakets bei der ersten Implementierung abgedeckt wird, wird empfohlen, die Einrichtung Ihres CRM-Pakets einmal jährlich zu überprüfen. Diese Überprüfung bestätigt, dass alle Seiten-Layouts korrekt eingerichtet sind und dass alle entsprechenden Team-Mitglieder Zugriff auf [!DNL Marketo Measure] Berichte und Dashboards haben.

Andere Gründe dafür könnten Trigger einer Überprüfung…

* Hinzufügung neuer Teammitglieder
* Aktualisierungen der [!DNL Salesforce] Seitenlayouts
* Migration von [!DNL Salesforce] Classic zu Lightning
* Aktualisierungen Ihres [!DNL Marketo Measure]
* Vergewissern Sie sich, dass Sie die neueste Version des Buyer-Touchpoints-Pakets in [!DNL Salesforce] installiert haben

>[!NOTE]
>Wenn Sie Marketo Measure beim Exportieren von Daten nach Salesforce deaktivieren, werden keine vorhandenen Daten gelöscht. Um sie zu entfernen, führen Sie die Schritte in [diesem Salesforce-Hilfeartikel](https://help.salesforce.com/s/articleView?language=en_US&id=sf.c360_a_delete_data_stream_records.htm&type=5){target="_blank"} aus.

>[!MORELIKETHIS]
> [Buyer Touchpoint-Paket aktualisieren](/help/configuration-and-setup/marketo-measure-and-salesforce/install-set-up.md)
> [[!DNL Marketo Measure] Berechtigungssätze](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
> [Freigabe des Ordners „Berichte und Dashboards“](https://help.salesforce.com/s/articleView?language=de_DE&id=analytics_share_folder.htm&type=0)
> [Verbinden von Marketo Measure mit Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
