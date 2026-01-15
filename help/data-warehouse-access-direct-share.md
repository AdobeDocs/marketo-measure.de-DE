---
description: Erfahren Sie mehr über die Anforderungen und Schritte zum Aktivieren des direkten Freigabezugriffs auf das Marketo Measure Data Warehouse in Snowflake
title: Data Warehouse Access - Direct Share
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---

# Data Warehouse Access - Direct Share {#data-warehouse-access-direct-share}

## Anforderungen {#requirements}

Damit [!DNL Marketo Measure] eine direkte Freigabe für das Data Warehouse einrichten können, müssen Sie die folgenden Anforderungen erfüllen.

* Sie verfügen über eine eigene Snowflake-Instanz.
* Ihre Snowflake-Instanz befindet sich in der Region Azure East US 2 Snowflake .
* Sie geben [!DNL Marketo Measure] Ihre Snowflake-Konto-ID an.

## Einschränkungen {#limitations}

[!DNL Marketo Measure] können Snowflake Direct Shares aufgrund der aktuellen Snowflake Direct Share-Einschränkungen nur für Konten in Azure East US 2 einrichten. Wenn Ihre Daten in anderen Snowflake-Regionen verfügbar gemacht werden sollen, empfehlen wir, eine Kopie der Daten in einem Snowflake-Konto in Azure East US 2 zu erstellen und die Funktion [Snowflake-Datenbankreplikation](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} zu verwenden, um Ihre Daten in die gewünschte Snowflake-Region/das gewünschte Konto zu kopieren.

## Snowflake-Konto-ID eingeben {#enter-snowflake-account-id}

Öffnen Sie den **Einstellungen** in der Marketo Measure-App und navigieren Sie zur Seite **Data Warehouse**. Geben Sie im Abschnitt **Direct Share** Ihre [Snowflake-Konto-ID](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in das bereitgestellte Feld ein und klicken Sie auf **Verbinden**.

![Öffnen Sie den Abschnitt Einstellungen in der Marketo Measure-App und navigieren Sie zu](assets/data-share-1.png)

## Zugriff auf die Freigabe {#accessing-the-share}

Nachdem die Freigabe für die angegebene Konto-ID erstellt wurde, müssen Sie die [Einrichtungsschritte](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} in Ihrer Snowflake-Instanz ausführen, um auf die Daten zuzugreifen.

>[!NOTE]
>
>Sie können einen beliebigen Datenbanknamen auswählen. Sie können die Berechtigungen einer beliebigen Rolle zuweisen, sofern diese in Ihrer Snowflake-Instanz vorhanden ist.

* Konto-Administratorrolle verwenden

```sql
USE ROLE ACCOUNTADMIN
```

* Verfügbare Aktien anzeigen (hier wird der Name der gewährten Aktie angezeigt)

```sql
SHOW SHARES
```

* Erstellen einer Datenbank für die Freigabe

```sql
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Gewähren von Berechtigungen für die freigegebene Datenbank

```sql
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Detailliertere Anweisungen und Schritte zum Durchführen dieser Schritte über die Snowflake-Benutzeroberfläche finden Sie in der [Dokumentation von Snowflake](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
