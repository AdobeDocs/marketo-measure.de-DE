---
description: Datenschutzanfragen - [!DNL Marketo Measure]
title: Datenschutzanfragen
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
TQID: https://experienceleague.adobe.com/y6cWoJaRD7Tf1o4-aCY9MJdcLGt4RVF-ATuiFpAxyWI
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: fb43f4c1-87d9-4081-8df1-6fe7e6e5cdc8
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 27%

---

# Datenschutzanfragen {#privacy-requests}

Dieses Dokument bietet einen Überblick über die Verwaltung einzelner Datenschutzanfragen, die Sie über die [!DNL Privacy Service]-Benutzeroberfläche und die **[!DNL Privacy Service]-API an [!DNL Marketo Measure] senden**.

Sie können einzelne Anfragen zum Zugreifen auf und Löschen von Verbraucherdaten aus [!DNL Marketo Measure] auf zwei Arten senden:

* Über die [[!DNL Privacy Service] Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=de){target="_blank"}.
* Über die **[!DNL Privacy Service]-API**. Siehe die Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=de){target="_blank"} und die API-Referenz [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

Die [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de){target="_blank"} unterstützt zwei Arten von Anfragen: Datenzugriff und Datenlöschung.

Sehen wir uns an, wie Sie Zugriffs- und Löschanfragen erstellen können.

## Erforderliche Einrichtung zum Senden von Anfragen an Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

Um Anfragen zum Zugreifen auf und Löschen von Daten für [!DNL Marketo Measure] zu stellen, ist Folgendes erforderlich:

1. Sie benötigen:

   a. Kennung der IMS-Organisation

   b. E-Mail-Adresse der Person, für die Sie eine Aktion durchführen möchten

   Eine IMS-Organisations-ID ist eine 24-stellige alphanumerische Zeichenfolge, die an @AdobeOrg angehängt wird. Wenn Ihr Marketing-Team oder Ihr interner Adobe-Systemadministrator die IMS-Organisations-ID Ihres Unternehmens nicht kennen, wenden Sie sich an die Adobe-Kundenunterstützung unter gdprsupport@adobe.com. Sie benötigen die IMS-Organisations-ID, um Anfragen an die Datenschutz-API zu senden.

1. In [!DNL Privacy Service] können Sie Zugriffs- und Löschanfragen an [!DNL Marketo Measure] senden und den Status vorhandener Anfragen überprüfen.

## Erforderliche Feldwerte in JSON-Anfragen für [!DNL Marketo Measure] {#required-field-values-in-marketo-measure-json-requests}

„companyContexts“:

* &quot;namespace&quot;: **imsOrgID**
* „value“: `<Your IMS Org ID Value>`

&quot;users&quot;:

* „Aktion“: Entweder [!UICONTROL Zugriff] oder Löschen
* „userIDs“:
   * „namespace“: E-Mail
   * „Typ“: Standard
   * „value“: `<Data Subject's Email Address>`

„Include“:

* **marketoMeasure** (das Adobe-Produkt, das für die Anfrage gilt)

„Verordnung“:

* **DSGVO**, **CCPA**, **PDPA**, **LGPD_BRA** oder **NZPA_NZL** (dies ist die Datenschutzverordnung, die für die Anfrage gilt)

## Beispiel 1: DSGVO-Löschanfrage {#gdpr-delete-request}

JSON-Anfrage

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

JSON-Antwort

```text
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## Beispiel 2: CCPA-Zugriffsanfrage {#ccpa-access-request}

JSON-Anfrage

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

JSON-Antwort

```text
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
