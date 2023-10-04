---
description: Best Practices für Online-Kanäle – Produktdokumentation zu  [!DNL Marketo Measure]
title: Best Practices für Online-Kanäle
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '612'
ht-degree: 100%

---

# Best Practices für Online-Kanäle {#best-practices-for-online-channels}

## Überblick {#overview}

Um korrektes Reporting für [!DNL Marketo Measure] zu erhalten, müssen Ihre Marketing-Kanäle korrekt eingerichtet sein. Im Feld „Marketing-Kanal“ wird die Gruppe der Marketing-Aktivitäten auf höchster Ebene angezeigt, zu der ein Touchpoint gehören kann (z. B. Paid Search, Direkt, Social usw.).

Die Einrichtung Ihrer Marketing-Kanäle hat zwei Aspekte: Online und Offline. Dieses Dokument konzentriert sich auf die empfohlenen Best Practices für [!DNL Marketo Measure] bei der Einrichtung und Verwaltung Ihrer Online-Kanäle.

Online-Kanalregeln sind Richtlinien dafür, wie [!DNL Marketo Measure] Ihre digitalen Touchpoints zuordnet, d. h. alle Touchpoints, die über das JavaScript von [!DNL Marketo Measure] auf Ihrer Site nachverfolgt und erstellt werden. Wenn diese Regeln nicht vollständig oder nicht korrekt zugeordnet sind, können Touchpoints dem falschen Kanal zugeschrieben werden, wodurch die Genauigkeit Ihrer Berichterstellung beeinträchtigt wird. Wenn Sie sicherstellen, dass Ihre Online-Kanal-Regeln korrekt und aktuell sind, garantieren Sie, dass Ihre digitalen Daten in Ihrer Berichterstellung für [!DNL Marketo Measure] dem richtigen Kanal und den richtigen Unterkanälen zugeschrieben werden.

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, um sicherzustellen, dass die Regeln korrekt sind, unabhängig davon, ob Sie Ihre Regeln zum ersten Mal einrichten oder sie nur überprüfen.

Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und darüber, wie sie in das Framework von [!DNL Marketo Measure] passen. Bestimmen Sie, welche Kanäle und Unterkanäle in Ihren Online-Kanälen angezeigt werden sollen und welche Kampagnen, UTM-Parameter oder verweisenden Websites diese Kanäle voneinander unterscheiden.

Folgendes sollte beachtet werden:

* Alle digitalen Kanäle und Unterkanäle sollten mit mindestens einer Regel vertreten sein
   * Wenn der Kanal keine Leute zu Ihrer Site bringt, handelt es sich nicht um einen Online-Kanal
* Es ist in Ordnung, mehrere Regeln für einen Kanal/Unterkanal zu haben
   * Mit mehr Regeln wird bildlich gesprochen „ein größeres Netz ausgeworfen“, um sicherzustellen, dass jeder Touchpoint korrekt zugeordnet wird. Oft können Parameter falsch hinzugefügt oder vollständig vergessen worden sein, daher ist es empfehlenswert, mehrere Regeln zum Erfassen eines Kanals/Unterkanals zu haben, um die Genauigkeit der Zuordnung sicherzustellen.
* Die Logik von [!DNL Marketo Measure] priorisiert Daten in absteigender Reihenfolge, beginnend mit der obersten Zeile der Tabelle und dann weiter nach unten
   * [!DNL Marketo Measure] liest jede Regel (Zeile) und sucht nach der ersten passenden Regel. Der Touchpoint wird dann diesem Kanal/Unterkanal zugeordnet
   * Sortieren Sie Ihr Blatt nicht in alphabetischer Reihenfolge, da dies die Logikregeln stört.
* Behalten Sie die Regeln in Klammern bei, bearbeiten Sie sie nicht und fügen Sie ihnen nichts hinzu (Beispiel; [AdWords Paid Search] oder [Facebook Paid])
   * Diese sind vorkonfigurierte Regeln für [!DNL Marketo Measure] mit einer integrierten Logik, die an die [!DNL Marketo Measure]-Integrationen gebunden sind. Weisen Sie diesen Regeln die oberste Priorität für diesen Kanal/Unterkanal-Abschnitt zu, um sicherzustellen, dass [!DNL Marketo Measure]-Integrationen wie gewünscht funktionieren können.
* Nach dem Hochladen der Datei können Sie für sieben Tage keine der Regeln ändern
   * [!DNL Marketo Measure] nutzt diese Zeit, um die Touchpoints zu verarbeiten und zu aktualisieren. Überprüfen Sie daher vor dem Hochladen Ihre Regeln.

## Best Practice für die Wartung {#best-practice-for-maintenace}

Nach dem Speichern und Verarbeiten arbeiten die Regeln des Online-Kanals kontinuierlich, um Ihre digitalen Touchpoints in Buckets zu organisieren. Bestimmte Änderungen oder Szenarien führen jedoch dazu, dass Sie die Einrichtung Ihres Online-Kanals überprüfen sollten. [!DNL Marketo Measure] empfiehlt, dass Sie Ihre Online-Kanalregeln alle sechs Monate überprüfen. Dadurch wird sichergestellt, dass Ihre [!DNL Marketo Measure]-Daten mit Ihren internen Definitionen von Online-Kanälen/-Unterkanälen und Ihrer Verwendung von UTMs abgestimmt sind.

Im Folgenden werden weitere Vorkommnisse aufgelistet, die Ihr Team dazu veranlassen könnten, den Online-Kanal zu warten …

* Start eines neuen digitalen Kanals/Unterkanals
* UTM-Parameter werden aktualisiert oder geändert
* Änderungen an Ihrer Kanalorganisation oder Ihren Namenskonventionen
* Wechsel in Ihrem Marketing-Team

Wenn in Ihrem Team in letzter Zeit eines der oben genannten Dinge aufgetreten ist, empfiehlt [!DNL Marketo Measure], dass Sie die Regeln Ihrer Online-Kanäle überprüfen und die entsprechenden Änderungen vornehmen.

>[!MORELIKETHIS]
>
>* [Einrichtung des Online-Kanals](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM-Parameter](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Marketing-Kanal und -Unterkanal](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Best Practices für UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
