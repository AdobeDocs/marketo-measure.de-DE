---
description: Erfahren Sie mehr über den Migrationsprozess beim Wechsel vom  [!DNL Marketo Measure] gestuften Abonnement zu [!DNL Marketo Measure] Ultimate.
hide: true
hidefromtoc: true
title: Migration von Tier zu [!DNL Marketo Measure] Ultimate
feature: Integration, Tracking, Attribution
source-git-commit: 0c94276bec390bb67dafe5dd679c1a0378a05c85
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Migration von Stufe 1-2 zu [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

In diesem Artikel wird der Migrationsprozess für Benutzer beschrieben, die von der Tier 1- oder Tier 2-Mitgliedschaft zu Marketo Measure Ultimate wechseln.

>[!IMPORTANT]
>
>Denken Sie daran, Ihre vorhandene Tier-Instanz so lange beizubehalten, bis die Migration abgeschlossen ist.

## Datenerfassung {#data-collection}

### Web-Traffic-Daten {#web-traffic-data}

* Für die JavaScript-Implementierung sind keine Änderungen erforderlich.

* Aktivieren Sie Domänen in der neuen Ultimate-Instanz.

* Senden Sie bei Bedarf ein Ticket, um historische Web-Daten zu migrieren und erneut zu verarbeiten.

* Anzeigenintegrationen bleiben unverändert, aber denken Sie daran, sie in Ultimate erneut zu verbinden. Stellen Sie zunächst sicher, dass Sie Ihre Anzeigenkonten im Tier-Mandanten trennen.

>[!NOTE]
>
>Historische Daten zu Anzeigenkosten werden nicht importiert. Daten zu Anzeigenkosten werden erst importiert, nachdem die Anzeigenkonten erneut verbunden wurden.

### Enterprise-Datenverbindung {#enterprise-data-connection}

Implementieren Sie alle Quelldatenverbindungen in AEP, einschließlich CRM- und Marketo Engage-Verbindungen.

## Datenumwandlung {#data-transformation}

* Account-Based Marketing-Funktionen, einschließlich der Übereinstimmung von Interessenten mit Konten und der prädiktiven Interaktionswerte, sind in Ultimate nicht verfügbar.

   * Sie können jedoch die Ergebnisse Ihrer Lead-zu-Konto-Abgleiche über AEP importieren und innerhalb der Plattform verwenden.

* In Ultimate werden Verlaufsumstellungen im CRM-System nicht direkt gelesen, sondern abgeleitet, da es keine direkte CRM-Verbindung gibt.

   * Wir lesen Opportunity-Einträge und Zeitstempel, sehen die aktuelle Bühne und schließen dann die historischen Bühnen ab.

## Berichterstellung {#reporting}

* Ultimate sendet keine Daten an CRMs.

   * Wenn Daten an das CRM zurückgesendet werden sollen, ist eine benutzerdefinierte ETL-Pipeline erforderlich, um Daten aus dem Marketo Measure-Snowflake in das CRM-System zu extrahieren. Sie müssen ein benutzerdefiniertes Datenmodell in Ihrem CRM-System einrichten.

* Alle Discover-Dashboards bleiben mit Attribution AI-Dashboards identisch mit der gestuften -Lösung.
