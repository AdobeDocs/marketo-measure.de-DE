---
description: '[!DNL Marketo Measure] CRM Package-Less-Integration - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] CRM-Paketlose Integration'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---


# [!DNL Marketo Measure] CRM-Paketlose Integration {#marketo-measure-crm-packageless-integration}

Nicht alle Marketing-Teams möchten (oder haben Zugriff) Marketing-Berichte außerhalb des CRM ausführen, unabhängig davon, ob dies aufgrund von eingeschränktem Zugriff, CRM-Eigentümerschaft, längerer Wertschöpfungszeit oder rechtlichen Auswirkungen geschieht. Wenn Sie den Weg [!DNL Marketo Measure] Schnellstarts beschreiten, erhalten Sie die Möglichkeit, [!DNL Marketo Measure] effektiv und mit möglichst wenig Abhängigkeit vom CRM zu implementieren und auszuführen.

## [!DNL Marketo Measure] Standardinstallation {#standard-marketo-measure-installation}

Über die standardmäßige [!DNL Marketo Measure]-Installation müssen Sie ein [!DNL Salesforce] Package oder eine [!DNL Microsoft Dynamics] Managed Solution installieren. Die Installation umfasst benutzerdefinierte Objekte/Entitäten und benutzerdefinierte Felder, die dem CRM hinzugefügt werden, in die [!DNL Marketo Measure] dann Daten schreiben können.

Eine paketlose Integration mit [!DNL Marketo Measure] ist für Kunden gedacht, die keine benutzerdefinierten Objekte/Entitäten oder Felder in Ihrem CRM erstellen möchten. Dies ist auch eine gute Option für Kunden, die eine externe Data Warehouse verwenden.

## Berechtigungen {#permissions}

Eine [!DNL Marketo Measure] CRM-Paketlose Integration erfordert weiterhin den Zugriff auf standardmäßige CRM-Objekte wie Leads und Kontakte. Es wird empfohlen, dass ein dedizierter Benutzer als verbundener Benutzer dient, da er über die entsprechenden Datenzugriffsberechtigungen verfügt.

Um sicherzustellen, dass alle Daten ordnungsgemäß aus Ihrem CRM abgerufen werden, benötigen wir die folgenden Einstellungen für Sicherheit und Barrierefreiheit: Alle Daten für das Profil des dedizierten Benutzers anzeigen. Dieser Berechtigungssatz bietet [!DNL Marketo Measure] den Zugriff, der zum Herunterladen von Daten aus Standardobjekten erforderlich ist. Dieser Berechtigungssatz befindet sich auf Profilebene.

## Einrichten des Identitäts-Providers und der Datenverbindungen {#setup-your-identity-provider-and-data-connections}

Überspringen Sie in den folgenden Handbüchern die Schritte zum Installieren des [!DNL Salesforce]-Pakets oder [!DNL Microsoft Dynamics] Managed Solution und befolgen Sie nur die Anweisungen zu Berechtigungen und Integration .

[!DNL Salesforce] Kunden klicken [hier](/help/configuration-and-setup/marketo-measure-and-salesforce/install-set-up.md).

[!DNL Microsoft Dynamics] Kunden klicken [hier](/help/marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Nachdem Sie diese Schritte abgeschlossen haben, sollte die Integration funktionsfähig sein. Wenden Sie sich bei Problemen an Ihren [!DNL Marketo Measure] oder an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>Wenn Sie mit der [!DNL Marketo Measure] CRM-Paketlosen Integration beginnen, können Sie das Salesforce-Paket oder die Microsoft Dynamics Managed Solution später installieren.
