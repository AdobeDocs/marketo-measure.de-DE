---
description: Aktuelle Versionshinweise – [!DNL Marketo Measure]
title: Aktuelle Versionshinweise
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 9ea72d0e1cf0f754cc8fe844944b93705fb2b12f
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 94%

---

# Versionshinweise 2024 {#release-notes-2024}

Nachstehend finden Sie Informationen zu allen neuen und aktualisierten Funktionen unserer Versionen aus dem Jahr 2024.

## Q4-Version {#q4-release}

### Neues Verhalten für Sitzungskanal-Übertragung

Der Kanal aus der vorherigen Sitzung wird nun übernommen, wenn eine neue Sitzung nach 30 Minuten Inaktivität innerhalb von sieben Tagen beginnt, und dies gilt nur für Direktbesuche (keine Referrer oder internen Referrer). Nach sieben Tagen Inaktivität wird die Sitzung standardmäßig auf „Direkt/Sonstige“ eingestellt. Nicht-direkte Kanäle werden durch Daten aus früheren Sitzungen nicht überschrieben.

Darüber hinaus werden Sitzungen mit Social-Media-Anmeldung (Google, Microsoft oder Apple) jetzt zu einer fortlaufenden Sitzung zusammengeführt, um ein reibungsloseres Erlebnis zu gewährleisten. Ohne Aktivierung dieser Übertragung könnten Social-Media-Anmeldungen aufgrund von Unterschieden bei externen Referrern separate Sitzungen erstellen.

Bei neuer Kundschaft ist die Übertragung des Sitzungskanals jetzt das Standardverhalten. Bestehende Kunden können dies aktivieren, indem sie den Umschalter Sitzungskanal-Übertragung unter Einstellungen > Everytouch-Attribution aktivieren. Nach der Aktivierung kann diese Einstellung nicht mehr rückgängig gemacht werden.

Dokumentation: [Definition von Marketo Measure-Web-Sitzungen](https://experienceleague.adobe.com/de/docs/marketo-measure/using/marketo-measure-tracking/setting-up-tracking/definition-of-marketo-measure-web-sessions){target="_blank"}

### Keyword-ROI-Dashboard

Das neue Keyword-ROI-Dashboard bietet detaillierte Erkenntnisse zur Leistung von Paid-Search-Kampagnen und bietet einen umfassenden Überblick über die Kosten auf Keyword-Ebene, den zugeordneten Umsatz sowie die generierten Leads und Opportunities. Mit diesem Dashboard können Sie den ROI der einzelnen Suchbegriffe für Google Adwords, LinkedIn, Bing Ads usw. auswerten.

Dokumentation: [Keyword-ROI-Dashboard](https://experienceleague.adobe.com/de/docs/marketo-measure/using/marketo-measure-discover-ui/dashboards/keyword-roi-dashboard){target="_blank"}

### Erweiterte Segmentregeln

Sie können jetzt Segmente über die Felder „Kampagne“ und „Kampagnenmitglied“, zusätzlich zu den Feldern „Touchpoint“ und „Kontakt“, erstellen. Dank dieser Erweiterung können Sie Ihre Daten in Discover noch effizienter analysieren und aufschlüsseln.

![Erweiterte Segmentregeln](assets/mm-q4-release-1.png)

### Aktualisierung: Fehlerbehandlungseinstellung für CRM-Exporte

Wir haben auf Ihr Feedback bezüglich des Anhaltens von Aufträgen gehört und führen eine neue Funktion in der Benutzeroberfläche ein. Ab heute können Sie festlegen, ob Exportaufträge beim Auftreten von Fehlern angehalten werden sollen. Verwenden Sie den neuen Umschalter in **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein**. Dieser Schalter ist standardmäßig aktiviert, um die Datenintegrität und -transparenz zu verbessern. Wenn Sie diese Funktion jedoch lieber nicht verwenden möchten, können Sie sie in der Benutzeroberfläche deaktivieren, und die Exportaufträge werden fortgesetzt. Diese Aktualisierung soll die Zuverlässigkeit Ihrer Daten-Management-Prozesse erhöhen und Ihnen gleichzeitig mehr Kontrolle geben.

#### Wichtige Daten und gestaffelter Rollout

1. **Sofortige Verfügbarkeit des Umschalters:** Der Umschalter ist jetzt in der Benutzeroberfläche aktiv und standardmäßig aktiviert, um zu verhindern, dass Daten bei Exportaufträgen übersprungen werden. Wenn Sie es vorziehen, dass Exportaufträge trotz aufgetretener Fehler weiterhin ausgeführt werden, deaktivieren Sie den Umschalter.

1. **Das Anhalten von Aufträgen wird am 1. Oktober aktiviert:** Ab dem 1. Oktober 2024 wird, wenn der Umschalter aktiv ist und während eines Exportauftrags ein Fehler auf Eintragsebene auftritt, der Auftrag angehalten, damit keine Daten verloren gehen. Diese Fehler sind in der Regel auf fehlende Berechtigungen, falsch angewendete benutzerdefinierte Validierungsregeln oder Probleme in Workflows/Triggern zurückzuführen. Sie erhalten Benachrichtigungen zu dem Problem, und sobald es behoben wurde, wird der Exportauftrag vom Zeitpunkt der Unterbrechung aus fortgesetzt. Wenn Sie das Anhalten des Auftrags abwählen, erhalten Sie weiterhin Benachrichtigungen zu Problemen, und wenn diese behoben sind, werden die übersprungenen Einträge automatisch erneut exportiert.

#### Warum das wichtig ist

* **Verbesserte Datenintegrität und Zukunftssicherheit für Ihre Integration:** Wir stoppen den Auftrag beim ersten Anzeichen von Problemen, um Datenverlust zu vermeiden und Genauigkeit zu gewährleisten. Dies ermöglicht eine schnelle Fehlerbehebung, was zu einer verbesserten Datenexportqualität und einer allgemein höheren Systemzuverlässigkeit führt.

* **Sofortige Transparenz:** Durch Pulsbenachrichtigungen erhalten Sie zeitnahe Warnungen bei Berechtigungsfehlern, die eine umgehende Reaktion ermöglichen und potenzielle Auswirkungen auf Ihre Vorgänge minimieren.

#### Unterstützung des Übergangs

Um Ihnen bei der Anpassung an diese Änderung zu helfen, haben wir eine Dokumentation zu der neuen Funktion erstellt, die klare Fehlerbeschreibungen mit umfassenden Schritten zur Fehlerbehebung bietet.

* Neue Dokumentation: [Fehlerbehandlungseinstellung für CRM-Exporte](/help/configuration-and-setup/marketo-measure-and-salesforce/crm-error-handling.md)
* [Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md)

## Q3-Version {#q3-release}

<p>

### Erinnerung: Einstellung von Salesforce-Feldern - 14. Juni

Wie letztes Jahr angekündigt, werden wir unsere [Exportaufträge an Lead-/Kontaktobjekte schrittweise auslaufen lassen](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"}, um unsere Integration zu vereinfachen und den Export in Salesforce-Standardobjekte unnötig zu machen. Sie können dieselben Daten von Ihren Touchpoint-Objekten abrufen, indem Sie die folgenden [hier dokumentierten](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"} Schritte ausführen. Wir werden auch die Dokumentation zum Erstellen von Workflows teilen, um diese Daten zum Lead-/Kontaktobjekt hinzuzufügen. Die Einstellung wird am 14. Juni 2024 wirksam.

Diese Änderung bringt zwei wesentliche Vorteile:

* **Geringere Salesforce-API-Kosten**: Kundinnen und Kunden können damit rechnen, dass ihre Salesforce-API-Kosten um etwa 10 % sinken.
* **Optimierte Integration**: Die meisten Fehler in unseren Exportaufträgen hängen mit diesen Prozessen zusammen. Durch deren Entfernung wird unsere Integration erheblich optimiert.

### Dashboard „Zugewiesene Opportunity“

Wir freuen uns, das neue [Dashboard „Zugewiesene Opportunity“](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"} einzuführen, mit dem Sie einen umfassenden Überblick darüber erhalten, wie Ihre Marketing-Maßnahmen sowohl zu neuen als auch ausgereiften Pipeline-Opportunitys beitragen. Mit diesem Dashboard können Sie die Details jeder offenen und abgeschlossenen Opportunity, die Ihren Strategien zuzuordnen ist, einsehen und flexibel nach dem Schritt der Opportunity filtern. Es bietet Erkenntnisse, welche Kanäle, Unterkanäle oder Kampagnen in Bezug auf die zugewiesene Opportunity-Anzahl am besten platziert werden, und zeigt die insgesamt zugewiesene Opportunity-Anzahl zusammen mit der Anzahl der zugewiesenen offenen und geschlossenen Opportunitys an.

### Marketo Engage-Cookie-Synchronisation für Marketo Measure Ultimate

Die Synchronisation der Marketo Engage-Cookies ist jetzt für Marketo Measure Ultimate verfügbar. So verwenden Sie diese Funktion:

1. Bearbeiten Sie auf der Seite „AEP-Schemata“ das Schema „B2B-Person“ und fügen Sie die Feldergruppe „Marketo Engage-Personendetails“ hinzu.
1. Wenn Sie die Daten in MMU einlesen, ordnen Sie das Feld „Cookie-ID“ aus der Feldgruppe dem Feld „Cookies“ aus Marketo Engage zu.

### Boomerang-Stadien für Tier 2-Kunden aktiviert

Die bisher nur für Kundschaft der Stufe 3 verfügbare Funktion „Boomerang-Phasen“ steht ab dem 13. Juni 2024 auch für Kundschaft der Stufe 2 zur Verfügung. Weitere Informationen zu dieser Funktion finden Sie in der folgenden Dokumentation.

* [Boomerang-Phasen und Touchpoints](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [Einrichten von Boomerang-Phasen](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [Szenarien zu Boomerang-Phasen](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## Q2-Version {#q2-release}

<p>

### Einstellung von Marketo Measure-Funktionen als Reaktion auf den schrittweisen Ausstieg aus Drittanbieter-Cookies

Als Reaktion auf wachsende Datenschutzbedenken werden Drittanbieter-Cookies schrittweise eingestellt. Die endgültige Einstellung erfolgt bis zur Frist von Google Chrome für das dritte Quartal 2024. Marketo Measure stellt bestimmte Funktionen ein, die von Drittanbieter-Cookies abhängig sind, insbesondere Domain-übergreifendes Tracking und Durchsichtszuordnung, was auf dem Impressions-Cookie „Google/DoubleClick“ basiert. Diese Änderung hat keine Auswirkungen auf andere Marketo Measure-Funktionen oder die Verwendung von Erstanbieter-Cookies. Nach dem Zeitplan von Google werden diese Funktionen voraussichtlich bis zum 1. Juni eingestellt, Die Daten, die vor diesem Datum erfasst werden, werden Kundinnen und Kunden allerdings weiterhin zur Verfügung stehen.

* [Anpassung an die Einstellung von Drittanbieter-Cookies in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure-Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

### Schrittweiser Rollout unserer erweiterten Fehlerbehandlung

Wir führen phasenweise eine verbesserte Fehlerhandhabung für Exportvorgänge ein, beginnend mit sofortigen In-App-Pulsbenachrichtigungen für Berechtigungsfehler. Außerdem stellen wir auf einen neuen Ansatz um, bei dem Exportvorgänge an der Fehlerstelle pausiert werden. Diese Änderung zielt darauf ab, die Datenintegrität und -sichtbarkeit zu verbessern und sicherzustellen, dass unsere Benutzerinnen und Benutzer reibungslosere und zuverlässigere Datenverwaltungsprozesse nutzen können. Um einen reibungslosen Übergang und eine minimale Unterbrechung Ihrer Vorgänge sicherzustellen, implementieren wir diese Änderungen in zwei Phasen:

* Sofortige Verfügbarkeit von Pulsbenachrichtigungen: Sie erhalten In-App-Pulsbenachrichtigungen zu Berechtigungsfehlern bei Exportvorgängen. Dies unterbricht Ihre Exporte nicht und hilft Ihnen, mehr über die Fehler zu erfahren, ohne Ihre aktuellen Vorgänge zu beeinträchtigen.
* Implementierung der Vorgangspausierung am 25. April: **VERSCHOBEN** – Unter Berücksichtigung des Feedbacks von Marketo Measure-Benutzenden haben wir beschlossen, die ursprünglich für den 25. April geplante Implementierung der Pausierung von Exportvorgängen an der Fehlerstelle zu verschieben. Wir verstehen, dass das Anhalten von Vorgängen möglicherweise nicht der effektivste Ansatz ist. Wir arbeiten daran, eine bessere Lösung zu finden, bei der die Datenintegrität gewahrt bleibt und Störungen minimiert werden. Wir werden keine Änderungen an unserem aktuellen System vornehmen, bis wir eine Lösung gefunden haben, die besser auf die Bedürfnisse unserer Benutzenden abgestimmt ist.

_Warum das wichtig ist_

Verbesserte Datenintegrität und Zukunftssicherheit für Ihre Integration: Wir stoppen den Vorgang beim ersten Anzeichen von Problemen, um Datenverlust zu vermeiden und Genauigkeit zu gewährleisten. Dies ermöglicht eine schnelle Problembehebung, was die Qualität des Datenexports und die Systemzuverlässigkeit verbessert.

Sofortige Sichtbarkeit: Die Einführung von Pulsbenachrichtigungen ermöglicht eine umgehende Reaktion auf Berechtigungsfehler, wodurch mögliche Auswirkungen auf Vorgänge verhindert werden.

_Unterstützung des Übergangs_

Um Ihnen bei der Anpassung an diese Änderung zu helfen, [haben wir eine Dokumentation erstellt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}, die klare Fehlerbeschreibungen und umfassende Schritten zur Fehlerbehebung bietet.

<br>

### Für die LinkedIn-Integration erforderliche Aktion

LinkedIn hat kürzlich eine aktualisierte Version seiner Lead Sync-API veröffentlicht. Bitte authentifizieren Sie die LinkedIn-Verbindung in Ihrer Marketo Measure-Instanz bis zum 20. Mai erneut, um Unterbrechungen zu vermeiden.
