---
description: Erfahren Sie mehr über den Migrationsprozess beim Wechsel vom  [!DNL Marketo Measure]  Abonnement zu  [!DNL Marketo Measure] Ultimate.
title: Migration von Stufe zu  [!DNL Marketo Measure] Ultimate
feature: Integration, Tracking, Attribution
exl-id: 828c9bba-3835-484a-bd80-84b5a6b67e22
source-git-commit: 827469c68e518ff7a6497c3167ced7039323af62
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# Migration von Tier 1-2 zu [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

In diesem Artikel wird der Migrationsprozess für Benutzende beschrieben, die vom Tier 1- oder Tier 2-Abonnement zu [!DNL Marketo Measure] Ultimate wechseln.

>[!IMPORTANT]
>
>Denken Sie daran, Ihre vorhandene Tier-Instanz beizubehalten, bis die Migration abgeschlossen ist.

## Datenerfassung {#data-collection}

### Datenverkehr im Web {#web-traffic-data}

* Für die JavaScript-Bereitstellung sind keine Änderungen erforderlich.

* Aktivieren von Domains in der neuen Ultimate-Instanz.

* Senden Sie bei Bedarf ein Ticket, um historische Web-Daten zu migrieren und erneut zu verarbeiten.

* Anzeigenintegrationen bleiben unverändert, denken Sie jedoch daran, sie in Ultimate erneut zu verbinden. Bevor Sie dies tun, stellen Sie sicher, dass Sie Ihre Werbekonten im Ebenenmandanten trennen.

>[!NOTE]
>
>Historische Anzeigenkostendaten werden nicht importiert. Wir importieren erst die Anzeigenkostendaten, nachdem die Werbekonten wieder verbunden wurden.

### Unternehmensdatenverbindung {#enterprise-data-connection}

Implementieren Sie alle Quelldatenverbindungen in AEP neu, einschließlich CRM- und Marketo Engage-Verbindungen.

## Datenumwandlung {#data-transformation}

* Account-Based Marketing-Funktionen, einschließlich Lead-Konto-Zuordnung und prädiktiver Interaktionswerte, sind in Ultimate nicht verfügbar.

   * Sie können jedoch Ihre Ergebnisse der Lead-Konto-Zuordnung über AEP importieren und innerhalb der Plattform verwenden.

* In Ultimate werden historische CRM-Stadienübergänge abgeleitet und nicht direkt gelesen, da keine direkte CRM-Verbindung besteht.

   * Wir lesen Opportunity-Aufzeichnungen und Zeitstempel und sehen die aktuelle Phase und schließen daraus die historischen Stadien.

## Berichterstellung {#reporting}

* Ultimate sendet keine Daten zurück zu CRMs.

   * Wenn ein Zurückschieben von Daten an das CRM gewünscht wird, ist eine benutzerdefinierte ETL-Pipeline erforderlich, um Daten von der Marketo Measure-Snowflake in das CRM zu extrahieren. Sie müssen in Ihrem CRM ein benutzerdefiniertes Datenmodell einrichten.

* Alle Discover-Dashboards bleiben dieselben wie in der mehrstufigen Lösung, mit dem Zusatz von Attribution AI-Dashboards.
