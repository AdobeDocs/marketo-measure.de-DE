---
description: Beschreibt das Einrichten und Verwenden eines Readerkontos für den Zugriff auf das Marketo Measure Data Warehouse
title: Data Warehouse Access - Reader-Konto
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 3%

---

# Data Warehouse Access - Reader-Konto {#data-warehouse-access-reader-account}

## Snowflake-Zugriffs-Link {#snowflake-access-link}

Um auf Ihr Snowflake Data Warehouse zuzugreifen, müssen Sie zur spezifischen URL für Ihr Snowflake-Konto navigieren. Sie können diesen Zugriffs-Link finden, indem Sie sich bei [!DNL Marketo Measure] anmelden und die folgenden Schritte ausführen, um zur Informationsseite von Data Warehouse zu navigieren.

1. Klicken Sie in [!DNL Marketo Measure] oben auf der Seite auf **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]**.

   ![1. Klicken Sie in Marketo Measure oben auf der Seite auf](assets/data-account-7.png)

1. Klicken Sie im Menü links unter Sicherheit auf **[!UICONTROL Data Warehouse]**.

   ![1. Klicken Sie im Menü links unter Sicherheit auf Data Warehouse.](assets/data-account-8.png)

1. Diese Seite enthält den Link zu Ihrem Snowflake Data Warehouse und Ihrem Benutzernamen.

   ![1. Diese Seite enthält den Link zu Ihrem Snowflake Data Warehouse und](assets/data-account-9.png)

   >[!NOTE]
   >
   >Dies ist ein schreibgeschütztes Konto, das für Ihre Organisation verfügbar ist, nicht nur für einzelne Benutzer. Jeder Benutzer in Ihrem Unternehmen, der Zugriff auf [!DNL Marketo Measure] hat, kann dieses Konto verwenden, um sich beim Snowflake Data Warehouse-Leserkonto anzumelden.

1. Klicken Sie auf den in der Snowflake-URL angegebenen Link, um zur Snowflake-Anmeldeseite zu gelangen, auf der Sie Ihren Benutzernamen und Ihr Kennwort eingeben. _Wenn Sie Ihr Kennwort nicht haben, können Sie es mit den folgenden Schritten zurücksetzen_.

   ![1. Klicken Sie auf den in der Snowflake-URL angegebenen Link. Daraufhin werden Sie weitergeleitet](assets/data-account-5.png)

1. Klicken Sie nach der Anmeldung **[!UICONTROL oben]** der Seite auf „Arbeitsblätter“.

   ![1. Klicken Sie nach der Anmeldung oben im Bildschirm auf Arbeitsblätter](assets/data-account-6.png)

1. Die BIZIBLE_ROI_V3-Datenbankobjekte befinden sich auf der linken Bildschirmseite. Geben Sie Warehouse, Datenbank und Schema aus den Dropdown-Optionen oben im Abfragefenster ein. Es sollte nur eine Option für jeden geben. Jetzt können Sie Abfragen im Abfrage-Editor von Snowflake ausführen.

   ![1. Die BIZIBLEROIV3-Datenbankobjekte befinden sich auf der linken Seite des](assets/data-account-4.png)

## Ihr Passwort zurücksetzen {#reset-your-password}

[!DNL Marketo Measure] hat keinen Zugriff auf Ihr Snowflake-Anmeldekennwort. Wenn Sie Ihr Kennwort zurücksetzen müssen, klicken Sie auf der Informationsseite von Data Warehouse auf [!UICONTROL Kennwort zurücksetzen] und befolgen Sie die Anweisungen. Ein temporäres Kennwort wird sofort in der Benutzeroberfläche angezeigt. Bei der nächsten Data Warehouse-Anmeldung werden Sie aufgefordert, Ihr eigenes Passwort zu erstellen.

>[!NOTE]
>
>* Durch Zurücksetzen des Kennworts wird es für alle [!DNL Marketo Measure] Benutzer in Ihrer Organisation zurückgesetzt, nicht nur für die aktuell angemeldeten Benutzer.
>* Wir zeigen nur das temporäre Passwort in der Benutzeroberfläche an. Eine E-Mail wird nicht gesendet.

![Wir zeigen nur das temporäre Kennwort in der Benutzeroberfläche an. Eine E-Mail wird](assets/data-account-3.png)

![Wir zeigen nur das temporäre Kennwort in der Benutzeroberfläche an. Eine E-Mail wird](assets/data-account-1.png)

## Herstellen einer Verbindung zu Snowflake über Drittanbieter-Tools {#connecting-to-snowflake-via-third-party-tools}

Sie müssen einige Informationen eingeben, um Ihr Snowflake Data Warehouse mit einem Tool eines Drittanbieters zu verbinden.

>[!NOTE]
>
>Jedes Tool hat unterschiedliche Verbindungsanforderungen. Es wird empfohlen, die Dokumentation für das jeweilige Tool zu konsultieren, das verbunden werden soll.

* **URI** (immer erforderlich)
   * Dies ist der Domain-Name des Snowflake-Kontos. Sie ist in einem Abschnitt des Snowflake-Anmelde-Links enthalten.
* **Benutzername** (immer erforderlich)
   * Der Benutzername wird auf der Data Warehouse-Informationsseite in [!DNL Marketo Measure] aufgeführt.
* **Kennwort** (immer erforderlich)
   * Dies ist das Kennwort, das Sie beim ersten Anmelden bei Ihrem Snowflake-Konto festgelegt haben. Gehen Sie wie oben beschrieben vor, um Ihr Kennwort zurückzusetzen.
* **Datenbankname** (nicht immer erforderlich)
   * Die -Datenbank speichert die Daten in Snowflake. Es ist die Speicherressource. Der Datenbankname wird auf der Data Warehouse-Informationsseite in [!DNL Marketo Measure] aufgeführt.
* **Warehouse-Name** (nicht immer erforderlich)
   * Das Warehouse ist das, was Abfragen in Snowflake ausführt. Dies ist die berechnete Ressource. Der Warehouse-Name wird auf der Data Warehouse-Informationsseite in [!DNL Marketo Measure] aufgeführt.

  ![Das Warehouse führt Abfragen in Snowflake aus. Es ist der berechnete](assets/data-account-2.png)
