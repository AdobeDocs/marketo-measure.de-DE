---
unique-page-id: 18874716
description: Attributionszuordnungsmethode - [!DNL Marketo Measure] - Produktdokumentation
title: Attributionszuordnungsmethode
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Attributionszuordnungsmethode {#attribution-mapping-methodology}

Die Attributionszuordnungsmethode besteht darin, bestimmte Objekte in Ihrem CRM-System (Kontakte, Chancen, Konten) zu suchen, um Zuordnungs-Touchpoints in die zugehörige Chance zu erstellen. Mit anderen Worten, es ist das [!DNL Marketo Measure] Informationen dazu, welche Touchpoints basierend auf den Prozessen Ihres aktuellen CRM-Systems in das Attributionsmodell aufgenommen werden.

## Konto-ID-Zuordnung {#account-id-mapping}

Vorkonfiguriert, [!DNL Marketo Measure] stellt die Zuordnung der Konto-ID bereit. Das bedeutet: [!DNL Marketo Measure] betrachtet das Konto und dessen Marketing-Informationen zu Kontakten , um mit dieser Gelegenheit verbundene Attribution-Touchpoints zu erstellen. Im Folgenden finden Sie eine einfache Darstellung dieses Prozesses.

![](assets/1-1.png)

Beachten Sie bitte Folgendes: **nicht alle** Touchpoints von Ihren Kontakten werden als Attribution Touchpoints in die Chance geleitet. In der Timeline der Opportunity (d. h. das Erstkontakt-Datum - das geschlossene Datum) wird bestimmt, ob ein Touchpoint als Einflussnehmer auf die Opportunity gezählt wird. Wenn daher ein Touchpoint auf Kontakt A auftritt, nachdem die Gelegenheit geschlossen wurde/verloren wurde, [!DNL Marketo Measure] wird diesen Touchpoint nicht an die Gelegenheit weiterleiten. Dieses Timeline-Verfahren wird bei allen anderen Attributionsobjektzuordnungen angewendet.

Vorteile: Diese Attributionsmethode ist für die meisten Unternehmen sehr effektiv. Das Marketing-Team muss sich nicht darauf verlassen, dass das Vertriebsteam alle Kontakte einer bestimmten Gelegenheit zuordnet (was häufig ein Problem darstellt). Selbst wenn ein Vertriebsteam Kontaktrollen zuordnet, kann es zudem zu einer großen Anzahl von Interaktionen anderer Kontakte mit Marketingmaterialien kommen. Schließlich unterstützt diese Methode ABM-Strategien, die darauf abzielen, die Gesamtheit eines Kontos und nicht bestimmte Einflussnehmer zu beeinflussen.

Nachteile: Wenn es starke Marketing &amp; Sales-SLAs gibt, die definieren, wem welche gutgeschrieben werden soll, könnte diese Methode problematisch sein. Darüber hinaus können, wenn Benutzer keine Kontohierarchien verwenden, um innerhalb eines größeren Kontos (z. B. IBM) bestimmte Geschäftseinheiten zu definieren, für eine Geschäftseinheit spezifische Marketing-Interaktionen auf andere Geschäftsbereichsmöglichkeiten verteilt werden.

## Opportunity Contact Role Mapping {#opportunity-contact-role-mapping}

Während die meisten Kunden die Zuordnung der Konto-ID nutzen, [!DNL Marketo Measure] hat die Möglichkeit, innerhalb einer Gelegenheit nach den Kontaktrollen (mit der Gelegenheit verbundene Kontakte) zu suchen, um den Attributionsprozess aufzuschlüsseln. Das bedeutet: [!DNL Marketo Measure] Push-Marketing-Interaktionen, die mit den Kontaktrollen verknüpft sind, werden nur auf der Opportunity als &quot;Buyer Attribution Touchpoints&quot;übertragen. Nachfolgend finden Sie eine Darstellung dieses Prozesses.

![](assets/2-1.png)

Vorteile: Wenn Ihr Team über einen sehr gut definierten Prozess von Kontaktrollen verfügt, kann dieser Typ von Attribution Mapping für Sie ideal sein. Dies wird dazu beitragen, Vertrieb und Marketing ein wenig besser aufeinander abzustimmen, da alle verstehen würden, wie die Attribution aufgeschlüsselt wird. Dieser Prozess ist auch sehr hilfreich, wenn Unternehmen mehrere Geschäftsbereiche innerhalb eines großen Unternehmens ansprechen und gleichzeitig verschiedene Produkte verkaufen.

Nachteile: Wenn jedoch kein Prozess für die Kontaktrolle vorhanden ist, verliert das Marketing eine Menge Marketing-Daten und das Team erhält am Ende deutlich weniger Anerkennung für seine Marketing-Maßnahmen, die Chancen beeinflussen.

## Opportunity Primär Contact Role Mapping {#opportunity-primary-contact-role-mapping}

Neben der bloßen Betrachtung der Kontaktrollen für die Gelegenheit, [!DNL Marketo Measure] kann sich noch mehr darauf konzentrieren, nur die Primären Kontakte auf eine Chance zu betrachten. Mit diesem Setup sollten Sie [!DNL Marketo Measure] erfasst nur den Marketing-Touchpoint, der mit den primären Kontakten auf einer Gelegenheit verknüpft ist, und leitet diese Informationen in die Zuordnungsgeschichte dieser spezifischen Gelegenheit weiter. Siehe Abbildung unten.

![](assets/3.png)

Vorteile: Wenn Ihr Team nur daran interessiert ist, den Marketing-Einfluss auf Kontakte zu verstehen, die als &quot;primär&quot;für die Gelegenheit festgelegt sind, wird diese Art von Zuordnung am besten zum Team passen.

Nachteile: Dies ist sicherlich der am wenigsten genutzte Mapping-Prozess und kann den Marketing-Einfluss stark untergraben, der die Nadel bei einer Gelegenheit über andere Kontakte bewegt.
