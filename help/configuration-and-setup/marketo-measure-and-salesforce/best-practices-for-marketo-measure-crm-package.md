---
description: Best Practices für [!DNL Marketo Measure] CRM-Package - [!DNL Marketo Measure]
title: Best Practices für [!DNL Marketo Measure] CRM-Package
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Best Practices für [!DNL Marketo Measure] CRM-Package {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;Bizible&quot;in Ihrem CRM. Dies wird aktualisiert und das Rebranding wird sich in Kürze in Ihrem CRM-System widerspiegeln.

## Überblick {#overview}

[!DNL Marketo Measure] integriert in beide [!DNL Salesforce] und [!DNL Microsoft Dynamics], konzentriert sich dieses Dokument auf die [!DNL Marketo Measure] Best Practices für CRM-Pakete, die für [!DNL Salesforce].

Während der Implementierung wären die beiden folgenden Pakete in Ihrem [!DNL Salesforce] -Instanz.

Basispaket: Dies ist das Basispaket, das benutzerdefinierte Objekte und Felder enthält. Es wird empfohlen, die Installation in der Produktion für alle Benutzer durchzuführen.
Dashboard-Erweiterungspaket: Dies ist unser Dashboard-Erweiterungspaket, das drei vordefinierte Dashboards enthält. Es wird empfohlen, die Installation in der Produktion für alle Benutzer durchzuführen. Dies ist optional, wir empfehlen jedoch Kunden, die Installation durchzuführen.

Diese Pakete ermöglichen [!DNL Marketo Measure] -Benutzer können einfach auf Touchpoint-Daten in ihrer gesamten [!DNL Salesforce] -Instanz. Die Bestätigung, dass Sie diese Pakete richtig konfiguriert haben, ist entscheidend, um sicherzustellen, dass Seitenlayouts, Berechtigungssätze, Berichte und Dashboards für Ihre [!DNL Marketo Measure] -Benutzer wie erwartet.

## Best Practices {#best-practice}

Bei der Implementierung und Verwaltung Ihrer [!DNL Marketo Measure] [!DNL Salesforce] Beachten Sie beim Paket die folgenden Best Practices.

* Vergewissern Sie sich, dass alle erforderlichen Teammitglieder Zugriff auf die [!DNL Marketo Measure] Berichtsordner. Es sollte 1-3 geben [!DNL Marketo Measure] Ordner (diese werden nachfolgend erläutert). Um den Zugriff zu öffnen, muss die Person, die die Pakete installiert hat, die Berichtsordner für die entsprechenden Benutzer oder Rollen freigeben.
   * **Touchpoint-Berichte des Käufers** - für alle zugänglich
   * **[!DNL Marketo Measure]Kontobasierte Marketing-Berichte** - Berichte werden nur an Kunden der Stufe 2 und höher ausgefüllt
   * **Touchpoint-Dashboards des Käufers** - für alle verfügbar, obwohl dieses Paket optional ist.

## Best Practice für die Wartung {#best-practice-for-maintenance}

Während die Einrichtung Ihres CRM-Pakets während der ersten Implementierung behandelt wird, wird empfohlen, die Einrichtung Ihres CRM-Pakets einmal jährlich zu überprüfen. Diese Überprüfung bestätigt, dass alle Seitenlayouts korrekt eingerichtet sind und dass alle entsprechenden Team-Mitglieder Zugriff auf [!DNL Marketo Measure] Berichte und Dashboards.

Andere Gründe dafür könnten Trigger für eine Überprüfung sein...

* Hinzufügung neuer Teammitglieder
* Aktualisierungen für Ihre [!DNL Salesforce] Seitenlayouts
* Migration für [!DNL Salesforce] Von Classic zu Lighting
* Upgrades auf Ihre [!DNL Marketo Measure] Auftrag
* Überprüfen Sie, ob Sie die neueste Version des Käufer-Touchpoints-Pakets in installiert haben. [!DNL Salesforce]

>[!NOTE]
>
>Wenn Sie Marketo Measure deaktivieren und Daten in Salesforce exportieren, werden keine vorhandenen Daten gelöscht. Um sie zu entfernen, führen Sie die Schritte unter [dieser Salesforce-Hilfeartikel](https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Aktualisieren des Käufer-Touchpoint-Pakets](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Berechtigungssätze](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Ordner &quot;Berichte und Dashboards freigeben&quot;](https://help.salesforce.com/s/articleView?language=en_US&amp;id=analytics_share_folder.htm&amp;type=0)
>* [Verbinden von Marketo Measure mit Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
