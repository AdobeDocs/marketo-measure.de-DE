---
unique-page-id: 18874558
description: Bomerang-Phasen und Touchpoints - [!DNL Marketo Measure] - Produktdokumentation
title: Boomerang-Phasen und Touchpoints
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 1%

---

# Boomerang-Phasen und Touchpoints {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Die Boomerang-Funktion ist nur für Tier-3-Kunden aktiviert. Wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer), um eine höhere Kontoebene anzufordern.

[!DNL Marketo Measure] hat unsere Boomerang Stage Funktion veröffentlicht! Die Bomerang-Staging-Funktion wurde entwickelt, um die Journey des Kunden für [!DNL Marketo Measure] Kunden mit langen Verkaufszyklen. Mit dieser Funktion können Marketingexperten Touchpoints für alle Staging-Transitionen erstellen, die in der Opportunity-Journey auftreten, z. B. wenn ein Kontakt-MQLs, dann zu SAL wechselt und dann zur MQL-Bühne zurückkehrt. Bei Kontakten, die &quot;erneut in die MQL-Bühne eintreten&quot;oder &quot;MQLs erneut eintreten&quot;, wird die MQL als Bomerang-Bühne betrachtet. Die Funktion &quot;Boomerang-Bühne&quot;funktioniert neben [!DNL Marketo Measure] Benutzerdefinierte Phasen.

## Funktion {#what-this-feature-does}

* Erstellt einen &quot;boomerang&quot;-Touchpoint für alle Phasenübergänge, die auf der Journey einer Opportunity auftreten
* Verfolgt wiederholte Übergänge zwischen benutzerdefinierten Phasen (z. B. wenn eine Kontakt-MQLs zu SAL wechselt und dann zur MQL-Bühne zurückkehrt)
* Hiermit können Sie angeben, wie viele und welche Transitionen der Phase Sie in die Option aufnehmen möchten (z. B. Die ersten 10 MQLs ODER die letzten 5 MQLs)
* Wenn Sie ein Benutzer des benutzerdefinierten Modells sind, können Sie die Attributionsgewichtung und die Prozentzurechnung bestimmen, die Sie jeder dieser Phasen zuweisen möchten (z. B. Zuordnungsgewichtung zum ersten oder letzten MQL-Vorkommen zuweisen oder die Zuordnungsgewichtung gleichmäßig auf alle Vorkommen verteilen)

>[!NOTE]
>
>[Anweisungen zum Einrichten von Boomerang-Phasen](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Wie Boomerang-Phasen und Touchpoints in Ihrem CRM aussehen {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Ohne Boomerang-Bühnen (das &quot;before&quot;) sehen Sie nur die neueste MQL oder den neuesten SQL-Touchpoint, der mit einem Lead-/Kontaktdatensatz verknüpft ist.

![](assets/1.png)

Bei Boomerang-Phasen und Touchpoints werden Touchpoints angezeigt, die für jede Schritttransition auftreten. Die Namenskonvention für diese Bomerang-Touchpoints lautet wie folgt:

**[Staging-Name]-00.**

Im folgenden Beispiel wird dies [!DNL Marketo Measure] -Konto hat MQL und SQL in ihre Bumerang-Bühnen aufgenommen und zwei Bomerang-Touchpoints pro Phase angezeigt.

![](assets/2.png)

**MQL-01** ist die erste MQL-Schritttransition.

Der numerische Wert in der Touchpoint-Position gibt die Reihenfolge an, in der die Phasenübergänge stattgefunden haben. Der letzte Bomerang-Touchpoint wird wie folgt gestempelt:

MQL-02 **(Letzte)**

## Änderung vorhandener Daten durch Bomerang-Phasen {#how-boomerang-stages-change-your-existing-data}

Boomerang-Phasen wirken sich darauf aus:

**Zuordnung nach Kanal**

* Seit [!DNL Boomerang Stages] mehr Touchpoints erstellen, wird sich dadurch die Verteilung der Attribution auf die Touchpoints ändern, die derzeit in Ihren Daten vorhanden sind. Dies kann dazu führen, dass sich die Umsatzwerte zwischen den Marketing-Kanälen ändern. Berücksichtigen Sie dies vor der Implementierung von [!DNL Boomerang stages]oder wenden Sie sich für weitere Informationen an Ihren Kundenbetreuer.

**Alle Berichte mit &quot;gleich&quot; [Touchpoint-Position]&quot;**

* In Boomerang-Bühnen werden neue Touchpoint-Positionen zu Ihren Daten eingeführt. [!DNL Marketo Measure] ändert das Format der Touchpoint-Position, um das Vorkommen der Bühne einzuschließen, z. B. &quot;MQL-01&quot;oder &quot;MQL-05 (Letzter)&quot;. Mithilfe dieses Beispiels wirken sich Boomerang Stages auf alle Berichte aus, die &quot;Touchpoint-Position ist gleich MQL&quot;verwenden. Um diese Berichte anzupassen, sollte der Filter stattdessen den Operator &quot;enthält&quot;verwenden.

## FAQs {#faq}

**Wie viele Bomerang-Bühnen kann ich in mein Attributionsmodell einbeziehen?**

Sie können bis zu 15 Etappen auswählen.

**F: Wie viele &quot;boomerang&quot; Touchpoints kann ich pro Bühne haben?**

Sie können bis zu 10 Bomerang-Touchpoints pro Bühne auswählen.

**F: Warum sind wir nur auf 10 Bumerangs pro Staging beschränkt?**

[!DNL Marketo Measure] muss die Anzahl der Phasen begrenzen, damit die Verarbeitungszeiten unter Kontrolle bleiben. Wenn Sie sich dafür entscheiden, alle 15 Bomerang-Phasen in Ihr Attributionsmodell und 10 Bomerang-Touchpoints pro Phase einzubeziehen, könnten Sie über mehr als 150 Touchpoints pro Lead-/Kontaktdatensatz verfügen.

**F: Ich habe Data Warehouse. Erhalte ich alle Daten oder gilt die Boomerang Stages-Obergrenze auch für mich?**

Die Obergrenze gilt für Data Warehousen und CRMs aufgrund der Verarbeitungsbeschränkungen, die [!DNL Marketo Measure] verfügt. Für die Data Warehouse gilt außerdem die Beschränkung von 10 Touchpoints pro Phase.

**F: Welchen Nutzen hat die Verwendung von Boomerang Stages mit benutzerdefinierter Modellierung?**

Verwenden [!UICONTROL Boomerang] In Phasen mit benutzerdefinierter Modellierung können Sie die Attributionsgewichtung zu [!UICONTROL Boomerang] Touchpoints, die diesen Phasen eine Umsatzgutschrift zuweisen.

Ohne benutzerdefinierte Modellierung, [!DNL Marketo Measure] erstellt Touchpoints für jede Bomerang- und Staging-Transition, weist diesen Touchpoints jedoch keine Zuordnungsgutschriften zu. Die einzigen Bomerang-Touchpoints, die Attributionszuschüsse erhalten, sind Touchpoints der Formularübermittlung. Ohne benutzerdefiniertes Modell [!DNL Boomerang] Touchpoints werden als identisch mit einem &quot;mittleren Touch&quot;betrachtet und erhalten dementsprechend eine Attribution.
