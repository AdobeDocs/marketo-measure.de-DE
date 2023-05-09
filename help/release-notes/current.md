---
description: Aktuelle Versionshinweise - [!DNL Marketo Measure] - Produktdokumentation
title: Aktuelle Versionshinweise
source-git-commit: 8e8ddd80d69102455fa678a32f31a9fe8319822c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Versionshinweise: 2023 {#release-notes-2023}

Unten finden Sie alle neuen und aktualisierten Funktionen für unsere Versionen 2023.

## Q2-Version {#q2-release}

<p>

**Salesforce-Paketkonsolidierung**

* Wir führen alle Salesforce-Pakete zu einem einzigen, umfassenden Paket zusammen, um ein besseres Benutzererlebnis und eine vereinfachte Nutzung zu ermöglichen. Die Pakete V1, V2_EXT und Reporting werden im nächsten Quartal eingestellt. Das neue Paket kombiniert alle vorherigen Funktionen und ermöglicht so ein effizienteres Tracking und tiefere Kundeneinblicke.
* Kunden, die bereits das V2-Paket installiert haben, müssen es auf die neue konsolidierte Version aktualisieren.
* Wir haben zwei neue Felder hinzugefügt, um Ihre Berichterstellungsfunktionen zu verbessern:
   * form_name: Dieses Feld ist jetzt in BT-/BAT-Objekten verfügbar und ermöglicht Benutzern das Erstellen von Berichten anhand von Formularnamen.
   * user_touchpoint_id: Mit diesem Feld können Benutzer Berichte mit Touchpoint-Zählungen für Unique User erstellen.
* [Dieser Artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} enthält Anleitungen zum Erstellen von Berichten und Dashboards aus den veralteten Reporting-Paketen.

**Aktualisierungen der Salesforce-API-Version**

* Alle Salesforce-API-Versionen von Apex-Klassen, einschließlich der UserActivityContext-Klasse, werden auf unterstützte Versionen aktualisiert. (31.0 bis 57.0)

**Neue Paketinstallation**

* Der neue konsolidierte Paketinstallationslink [finden Sie hier .](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### Was kommt? {#whats-coming}

<p>

**Änderungen beim IP-Adressenspeicher**

* Aus Datenschutzgründen werden wir keine IP-Adressen mehr in unserem System speichern. Wir werden den geografischen Standort der IP-Adresse weiterhin identifizieren und speichern, aber das Format wird sich ändern (z. B. &quot;USA&quot;in &quot;US&quot;).
