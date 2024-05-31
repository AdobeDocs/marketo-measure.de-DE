---
unique-page-id: 18874558
description: Bomerang-Phasen und Touchpoints - [!DNL Marketo Measure]
title: Boomerang-Phasen und Touchpoints
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: ea113b02b910fbc894311200aff83286636d4b32
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---

# Boomerang-Phasen und Touchpoints {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>Die Boomerang-Funktion ist nur für Tier-2- und -3-Kunden aktiviert. Wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer), um eine höhere Kontoebene anzufordern.

[!DNL Marketo Measure] hat die Funktion Boomerang Stage veröffentlicht! Die Bomerang-Staging-Funktion wurde entwickelt, um die Journey des Kunden für [!DNL Marketo Measure] Kunden mit langen Verkaufszyklen. Mit dieser Funktion können Marketingexperten Touchpoints für alle Staging-Transitionen erstellen, die in der Journey &quot;Chancen&quot;auftreten, z. B. wenn ein Kontakt-MQLs erstellt, dann zu SAL wechselt und dann zur MQL-Bühne zurückkehrt. Wenn Kontakte &quot;in die MQL-Bühne zurückkehren&quot;oder &quot;MQLs erneut aufrufen&quot;, gilt die MQL als Bomerang-Bühne. Die Funktion &quot;Boomerang-Bühne&quot;funktioniert neben [!DNL Marketo Measure] Benutzerdefinierte Phasen.

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

Bei Bomerang-Phasen und Touchpoints werden Touchpoints angezeigt, die für jede Phasenübergang auftreten. Die Namenskonvention für diese Bomerang-Touchpoints lautet:

**[Staging-Name]-00.**

Im folgenden Beispiel wird dies [!DNL Marketo Measure] -Konto hat MQL und SQL in ihre Bumerang-Bühnen aufgenommen und zwei Bomerang-Touchpoints pro Phase angezeigt.

![](assets/2.png)

**MQL-01** ist die erste MQL-Schritttransition.

Der numerische Wert in der Touchpoint-Position gibt die Reihenfolge an, in der die Phasenübergänge aufgetreten sind. Der letzte Bomerang-Touchpoint wird wie folgt gestempelt:

MQL-02 **(Letzte)**

## Änderung vorhandener Daten durch Bomerang-Phasen {#how-boomerang-stages-change-your-existing-data}

Auswirkungen von Boomerang-Phasen:

**Zuordnung nach Kanal**

* Seit [!DNL Boomerang Stages] erstellt mehr Touchpoints, wodurch sich die Verteilung der Attribution auf die Touchpoints ändert, die derzeit in Ihren Daten vorhanden sind. Dies kann dazu führen, dass sich die Umsatzwerte zwischen den Marketing-Kanälen verlagern. Berücksichtigen Sie dies vor der Implementierung [!DNL Boomerang stages]oder wenden Sie sich für weitere Informationen an Ihren Kundenbetreuer.

**Alle Berichte mit &quot;gleich&quot; [Touchpoint-Position]&quot;**

* In Boomerang-Bühnen werden neue Touchpoint-Positionen zu Ihren Daten eingeführt. [!DNL Marketo Measure] ändert das Format der Touchpoint-Position, um das Vorkommen der Bühne einzuschließen, z. B. &quot;MQL-01&quot;oder &quot;MQL-05 (Letzter)&quot;. Unter Verwendung dieses Beispiels wirken sich Boomerang Stages auf alle Berichte aus, die &quot;Touchpoint-Position ist gleich MQL&quot;verwenden. Um diese Berichte anzupassen, sollte der Filter stattdessen den Operator &quot;enthält&quot;verwenden.

## FAQs {#faq}

**Wie viele Bomerang-Bühnen kann ich in mein Attributionsmodell einbeziehen?**

Sie können bis zu 15 Etappen auswählen.

**F: Wie viele &quot;boomerang&quot; Touchpoints kann ich pro Bühne haben?**

Sie können bis zu zehn Bomerang-Touchpoints pro Phase auswählen.

**F: Warum gibt es eine Grenze von zehn Bomerangs pro Stufe?**

[!DNL Marketo Measure] muss die Anzahl der Phasen begrenzen, damit die Verarbeitungszeiten unter Kontrolle bleiben. Wenn Sie sich dafür entscheiden, alle 15 Bomerang-Phasen in Ihr Attributionsmodell und 10 Bomerang-Touchpoints pro Phase einzubeziehen, könnten Sie über mehr als 150 Touchpoints pro Lead-/Kontaktdatensatz verfügen.

**F: Ich habe Data Warehouse. Erhalte ich alle Daten oder gilt die Boomerang Stages-Obergrenze auch für mich?**

Die Obergrenze gilt für Data Warehouse und CRMs, da die Verarbeitungsbeschränkungen, die [!DNL Marketo Measure] verfügt. Data Warehouse sieht auch die Grenze von zehn Touchpoints pro Phase.

**F: Welchen Nutzen hat die Verwendung von Boomerang Stages mit benutzerdefinierter Modellierung?**

Verwenden [!UICONTROL Boomerang] Mit Phasen mit benutzerdefinierter Modellierung können Sie die Attributionsgewichtung zu [!UICONTROL Boomerang] Touchpoints, die diesen Phasen Umsatzgutschriften zuweisen.

Ohne benutzerdefinierte Modellierung, [!DNL Marketo Measure] erstellt Touchpoints für jeden Bomerang und jede Staging-Transition, weist diesen Touchpoints jedoch keine Zuordnungsgutschriften zu. Die einzigen Bomerang-Touchpoints, die Attributionsgutschriften erhalten, stammen aus Übermittlungs-Touchpoints. Ohne benutzerdefiniertes Modell [!DNL Boomerang] Touchpoints werden als identisch mit einem &quot;mittleren Touch&quot;betrachtet und erhalten dementsprechend eine Attribution.
