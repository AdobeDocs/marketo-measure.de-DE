---
unique-page-id: 37356027
description: "[!DNL Marketo Measure] Packaglose CRM-Integration - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Integration ohne CRM"
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 1%

---

# [!DNL Marketo Measure] CRM-Paketlose Integration {#marketo-measure-crm-packageless-integration}

Nicht alle Marketing-Teams möchten (oder haben Zugriff), dass Marketing-Berichte aus dem CRM-System ausgeführt werden, unabhängig davon, ob dies auf eingeschränkten Zugriff, CRM-Eigentum, längere Wertdauer oder rechtliche Auswirkungen zurückzuführen ist. Den Pfad von [!DNL Marketo Measure] Schnellstart bietet Ihnen die Möglichkeit, die Implementierung und Ausführung effektiv durchzuführen [!DNL Marketo Measure] mit möglichst wenig Vertrauen in das CRM.

## Standard [!DNL Marketo Measure] Installation {#standard-marketo-measure-installation}

Durch den Standard [!DNL Marketo Measure] Installation, müssen Sie eine [!DNL Salesforce] Paket oder [!DNL Microsoft Dynamics] Verwaltete Lösung. Die Installation umfasst benutzerdefinierte Objekte/Entitäten und benutzerdefinierte Felder, die dem CRM-System hinzugefügt werden, das [!DNL Marketo Measure] kann dann Daten in schreiben.

Eine verpackungslose Integration mit [!DNL Marketo Measure] ist für Kunden bestimmt, die keine benutzerdefinierten Objekte/Entitäten oder benutzerdefinierten Felder in Ihrem CRM-System erstellen möchten. Es ist auch eine gute Option für Kunden, die eine externe Data Warehouse verwenden.

## Berechtigungen {#permissions}

A [!DNL Marketo Measure] Die Integration ohne CRM-Lösung erfordert weiterhin Zugriff auf Standard-CRM-Objekte wie Leads und Kontakte. Es wird empfohlen, dass ein dedizierter Benutzer als verbundener Benutzer fungiert, da er über die entsprechenden Datenzugriffsberechtigungen verfügt.

Um sicherzustellen, dass alle Daten ordnungsgemäß aus Ihrem CRM-System abgerufen werden, benötigen wir die folgenden Sicherheits- und Barrierefreiheitseinstellungen: Alle Daten für das Profil des dedizierten Benutzers anzeigen. Dieser Berechtigungssatz gibt [!DNL Marketo Measure] den zum Herunterladen von Daten von Standardobjekten benötigten Zugriff. Dieser Berechtigungssatz befindet sich auf Profilebene.

## Einrichten Ihres Identitäts-Providers und Ihrer Datenverbindungen {#setup-your-identity-provider-and-data-connections}

Überspringen Sie in den nachstehenden Handbüchern die Schritte zur Installation der [!DNL Salesforce] Paket oder [!DNL Microsoft Dynamics] Managed Solution und befolgen Sie nur die Berechtigungen und Integrationsanweisungen.

[!DNL Salesforce] Kunden klicken [here](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] Kunden klicken [here](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Sobald Sie die oben genannten Schritte ausgeführt haben, können Sie loslegen. Wenn Sie auf dem Weg auf Probleme stoßen, wenden Sie sich bitte an Ihren [!DNL Marketo Measure] repräsentativ oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>
>Wenn Sie mit dem [!DNL Marketo Measure] Die CRM-Paketlose Integration ermöglicht die spätere Installation des Salesforce-Packages oder der Microsoft Dynamics Managed Solution.
