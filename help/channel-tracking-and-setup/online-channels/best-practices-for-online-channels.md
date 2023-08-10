---
description: Best Practices für Online-Kanäle - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für Online-Kanäle
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 9%

---

# Best Practices für Online-Kanäle {#best-practices-for-online-channels}

## Überblick {#overview}

Richtig [!DNL Marketo Measure] Berichterstellung, müssen Ihre Marketing-Kanäle korrekt eingerichtet sein. Im Feld Marketing-Kanal wird die Gruppe der Marketing-Aktivitäten auf höchster Ebene angezeigt, zu der ein Touchpoint gehören kann (z. B. Paid Search, Direct, Social usw.).

Die Einrichtung Ihrer Marketing-Kanäle hat zwei Aspekte: Online und Offline. Dieses Dokument konzentriert sich auf die [!DNL Marketo Measure] Best Practice-Empfehlungen für die Einrichtung und Verwaltung Ihrer Online-Kanäle.

Online-Kanalregeln sind Richtlinien dafür, wie [!DNL Marketo Measure] ordnet Ihre digitalen Touchpoints zu, d. h. alle Touchpoints, die verfolgt und über die [!DNL Marketo Measure] JS auf Ihrer Site. Wenn diese Regeln nicht vollständig oder nicht korrekt angeordnet sind, können Touchpoints dem falschen Kanal zugeordnet werden, wodurch die Genauigkeit Ihrer Berichterstellung beeinträchtigt wird. Wenn Sie sicherstellen, dass Ihre Online-Kanal-Regeln korrekt und aktuell sind, garantieren Sie, dass Ihre digitalen Daten dem richtigen Kanal und den richtigen Unterkanälen in Ihren [!DNL Marketo Measure] Berichterstellung

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie Ihre Regeln zum ersten Mal einrichten oder sie nur überprüfen, um sicherzustellen, dass sie korrekt sind.

Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und darüber, wie sie in die [!DNL Marketo Measure] Framework. Bestimmen Sie, welche Kanäle und Subkanäle in Ihren Online-Kanälen angezeigt werden sollen und welche Kampagnen, UTM-Parameter oder verweisenden Websites diese Kanäle voneinander unterscheiden.

Folgendes sollte beachtet werden:

* Alle digitalen Kanäle und Unterkanäle sollten mit mindestens einer Regel dargestellt werden
   * Wenn der Kanal keine Personen zu Ihrer Site bringt, handelt es sich nicht um einen Online-Kanal
* Es ist in Ordnung, mehrere Regeln für einen Kanal/Subkanal zu haben
   * Mehrere Regeln können als &quot;Gießen eines größeren Netzes&quot;betrachtet werden, um sicherzustellen, dass jeder Touchpoint korrekt zugeordnet wird. Oft können Parameter falsch hinzugefügt oder vollständig verpasst werden. Daher ist es empfehlenswert, mehrere Regeln zum Erfassen eines Kanals/Subkanals zu haben, um die Genauigkeit der Zuordnung sicherzustellen.
* [!DNL Marketo Measure] Die Logik priorisiert die Touchpoint-Zuordnung in absteigender Reihenfolge, beginnend mit der obersten Zeile des Arbeitsblatts und nach unten.
   * [!DNL Marketo Measure] liest jede Regel (Zeile) und sucht nach der richtigen und ersten Anpassung. Der Touchpoint wird dann diesem Kanal/Unterkanal zugeordnet.
   * Sortieren Sie Ihr Blatt nicht in alphabetischer Reihenfolge, da dies die Logikregeln stört.
* Beibehalten der mit Klammern versehenen Regeln, weder Bearbeiten noch Hinzufügen der mit Klammern versehenen Regeln (Beispiel); [Gebührenpflichtige AdWords-Suche] oder [Facebook Paid] )
   * Diese sind vorkonfiguriert [!DNL Marketo Measure] Regeln, die eine Logik integriert haben, die mit der [!DNL Marketo Measure] Integrationen. Weisen Sie diesen Regeln die oberste Priorität für diesen Kanal/Unterkanalabschnitt zu, um sicherzustellen, dass [!DNL Marketo Measure] Integrationen können wie gewünscht funktionieren.
* Nach dem Hochladen der Datei können Sie für sieben Tage keine der Regeln ändern
   * [!DNL Marketo Measure] nutzt diese Zeit, um die Touchpoints zu verarbeiten und zu aktualisieren. Überprüfen Sie daher vor dem Hochladen Ihre Regeln.

## Best Practice für die Wartung {#best-practice-for-maintenace}

Nach dem Speichern und Verarbeiten arbeiten die Regeln des Online-Kanals kontinuierlich, um Ihre digitalen Touchpoints zu sammeln. Bestimmte Änderungen oder Szenarien führen jedoch dazu, dass Sie die Einrichtung Ihres Online-Kanals überprüfen möchten. [!DNL Marketo Measure] empfiehlt, dass Sie Ihre Online-Kanalregeln alle sechs Monate überprüfen. Dadurch wird sichergestellt, dass Ihre [!DNL Marketo Measure] -Daten sind mit Ihren internen Definitionen von Online-Kanälen/Subkanälen und Ihrer Verwendung von UTMs abgestimmt.

Weitere Artikel, die Ihr Team möglicherweise für die Wartung des Online-Kanals Trigger haben könnten, sind ...

* Neuer digitaler Kanal/Subkanal gestartet
* UTM-Parameter werden aktualisiert oder geändert
* Änderungen an Ihrer Kanalorganisation oder Ihren Namenskonventionen
* Wechsel in Ihrem Marketing-Team

Wenn Ihr Team kürzlich einen der oben genannten Punkte erfahren hat [!DNL Marketo Measure] empfiehlt, dass Sie die Regeln Ihrer Online-Kanäle überprüfen und die entsprechenden Änderungen vornehmen.

>[!MORELIKETHIS]
>
>* [Online-Kanal-Einrichtung](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM-Parameter](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Marketingkanal und Subkanal](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Best Practices für UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
