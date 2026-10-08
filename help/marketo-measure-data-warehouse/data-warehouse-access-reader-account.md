---
description: Data Warehouse-Zugriff - Reader-Konto - Produktdokumentation
title: Data Warehouse-Zugriff – Reader-Konto
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
TQID: 'https://experienceleague.adobe.com/3ZD-17UlkoJpMExA-ZdV-coGFa0DSeZMW0gjFZodlMM'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: 09cd1bee-ffcc-509c-9a9a-ca8384eac8e8
    internal-label: Data Warehouse
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 2%
---
# Data Warehouse-Zugriff – Reader-Konto {#data-warehouse-access-reader-account}

## Snowflake-Zugriffs-Link {#snowflake-access-link}

Um auf Ihr Snowflake Data Warehouse zuzugreifen, müssen Sie zur spezifischen URL für Ihr Snowflake-Konto navigieren. Sie können diesen Zugriffs-Link finden, indem Sie sich bei [!DNL Marketo Measure] anmelden und die folgenden Schritte ausführen, um zur Informationsseite von Data Warehouse zu navigieren.

1. Klicken Sie in [!DNL Marketo Measure] oben auf der Seite auf **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]**.

   ![](assets/data-warehouse-access-reader-account-1.png)

1. Klicken Sie im Menü links unter Sicherheit auf **[!UICONTROL Data Warehouse]**.

   ![](assets/data-warehouse-access-reader-account-2.png)

1. Diese Seite enthält den Link zu Ihrem Snowflake Data Warehouse und Ihrem Benutzernamen.

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >Dies ist ein schreibgeschütztes Konto, das für Ihre Organisation verfügbar ist, nicht nur für einzelne Benutzer. Jeder Benutzer in Ihrem Unternehmen, der Zugriff auf [!DNL Marketo Measure] hat, kann dieses Konto verwenden, um sich beim Snowflake Data Warehouse-Leserkonto anzumelden.

1. Klicken Sie auf den in der Snowflake-URL angegebenen Link, um zur Snowflake-Anmeldeseite zu gelangen, auf der Sie Ihren Benutzernamen und Ihr Kennwort eingeben. _Wenn Sie Ihr Kennwort nicht haben, können Sie es mit den folgenden Schritten zurücksetzen_.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. Klicken Sie nach der Anmeldung **[!UICONTROL oben]** der Seite auf „Arbeitsblätter“.

   ![](assets/data-warehouse-access-reader-account-5.png)

1. Die BIZIBLE_ROI_V3-Datenbankobjekte befinden sich auf der linken Bildschirmseite. Geben Sie Warehouse, Datenbank und Schema aus den Dropdown-Optionen oben im Abfragefenster ein. Es sollte nur eine Option für jeden geben. Jetzt können Sie Abfragen im Abfrage-Editor von Snowflake ausführen.

   ![](assets/data-warehouse-access-reader-account-6.png)

## Ihr Passwort zurücksetzen {#reset-your-password}

[!DNL Marketo Measure] hat keinen Zugriff auf Ihr Snowflake-Anmeldekennwort. Wenn Sie Ihr Kennwort zurücksetzen müssen, klicken Sie auf der Informationsseite von Data Warehouse auf [!UICONTROL Kennwort zurücksetzen] und befolgen Sie die Anweisungen. Ein temporäres Kennwort wird sofort in der Benutzeroberfläche angezeigt. Bei der nächsten Data Warehouse-Anmeldung werden Sie aufgefordert, Ihr eigenes Passwort zu erstellen.

>[!NOTE]
>
>* Durch Zurücksetzen des Kennworts wird es für alle [!DNL Marketo Measure] Benutzer in Ihrer Organisation zurückgesetzt, nicht nur für die aktuell angemeldeten Benutzer.
>* Wir zeigen nur das temporäre Passwort in der Benutzeroberfläche an. Eine E-Mail wird nicht gesendet.

![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## Herstellen einer Verbindung zu Snowflake über Drittanbieter-Tools {#connecting-to-snowflake-via-third-party-tools}

Sie müssen einige Informationen eingeben, um Ihr Snowflake Data Warehouse mit einem Tool eines Drittanbieters zu verbinden.

>[!NOTE]
>
>Jedes Tool hat unterschiedliche Verbindungsanforderungen. Es wird empfohlen, die Dokumentation für das spezifische Tool zu konsultieren, das Sie verbinden möchten.

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

  ![](assets/data-warehouse-access-reader-account-9.png)
