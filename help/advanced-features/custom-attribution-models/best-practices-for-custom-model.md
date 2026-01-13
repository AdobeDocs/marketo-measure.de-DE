---
description: Best Practices für ein benutzerdefiniertes Modell - [!DNL Marketo Measure]
title: Best Practices für benutzerdefiniertes Modell
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 2%

---


# Best Practices für benutzerdefiniertes Modell {#best-practices-for-custom-model}

## Überblick {#overview}

Zusätzlich zu den [!DNL Marketo Measure] vordefinierten Attributionsmodellen haben Tier 2-Kunden und höher Zugriff auf ein benutzerdefiniertes Attributionsmodell.

Mit dem [!DNL Marketo Measure] benutzerdefinierten Attributionsmodell können Benutzer auswählen, welche Meilenstein-Touchpoint-Positionen und/oder benutzerdefinierten Stadien in das Modell aufgenommen werden sollen. Darüber hinaus können Benutzer den Prozentsatz der Gutschrift steuern, der jeder Stufe innerhalb des Modells zugeordnet wurde (Benutzer können bis zu 6 zusätzliche benutzerdefinierte Stufen definieren), oder sie können die prozentualen Werte der Zuordnung verwenden, die vom Modell für maschinelles Lernen [!DNL Marketo Measure] vorgeschlagen werden.

Es gibt zwei wichtige Aspekte Ihres benutzerdefinierten Attributionsmodells:

**Benutzerdefinierte Stadien** ermöglichen es Benutzenden, ihre funnel in Bezug auf ihr Unternehmen und ihre Prozesse zu definieren. Benutzerdefinierte Stadien sollten „Meilensteine“ auf der gesamten Journey des Käufers darstellen, ähnlich wie die [!DNL Marketo Measure] Meilensteine (Erstkontakt, Lead-Erstellungs-Touch, Opportunity-Erstellungs-Touch und Abgeschlossen-Gewonnen-Touch) in den Attributionsmodellen für Aktien. Es ist wichtig, dass Ihre benutzerdefinierten Stadien in Ihrem Konto ordnungsgemäß definiert und zugeordnet werden, um sicherzustellen, dass [!DNL Marketo Measure] Stadienübergänge ordnungsgemäß verfolgt. Dadurch soll ermittelt werden, welche Touchpoints mit jedem Stadium verknüpft werden sollen, und eine entsprechende Zuordnung ermöglicht werden. Benutzerdefiniertes Stadium-Mapping ist im Wesentlichen eine Erweiterung des standardmäßigen „Stadien-Mappings“ und sollte denselben Praktiken folgen.

>[!NOTE]
>Weitere Informationen finden Sie in der Best Practice-Ressource für die Stadienzuordnung .

**Benutzerdefinierte Attributionsmodellierung** wird definiert, sobald Sie Ihre benutzerdefinierte Stadien-funnel auswählen. Benutzer können dann steuern, wie viel Attributionsguthaben den einzelnen benutzerdefinierten Stadien sowie den [!DNL Marketo Measure] Meilensteinstadien zugewiesen werden soll. Benutzer können jedem Stadium eine Gewichtung zuweisen, wenn sie dies für richtig halten, oder auf das Modell für maschinelles Lernen [!DNL Marketo Measure] verweisen, das auf der Grundlage historischer Daten als „suggestives Modell“ fungiert.

Es ist wichtig, dass diese beiden Aspekte Ihres benutzerdefinierten Modells korrekt und präzise definiert werden, um sicherzustellen, dass [!DNL Marketo Measure] ein genaues benutzerdefiniertes Attributionsmodell erstellt.

## Best Practices {#best-practice}

Unabhängig davon, ob Sie Ihr benutzerdefiniertes Modell zum ersten Mal einrichten oder überprüfen, was zuvor eingerichtet wurde, ist es wichtig, die folgenden Best Practices zu beachten.

* Einfach starten
   * Identifizieren Sie die wichtigsten Phasen, die Sie zu Ihrem benutzerdefinierten Modell hinzufügen möchten und die für Ihre [!DNL Marketo Measure]-Berichterstellung von entscheidender Bedeutung sind. In der Regel handelt es sich dabei um Stadien, an denen Sie häufig gemessen werden oder auf denen Sie insight erwerben möchten
   * Sie können Ihrem benutzerdefinierten Modell jederzeit im Laufe der Zeit hinzufügen
* Verwenden des Modells für maschinelles Lernen [!DNL Marketo Measure]
   * Wenn Sie Schwierigkeiten bei der Entscheidung über den prozentualen Zuordnungsdurchbruch haben, kann das Modell des [!DNL Marketo Measure] maschinellen Lernens Ihnen dabei helfen, fundierte Entscheidungen beim Festlegen Ihres benutzerdefinierten Attributionsmodells zu treffen.
   * Beim Anzeigen des Modells für maschinelles Lernen spiegeln die Prozentsätze der Attribution jedes Schritts die potenziellen Auswirkungen Ihrer Marketing-Maßnahmen wider
      * Ein höherer Prozentsatz bedeutet, dass das Marketing die Bewegung der funnel zu diesem Zeitpunkt direkt beeinflussen kann
      * Ein niedrigerer Attributionsprozentsatz bedeutet, dass Stadien für Ihr Team weniger wichtig sind
* Sie müssen die funnel-Spitzenphasen entweder anhand der Lead- oder anhand der Kontaktphasen definieren, nicht über beide
   * Das bedeutet, dass Sie sicherstellen müssen, dass alle Personen diese Phase auf dem relativen Objekt durchlaufen
      * Beispiel: Wenn Sie die MQL-Phase ausgehend vom Lead-Objekt definieren, müssen alle Personen in Ihr System als Lead eintreten und in ihrem Lead-Datensatz als MQL gekennzeichnet werden, damit [!DNL Marketo Measure] genau widerspiegeln können, welche Berührung mit der Umstellung des Leads auf MQL verbunden war. Wenn dies nicht der Fall ist und einige Personen Kontakt aufnehmen, bevor sie als Lead zu MQL werden, können [!DNL Marketo Measure] dies in Ihren Touchpoint-Daten nicht genau berücksichtigen, und wir müssen davon ausgehen, dass die Person bereits MQL verwendet hat. [!DNL Marketo Measure] kann das Stadium-Hopping nicht erklären. Daher schließen wir, dass Stadien durchlaufen wurden, auch wenn dies nicht der Fall war.
* Stellen Sie sicher, dass die Feldverlaufsverfolgung für alle Felder aktiviert ist, die zum Definieren von benutzerdefinierten Stadien verwendet werden, die Sie einbinden
* Verwenden Sie keine Formelfelder, um einen benutzerdefinierten Schritt zu definieren
   * Ein boolesches Feld ist eine Best-Practice-Empfehlung
* Binden Sie keine benutzerdefinierten Stadien in Ihr benutzerdefiniertes Modell ein, die mit einer [!DNL Marketo Measure] Milestone Touchpoint-Position (FT, LC, OC, Closed Won/Lost) übereinstimmen.
   * Wenn Sie dies tun, treten diese Positionen immer gleichzeitig auf und können zu überhöhten Attributionsgutschriften an Teile Ihrer funnel führen.
* Arbeiten mit Ihrem Vertriebschancen-Team
   * Das Einbringen des Teams, das mit den Stadien am nächsten arbeitet, und seiner Bedeutung stellt sicher, dass Sie die richtigen Stadien verwenden und dass sie richtig definiert sind

## Best Practices für die Wartung {#best-practice-for-maintenance}

Wenn Sie Ihr benutzerdefiniertes Modell mindestens zweimal jährlich überprüfen, stellen Sie sicher, dass Ihr benutzerdefiniertes Attributionsbericht korrekt und zuverlässig ist.

Wenn Ihr benutzerdefiniertes Modell das Modell für maschinelles Lernen verwendet, sollten Sie seine Anwendung innerhalb des benutzerdefinierten Modells vierteljährlich überprüfen, um sicherzustellen, dass Ihr benutzerdefiniertes Modell so aktuell wie möglich ist.

Andere Gründe, die einen Trigger für eine Überprüfung Ihres benutzerdefinierten Modells darstellen könnten, sind…

* Wechsel in Ihrem Marketing-Team
* Alle Änderungen an Ihren CRM-Phasen
* Updates für funnel in Ihren Unternehmen
* Anzeige ungenauer Umsatzdaten in Ihren [!DNL Marketo Measure]-Berichten beim Anwenden des benutzerdefinierten Modells
* Es werden Touchpoint-Positionen angezeigt, die nicht mehr für Ihr Unternehmen funnel relevant sind.

>[!MORELIKETHIS]
> [Benutzerdefiniertes Attributionsmodell und Setup](/help/advanced-features/custom-attribution-models/custom-attribution-model-and-setup.md)
> [Feldverlauf-Tracking für benutzerdefiniertes Modell aktivieren](/help/advanced-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
> [Modell für maschinelles Lernen](/help/advanced-features/custom-attribution-models/machine-learning-model-faq.md)
