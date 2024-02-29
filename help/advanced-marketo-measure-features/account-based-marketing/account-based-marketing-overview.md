---
unique-page-id: 18874730
description: Erfahren Sie mehr über Account-Based Marketing (ABM) und wie Adobe Marketo Measure Marketing- und Vertriebsteams dabei unterstützt, erfolgreiche ABM-Strategien auszuführen.
title: Kontobasiertes Marketing – Überblick
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 53%

---

# Kontobasiertes Marketing – Überblick {#account-based-marketing-overview}

In den folgenden Abschnitten erhalten Sie einen kurzen Überblick über ABM, die Komponenten der [!DNL Marketo Measure] ABM-Funktion und wie Sie sie zu Ihrem [!DNL Salesforce] Seitenlayout. Weitere Informationen zu ABM finden Sie unter Adobe. [ABM-Blog](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

Detaillierte Anweisungen zur Einrichtung von ABM in Ihrem [!DNL Salesforce] -Instanz, gehen Sie zu [Einrichten des ABM-Seitenlayouts in Salesforce](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Was ist ABM? {#what-is-abm}

Kontobasiertes Marketing (account-based marketing, ABM), ist eine Marketing-Strategie, bei der Sie Unternehmen und Konten als Ganzes ansprechen und an sie verkaufen, nicht nur an Einzelpersonen. [!DNL Marketo Measure] hilft Marketing- und Vertriebs-Teams bei der Ausführung erfolgreicher ABM-Strategien mit der Zuordnungsfunktion „Lead-zu-Konto“ und einer prädiktiven Interaktionsbewertung.

Damit unser Account-basiertes Marketing-Modell in Ihr CRM-System integriert werden kann, [!DNL Marketo Measure] muss die folgenden Kriterien erfüllen:

* Ihr CRM-System benötigt mindestens 25 Konten, für die mindestens eine geschlossene Won-Chance besteht, um die Gemeinsamkeiten eines &quot;erfolgreichen&quot;Kontos/-angebots für Ihr Unternehmen besser einschätzen zu können.
* Auf der anderen Seite der Medaille benötigt Ihr CRM mindestens 25 Konten ohne Geschlossene Won-Chancen (alle Ops müssen entweder in der Kategorie &quot;Offen&quot;oder in der Kategorie &quot;Geschlossener Verlust&quot;sein) - dies hilft uns, abzuschätzen, was ein Konto der niedrigeren Klasse in Ihrer Organisation macht.

>[!NOTE]
>
>Die oben genannten &quot;schlechten&quot;Konten müssen mindestens 12 Monate lang offen sein, ohne eine geschlossene Won-Opp zu akkumulieren; dies ist die grundlegende Richtlinie dafür, ob eine Opp für Modellzwecke veraltet ist.

## Lead-zu-Konto-Zuordnung {#lead-to-account-mapping}

Die Lead-zu-Konto-Zuordnung ist ein wesentlicher Bestandteil eines effektiven ABM-Ansatzes. Mit der Lead-zu-Konto-Zuordnung werden interessierte Personen (oder Leads), die mit Ihrer Marke interagieren, in demselben Unternehmenskonto zusammengefasst. Auf diese Weise können Sie Einzelpersonen desselben Unternehmens auf konsistente Weise ansprechen und an diese verkaufen. Es gibt keine zusätzlichen [!DNL Salesforce] -Konfiguration erforderlich, um von dieser Funktion profitieren zu können. Dies sind die fünf Übereinstimmungsmethoden für die Lead-zu-Konto-Zuordnung von [!DNL Marketo Measure]:

* Lead-Website zu Konto-Website
* Lead-E-Mail-Domain zu Konto-Website-Domain
* Lead-Firmenname zu Kontoname
* Lead-Firma zu Konto-Website-Domain
* Abgleichen der Domain der E-Mail-Adresse des Leads mit dem Konto über die E-Mail-Adresse des Kontakts

>[!NOTE]
>
>Jeder Lead versucht, in der oben genannten bevorzugten Reihenfolge der Methoden mit einem Konto abgeglichen zu werden. Sobald eine Übereinstimmung gefunden wurde, wird die Konto-ID sofort auf den Lead festgelegt und nicht mehr mit einer anderen Methode abgeglichen. Wenn der Lead bereits über eine gültige Konto-ID verfügt, wird der Lead übersprungen.

## Prädiktive Interaktionsbewertung {#predictive-engagement-score}

Die prädiktive Interaktionsbewertung (Predictive Engagement Score, PES) von [!DNL Marketo Measure] ist ein dynamischer Wert, der veranschaulicht, wie stark ein bestimmtes Konto mit Ihren Marketing-Maßnahmen interagiert. Diese Bewertung ist hilfreich, um Konten zielgerichtet ansprechen zu können. Sie ist ein wertvolles Instrument zur Identifizierung von Konten, um effektiver und effizienter zu agieren.

Es gibt viele Komponenten, die in den Algorithmus eingehen, mit dem die PES berechnet wird. Neuigkeit und Alter haben einen großen Einfluss auf die Bewertungsänderungen sowie auf die letzte Touchpoint-Aktivität oder Seitenansichten. Das Hinzufügen neuer Kontakte zu einem Konto wirkt sich ebenfalls auf den PES aus. Nachfolgend finden Sie eine Liste einiger PES-Eingaben:

* Gesamtzahl der Seitenansichten von dem Konto aus
* Durchschnittliche Anzahl der Seitenansichten
* Durchschnittliche Anzahl der Personen in dem Konto
* Alter der letzten Seitenansicht
* Durchschnittliches Alter der Seitenansichten
* Anzahl der Personen in dem Konto
* Spezifische, wichtige Seiten, und ob dort in den letzten 30/60/90 Tagen ein Besuch stattgefunden hat
* Ob das Konto ein geschlossenes verlorenes/gewonnenes Geschäft aufweist
* Wahrscheinlichkeit, dass geschlossen/geschlossen wird

>[!NOTE]
>
>Sie werden bei einigen Konten die Bewertung „Nicht zutreffend“ oder „-“ (Bindestrich) in Ihrer prädiktiven Interaktionsbewertung sehen.

_Eine Klasse von &quot;K/A&quot;bedeutet einfach, dass es nicht genügend Daten für dieses Konto gibt, damit das Modell eine wahre Klasse generieren kann - mit mehr Daten wird schließlich eine Klasse gegeben._
_Die Abstufung &quot;-&quot;(das Bindezeichen) bedeutet, dass dieses Konto aufgrund von Zeitbeschränkungen, gelegentlich fehlenden Prozessen usw. vom ABM-Prozess noch nicht verarbeitet werden muss. Wenn Sie glauben, dass ein Konto eine Bewertung haben sollte, die auf anderen ähnlichen Konten oder Zeitrahmen basiert, wenden Sie sich an und lassen Sie [!DNL Marketo Measure] kennen._

## Einrichten des ABM-Seiten-Layouts in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Um mit der Verwendung des PES zu beginnen, müssen Sie das Feld PES und die zugehörige Liste zu den entsprechenden Seitenlayouts in [!DNL Salesforce].

1. Navigieren Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Konten]** > **[!UICONTROL Seiten-Layout]**. Wählen Sie dann das Seitenlayout aus, das Sie bearbeiten möchten.
1. Navigieren Sie zu [!UICONTROL Felder] und verschieben Sie das Feld „Prädiktive Interaktionsbewertung“ in den Abschnitt „Kontoinformationen“.

   ![](assets/1.png)

1. Navigieren Sie schließlich zu [!UICONTROL Zugehörige Listen] und verschieben Sie die zugehörige Liste für die Leads in Ihr Seiten-Layout.

   ![](assets/2.png)

1. Navigieren Sie dann zu **[!UICONTROL Setup]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Leads]** > **[!UICONTROL Seiten-Layout]** und wählen Sie die entsprechenden Seiten-Layouts aus, die Sie bearbeiten möchten.
1. Klicken Sie auf **[!UICONTROL Felder]** und fügen Sie das Feld [!UICONTROL Konto] dort hinzu, wo Sie es auf der Seite haben möchten.

   ![](assets/3.png)

Das war’s schon!

