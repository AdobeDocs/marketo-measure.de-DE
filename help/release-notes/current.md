---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure]
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 69b937f53f8ba3e449f7b13fb92d169dadc14c17
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 61%

---

# Versionshinweise 2024 {#release-notes-2024}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2024.

## Version Q3 {#q3-release}

<p>

**Erinnerung: Einstellung der Salesforce-Felder - 14. Juni**

Wie bereits im vergangenen Jahr angekündigt, werden wir unsere Exportaufträge an Lead-/Kontaktobjekte auslaufen lassen, um unsere Integration zu vereinfachen und die Notwendigkeit zu beseitigen, in Salesforce-Standardobjekte zu exportieren. Sie können dieselben Daten von Ihren Touchpoint-Objekten abrufen, indem Sie die folgenden Schritte ausführen [hier dokumentiert](/help/release-notes/previous-releases/2023.md#deprecations). Wir werden auch die Dokumentation zum Erstellen von Workflows teilen, um diese Daten zum Lead-/Kontaktobjekt hinzuzufügen. Die Einstellung wird am 14. Juni 2024 wirksam.

Diese Änderung bringt zwei wesentliche Vorteile:

* **Geringere Salesforce-API-Kosten**: Kunden können damit rechnen, dass sie ihre Salesforce-API-Kosten um etwa 10 % senken.
* **Optimierte Integration**: Die höchste Anzahl von Fehlern in unseren Exportvorgängen hängt mit diesen Prozessen zusammen. Durch deren Entfernung wird unsere Integration erheblich optimiert.

**Dashboard &quot;Zugewiesene Möglichkeiten&quot;**

Wir freuen uns, die neue [Dashboard &quot;Zugewiesene Möglichkeiten&quot;](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md), mit dem Sie einen umfassenden Überblick darüber erhalten, wie Ihre Marketingbemühungen sowohl zu neuen als auch ausgereiften Pipeline-Chancen beitragen. Dieses Dashboard bietet Ihnen die Möglichkeit, Details zu allen offenen und geschlossenen Möglichkeiten, die Ihren Strategien zugeordnet werden können, mit der Flexibilität, nach Opportunity zu filtern. Es bietet Einblicke, welche Kanäle, Unterkanäle oder Kampagnen in Bezug auf die zugewiesene Opportunitätsmenge am besten platziert werden, und zeigt die insgesamt zugewiesene Opportunity-Menge zusammen mit der Anzahl der zugewiesenen offenen und geschlossenen Gelegenheiten an.

**Marketo Engage-Cookie-Synchronisation für Marketo Measure Ultimate**

Marketo Engage-Cookie-Synchronisation ist jetzt für Marketo Measure Ultimate verfügbar. So verwenden Sie diese Funktion:

1. Bearbeiten Sie auf der Seite &quot;AEP-Schemas&quot;das Schema &quot;B2B-Person&quot;und fügen Sie die Feldergruppe &quot;Marketo Engage-Persönlichkeitsdetails&quot;hinzu.
1. Mappen Sie bei der Aufnahme der Daten in MMU das Feld Cookie-ID aus der Feldergruppe dem Feld Cookies aus Marketo Engage.

<p>

## Q2-Version {#q2-release}

<p>

**Einstellung von Marketo Measure-Funktionen als Reaktion auf die Einstellung von Drittanbieter-Cookies**

Als Reaktion auf wachsende Datenschutzbedenken werden Drittanbieter-Cookies schrittweise eingestellt. Die endgültige Einstellung erfolgt bis zur Frist von Google Chrome für das dritte Quartal 2024. Marketo Measure stellt bestimmte Funktionen ein, die von Drittanbieter-Cookies abhängig sind, insbesondere Domain-übergreifendes Tracking und Durchsichtszuordnung, was auf dem Impressions-Cookie „Google/DoubleClick“ basiert. Diese Änderung hat keine Auswirkungen auf andere Marketo Measure-Funktionen oder die Verwendung von Erstanbieter-Cookies. Nach dem Zeitplan von Google werden diese Funktionen voraussichtlich bis zum 1. Juni eingestellt, Die Daten, die vor diesem Datum erfasst werden, werden Kundinnen und Kunden allerdings weiterhin zur Verfügung stehen.

* [Anpassung an die Einstellung von Drittanbieter-Cookies in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure-Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Einführung in Phasen unserer erweiterten Fehlerhandhabung**

Wir führen phasenweise eine verbesserte Fehlerhandhabung für Exportvorgänge ein, beginnend mit sofortigen In-App-Pulsbenachrichtigungen für Berechtigungsfehler. Außerdem stellen wir auf einen neuen Ansatz um, bei dem Exportvorgänge an der Fehlerstelle pausiert werden. Diese Änderung zielt darauf ab, die Datenintegrität und -sichtbarkeit zu verbessern und sicherzustellen, dass unsere Benutzerinnen und Benutzer reibungslosere und zuverlässigere Datenverwaltungsprozesse nutzen können. Um einen reibungslosen Übergang und eine minimale Unterbrechung Ihrer Vorgänge sicherzustellen, implementieren wir diese Änderungen in zwei Phasen:

* Sofortige Verfügbarkeit von Pulsbenachrichtigungen: Sie erhalten In-App-Pulsbenachrichtigungen zu Berechtigungsfehlern bei Exportvorgängen. Dies unterbricht Ihre Exporte nicht und hilft Ihnen, mehr über die Fehler zu erfahren, ohne Ihre aktuellen Vorgänge zu beeinträchtigen.
* Implementierung der Vorgangspausierung am 25. April: **VERSCHOBEN** – Unter Berücksichtigung des Feedbacks von Marketo Measure-Benutzenden haben wir beschlossen, die ursprünglich für den 25. April geplante Implementierung der Pausierung von Exportvorgängen an der Fehlerstelle zu verschieben. Wir verstehen, dass das Anhalten von Vorgängen möglicherweise nicht der effektivste Ansatz ist. Wir arbeiten daran, eine bessere Lösung zu finden, bei der die Datenintegrität gewahrt bleibt und Störungen minimiert werden. Wir werden keine Änderungen an unserem aktuellen System vornehmen, bis wir eine Lösung gefunden haben, die besser auf die Bedürfnisse unserer Benutzenden abgestimmt ist.

_Warum das wichtig ist_

Verbesserte Datenintegrität und Zukunftssicherheit für Ihre Integration: Wir stoppen den Vorgang beim ersten Anzeichen von Problemen, um Datenverlust zu vermeiden und Genauigkeit zu gewährleisten. Dies ermöglicht eine schnelle Problembehebung, was die Qualität des Datenexports und die Systemzuverlässigkeit verbessert.

Sofortige Sichtbarkeit: Die Einführung von Pulsbenachrichtigungen ermöglicht eine umgehende Reaktion auf Berechtigungsfehler, wodurch mögliche Auswirkungen auf Vorgänge verhindert werden.

_Unterstützung des Übergangs_

Um Ihnen bei der Anpassung an diese Änderung zu helfen, [haben wir eine Dokumentation erstellt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}, die klare Fehlerbeschreibungen und umfassende Schritten zur Fehlerbehebung bietet.

<br>

**Erforderliches Handeln für die LinkedIn-Integration**

LinkedIn hat kürzlich eine aktualisierte Version seiner Lead Sync-API veröffentlicht. Bitte authentifizieren Sie die LinkedIn-Verbindung in Ihrer Marketo Measure-Instanz bis zum 20. Mai erneut, um Unterbrechungen zu vermeiden.

