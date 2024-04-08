---
description: Aktuelle Versionshinweise - [!DNL Marketo Measure]
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: db71cbfaf7deb5b724ac4babc38e835c04fadac7
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Versionshinweise 2024 {#release-notes-2024}

Unten finden Sie alle neuen und aktualisierten Funktionen für unsere Versionen von 2024.

## Q2-Version {#q2-release}

<p>

**Einstellung von Marketo Measure-Funktionen als Reaktion auf den Ausstieg aus Drittanbieter-Cookies**

Als Reaktion auf wachsende Datenschutzbedenken werden Drittanbieter-Cookies schrittweise abgeschafft, und die Frist von Google Chrome für das 3. Quartal 2024 signalisiert ihr Ende. Marketo Measure wird bestimmte Funktionen, die von Drittanbieter-Cookies abhängig sind, verwerfen, insbesondere Domain-übergreifendes Tracking und View-Through-Attribution, die auf dem Google/DoubleClick-Impression-Cookie basieren. Diese Änderung wirkt sich nicht auf andere Marketo Measure-Funktionen oder die Verwendung von Erstanbieter-Cookies aus. Nach dem Zeitplan von Google werden diese Funktionen voraussichtlich zum 1. Juni eingestellt, obwohl Kunden weiterhin auf Daten zugreifen können, die vor diesem Datum erfasst wurden.

* [Anpassen an die Einstellung von Drittanbieter-Cookies in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Cookies in Marketo Measure](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Schrittweiser Rollout unserer erweiterten Fehlerbehandlung**

Wir führen einen schrittweisen Rollout der verbesserten Fehlerbehandlung für Exportvorgänge ein, beginnend mit sofortigen In-App-Pulsbenachrichtigungen bei Berechtigungsfehlern und bis hin zu einem neuen Ansatz, bei dem Exportvorgänge am Fehlerpunkt anhalten. Diese Änderung zielt darauf ab, die Integrität und Sichtbarkeit der Daten zu verbessern und sicherzustellen, dass unsere Benutzer reibungslosere und zuverlässigere Datenverwaltungsprozesse erhalten. Um einen reibungslosen Übergang und minimale Betriebsunterbrechungen zu gewährleisten, implementieren wir diese Änderungen in zwei Phasen:

* Sofortige Verfügbarkeit von Pulse-Benachrichtigungen: Sie erhalten In-App-Pulse-Benachrichtigungen für Berechtigungsfehler während Exportvorgängen. Dadurch werden Ihre Exporte nicht unterbrochen, aber Sie erfahren mehr über die Fehler, ohne dass sich dies auf Ihre aktuellen Aufträge auswirkt.
* Implementierung der Vorgangspause am 25. April: Ab dem 25. April pausiert unser System den Vorgang, um sicherzustellen, dass keine Daten übersprungen werden, wenn während eines Exportvorgangs ein Berechtigungsfehler auftritt. Sie werden über alle Probleme benachrichtigt und sobald die Berechtigungen korrigiert wurden, wird der Exportvorgang von der Stelle, an der er abgebrochen wurde, nahtlos fortgesetzt.

_Warum das wichtig ist_

Verbesserte Datenintegrität und Zukunftssicherheit für Ihre Integration: Wir stoppen den Vorgang beim ersten Anzeichen von Problemen, um Datenverlust zu verhindern und die Genauigkeit sicherzustellen. Dies ermöglicht eine schnelle Problembehebung und verbessert die Qualität des Datenexports sowie die Zuverlässigkeit des Systems.

Sofortige Sichtbarkeit: Die Einführung von Pulse-Benachrichtigungen ermöglicht eine sofortige Reaktion auf Berechtigungsfehler und verhindert potenzielle Auswirkungen auf den Betrieb.

_Unterstützung des Übergangs_

Um Ihnen bei der Anpassung an diese Änderung zu helfen, [Wir haben Dokumentation erstellt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} mit klaren Fehlerbeschreibungen und umfassenden Schritten zur Fehlerbehebung.

<br>
**Aktion erforderlich für LinkedIn-Integration**

LinkedIn hat kürzlich eine aktualisierte Version seiner Lead Sync-API veröffentlicht. Bitte authentifizieren Sie die LinkedIn-Verbindung in Ihrer Marketo Measure-Instanz bis zum 20. Mai erneut, um Unterbrechungen zu vermeiden.

