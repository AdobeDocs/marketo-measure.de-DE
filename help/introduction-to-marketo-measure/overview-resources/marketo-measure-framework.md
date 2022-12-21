---
unique-page-id: 18874570
description: Marketo Measurement Framework - Marketo-Maßnahme - Produktdokumentation
title: Marketo Measurement Framework
exl-id: fa6de27c-cdd2-4fd9-ac35-7286fe2752d8
source-git-commit: 7eb5ef616e3ae77d53056496f9a1b301ce59d6ee
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Marketo Measurement Framework {#marketo-measure-framework}

Erfahren Sie mehr über die vier Hauptkomponenten des Marketo Measurement-Frameworks. Marketo Measurement nutzt diese Anwendungen zum Tracking, Organisieren und Verwalten von Daten sowie zur Bereitstellung von Berichtsfunktionen. Die vier Bestandteile des Marketo-Maßnahmenrahmens sind:

* JavaScript von Marketo Measurement
* CRM-Integrationen
* Anwendungen/Systeme von Drittanbietern
* Marketo Measurement Application

## Marketo Measure JavaScript {#marketo-measure-javascript}

Das Marketo Measure JavaScript verfolgt alle Online-Marketing-Interaktionen, auch Touchpoints genannt, die Interessenten/Leads mit Ihrem Unternehmen haben. Es handelt sich um ein benutzerdefiniertes Skript, das vor dem schließenden `</head>` -Tags auf jeder Seite Ihrer Website.

`<script type="text/javascript" src="//[cdn.bizible.com/scripts/bizible.js](http://cdn.bizible.com/scripts/bizible.js)" async=""></script>`

>[!NOTE]
>
>Anweisungen zum Hinzufügen des Marketo Measurement JS finden Sie unter [Hier klicken](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md).

Das JS von Marketo Measurement erfasst Daten von Webbesuchen (einschließlich anonymer Webbesuche), allgemeiner Traffic-/Seitennavigation, Inhaltsdownloads und Formularübermittlungen. Diese Daten werden in Ihr CRM-System übertragen und jede Marketing-Interaktion wird als Touchpoint angezeigt.

## CRM-Integrationen {#crm-integrations}

Marketo Measurement kann in CRMs integriert werden, um alle Daten zu speichern und zu organisieren, die von Marketo Measurement JS erfasst werden. Derzeit verfügt Marketo Measurement über API-Integrationen mit zwei CRMs:

![](assets/1-2.png)

Durch das Aufrufen von Marketo Measure -Daten in Ihrem CRM-System können Sie die detaillierten Informationen zu jedem Touchpoint anzeigen und Berichte generieren, um die Leistung Ihrer Kanäle zu verstehen.

## Drittanbieteranwendungen {#third-party-applications}

Die meisten Marketing-Experten sind für ihre Marketing-Maßnahmen auf einige verschiedene Anwendungen angewiesen. Zusätzlich zu Salesforce und MS Dynamics ist Marketo Measure in 13 Anwendungen von Drittanbietern integriert (siehe unten).

![](assets/2-1.png)

Wenn Sie Marketingbemühungen mit den oben genannten Anwendungen ausführen, können Sie diese Konten mit Ihrem Marketo Measurement-Konto verknüpfen. Dies ermöglicht das einfache Tracking und die Übertragung von Daten an Ihr Marketo Measurement-Konto.

## Marketo Measurement Application {#marketo-measure-application}

Die Marketo Measurement-Anwendung wird verwendet, um Ihre Attributionsdaten anzuzeigen und darüber zu berichten, Kontoeinstellungen zu konfigurieren und Kontoinformationen zu aktualisieren. Die Hauptmenüelemente der Marketo Measurement App sind:

**Kontokonfiguration**

Hier können Sie die allgemeinen Informationen Ihres Unternehmens aktualisieren und auf das Marketo Measure JavaScript zugreifen.

**Einstellungen**

In diesem Menüpunkt können Sie Ihre Zuordnungs- und Kanalzuordnungseinstellungen konfigurieren, Integrationen mit CRMs und Drittanbieteranwendungen verwalten, Marketo Measure-Kontobenutzer anzeigen/hinzufügen und Rechnungsinformationen aktualisieren.

**Marketing-ROI-Dashboard**

Im Menüelement Marketing-ROI-Dashboard können Sie Ihre Daten anhand der Kanalleistung, -aktivität und -kosten visualisieren.
