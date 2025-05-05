---
unique-page-id: 42762310
description: Synchronisieren historischer Daten - [!DNL Marketo Measure]
title: Synchronisieren historischer Daten
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
feature: Channels
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 3%

---

# Synchronisieren historischer Daten {#syncing-historical-data}

[!DNL Marketo Measure] ist eine Lösung, die die detailliertesten, umsetzbaren Daten bereitstellt. Nach unserem Kenntnisstand verfügen Sie möglicherweise über vorhandene Daten, für die Sie eine Attribution wünschen. Es ist möglich, Touchpoints für historische Daten zu generieren, aber es ist wichtig, einige Faktoren zu berücksichtigen, bevor Sie mit diesem Prozess fortfahren.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

## Zu berücksichtigende Faktoren {#factors-to-consider}

**Sind die Daten bereits in Kampagnen unterteilt?**

a. Die Daten müssen in Kampagnen organisiert und mit [!DNL Marketo Measure] synchronisiert werden, damit Touchpoints generiert werden können. Wenn er derzeit nicht in Kampagnen unterteilt ist, sollten Sie prüfen, ob sich die Zeit und die Ressourcen lohnen, die für die Segmentierung der Daten in die entsprechenden Kampagnen erforderlich sind.

b. Das Datum, an dem das Mitglied der Kampagne hinzugefügt wurde oder als beantwortet markiert wurde, wird für das Touchpoint-Datum verwendet. Daher muss dieses Datum auch korrekt sein. [!DNL Marketo Measure] bietet Problemumgehungen sowohl in SFDC als auch in MSD, um die Daten zu aktualisieren. Dies kann jedoch je nach Volumen zeitaufwendig sein.

**Haben Sie für alle Kanäle (Paid Search, Ereignisse, Organic usw.) eine relativ gleiche Datenmenge in Kampagnen organisiert?**

Es ist wichtig, ein ausgewogenes Bild der Attribution zu haben, um eine genaue und „faire“ Berichterstattung zu haben. Wenn Sie beispielsweise nur Daten für historische Offline-Kanal-Bemühungen wie Ereignisse haben, sind die Daten ohne historische Online-Daten inhärent verzerrt, um sie zu ergänzen.

**Welchen Grad an Granularität erwarten Sie?**

Sie kennen im Wesentlichen nur den Kanal, den Unterkanal und den Kampagnennamen.

**Welche Reporting-Ziele werden Sie in Zukunft verfolgen?**

Diese Daten sind begrenzt, daher ist es wichtig zu überlegen, wie Sie sie verwenden möchten. Vielleicht ist es nicht am sinnvollsten, historische Daten mit zukünftigen Daten zu vergleichen.

**Wie weit wollen Sie zurück gehen?**

[!DNL Marketo Measure] empfiehlt dringend, nicht über das Vorjahr hinauszugehen.

Dies ist ein Thema, das wir dringend empfehlen, zuerst mit Ihrem [!DNL Marketo Measure] Kontakt zu besprechen. Wenn Sie die obigen Überlegungen angestellt haben und fortfahren möchten, finden Sie im Folgenden allgemeine Anweisungen (für [!DNL Salesforce] und [!DNL Microsoft Dynamics] getrennt).

## Synchronisieren historischer Kampagnen in [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**Online:**

Um historische Online-Daten zu synchronisieren, müssen die Daten in Salesforce-Kampagnen unterteilt sein. Diese können dann über [!DNL Salesforce] Regeln für die Kampagnensynchronisierung in der [!DNL Marketo Measure] App mit [!DNL Marketo Measure] synchronisiert werden. Sie müssen sicherstellen, dass aus keiner dieser Kampagnen nach dem Tag der Live-Schaltung Ihrer JavaScript Touchpoints generiert werden. Der Grund dafür ist, doppelte Touchpoints zu vermeiden. Nach der Live-Schaltung der JavaScript werden Online-Anstrengungen automatisch verfolgt, sodass wir sie nicht auch über eine SFDC-Kampagne verfolgen möchten. Um dieses Problem zu vermeiden, sollten Sie der Regel eine gewisse Zeit hinzufügen. Möglicherweise liegt das Erstellungsdatum des Kampagnenmitglieds unter dem [JavaScript-Tag der Live-Schaltung].

![](assets/syncing-historical-data-1.png)

Die Kanalzuordnungskomponente für historische Online-Daten kann etwas kompliziert sein. Wir möchten, dass sie mit Ihren aktuellen Online-Kanalregeln (aus dem Online-Regelblatt) für sauberes Reporting so gut wie möglich übereinstimmt. Im Folgenden finden Sie ein Beispiel für eine ideale Kanalzuordnung.

>[!NOTE]
>
>Diese Kanalzuordnung erfolgt im Abschnitt [!UICONTROL Offline-Kanäle] der [!DNL Marketo Measure]-App, da wir SFDC-Kampagnen verwenden.

| Salesforce-Kampagnentyp | Kanal | Unterkanal |
|---|---|---|
| Paid Search - AdWords | Paid Search | AdWords |
| Paid Search - Bing | Paid Search | Bing |
| Bezahlte Suche - Yahoo | Paid Search | Yahoo |

Online-Daten, die auf diese Weise hinzugefügt werden, sind von Natur aus weniger detailliert als Online-Daten, die über JavaScript [!DNL Marketo Measure] werden. Zum Beispiel werden Felder wie Formular-URL, Landingpage, Referrer-Seite usw. nicht ausgefüllt. Daher wird empfohlen, die Kampagnen nach Möglichkeit in jede Quelle aufzuteilen. Wie im obigen Beispiel gezeigt, müssten Sie mehrere Kampagnentypen für jede Quelle haben, um eine Granularität im Reporting zu haben.

Es ist möglicherweise nicht möglich oder sinnvoll, die Anzahl der SFDC-Kampagnentypen zu verwenden, um eine granulare Kanalzuordnung zu unterstützen. Daher müssen Sie möglicherweise nur auf die Kanalebene zuordnen und die Unterkanäle ignorieren. Wenn die Kanalebene ebenfalls nicht bekannt ist, können Sie einen Proxy-Kanal wie „Historic Digital“ einrichten, damit Sie zumindest wissen, dass es sich um einen Online-Touch handelte.

Wenn Sie das Touchpoint-Datum, das für diese historischen Online-Bemühungen gesendet wird, massenweise bearbeiten müssen, verwenden Sie die [!DNL Marketo Measure] benutzerdefinierte Schaltfläche „Touchpoint-Datum [!UICONTROL &#x200B; Massenaktualisierung] (dieses Feld ist als benutzerdefiniertes Feld im Kampagnenobjekt in SFDC verfügbar). Wenn die Kampagne eine kurze Zeitspanne hat, wäre es vielleicht sinnvoll, das Touchpoint-Datum massenweise in einem Tagesintervall zu bearbeiten, während es möglicherweise sinnvoll wäre, die Massenaktualisierung wöchentlich durchzuführen, wenn die Kampagne eine längere Zeitspanne hat. Wenn Sie die Funktion „Massen-Update-Touchpoint-Datum“ verwenden, stellen Sie sicher, dass Sie die Kampagnensynchronisierungsregel aktualisieren, um das Buyer Touchpoint-Datum im Datumsfeld zu verwenden. Beachten Sie, dass Sie dazu möglicherweise kreativ mit Ihren Kampagnen-Synchronisierungsregeln umgehen müssen, wenn dies nur für eine oder zwei Kampagnen gilt und nicht für alle.

**offline:**

Verlaufsdaten von Offline-Marketing-Maßnahmen (die nicht über JavaScript verfolgt werden können) müssen ebenfalls in SFDC-Kampagnen unterteilt werden. SFDC-Kampagnen ermöglichen [!DNL Marketo Measure] Nachverfolgung von Offline-Aktivitäten, unabhängig davon, ob es sich um eine „historische“ Aktivität oder eine „aktuelle/[!DNL Marketo Measure] Implementierung“ handelt. Befolgen Sie daher die gleiche Kanalzuordnung, die in der ursprünglichen Schulung zur Offline-Kanalkonfiguration festgelegt wurde.

Verwenden Sie bei Bedarf die Schaltfläche „Massen-Touchpoint-Datum aktualisieren“, um das Touchpoint-Datum für Kampagnenmitglieder massenweise zu bearbeiten. Wenn Sie beispielsweise SFDC-Kampagnen erstellen, nachdem das Ereignis aufgetreten ist, sollten Sie für das richtige Datum eine Massenbearbeitung durchführen. Wenn Sie die Funktion „Massen-Update-Touchpoint-Datum“ verwenden, stellen Sie sicher, dass Sie die Kampagnensynchronisierungsregel aktualisieren, um das Buyer Touchpoint-Datum im Datumsfeld zu verwenden. Beachten Sie, dass Sie dazu möglicherweise kreativ mit Ihren Kampagnen-Synchronisierungsregeln umgehen müssen, wenn dies nur für eine oder zwei Kampagnen gilt und nicht für alle.

## Synchronisieren historischer Kampagnen in [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] ist in der Lage, rückwirkend Touchpoints für Interaktionen zu generieren, die in der Vergangenheit stattgefunden haben, solange sie innerhalb von [!DNL Dynamics] in Kampagnen organisiert sind.

Dies umfasst in der Regel die Arbeit im CRM, um historische Daten zu berücksichtigen. Die Handhabung unterscheidet sich auch bei Online-Aktivitäten (die von JS verfolgt werden) und Offline-Aktivitäten (die von JS nicht verfolgt werden können).

Befolgen Sie die nachstehenden Anweisungen, um historische Daten in [!DNL Dynamics] in einem Format zu organisieren, das mit [!DNL Marketo Measure] synchronisiert werden kann.

**Online:**

Historische digitale Daten müssen in [!DNL Dynamics] Kampagnen organisiert werden, damit sie aufgestockt werden können. Idealerweise ist diese Struktur bereits vorhanden.

Wenn die Daten an einem anderen Ort gespeichert sind (z. B. noch in der Marketing-Automatisierung), müssen sie in [!DNL Dynamics] verschoben und in die entsprechenden Kampagnen organisiert werden. Dann müssen Sie das Touchpoint-Datum berücksichtigen, da Sie möchten, dass es das Datum aus der Vergangenheit widerspiegelt und nicht das Datum, an das Sie es [!DNL Dynamics] verschoben haben. Um dieses Datum zu überschreiben, können Sie das benutzerdefinierte Feld &quot;Buyer Touchpoint-Datum“ verwenden, um das Datum zu ändern. Sie müssen dies dem Marketing-Listenformular hinzufügen.

![](assets/syncing-historical-data-2.png)

Daher können Sie das Datum für alle Personen in dieser Marketing-Liste, die für das Touchpoint-Datum verwendet werden, global festlegen. Um genauere historische Daten zu erhalten, erstellen Sie mehrere Marketing-Listen für dieselbe Kampagne - jede mit einem eigenen Touchpoint-Datum. Wenn die Kampagne eine kurze Zeitspanne hat, wäre es vielleicht sinnvoll, eine Marketing-Liste für jeden Tag zu erstellen. Wenn die Kampagne eine längere Zeitspanne hat, kann es sinnvoll sein, wöchentlich eine Marketing-Liste zu erstellen.

Weitere Informationen zum Synchronisieren von Marketing-Listen finden Sie hier: [[!DNL Dynamics] Kampagnen und Marketing-Listen](/help/channel-tracking-and-setup/offline-channels/legacy-processes/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>Wenn Sie aus irgendeinem Grund eine Online-Kampagnenverfolgungs-Aktivität haben, die nach dem JavaScript-Live-Datum aktiv ist, stellen Sie sicher, dass Sie das Feld &quot;[!UICONTROL Touchpoint-Enddatum] auf das Datum setzen, an dem die JS live ging. Dadurch soll vermieden werden, dass für dieselbe Interaktion doppelte Touchpoints vorhanden sind.

Überlegungen: Online-Daten, die auf diese Weise hinzugefügt werden, sind von Natur aus weniger detailliert als Online-Daten, [!DNL Marketo Measure] über JavaScript nachverfolgt werden. Beispielsweise werden Felder wie Formular-URL, Landingpage, Referrer-Seite usw. nicht ausgefüllt. Daher wird empfohlen, die Kampagnen nach Möglichkeit in jede Quelle aufzuteilen. Im Folgenden finden Sie ein Beispiel für eine ideale Zuordnung.

| Kampagnentyp Dynamics | Kanal | Unterkanal |
|---|---|---|
| Paid Search - AdWords | Paid Search | AdWords |
| Paid Search - Bing | Paid Search | Bing |
| Bezahlte Suche - Yahoo | Paid Search | Yahoo |

Wenn Sie keine Möglichkeit haben, eine Quelle zu identifizieren, oder es die Zeit und den Aufwand nicht wert ist, können Sie einen Kampagnentyp verwenden, der einem Kanal zugeordnet ist, der so etwas wie „Legacy Digital“ oder „Historische Website“ genannt wird.

**offline:**

Um Touchpoints für Offline-Marketing-Maßnahmen aus der Vergangenheit zu haben, müssen die Daten in [!DNL Dynamics] Kampagnen organisiert und mit [!DNL Marketo Measure] synchronisiert werden. Der Prozess ist der gleiche wie für aktuelle Offline-Kanäle (die Kampagne wird über Marketing-Listen oder Kampagnenantworten synchronisiert). Nachfolgend finden Sie ein Beispiel für die Kanalzuordnung.

| Kampagnentyp Dynamics | Kanal | Unterkanal |
|---|---|---|
| Veranstaltungen - Gesponserte Konferenzen | Events | Gesponserte Konferenzen |
| Veranstaltungen - Partnerveranstaltungen | Events | Partnerveranstaltungen |
| Ereignisse - gehostete Ereignisse | Events | Gehostete Ereignisse |
| Webinar - Partner-Webinar | Webinar | Partner-Webinar |

Wenn diese Daten nicht bereits in Kampagnen mit den richtigen Datumsangaben organisiert sind, können Sie das Feld &quot;Buyer Touchpoint-Datum“ verwenden, um das genaue Datum aus der Offline-Aktivität in der Vergangenheit anzuzeigen.

