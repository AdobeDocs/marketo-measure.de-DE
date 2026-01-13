---
description: Boomerang-Stadien und Touchpoints - [!DNL Marketo Measure]
title: Boomerang-Phasen und Touchpoints
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 1%

---


# Boomerang-Phasen und Touchpoints {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>Die Boomerang-Funktion ist nur für Kunden der Ebenen 2 und 3 aktiviert. Um eine höhere Kontoebene anzufordern, wenden Sie sich an das Adobe Account Team (Ihren Account Manager).

[!DNL Marketo Measure] hat die Boomerang Stage Funktion veröffentlicht! Die Boomerang-Staging-Funktion wurde entwickelt, um Kunden mit langen Verkaufszyklen einen besseren Einblick in die Journey des [!DNL Marketo Measure] zu bieten. Mit dieser Funktion können Marketing-Fachleute Touchpoints für alle Stadienübergänge erstellen, die in der Opportunity-Journey auftreten, z. B. wenn eine Kontakt-MQL aufgerufen wird, dann zu SQL wechselt und dann zum MQL-Stadium zurückkehrt. Wenn Kontakte „in die MQL-Phase eintreten“ oder „erneut in die MQL-Phase eintreten“, wird die MQL als Boomerang-Phase betrachtet. Die Boomerang-Stadium -Funktion funktioniert neben den [!DNL Marketo Measure] benutzerdefinierten Stadien.

## Funktionsweise dieser Funktion {#what-this-feature-does}

* Erstellt einen „Boomerang“-Touchpoint für alle Stadienübergänge, die beim Journey einer Opportunity auftreten
* Verfolgt wiederholte Übergänge zwischen benutzerdefinierten Stadien (z. B. wenn eine Kontakt-MQLs, zu SQL wechselt und dann zurück zur MQL-Phase geht)
* Hier können Sie angeben, wie viele und welche Gruppe von Stadienübergängen in der Opportunity enthalten sein sollen (z. B. Die ersten 10 MQLs ODER die letzten 5 MQLs)
* Wenn Sie ein Benutzer eines benutzerdefinierten Modells sind, können Sie die Attributionsgewichtung und den Kreditprozentsatz bestimmen, den Sie jedem dieser Stadien zuweisen möchten (z. B. Attributionsgewichtung auf das erste oder letzte MQL-Vorkommen festlegen oder die Attributionsgewichtung gleichmäßig auf alle Vorkommen verteilen)

>[!NOTE]
>[Anleitung zum Einrichten von Boomerang-Stadien](/help/advanced-features/boomerang/setting-up-boomerang-stages.md).

## Wie Boomerang-Stadien und Touchpoints in Ihrem CRM aussehen {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Ohne Boomerang-Stadien (das „Vorher„) sehen Sie nur den letzten SQL-Touchpoint, der einem Lead/Kontakt-Datensatz zugeordnet ist.

![Opportunity-Eintrag zeigt nur Touchpoints des letzten Stadiums ohne Boomerang](assets/1.png)

Bei Boomerang-Stadien und Touchpoints sehen Sie Touchpoints, die für jede Stadienübergabe auftreten. Die Namenskonvention für diese Bumerang-Touchpoints lautet:

**[Name des Stadiums]-00.**

Unter Verwendung des folgenden Beispiels hat dieses [!DNL Marketo Measure]-Konto MQL und SQL in ihre Boomerang-Stadien aufgenommen und sich dafür entschieden, zwei Boomerang-Touchpoints pro Stadium anzuzeigen.

![Boomerang-Touchpoints für mehrere MQL- und SQL-Staging-Transitionen aufgeführt](assets/2.png)

**MQL-01** ist die erste MQL-Stadienübergabe.

Der numerische Wert in der Touchpoint-Position gibt die Reihenfolge an, in der der Stufenübergang stattgefunden hat. Der letzte Boomerang-Touchpoint wird wie folgt gestempelt:

MQL-02 **(Letzter)**

## Wie Boomerang-Stadien Ihre vorhandenen Daten ändern {#how-boomerang-stages-change-your-existing-data}

Boomerang-Stadien Einfluss:

**Attribution nach Kanal**

* Da [!DNL Boomerang Stages] weitere Touchpoints erstellt, ändert sich dadurch die Art und Weise, wie die Attribution auf die Touchpoints verteilt wird, die derzeit in Ihren Daten vorhanden sind. Infolgedessen kann dies bedeuten, dass sich die Umsatzwerte zwischen den Marketing-Kanälen verschieben. Berücksichtigen Sie dies, bevor Sie [!DNL Boomerang stages] implementieren, oder wenden Sie sich an Ihren Account Manager, um weitere Informationen zu erhalten.

**Alle Berichte, die „ist gleich [Touchpoint-Position] verwenden**

* Boomerang-Stadien führen neue Touchpoint-Positionen in Ihre Daten ein. [!DNL Marketo Measure] ändert das Format der Touchpoint-Position, um das Auftreten des Stadiums einzuschließen, z. B. „MQL-01“ oder „MQL-05 (Letzte)“. In diesem Beispiel wirken sich Boomerang-Stadien auf alle Berichte aus, die „Touchpoint-Position ist gleich MQL“ verwenden. Um diese Berichte anzupassen, sollte der Filter stattdessen den Operator „enthält“ verwenden.

## FAQs {#faq}

**Wie viele Boomerang-Stadien kann ich in mein Attributionsmodell einbeziehen?**

Sie können bis zu 15 Phasen auswählen.

**F: Wie viele „Boomerang“-Touchpoints kann ich pro Stadium haben?**

Sie können bis zu zehn Boomerang-Touchpoints pro Stadium auswählen.

**F: Warum gibt es ein Limit von zehn Boomerangs pro Stadium?**

[!DNL Marketo Measure] muss die Anzahl der Phasen begrenzen, um die Verarbeitungszeiten unter Kontrolle zu halten. Wenn Sie alle 15 Boomerang-Stadien in Ihr Attributionsmodell einbeziehen und 10 Boomerang-Touchpoints pro Stadium, könnten Sie möglicherweise über 150 Touchpoints pro Lead/Kontakt-Datensatz haben.

**Q: Ich habe Data Warehouse. Erhalte ich alle Daten oder gilt die Begrenzung der Boomerang-Stadien auch für mich?**

Die Begrenzung gilt für Data Warehouse und CRMs aufgrund der von [!DNL Marketo Measure] festgelegten Verarbeitungsbeschränkungen. Für Data Warehouse gilt außerdem das Limit von zehn Touchpoints pro Stadium.

**F: Was ist der Vorteil der Verwendung von Boomerang-Stadien mit benutzerdefinierter Modellierung?**

Durch die Verwendung [!UICONTROL Boomerang]-Stadien mit benutzerdefinierter Modellierung können Sie den Touchpoints [!UICONTROL Boomerang“ eine Attributionsgewichtung zuweisen, ] diesen Stadien Umsatzgutschriften zuweist.

Ohne benutzerdefinierte Modellierung erstellt [!DNL Marketo Measure] Touchpoints für jeden Bumerang und jede Stadienübergabe, weist diesen Touchpoints jedoch keine Attributionszuordnung zu. Die einzigen Boomerang-Touchpoints, die Attributionsgutschriften erhalten, sind aus Submission Touchpoints. Ohne benutzerdefiniertes Modell werden [!DNL Boomerang] Touchpoints als „Middle Touch“ betrachtet und entsprechend angerechnet.
