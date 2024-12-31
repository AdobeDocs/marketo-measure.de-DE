---
description: Data Warehouse-Zugriff - Direct Share - Produktdokumentation
title: Data Warehouse Access - Direct Share
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 4%

---

# Data Warehouse Access - Direct Share {#data-warehouse-access-direct-share}

## Anforderungen {#requirements}

Damit [!DNL Marketo Measure] eine direkte Freigabe für das Data Warehouse einrichten können, müssen Sie die folgenden Anforderungen erfüllen.

* Sie haben Ihre eigene Snowflake-Instanz.
* Ihre Snowflake-Instanz befindet sich in der Azure East US 2 Snowflake-Region.
* Sie geben [!DNL Marketo Measure] Ihre Snowflake-Konto-ID an.

## Einschränkungen {#limitations}

[!DNL Marketo Measure] können aufgrund der aktuellen Beschränkungen für Snowflake Direct Share nur Snowflake-Freigaben für Konten in Azure East US 2 einrichten. Wenn Ihre Daten in anderen Snowflake-Regionen verfügbar gemacht werden sollen, empfehlen wir, eine Kopie der Daten in einem Snowflake-Konto in Azure East US 2 zu erstellen und die Funktion [Snowflake-Datenbankreplikation](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} zu verwenden, um Ihre Daten in die Snowflake-Region/das gewünschte Konto zu kopieren.

## Snowflake-Konto-ID eingeben {#enter-snowflake-account-id}

Öffnen Sie den **Einstellungen** in der Marketo Measure-App und navigieren Sie zur **Data Warehouse** Seite. Geben Sie im Abschnitt **Direct Share** Ihre [Snowflake-Konto-ID](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in das bereitgestellte Feld ein und klicken Sie auf **Verbinden**.

![](assets/data-warehouse-access-direct-share-1.png)

## Zugriff auf die Freigabe {#accessing-the-share}

Nachdem die Freigabe für die angegebene Konto-ID erstellt wurde, müssen Sie die [Einrichtungsschritte](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} in Ihrer Snowflake-Instanz ausführen, um auf die Daten zuzugreifen.

>[!NOTE]
>
>Sie können einen beliebigen Datenbanknamen auswählen. Sie können die Berechtigungen einer beliebigen Rolle zuweisen, sofern diese in Ihrer Snowflake-Instanz vorhanden ist.

* Konto-Administratorrolle verwenden

```
USE ROLE ACCOUNTADMIN
```

* Verfügbare Aktien anzeigen (hier wird der Name der gewährten Aktie angezeigt)

```
SHOW SHARES
```

* Erstellen einer Datenbank für die Freigabe

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Gewähren von Berechtigungen für die freigegebene Datenbank

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Detailliertere Anweisungen und Schritte zum Durchführen dieser Schritte über die Snowflake-Benutzeroberfläche finden Sie in der Dokumentation zur [Snowflake](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
