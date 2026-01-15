---
description: Anleitung zur Integration der Anrufverfolgung für Marketo Measure-Benutzer
title: Anrufverfolgungsintegration
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# Anrufverfolgungsintegration {#call-tracking-integration}

Unsere Integration mit [!DNL CallTrackingMetrics] soll eine Web-Sitzung mit einem Telefonanruf zusammenführen. Ein Telefonanruf wird als Formularübermittlung an [!DNL Marketo Measure] behandelt. Sie wird einer Web-Sitzung zugeschrieben, die ansonsten nur als Web-Besuch betrachtet worden wäre, da keine tatsächliche Formularübermittlung stattgefunden hat.

## Anruf-Tracking - Erklärung {#call-tracking-explained}

„Call Tracking“ im allgemeinen Sinne ist ein Produkt von Unternehmen wie [!DNL CallTrackingMetrics], [!DNL DiaglogTech], [!DNL Invoca] oder [!DNL CallRail], um nur einige zu nennen. Benutzerinnen und Benutzern werden basierend auf den verschiedenen Marketing-Kanälen oder Kampagnen, von denen sie kommen, eindeutige Telefonnummern angezeigt. Dadurch können Marketing-Fachleute sehen, wie diese Kanäle oder Kampagnen funktionieren.

![ „Call Tracking“ im allgemeinen Sinne ist ein Produkt von solchen Unternehmen](assets/other-resources-6.png)

## Vorher und Nachher {#before-and-after}

Sehen Sie sich das folgende Flussdiagramm an, um zu sehen, wie [!DNL Marketo Measure] verwendet werden, um Telefonanrufe ohne Integration mit CallTrackingMetrics zu verarbeiten. Der Telefonanruf wurde nicht verfolgt, sodass er als Web-Sitzung angesehen und kein Touchpoint für ihn erstellt wurde. Erst beim nächsten Besuch, bei dem der Benutzer ein Formular ausgefüllt hat, wurde schließlich ein Touchpoint ausgefüllt.

Bei der Integration können Sie sehen, dass die Web-Sitzung tatsächlich mit einem Telefonanruf verknüpft war. Das nächste ausgefüllte Formular ist schließlich ein PostLC-Touch und wird als Teil des Journey verfolgt.

![Mit der Integration können Sie sehen, dass die Web-Sitzung tatsächlich war](assets/other-resources-4.png)

## Funktionsweise {#how-it-works}

CallTrackingMetrics muss hierfür einige Entwicklungsarbeiten durchführen. Mit der JavaScript, die sie auf Ihrer Site platzieren, kann CallTrackingMetrics die `_biz_uid` vom [!DNL Marketo Measure]-Cookie abrufen. Diese „BizibleId“ wird dann von CallTrackingMetrics gespeichert.

Wenn ein Besucher auf Ihre Site kommt und einen Telefonanruf tätigt, ist es die Aufgabe von CallTrackingMetrics, diese Daten in [!DNL Salesforce] zu übertragen.  Normalerweise wird ein [!DNL Salesforce Task] erstellt, in dem Daten wie Telefonnummer, Betreff, Typ und jetzt die [!DNL BizibleId] ausgefüllt werden

Das [!DNL BizibleId] ist ein Feld, das mit Version 6.7+ des [!DNL Marketo Measure] Marketing Attribution -Pakets installiert wird.

Nachfolgend finden Sie ein Beispiel für einen Aufgabendatensatz mit ausgefülltem [!DNL BizibleId].

![Nachfolgend finden Sie ein Beispiel für einen Aufgabendatensatz mit der BizibleId](assets/other-resources-5.png)

Wenn [!DNL Marketo Measure] einen Aufgabendatensatz mit einem bekannten ausgefüllten [!DNL BizibleId] findet, können [!DNL Marketo Measure] diesen Benutzer einer Web-Sitzung mit demselben [!DNL BizibleId] zuordnen und diese Sitzung einem Telefonanruf anstelle eines Web-Besuchs zuweisen.

## Der Touchpoint {#the-touchpoint}

Wenn [!DNL Marketo Measure] die Aufgabe importieren/herunterladen können, verarbeiten wir diese Details zusammen mit der Websitzung. Normalerweise kann sie mit einem Referrer oder einer Anzeige zusammengeführt werden. Im folgenden Beispiel hat ein Besucher das Unternehmen über eine Paid Google-Anzeige gefunden und einen Telefonanruf getätigt.

Der [!UICONTROL Touchpoint]-Typ „Aufruf“ wird aus der Aufgabe, aus dem obigen Screenshot, gezogen, der auch von CallTrackingMetrics aufgefüllt wird, wenn die Aufgabe erstellt wird.

![Der Touchpoint-Typ „Anruf“ wird aus der Aufgabe, aus der ](assets/marketo-engage-activities-01.png)

## Berichterstellung {#reporting}

Touchpoint-Typ-Werte, die [!DNL Marketo Measure] normalerweise per Push übertragen werden, sind Web-Besuch, Web-Formular oder Web-Chat, aber im Fall von CallTrackingMetrics-Touchpoints ist der Touchpoint-Typ Telefonanruf. Auf diese Weise können Marketing-Fachleute sehen, welche Kanäle die meisten Telefonanrufe entgegennehmen, und so Umsätze für ihr Unternehmen generieren.

![Touchpoint-Typwerte, die Marketo Measure normalerweise sendet, sind „Web-Besuch“](assets/other-resources-1.png)

## FAQs {#faq}

**Warum ist mein Touchpoint-Web-Besuch?**

Der Touchpoint-Typ wird aus dem Feld Aufgabe.Typ gefüllt. Wenn das Feld Task.Type leer ist, setzt [!DNL Marketo Measure] den Touchpoint-Typ automatisch auf Web Visit. Sobald das Feld Task.Type ausgefüllt ist, liest [!DNL Marketo Measure] diesen Wert und füllt den Touchpoint-Typ entsprechend.

**Welche anderen Felder füllt der Touchpoint aus dem Telefonanruf?**

Sowohl der Touchpoint-Typ als auch Medium enthalten die Daten, die aus dem Task.Type abgerufen werden. Alle anderen Datenpunkte werden aus den Webtracking- und JavaScript-Daten abgerufen.

**Warum ist dieser Telefonanruf nicht an eine Websitzung gebunden?**

Überprüfen Sie zunächst die Aufgabe, um sicherzustellen, dass ein [!DNL BizibleId] ausgefüllt ist. Wenn kein Wert vorhanden ist, können wir keinen Touchpoint dafür erstellen. Dies muss mit CallTrackingMetrics eskaliert werden.

Wenn ein Wert vorhanden ist, beachten Sie, dass wir alle Web-Sitzungen nur als 30 Minuten betrachten. Wenn auf eine Google-Anzeige um 12::17pm geklickt wurde (Beginn der Sitzung auf der Website), der Telefonanruf jedoch erst um 1::05pm stattfand, werden die Websitzung und der Telefonanruf nicht zusammengeführt. Stattdessen erstellt [!DNL Marketo Measure] einen separaten [!DNL Salesforce Task]-Touchpoint, um den Telefonanruf zu verfolgen, der jedoch über keine Web-Sitzungsdaten verfügt.

![Wenn es einen Wert gibt, beachten Sie, dass wir nur alle Web](assets/other-resources-2.png)

## Partnerschaften {#partnerships}

[!DNL Marketo Measure] hat derzeit einen offiziellen Call-Tracking-Partner, der den „offiziellen“ Integrationsprozess mit uns durchlaufen hat, der Co-Marketing und Produktschulungen umfasste. Dieser eine Partner ist CallTrackingMetrics.
