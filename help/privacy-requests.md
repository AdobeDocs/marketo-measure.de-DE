---
description: Anleitung zu Datenschutzanfragen für Marketo Measure-Benutzende
title: Datenschutzanfragen
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 24%

---


# Datenschutzanfragen {#privacy-requests}

Dieses Dokument bietet einen Überblick über die Verwaltung einzelner Datenschutzanfragen, die Sie über die [!DNL Marketo Measure]-Benutzeroberfläche und die [!DNL Privacy Service]-API an **[!DNL Privacy Service]senden**.

Sie können einzelne Anfragen zum Zugreifen auf und Löschen von Verbraucherdaten aus [!DNL Marketo Measure] auf zwei Arten senden:

* Über die [[!DNL Privacy Service] Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=de){target="_blank"}.
* Über die **[!DNL Privacy Service]-API**. Siehe die Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=de){target="_blank"} und die API-Referenz [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

Die [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de){target="_blank"} unterstützt zwei Arten von Anfragen: Datenzugriff und Datenlöschung.

Sehen wir uns an, wie Sie Zugriffs- und Löschanfragen erstellen können.

## Erforderliche Einrichtung zum Senden von Anfragen an Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

Um Anfragen zum Zugreifen auf und Löschen von Daten für [!DNL Marketo Measure] zu stellen, ist Folgendes erforderlich:

1. Sie benötigen:

   a. Kennung der IMS-Organisation

   b. E-Mail-Adresse der Person, die Sie bearbeiten möchten

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

```json
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

```json
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

```json
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

```json
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
