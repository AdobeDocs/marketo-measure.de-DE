---
unique-page-id: 18874730
description: Kontobasierte Marketing-Übersicht - [!DNL Marketo Measure] - Produktdokumentation
title: Kontobasiertes Marketing – Überblick
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 1%

---

# Kontobasiertes Marketing – Überblick {#account-based-marketing-overview}

Nachfolgend finden Sie eine kurze Übersicht über ABM, die Komponenten der [!DNL Marketo Measure] ABM-Funktion und wie Sie sie zu Ihrem [!DNL Salesforce] Seitenlayout. Weitere Informationen zu ABM finden Sie unter [diese Seite](https://www.marketo.com/account-based-marketing/){target="_blank"}.

So navigieren Sie direkt zu den Anweisungen zum Einrichten von ABM in Ihrem [!DNL Salesforce] Instanz, bitte [Klicken Sie hier](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Was ist ABM? {#what-is-abm}

Account-basiertes Marketing, ABM, ist eine Marketingstrategie, bei der Sie Unternehmen und Konten als Ganzes ansprechen und verkaufen, nicht nur als Einzelpersonen. [!DNL Marketo Measure] hilft Marketing- und Verkaufsteams bei der Ausführung erfolgreicher ABM-Strategien mit der Zuordnungsfunktion &quot;Lead-zu-Konto&quot;und der Prädiktiven Interaktionsbewertung.

Damit unser Account-basiertes Marketing-Modell in Ihr CRM-System integriert werden kann, [!DNL Marketo Measure] muss die folgenden Kriterien erfüllen:

* Ihr CRM-System benötigt mindestens 25 Konten, für die mindestens eine geschlossene Won-Chance besteht, sodass wir die Gemeinsamkeiten eines &quot;erfolgreichen&quot;Kontos/Ihrer Chancen für Ihr Unternehmen besser abschätzen können.
* Auf der anderen Seite der Medaille benötigt Ihr CRM mindestens 25 Konten ohne Geschlossene Won-Chancen (alle Ops müssen entweder in der Kategorie &quot;Offen&quot;oder in der Kategorie &quot;Geschlossener Verlust&quot;aufgeführt sein - dies hilft uns, abzuschätzen, was in Ihrer Organisation zu einem Konto der niedrigeren Klasse führt.

>[!NOTE]
>
>Die oben genannten &quot;schlechten&quot;Konten müssen mindestens 12 Monate lang offen sein, ohne eine geschlossene Won-Opp zu akkumulieren. Das ist unsere Grundrichtlinie dafür, ob ein Opp für die Zwecke des Modells veraltet ist oder nicht.

## Zuordnung von Lead zu Konto {#lead-to-account-mapping}

Die Zuordnung von Lead-zu-Konto ist ein wesentlicher Bestandteil eines effektiven ABM-Ansatzes. Mit der Zuordnung von Interessenten zu Konten werden Interessenten oder Leads in demselben Unternehmenskonto zusammengefasst, in dem sie mit Ihrer Marke interagieren. Auf diese Weise können Sie Einzelpersonen desselben Unternehmens auf konsistente Weise ansprechen und verkaufen. Es gibt keine zusätzlichen [!DNL Salesforce] -Konfiguration erforderlich, damit diese Funktion in Anspruch genommen werden kann. Die [!DNL Marketo Measure] Führen Sie zur Kontozuordnung von fünf verschiedenen Übereinstimmungsmethoden:

* Lead-Website zur Konto-Website
* Lead-E-Mail-Domäne zur Konto-Website-Domäne
* Lead-Firmenname zum Kontonamen
* Lead-Unternehmen zur Konto-Website-Domäne
* Abgleichen der Domain der E-Mail-Adresse des Leads mit dem Konto über die E-Mail-Adresse des Kontakts

>[!NOTE]
>
>Jeder Lead wird versucht, in der oben genannten bevorzugten Reihenfolge der Methoden mit einem Konto abgeglichen zu werden. Sobald eine Übereinstimmung gefunden wurde, wird die AccountId sofort auf dem Lead festgelegt und nicht mit einer anderen Methode abgeglichen. Wenn der Lead bereits über eine gültige AccountId verfügt, wird der Lead übersprungen.

## Prädiktive Interaktionsbewertung {#predictive-engagement-score}

Die [!DNL Marketo Measure] Die prädiktive Interaktionsbewertung (PES) ist ein dynamischer Wert, der veranschaulicht, wie stark ein bestimmtes Konto mit Ihren Marketing-Maßnahmen interagiert. Diese Punktzahl ist hilfreich, um Konten zielgerichtet zu segmentieren. Es ist ein wertvolles Instrument zur Identifizierung von Konten, um effektiver und effizienter zu agieren.

Es gibt viele Komponenten, die in den Algorithmus eingehen, der die SPE berechnet. Neuigkeit und Alter haben großen Einfluss auf die Bewertungsänderungen sowie auf die letzte Touchpoint-Aktivität oder Seitenansichten. Das Hinzufügen neuer Kontakte zu einem Konto wirkt sich auch auf PES aus. Nachfolgend finden Sie eine Liste einiger PES-Eingaben:

* Gesamtzahl der Seitenansichten aus dem Konto
* Durchschnittliche Anzahl der Seitenansichten
* Durchschnittliche Anzahl von Personen auf dem Konto
* Alter der letzten Seitenansicht
* Durchschnittliches Alter der Seitenansichten
* Anzahl der Personen auf dem Konto
* Spezifische wichtige Seiten und falls in den letzten 30/60/90 Tagen ein Besuch stattgefunden hat
* Wenn das Konto einen geschlossenen verlorenen/geweckten Deal aufweist
* Wie wahrscheinlich wird es geschlossen verloren/gewonnen

>[!NOTE]
>
>Sie können bei einigen Konten eine Bewertung von &quot;K/A&quot;oder &quot;-&quot;(das Bindestrich-Symbol) in Ihrer Prädiktiven Interaktionsbewertung feststellen.

_Eine Klasse von &quot;K/A&quot; bedeutet einfach, dass wir noch nicht über ausreichende Daten zu diesem Konto verfügen, damit unser Modell eine wahre Klasse generieren kann - mit mehr Daten, wird schließlich eine Bewertung gegeben._
_Der Wert &quot;-&quot; (das Bindezeichen) bedeutet, dass dieses Konto aufgrund von Zeitbeschränkungen, gelegentlich fehlenden Prozessen usw. noch nicht von unserem ABM-Prozess verarbeitet werden muss. Wenn Sie der Meinung sind, dass ein Konto eine Bewertung haben sollte, die auf ähnlichen Konten oder Zeitrahmen basiert, wenden Sie sich bitte an und lassen Sie [!DNL Marketo Measure] kennen._

## Einrichten des ABM-Seitenlayouts in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Um mit der Verwendung des PES zu beginnen, müssen Sie einfach das Feld PES und die zugehörige Liste zu den entsprechenden Seitenlayouts in [!DNL Salesforce].

1. Navigieren Sie zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Konten]** > **[!UICONTROL Seitenlayout]**. Wählen Sie dann das Seitenlayout aus, das Sie bearbeiten möchten.
1. Navigieren Sie zu [!UICONTROL Felder] und verschieben Sie das Feld &quot;Prädiktive Interaktionsbewertung&quot;in Ihren Abschnitt &quot;Kontoinformationen&quot;.

   ![](assets/1.png)

1. Navigieren Sie schließlich zu [!UICONTROL Verwandte Listen] und verschieben Sie die &quot;Leads&quot;-Liste in Ihr Seitenlayout.

   ![](assets/2.png)

1. Navigieren Sie dann zu **[!UICONTROL Einrichtung]** > **[!UICONTROL Anpassen]** > **[!UICONTROL Leads]** > **[!UICONTROL Seitenlayout]** und wählen Sie die entsprechenden Seitenlayouts aus, die Sie bearbeiten möchten.
1. Klicks **[!UICONTROL Felder]** und fügen Sie [!UICONTROL Konto] -Feld, in dem Sie sehen, dass es auf der Seite passt.

   ![](assets/3.png)

Das war’s schon!

