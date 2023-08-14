---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure] – Produktdokumentation
title: Aktuelle Versionshinweise
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '232'
ht-degree: 100%

---

# Versionshinweise 2023 {#release-notes-2023}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2023.

## Q2-Version {#q2-release}

<p>

**Salesforce-Paketkonsolidierung**

* Wir führen alle Salesforce-Pakete zu einem einzigen, umfassenden Paket zusammen, um ein besseres Anwendererlebnis und eine vereinfachte Nutzung zu ermöglichen. Die V1-, V2_EXT- und Reporting-Pakete werden im nächsten Quartal eingestellt. Das neue Paket kombiniert alle vorherigen Funktionen und sorgt so für ein effizienteres Tracking und tiefere Kundenerkenntnisse.
* Kundinnen und Kunden, die bereits das V2-Paket installiert haben, müssen es auf die neue konsolidierte Version aktualisieren.
* Wir haben zwei neue Felder hinzugefügt, um Ihre Berichtsfunktionen zu erweitern:
   * form_name: Dieses Feld ist jetzt in BT-/BAT-Objekten verfügbar und ermöglicht Benutzenden das Erstellen von Berichten anhand von Formularnamen.
   * user_touchpoint_id: Mit diesem Feld können Berichte mit Touchpoint-Zählungen für eindeutige Benutzende erstellt werden.
* [Dieser Artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} enthält Anleitungen zum Erstellen von Berichten und Dashboards aus den älteren Reporting-Paketen.

**Aktualisierungen von Salesforce-API-Versionen**

* Alle Salesforce-API-Versionen von Apex-Klassen, einschließlich der Klasse UserActivityContext, werden auf unterstützte Versionen aktualisiert. (31.0 bis 57.0).

**Installation des neuen Pakets**

* Den Link zur Installation des neuen konsolidierten Pakets [ finden Sie hier](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### Und als Nächstes? {#whats-coming}

<p>

**Änderungen beim IP-Adressspeicher**

* Aus Datenschutzgründen werden wir keine IP-Adressen mehr in unserem System speichern. Wir werden die Geolokation der IP-Adresse weiterhin identifizieren und speichern, aber das Format wird sich ändern (z. B. von „Vereinigte Staaten“ zu „US“).
