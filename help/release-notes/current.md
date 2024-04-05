---
description: Aktuelle Versionshinweise - [!DNL Marketo Measure]
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 81ce4ead229e461eeb9e6e3b1e951108b627a4e8
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Versionshinweise 2024 {#release-notes-2024}

Nachfolgend finden Sie alle neuen und aktualisierten Funktionen für unsere Versionen 2024.

## Q2-Version {#q2-release}

<p>

**Einstellung von Marketo Measure-Funktionen als Reaktion auf die Einstellung von Drittanbieter-Cookies**

Als Reaktion auf die wachsenden Datenschutzbedenken werden Drittanbieter-Cookies schrittweise eingestellt, wobei der Termin für Google Chrome vom 3. Quartal 2024 anzeigt, dass sie beendet werden. Marketo Measure stellt bestimmte Funktionen ein, die von Drittanbieter-Cookies abhängig sind, insbesondere domänenübergreifendes Tracking und Durchsichtszuordnung, die auf dem Impressions-Cookie Google/DoubleClick basieren. Diese Änderung hat keine Auswirkungen auf andere Marketo Measure-Funktionen oder die Verwendung von Erstanbieter-Cookies. Nach dem Zeitplan von Google werden diese Funktionen voraussichtlich ab dem 1. Juni eingestellt, doch stehen die vor diesem Datum erfassten Daten für Kunden weiterhin zur Verfügung.

* [Anpassen an die Einstellung von Drittanbieter-Cookies in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Cookies in Marketo Measure](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Schrittweise Einführung unseres erweiterten Umgang mit Fehlern**

Wir führen eine schrittweise Einführung in die verbesserte Fehlerbehebung für Exportaufträge ein, beginnend mit sofortigen In-App-Pulsbenachrichtigungen für Berechtigungsfehler und der Umstellung am 25. April auf einen neuen Ansatz, bei dem Exportaufträge zum Fehlerzeitpunkt ausgesetzt werden. Diese Änderung zielt darauf ab, die Datenintegrität und -sichtbarkeit zu verbessern und sicherzustellen, dass unsere Benutzer reibungslosere und zuverlässigere Datenverwaltungsprozesse nutzen können. Um einen reibungslosen Übergang und eine minimale Unterbrechung Ihrer Vorgänge sicherzustellen, implementieren wir diese Änderungen in zwei Phasen:

* Sofortige Verfügbarkeit von Pulse-Benachrichtigungen: Sie erhalten In-App-Pulsbenachrichtigungen, um bei Exportvorgängen Berechtigungsfehler zu erhalten. Dies unterbricht Ihre Exporte nicht, hilft Ihnen jedoch, mehr über die Fehler zu erfahren, ohne Ihre aktuellen Aufträge zu beeinträchtigen.
* Implementierung von Job Pausing am 25. April: Ab dem 25. April wird der Auftrag angehalten, um sicherzustellen, dass keine Daten übersprungen werden, wenn unser System während eines Exportvorgangs auf einen Berechtigungsfehler stößt. Sie werden über alle Probleme benachrichtigt. Sobald die Berechtigungen korrigiert wurden, wird der Exportauftrag nahtlos an der Stelle fortgesetzt, an der er abgebrochen wurde.

_Warum das wichtig ist_

Verbesserte Datenintegrität und künftige Testing Ihrer Integration: Wir stoppen den Vorgang beim ersten Anzeichen von Problemen, um Datenverlust zu vermeiden und Genauigkeit zu gewährleisten. Dies ermöglicht eine schnelle Problembehebung, die Verbesserung der Datenexportqualität und der Systemzuverlässigkeit.

Sofortige Sichtbarkeit: Die Einführung von Pulsbenachrichtigungen ermöglicht eine umgehende Reaktion auf Berechtigungsfehler, wodurch mögliche Auswirkungen auf Vorgänge verhindert werden.

_Unterstützung des Übergangs_

Um Ihnen bei der Anpassung an diese Änderung zu helfen, [Wir haben eine Dokumentation erstellt.](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} mit klaren Fehlerbeschreibungen und umfassenden Schritten zur Fehlerbehebung.

**Für die LinkedIn-Integration erforderliche Aktion**

LinkedIn hat kürzlich eine aktualisierte Version der Lead Sync-API veröffentlicht. Bitte authentifizieren Sie die LinkedIn-Verbindung in Ihrer Marketo Measure-Instanz bis zum 20. Mai erneut, um Unterbrechungen zu vermeiden.

