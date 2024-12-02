---
unique-page-id: 37356027
description: '[!DNL Marketo Measure] Integration ohne CRM - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] CRM-Paketlose Integration'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# [!DNL Marketo Measure] CRM-Paketlose Integration {#marketo-measure-crm-packageless-integration}

Nicht alle Marketing-Teams möchten (oder haben Zugriff), dass Marketing-Berichte aus dem CRM-System ausgeführt werden, unabhängig davon, ob dies auf eingeschränkten Zugriff, CRM-Eigentum, längere Wertdauer oder rechtliche Auswirkungen zurückzuführen ist. Wenn Sie den Pfad von [!DNL Marketo Measure] Quick Start hinuntergehen, können Sie [!DNL Marketo Measure] effektiv implementieren und ausführen, wobei Sie so wenig auf das CRM-System wie möglich angewiesen sind.

## Standardinstallation [!DNL Marketo Measure] {#standard-marketo-measure-installation}

Durch die Standardinstallation von [!DNL Marketo Measure] müssen Sie ein [!DNL Salesforce] -Paket oder eine [!DNL Microsoft Dynamics] verwaltete Lösung installieren. Die Installation umfasst benutzerdefinierte Objekte/Entitäten und benutzerdefinierte Felder, die dem CRM-System hinzugefügt werden und in die [!DNL Marketo Measure] dann Daten schreiben kann.

Eine packaglose Integration mit [!DNL Marketo Measure] ist für Kunden gedacht, die keine benutzerdefinierten Objekte/Entitäten oder benutzerdefinierten Felder in Ihrem CRM-System erstellen möchten. Es ist auch eine gute Option für Kunden, die eine externe Data Warehouse verwenden.

## Berechtigungen {#permissions}

Für eine Integration ohne CRM-Verpackung mit [!DNL Marketo Measure] ist weiterhin Zugriff auf Standard-CRM-Objekte wie Leads und Kontakte erforderlich. Es wird empfohlen, dass ein dedizierter Benutzer als verbundener Benutzer fungiert, da er über die entsprechenden Datenzugriffsberechtigungen verfügt.

Um sicherzustellen, dass alle Daten ordnungsgemäß aus Ihrem CRM-System abgerufen werden, benötigen wir die folgenden Sicherheits- und Barrierefreiheitseinstellungen: Alle Daten für das Profil des dedizierten Benutzers anzeigen. Dieser Berechtigungssatz gibt [!DNL Marketo Measure] den Zugriff, der zum Herunterladen von Daten von Standardobjekten erforderlich ist. Dieser Berechtigungssatz befindet sich auf Profilebene.

## Einrichten Ihres Identitäts-Providers und Ihrer Datenverbindungen {#setup-your-identity-provider-and-data-connections}

Überspringen Sie in den nachstehenden Handbüchern die Schritte zur Installation des [!DNL Salesforce]-Pakets oder der [!DNL Microsoft Dynamics] Managed Solution und befolgen Sie nur die Anweisungen zu Berechtigungen und Integration.

[!DNL Salesforce] -Kunden klicken auf [hier](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] -Kunden klicken auf [hier](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Nachdem Sie diese Schritte ausgeführt haben, sollte die Integration betriebsbereit sein. Wenn Probleme auftreten, wenden Sie sich an Ihren [!DNL Marketo Measure] -Kundenbetreuer oder an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>
>Wenn Sie mit der Integration ohne CRM beginnen, können Sie das Salesforce-Package oder die Microsoft Dynamics Managed Solution später installieren.[!DNL Marketo Measure]
