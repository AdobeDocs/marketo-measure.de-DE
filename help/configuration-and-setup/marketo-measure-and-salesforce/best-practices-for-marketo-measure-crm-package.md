---
description: Best Practices für das [!DNL Marketo Measure] CRM-Paket - [!DNL Marketo Measure]
title: Best Practices für [!DNL Marketo Measure] CRM-Package
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 7%

---

# Best Practices für das CRM-Paket [!DNL Marketo Measure] {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Dies wird aktualisiert und das Rebranding wird sich in Kürze in Ihrem CRM-System widerspiegeln.

## Überblick {#overview}

[!DNL Marketo Measure] kann sowohl mit [!DNL Salesforce] als auch mit [!DNL Microsoft Dynamics] integriert werden. Dieses Dokument konzentriert sich auf die [!DNL Marketo Measure] Best Practices für die CRM-Pakete, die für [!DNL Salesforce] entwickelt wurden.

Während der Implementierung wären die beiden folgenden Pakete in Ihrer [!DNL Salesforce] -Instanz installiert worden.

Basispaket: Dies ist das Basispaket, das benutzerdefinierte Objekte und Felder enthält. Es wird empfohlen, die Installation in der Produktion für alle Benutzer durchzuführen.
Dashboard-Erweiterungspaket: Dies ist unser Dashboard-Erweiterungspaket, das drei vordefinierte Dashboards enthält. Es wird empfohlen, die Installation in der Produktion für alle Benutzer durchzuführen. Dies ist optional, wir empfehlen jedoch Kunden, die Installation durchzuführen.

Diese Pakete ermöglichen es Ihren [!DNL Marketo Measure] -Benutzern, einfach auf Touchpoint-Daten in ihrer [!DNL Salesforce] -Instanz zuzugreifen. Die Bestätigung, dass Sie diese Pakete richtig konfiguriert haben, ist entscheidend, um sicherzustellen, dass Seitenlayouts, Berechtigungssätze, Berichte und Dashboards Ihren [!DNL Marketo Measure] -Benutzern wie erwartet präsentiert werden.

## Best Practices {#best-practice}

Beachten Sie bei der Implementierung und Verwaltung Ihres [!DNL Marketo Measure] [!DNL Salesforce]-Pakets die folgenden Best Practices.

* Vergewissern Sie sich, dass alle erforderlichen Teammitglieder Zugriff auf die Ordner des Berichts [!DNL Marketo Measure] haben. Es sollten 1-3 [!DNL Marketo Measure] Ordner vorhanden sein (diese werden unten erläutert). Um den Zugriff zu öffnen, muss die Person, die die Pakete installiert hat, die Berichtsordner für die entsprechenden Benutzer oder Rollen freigeben.
   * **Buyer Touchpoint-Berichte** - für alle verfügbar
   * **[!DNL Marketo Measure]Kontobasierte Marketing-Berichte** - Berichte werden nur auf Ebene 2 und höher der Kunden aufgefüllt
   * **Buyer Touchpoint-Dashboards** - für alle verfügbar, dieses Paket ist jedoch optional.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Während die Einrichtung Ihres CRM-Pakets während der ersten Implementierung behandelt wird, wird empfohlen, die Einrichtung Ihres CRM-Pakets einmal jährlich zu überprüfen. Diese Überprüfung bestätigt, dass alle Seitenlayouts korrekt eingerichtet sind und dass alle entsprechenden Team-Mitglieder Zugriff auf [!DNL Marketo Measure] -Berichte und Dashboards haben.

Andere Gründe dafür könnten Trigger für eine Überprüfung sein...

* Hinzufügung neuer Teammitglieder
* Aktualisierungen Ihrer [!DNL Salesforce]-Seitenlayouts
* Migration von [!DNL Salesforce] Classic zu Lighting
* Upgrade auf Ihren [!DNL Marketo Measure]-Vertrag
* Überprüfen Sie, ob Sie die neueste Version des Käufer-Touchpoints-Pakets in [!DNL Salesforce] installiert haben.

>[!NOTE]
>
>Wenn Sie Marketo Measure deaktivieren und Daten in Salesforce exportieren, werden keine vorhandenen Daten gelöscht. Um sie zu entfernen, führen Sie die Schritte in [diesem Salesforce-Hilfeartikel](https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"} aus.

>[!MORELIKETHIS]
>
>* [Buyer Touchpoint-Paket aktualisieren](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Berechtigungssätze](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Ordner &quot;Berichte und Dashboards freigeben&quot;](https://help.salesforce.com/s/articleView?language=de_DE&amp;id=analytics_share_folder.htm&amp;type=0)
>* [Verbinden von Marketo Measure mit Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
