---
description: Data Warehouse Access - Direct Share - Produktdokumentation
title: Data Warehouse Access - Direct Share
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: 36ee02b2dfc2651987f72fc7f02fe629717f02a0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Data Warehouse Access - Direct Share {#data-warehouse-access-direct-share}

## Anforderungen {#requirements}

Zur [!DNL Marketo Measure] Um eine direkte Freigabe für Data Warehouse einzurichten, müssen Sie die folgenden Anforderungen erfüllen.

* Sie verfügen über eine eigene Snowflake-Instanz.
* Ihre Snowflake-Instanz befindet sich in der Region Azure East US 2 Snowflake.
* Sie [!DNL Marketo Measure] mit Ihrer Snowflake-Konto-ID.

## Einschränkungen {#limitations}

[!DNL Marketo Measure] Snowflake Direct Share kann nur mit Konten in Azure East US 2 eingerichtet werden, da das Snowflake Direct Share derzeit eingeschränkt ist. Wenn Sie möchten, dass Ihre Daten in anderen Snowflake-Regionen zur Verfügung gestellt werden, empfehlen wir, eine Kopie der Daten in einem Snowflake-Konto in Azure East US 2 zu erstellen und die [Snowflake-Datenbankreplikation](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} -Funktion verwenden, um Ihre Daten in die Region/das Konto Ihres Snowflake zu kopieren.

## Snowflake-Konto-ID eingeben {#enter-snowflake-account-id}

Öffnen Sie die **Einstellungen** in der Marketo Measurement-App und navigieren Sie zur **Data Warehouse** Seite. Im **Direkte Freigabe** eingeben. [Snowflake-Konto-ID](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in das bereitgestellte Feld ein und klicken Sie auf **Verbinden**.

![](assets/data-warehouse-access-direct-share-1.png)

## Zugriff auf die Freigabe {#accessing-the-share}

Nachdem die Freigabe für die angegebene Konto-ID erstellt wurde, müssen Sie die [Einrichtungsschritte](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} in Ihrer Snowflake-Instanz, um auf die Daten zuzugreifen.

>[!NOTE]
>
>Sie können einen beliebigen Datenbanknamen wählen. Sie können die Berechtigungen einer beliebigen Rolle zuweisen, sofern diese in Ihrer Snowflake-Instanz vorhanden ist.

* Verwenden der Kontoadministratorrolle

```
USE ROLE ACCOUNTADMIN
```

* Verfügbare Aktien anzeigen (dabei wird der Name der gewährten Aktie angezeigt)

```
SHOW SHARES
```

* Erstellen einer Datenbank für die Freigabe

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Berechtigungen für die freigegebene Datenbank gewähren

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Detaillierte Anweisungen und Schritte zum Ausführen dieser Schritte über die Snowflake-Benutzeroberfläche finden Sie unter [Snowflake-Dokumentation direkt](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
