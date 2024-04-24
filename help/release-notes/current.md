---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure]
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: cbb2afd48c0e462768be0a7cfe56007ae285c492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 71%

---

# Versionshinweise 2024 {#release-notes-2024}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2024.

## Q2-Version {#q2-release}

<p>

**Einstellung von Marketo Measure-Funktionen als Reaktion auf die Einstellung von Drittanbieter-Cookies**

Als Reaktion auf wachsende Datenschutzbedenken werden Drittanbieter-Cookies schrittweise eingestellt. Die endgültige Einstellung erfolgt bis zur Frist von Google Chrome für das dritte Quartal 2024. Marketo Measure stellt bestimmte Funktionen ein, die von Drittanbieter-Cookies abhängig sind, insbesondere Domain-übergreifendes Tracking und Durchsichtszuordnung, was auf dem Impressions-Cookie „Google/DoubleClick“ basiert. Diese Änderung hat keine Auswirkungen auf andere Marketo Measure-Funktionen oder die Verwendung von Erstanbieter-Cookies. Nach dem Zeitplan von Google werden diese Funktionen voraussichtlich bis zum 1. Juni eingestellt, Die Daten, die vor diesem Datum erfasst werden, werden Kundinnen und Kunden allerdings weiterhin zur Verfügung stehen.

* [Anpassung an die Einstellung von Drittanbieter-Cookies in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure-Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Einführung in Phasen unserer erweiterten Fehlerhandhabung**

Wir führen eine schrittweise Einführung in die verbesserte Fehlerbehebung für Exportvorgänge ein, beginnend mit sofortigen In-App-Pulsbenachrichtigungen für Berechtigungsfehler und der Umstellung auf einen neuen Ansatz, bei dem Exportvorgänge zum Zeitpunkt des Fehlers angehalten werden. Diese Änderung zielt darauf ab, die Datenintegrität und -sichtbarkeit zu verbessern und sicherzustellen, dass unsere Benutzerinnen und Benutzer reibungslosere und zuverlässigere Datenverwaltungsprozesse nutzen können. Um einen reibungslosen Übergang und eine minimale Unterbrechung Ihrer Vorgänge sicherzustellen, implementieren wir diese Änderungen in zwei Phasen:

* Sofortige Verfügbarkeit von Pulsbenachrichtigungen: Sie erhalten In-App-Pulsbenachrichtigungen zu Berechtigungsfehlern bei Exportvorgängen. Dies unterbricht Ihre Exporte nicht und hilft Ihnen, mehr über die Fehler zu erfahren, ohne Ihre aktuellen Vorgänge zu beeinträchtigen.
* Implementierung der Einstellung von Aufträgen am 25. April: **POSTPONED** - Nach Prüfung des Feedbacks von Marketo Measure-Benutzern haben wir beschlossen, die Implementierung der Aussetzung von Exportvorgängen an einem Fehlerpunkt zu verschieben, der ursprünglich für den 25. April geplant war. Wir erkennen an, dass die Einstellung von Arbeitsplätzen möglicherweise nicht der effektivste Ansatz ist. Wir sind entschlossen, eine bessere Lösung zu finden, die die Datenintegrität aufrecht erhält und Störungen minimiert. Wir werden daran festhalten, Änderungen an unserem aktuellen System vorzunehmen, bis wir eine Lösung sicherstellen können, die besser auf die Bedürfnisse unserer Benutzer abgestimmt ist.

_Warum das wichtig ist_

Verbesserte Datenintegrität und Zukunftssicherheit für Ihre Integration: Wir stoppen den Vorgang beim ersten Anzeichen von Problemen, um Datenverlust zu vermeiden und Genauigkeit zu gewährleisten. Dies ermöglicht eine schnelle Problembehebung, was die Qualität des Datenexports und die Systemzuverlässigkeit verbessert.

Sofortige Sichtbarkeit: Die Einführung von Pulsbenachrichtigungen ermöglicht eine umgehende Reaktion auf Berechtigungsfehler, wodurch mögliche Auswirkungen auf Vorgänge verhindert werden.

_Unterstützung des Übergangs_

Um Ihnen bei der Anpassung an diese Änderung zu helfen, [haben wir eine Dokumentation erstellt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}, die klare Fehlerbeschreibungen und umfassende Schritten zur Fehlerbehebung bietet.

<br>

**Erforderliches Handeln für die LinkedIn-Integration**

LinkedIn hat kürzlich eine aktualisierte Version seiner Lead Sync-API veröffentlicht. Bitte authentifizieren Sie die LinkedIn-Verbindung in Ihrer Marketo Measure-Instanz bis zum 20. Mai erneut, um Unterbrechungen zu vermeiden.

