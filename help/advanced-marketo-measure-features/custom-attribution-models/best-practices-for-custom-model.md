---
description: Best Practices für benutzerdefiniertes Modell - [!DNL Marketo Measure]
title: Best Practices für benutzerdefiniertes Modell
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 2%

---

# Best Practices für benutzerdefiniertes Modell {#best-practices-for-custom-model}

## Überblick {#overview}

Zusätzlich zu den vordefinierten Attributionsmodellen &quot;[!DNL Marketo Measure]&quot; haben Tier-2-Kunden und höher Zugriff auf ein benutzerdefiniertes Attributionsmodell.

Mit dem Modell [!DNL Marketo Measure] Benutzerdefinierte Zuordnung können Benutzer auswählen, welche Meilenstein-Touchpoint-Positionen und/oder benutzerdefinierten Bühnen in das Modell aufgenommen werden sollen. Darüber hinaus können Benutzer den Prozentsatz der Gutschriften steuern, die den einzelnen Phasen innerhalb des Modells zugeordnet werden (Benutzer können bis zu 6 zusätzliche benutzerdefinierte Phasen definieren), oder sie können die vom Modell für maschinelles Lernen empfohlenen Attributionsprozentwerte verwenden.[!DNL Marketo Measure]

Es gibt zwei wichtige Aspekte Ihres benutzerdefinierten Attributionsmodells:

**Benutzerdefinierte Phasen** ermöglichen es Benutzern, ihren Trichter in Bezug auf ihr Geschäft und ihre Prozesse zu definieren. Benutzerdefinierte Phasen sollten &quot;Meilensteine&quot;auf der gesamten Journey des Käufers darstellen, ähnlich wie die [!DNL Marketo Measure] Meilensteine (Erstkontakt, Lead-Kreation-Touch, Opportunity Creation Touch und Closed Won Touch) innerhalb der Aktienattributionsmodelle ausgeführt werden. Es ist wichtig, dass Ihre benutzerdefinierten Phasen in Ihrem Konto richtig definiert und zugeordnet werden, um sicherzustellen, dass [!DNL Marketo Measure] die Phasenübergänge ordnungsgemäß verfolgt. Dadurch soll ermittelt werden, welche Touchpoints mit jeder Phase verknüpft werden sollen, und eine entsprechende Zuordnung erfolgt. Die Zuordnung benutzerdefinierter Phasen ist im Wesentlichen eine Erweiterung der standardmäßigen &quot;Staging-Zuordnung&quot;und sollte denselben Verfahren entsprechen.

>[!NOTE]
>
>Weitere Informationen finden Sie in der Ressource &quot;Best Practices für die Staging-Zuordnung&quot;

**Benutzerdefinierte Attributionsmodellierung** wird definiert, sobald Sie Ihren Trichter Benutzerdefinierte Phasen auswählen. Die Benutzer können dann steuern, wie viel Attribution-Guthaben den einzelnen benutzerdefinierten Phasen sowie den [!DNL Marketo Measure] -Meilensteinen zugewiesen werden soll. Benutzer können jeder Phase eine Gutschrift zuweisen, wenn sie dies für richtig erachten, oder auf das Modell für maschinelles Lernen mit dem Namen [!DNL Marketo Measure] verweisen, das auf historischen Daten basiert und als &quot;anregendes Modell&quot;fungiert.

Es ist wichtig, dass diese beiden Aspekte Ihres benutzerdefinierten Modells korrekt und präzise definiert sind, um sicherzustellen, dass [!DNL Marketo Measure] ein genaues benutzerspezifisches Attributionsmodell erstellt.

## Best Practices {#best-practice}

Unabhängig davon, ob Sie Ihr benutzerdefiniertes Modell zum ersten Mal einrichten oder frühere Versionen überprüfen, sollten Sie folgende Best Practices beachten.

* Einfach starten
   * Identifizieren Sie die wichtigsten Schritte, die Sie Ihrem benutzerdefinierten Modell hinzufügen möchten, die für Ihr [!DNL Marketo Measure] -Reporting von entscheidender Bedeutung sind. In der Regel handelt es sich hierbei um Phasen, an denen Sie gemessen werden oder die Sie versuchen, Einblicke in
   * Sie können Ihrem benutzerdefinierten Modell jederzeit im Zeitverlauf hinzufügen
* Verwenden des Modells [!DNL Marketo Measure] für maschinelles Lernen
   * Wenn Sie Schwierigkeiten haben, die Verteilung der prozentualen Attribution zu bestimmen, können Sie mit dem Modell für maschinelles Lernen [!DNL Marketo Measure] fundierte Entscheidungen bei der Einstellung Ihres benutzerdefinierten Attributionsmodells treffen.
   * Beim Anzeigen des Modells für maschinelles Lernen spiegeln die Attributionsprozentsätze jeder Phase die potenziellen Auswirkungen Ihrer Marketing-Maßnahmen wider
      * Ein höherer Prozentsatz bedeutet, dass Marketing die Bewegung des Trichters zu diesem Zeitpunkt direkt beeinflussen kann
      * Ein geringerer Attributionsprozentsatz bedeutet, dass Phasen für Ihr Team weniger wichtig sind
* Sie müssen die wichtigsten Trichterphasen entweder auf der Lead- oder der Kontaktphase definieren, nicht auf beiden
   * Dies bedeutet, dass Sie sicherstellen müssen, dass alle Personen diese Phase auf dem relativen Objekt durchlaufen
      * Beispiel: Wenn Sie die MQL-Bühne aus dem Lead-Objekt definieren, müssen alle Personen als Lead in Ihr System einsteigen und als MQL in ihrem Lead-Datensatz gekennzeichnet werden, damit [!DNL Marketo Measure] genau widerspiegelt, welcher Kontakt mit der Umstellung des Leads auf MQL zusammenhängt. Wenn dies nicht der Fall ist und einige Personen zu Kontakt gelangen, bevor sie zu einer MQL als Lead werden, kann [!DNL Marketo Measure] dies nicht genau in Ihren Touchpoint-Daten berücksichtigen, und wir müssen davon ausgehen, dass diese Person bereits MQL&#39;d hat. [!DNL Marketo Measure] kann das Staging nicht berücksichtigen. Daher werden wir erkennen, dass die Bühnen auch dann durchlaufen wurden, wenn sie dies nicht getan haben.
* Stellen Sie sicher, dass die Verfolgung des Feldverlaufs für alle Felder aktiviert ist, die zum Definieren von benutzerdefinierten Bühnen verwendet werden, die Sie einbinden
* Verwenden Sie keine Formelfelder, um eine benutzerdefinierte Phase zu definieren
   * Ein boolesches Feld ist eine Best Practice-Empfehlung
* Integrieren Sie keine benutzerdefinierten Phasen in Ihr benutzerdefiniertes Modell, die mit einer [!DNL Marketo Measure] Milestone-Touchpoint-Position (FT, LC, OC, Closed Won/Lost) übereinstimmen.
   * Wenn Sie dies tun, treten diese Positionen immer gleichzeitig auf und können zu einer überhöhten Attribution zu Teilen Ihres Trichters führen.
* Arbeiten mit Ihrem Sales Opt-Team
   * Wenn Sie das Team einbinden, das am nächsten mit Bühnen und deren Bedeutung arbeitet, stellen Sie sicher, dass Sie die richtigen Bühnen verwenden und dass diese ordnungsgemäß definiert sind.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Wenn Sie Ihr benutzerdefiniertes Modell mindestens zweimal jährlich überprüfen, stellen Sie sicher, dass Ihre benutzerspezifischen Attributionsberichte genau und zuverlässig sind.

Wenn Ihr benutzerdefiniertes Modell das Modell für maschinelles Lernen verwendet, sollten Sie dessen Anwendung vierteljährlich im benutzerdefinierten Modell überprüfen, um sicherzustellen, dass Ihr benutzerdefiniertes Modell so aktuell wie möglich ist.

Weitere Gründe dafür könnten eine Überprüfung Ihres benutzerdefinierten Modells Trigger sein...

* Wechsel in Ihrem Marketing-Team
* Alle Änderungen an Ihren CRM-Phasen
* Aktualisierungen des Unternehmenstrichter
* Anzeigen ungenauer Umsatzdaten in Ihren [!DNL Marketo Measure] -Berichten bei der Anwendung des benutzerdefinierten Modells
* Anzeigen von Kontaktpunktpositionen, die für Ihren Unternehmenstrichter nicht mehr relevant sind

>[!MORELIKETHIS]
>
>* [Benutzerdefiniertes Attributionsmodell und Einrichtung](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [ Feldverlauf-Tracking für benutzerdefiniertes Modell aktivieren](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [Modell für maschinelles Lernen](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
