---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure] – Produktdokumentation
title: Aktuelle Versionshinweise
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 22f8cedf401a28444026d7b63384ce3cbabe0305
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 44%

---

# Versionshinweise 2023 {#release-notes-2023}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2023.

## Q4-Version {#q4-release}

<p>

**Dashboard-Neugestaltung**

Allen Benutzern von Marketo Measure werden unsere neu gestalteten In-App-Dashboards angezeigt, die eine verbesserte Benutzerfreundlichkeit mit einem Mehrwert kombinieren. Wir führen auch neue Metriken ein, wie &quot;Realized ROI&quot;, die die typische Verzögerung zwischen Marketing-Investitionen und Käufen in B2B-Go-Märkten berücksichtigen.

Die Einführung der neuen vordefinierten Dashboards in Schüben ist für den Beginn der ersten Oktober-Woche und deren Abschluss vor Jahresende geplant. Diese neuen Dashboards werden automatisch in Ihren Instanzen angezeigt, zusammen mit produktinternen Informationen und Links zur Dokumentation.

* [Neues Discover Dashboard-Handbuch](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [Dashboard-Grundlagen](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [Dashboard &quot;Umsatzübersicht&quot;](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [Dashboard &quot;Zugewiesener Umsatz&quot;](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI-Dashboard](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Passport-Dashboard](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>Während die aktuellen Dashboards Mitte Januar 2024 eingestellt werden, können Sie bis dahin beide Versionen verwenden, um einen reibungslosen Übergang zu gewährleisten.

### Veraltete {#deprecations}

<p>

* **Feld &quot;custom_properties&quot;**

In unserem Data Warehouse dient das Feld &quot;custom_properties&quot;als Speicher für zusätzliche Datenpunkte, die nicht von unserem festen Schema abgedeckt werden. Im JSON-Format gespeichert, ist die Nutzung dieses Felds begrenzt und seine Integration mit SQL-Abfragen kann kompliziert sein und die Leistung beeinträchtigen. Angesichts dieser Faktoren haben wir beschlossen, dieses Feld abzuschaffen. Diese Änderung betrifft hauptsächlich die Datenverarbeitungsschicht in unserem Azure-Tabellenspeicher und die in unser Data Warehouse exportierten Daten.

* **Dynamics Package-Zuordnung**

   * Um mit Dynamics verbunden zu bleiben, installieren Sie unsere neueste Paketversion v6.12. Alte Versionen `(<v6.12)` wird nicht mehr unterstützt. Diese Aktualisierung optimiert die Erstellung historischer Datensätze, um die Speicherbelegung zu reduzieren.

   * Die veraltete Methode von OAuth mit einem RefreshToken wird nicht mehr unterstützt. Siehe [diesem Handbuch](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} für die Aktualisierung Ihrer Anmeldedaten, um die Best Practices von Microsoft für die Verwendung von ClientSecret einzuhalten.

### Und als Nächstes? {#q4-whats-coming}

<p>

**Benutzerdefinierte In-App-Berichterstellung**

Marketo Measure-Kunden können erstmals ihre eigenen Berichte direkt in der App erstellen und speichern. Dies erfolgt im Anschluss an die Veröffentlichung der vordefinierten Dashboards Anfang 2024.

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
