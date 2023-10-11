---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure] – Produktdokumentation
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: dc4fda07004398207fb5067eb42ecd9e8ffe8624
workflow-type: ht
source-wordcount: '536'
ht-degree: 100%

---

# Versionshinweise 2023 {#release-notes-2023}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2023.

## Q4-Version {#q4-release}

<p>

**Entdecken Sie das umgestaltete Dashboard**

Allen Benutzenden von Marketo Measure werden unsere neu gestalteten In-App-Dashboards angezeigt, die eine verbesserte Benutzerfreundlichkeit mit einem Mehrwert kombinieren. Wir führen auch neue Metriken ein, wie „Erzielter ROI“, die die typische Verzögerung zwischen Marketing-Investitionen und Käufen in B2B-Go-to-Märkten berücksichtigen.

Die Einführung der neuen vordefinierten Dashboards erfolgt schrittweise ab der erste Oktoberwoche und wird vor Jahresende abgeschlossen sein. Diese neuen Dashboards werden automatisch in Ihren Instanzen angezeigt, zusammen mit produktinternen Informationen und Links zur Dokumentation.

* [Neues Handbuch zum Entdecken von Dashboards](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [Entdecken Sie die Grundlagen von Dashboards](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [Dashboard „Umsatzübersicht“](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [Dashboard „Zugewiesener Umsatz“](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI-Dashboard](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Passport-Dashboard](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>Während die aktuellen Dashboards Mitte Januar 2024 eingestellt werden, können Sie bis dahin beide Versionen verwenden, um einen reibungslosen Übergang zu gewährleisten.

### Abschaffungen {#deprecations}

<p>

* **Feld „custom_properties“**

In unserem Data Warehouse dient das Feld „custom_properties“ als Speicher für zusätzliche Datenpunkte, die nicht von unserem festen Schema abgedeckt werden. Aufgrund seines JSON-Formats kann dieses Feld nur eingeschränkt genutzt werden und lässt sich nur schwer in SQL-Anfragen integrieren, was die Leistung beeinträchtigt. Angesichts dieser Faktoren haben wir beschlossen, dieses Feld abzuschaffen. Diese Änderung betrifft hauptsächlich die Datenverarbeitungsschicht in unserem Azure-Tabellenspeicher und die in unser Data Warehouse exportierten Daten.

* **Zugehöriges Dynamics-Paket**

   * Um mit Dynamics verbunden zu bleiben, müssen Sie das neueste Paket (v6.12) installieren. Ältere Versionen `(<v6.12)` werden nicht länger unterstützt. Diese Aktualisierung optimiert die Erstellung historischer Einträge, um die Speicherbelegung zu reduzieren.

   * Die veraltete OAuth-Methode mit einem Aktualisierungs-Token wird nicht mehr unterstützt. In [dieser Anleitung](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} finden Sie Informationen zur Aktualisierung Ihrer Anmeldeinformationen entsprechend der Best Practices von Microsoft zur Verwendung von ClientSecret.

### Und als Nächstes? {#q4-whats-coming}

<p>

**Benutzerdefinierte In-App-Berichterstellung**

Marketo Measure-Kundinnen und -Kunden können erstmals ihre eigenen Berichte direkt in der App erstellen und speichern. Dies erfolgt im Anschluss an die Veröffentlichung der vordefinierten Dashboards Anfang 2024.

<br>

## Q2-Version {#q2-release}

<p>

* **Salesforce-Paketkonsolidierung**

Wir führen alle Salesforce-Pakete zu einem einzigen, umfassenden Paket zusammen, um ein besseres Anwendererlebnis und eine vereinfachte Nutzung zu ermöglichen. Die V1-, V2_EXT- und Reporting-Pakete werden im nächsten Quartal eingestellt. Das neue Paket kombiniert alle vorherigen Funktionen und sorgt so für ein effizienteres Tracking und tiefere Kundenerkenntnisse.

Kundinnen und Kunden, die bereits das V2-Paket installiert haben, müssen es auf die neue konsolidierte Version aktualisieren.

Wir haben zwei neue Felder hinzugefügt, um Ihre Berichtsfunktionen zu erweitern:

* form_name: Dieses Feld ist jetzt in BT-/BAT-Objekten verfügbar und ermöglicht Benutzenden das Erstellen von Berichten anhand von Formularnamen.
* user_touchpoint_id: Mit diesem Feld können Berichte mit Touchpoint-Zählungen für eindeutige Benutzende erstellt werden.

[Dieser Artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} enthält Anleitungen zum Erstellen von Berichten und Dashboards aus den älteren Reporting-Paketen.

* **Aktualisierungen von Salesforce-API-Versionen**

Alle Salesforce-API-Versionen von Apex-Klassen, einschließlich der Klasse UserActivityContext, werden auf unterstützte Versionen aktualisiert. (31.0 bis 57.0).

* **Installation des neuen Pakets**

Den Link zur Installation des neuen konsolidierten Pakets [ finden Sie hier](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### Und als Nächstes? {#q2-whats-coming}

<p>

**Änderungen beim IP-Adressspeicher**

Aus Datenschutzgründen werden wir keine IP-Adressen mehr in unserem System speichern. Wir werden die Geolokation der IP-Adresse weiterhin identifizieren und speichern, aber das Format wird sich ändern (z. B. von „Vereinigte Staaten“ zu „US“).
