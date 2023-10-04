---
unique-page-id: 18874730
description: Kontobasiertes Marketing – Überblick – Produktdokumentation zu  [!DNL Marketo Measure]
title: Kontobasiertes Marketing – Überblick
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: ht
source-wordcount: '782'
ht-degree: 100%

---

# Kontobasiertes Marketing – Überblick {#account-based-marketing-overview}

Nachfolgend finden Sie einen kurzen Überblick über ABM und die Komponenten der ABM-Funktion von [!DNL Marketo Measure], und Sie erfahren, wie Sie sie zu Ihrem Seiten-Layout von [!DNL Salesforce] hinzufügen. Weitere Informationen zu ABM finden Sie auf [dieser Seite](https://www.marketo.com/account-based-marketing/){target="_blank"}.

Um direkt zu den Anweisungen zum Einrichten von ABM in Ihrer Instanz von [!DNL Salesforce] zu gelangen, [klicken Sie hier](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Was ist ABM? {#what-is-abm}

Kontobasiertes Marketing (account-based marketing, ABM), ist eine Marketing-Strategie, bei der Sie Unternehmen und Konten als Ganzes ansprechen und an sie verkaufen, nicht nur an Einzelpersonen. [!DNL Marketo Measure] hilft Marketing- und Vertriebs-Teams bei der Ausführung erfolgreicher ABM-Strategien mit der Zuordnungsfunktion „Lead-zu-Konto“ und einer prädiktiven Interaktionsbewertung.

Damit unser ABM-Modell in Ihr CRM-System integriert werden kann, muss [!DNL Marketo Measure] die folgenden Kriterien erfüllen:

* Ihr CRM-System benötigt mindestens 25 Konten, für die mindestens eine geschlossene, gewonnene Opportunity vorhanden ist, damit wir die Gemeinsamkeiten von „erfolgreichen“ Konten/Opportunitys für Ihr Unternehmen einschätzen können.
* Auf der anderen Seite muss Ihr CRM mindestens 25 Konten ohne geschlossene, gewonnene Opportunity haben (alle anderen Opportunitys müssen entweder in der Kategorie „Offen“ oder in der Kategorie „Geschlossen, verloren“ sein). Dies hilft uns einzuschätzen, was Konten von geringerer Qualität in Ihrem Unternehmen ausmacht.

>[!NOTE]
>
>Die oben genannten „schlechten“ Konten müssen mindestens 12 Monate lang offen sein, ohne dass sich eine geschlossene, gewonnene Opportunity angesammelt hat. Dies ist für die Zwecke des Modells unsere Grundrichtlinie dafür, ob eine Opportunity veraltet ist oder nicht.

## Lead-zu-Konto-Zuordnung {#lead-to-account-mapping}

Die Lead-zu-Konto-Zuordnung ist ein wesentlicher Bestandteil eines effektiven ABM-Ansatzes. Mit der Lead-zu-Konto-Zuordnung werden interessierte Personen (oder Leads), die mit Ihrer Marke interagieren, in demselben Unternehmenskonto zusammengefasst. Auf diese Weise können Sie Einzelpersonen desselben Unternehmens auf konsistente Weise ansprechen und an diese verkaufen. Es sind keine zusätzlichen Konfigurationen für [!DNL Salesforce] erforderlich, damit diese Funktion in Anspruch genommen werden kann. Dies sind die fünf Übereinstimmungsmethoden für die Lead-zu-Konto-Zuordnung von [!DNL Marketo Measure]:

* Lead-Website zu Konto-Website
* Lead-E-Mail-Domain zu Konto-Website-Domain
* Lead-Firmenname zu Kontoname
* Lead-Firma zu Konto-Website-Domain
* Abgleichen der Domain der E-Mail-Adresse des Leads mit dem Konto über die E-Mail-Adresse des Kontakts

>[!NOTE]
>
>Für jeden Lead wird in der oben genannten, bevorzugten Reihenfolge der Methoden versucht, ihn mit einem Konto abzugleichen. Sobald eine Übereinstimmung gefunden wurde, wird die Konto-ID sofort auf den Lead festgelegt und nicht mehr mit einer anderen Methode abgeglichen. Wenn der Lead bereits über eine gültige Konto-ID verfügt, wird der Lead übersprungen.

## Prädiktive Interaktionsbewertung {#predictive-engagement-score}

Die prädiktive Interaktionsbewertung (Predictive Engagement Score, PES) von [!DNL Marketo Measure] ist ein dynamischer Wert, der veranschaulicht, wie stark ein bestimmtes Konto mit Ihren Marketing-Maßnahmen interagiert. Diese Bewertung ist hilfreich, um Konten zielgerichtet ansprechen zu können. Sie ist ein wertvolles Instrument zur Identifizierung von Konten, um effektiver und effizienter zu agieren.

Es gibt viele Komponenten, die in den Algorithmus eingehen, mit dem die PES berechnet wird. Neuigkeit und Alter haben großen Einfluss auf die Bewertungsänderungen, neben der letzten Touchpoint-Aktivität oder Seitenansichten. Das Hinzufügen neuer Kontakte zu einem Konto wirkt sich ebenfalls auf den PES aus. Nachfolgend finden Sie eine Liste einiger PES-Eingaben:

* Gesamtzahl der Seitenansichten von dem Konto aus
* Durchschnittliche Anzahl der Seitenansichten
* Durchschnittliche Anzahl der Personen in dem Konto
* Alter der letzten Seitenansicht
* Durchschnittliches Alter der Seitenansichten
* Anzahl der Personen in dem Konto
* Spezifische, wichtige Seiten, und ob dort in den letzten 30/60/90 Tagen ein Besuch stattgefunden hat
* Ob das Konto ein geschlossenes verlorenes/gewonnenes Geschäft aufweist
* Wie wahrscheinlich ein Geschäft als verloren/gewonnen geschlossen wird

>[!NOTE]
>
>Sie werden bei einigen Konten die Bewertung „Nicht zutreffend“ oder „-“ (Bindestrich) in Ihrer prädiktiven Interaktionsbewertung sehen.

_Die Bewertung „Nicht zutreffend“ bedeutet einfach, dass wir noch nicht über ausreichende Daten zu diesem Konto verfügen, damit unser Modell eine echte Bewertung generieren kann – wenn mehr Daten verfügbar werden, wird schließlich eine Bewertung gegeben._
_Die Bewertung „-“ (Bindestrich) bedeutet, dass dieses Konto aufgrund von Zeitbeschränkungen, gelegentlich fehlenden Prozessen usw. noch nicht von unserem ABM-Prozess verarbeitet wurde. Wenn Sie auf der Grundlage anderer ähnlicher Konten oder Zeiträume der Meinung sind, dass ein solches Konto eine Bewertung haben sollte, teilen Sie dies bitte [!DNL Marketo Measure] mit._

## Einrichten des ABM-Seiten-Layouts in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Um mit der Verwendung der PES zu beginnen, müssen Sie einfach das Feld „PES“ und die zugehörige Liste zu den entsprechenden Seiten-Layouts in [!DNL Salesforce] hinzufügen.

1. Navigieren Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Konten]** > **[!UICONTROL Seiten-Layout]**. Wählen Sie dann das Seiten-Layout aus, das Sie bearbeiten möchten.
1. Navigieren Sie zu [!UICONTROL Felder] und verschieben Sie das Feld „Prädiktive Interaktionsbewertung“ in den Abschnitt „Kontoinformationen“.

   ![](assets/1.png)

1. Navigieren Sie schließlich zu [!UICONTROL Zugehörige Listen] und verschieben Sie die zugehörige Liste für die Leads in Ihr Seiten-Layout.

   ![](assets/2.png)

1. Navigieren Sie dann zu **[!UICONTROL Setup]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Leads]** > **[!UICONTROL Seiten-Layout]** und wählen Sie die entsprechenden Seiten-Layouts aus, die Sie bearbeiten möchten.
1. Klicken Sie auf **[!UICONTROL Felder]** und fügen Sie das Feld [!UICONTROL Konto] dort hinzu, wo Sie es auf der Seite haben möchten.

   ![](assets/3.png)

Das war’s schon!

