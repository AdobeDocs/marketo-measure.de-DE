---
description: Datenschutzanfragen - [!DNL Marketo Measure] - Produktdokumentation
title: Datenschutzanfragen
exl-id: 883e475f-9868-412a-b505-230556f38484
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Datenschutzanfragen {#privacy-requests}

Dieses Dokument bietet einen Überblick über die Verwaltung von Datenschutzanfragen, die Sie an senden können [!DNL Marketo Measure] durch [!DNL Privacy Service] Benutzeroberfläche und **[!DNL Privacy Service]API**.

Sie können einzelne Anfragen zum Zugriff auf und zum Löschen von Verbraucherdaten aus senden [!DNL Marketo Measure] auf zwei Arten:

* Durch die [[!DNL Privacy Service] Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target="_blank"}.
* Durch die **[!DNL Privacy Service]API**. Weitere Informationen finden Sie in der Dokumentation [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target="_blank"} and the API reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

Die [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} unterstützt zwei Arten von Anforderungen: Datenzugriff und Datenlöschung.

Im Folgenden wird beschrieben, wie Sie Zugriffs- und Löschanfragen erstellen können.

## Erforderliche Einrichtung zum Senden von Anforderungen an Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

So stellen Sie Anfragen zum Zugreifen auf und Löschen von Daten für [!DNL Marketo Measure]müssen Sie:

1. Identifizieren Sie Folgendes:

   a. Kennung der IMS-Organisation

   b. E-Mail-Adresse der Person, auf die Sie reagieren möchten

   Eine IMS-Organisations-ID ist eine 24-stellige alphanumerische Zeichenfolge, die an @AdobeOrg angehängt wird. Wenn Ihr Marketing-Team oder Ihr Systemadministrator des internen Adobe die IMS-Organisations-ID Ihres Unternehmens nicht kennen, wenden Sie sich an die Kundenunterstützung von Adobe unter gdprsupport@adobe.com. Sie benötigen die IMS-Organisations-ID, um Anfragen an die Datenschutz-API zu senden.

1. In [!DNL Privacy Service], können Sie Zugriffs- und Löschanfragen an senden [!DNL Marketo Measure]und überprüfen Sie den Status vorhandener Anforderungen.

## Erforderliche Feldwerte in [!DNL Marketo Measure] JSON-Anforderungen {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContexts&quot;:

* &quot;namespace&quot;: **imsOrgID**
* &quot;Wert&quot;: `<Your IMS Org ID Value>`

&quot;Benutzer&quot;:

* &quot;action&quot;: entweder [!UICONTROL access] oder löschen
* &quot;userIDs&quot;:
   * &quot;namespace&quot;: email
   * &quot;type&quot;: standard
   * &quot;Wert&quot;: `<Data Subject's Email Address>`

&quot;include&quot;:

* **marketoMeasure** (das Adobe-Produkt, das für die Anfrage gilt)

&quot;Verordnung&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra** oder **nzpa_nzl** (die Datenschutzverordnung, die für die Anfrage gilt)

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
