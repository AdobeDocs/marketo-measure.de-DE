---
unique-page-id: 42762310
description: Synchronisieren historischer Daten - [!DNL Marketo Measure] - Produktdokumentation
title: Synchronisieren historischer Daten
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 2%

---

# Synchronisieren historischer Daten {#syncing-historical-data}

[!DNL Marketo Measure] ist eine Lösung, die die detailliertesten und umsetzbaren Daten bereitstellt. Wir wissen jedoch, dass Sie möglicherweise vorhandene Daten haben, für die Sie eine Attribution vornehmen möchten. Es ist möglich, Touchpoints für historische Daten zu generieren, aber es ist wichtig, einige Faktoren zu berücksichtigen, bevor Sie diesen Prozess vorantreiben.

## Zu berücksichtigende Faktoren {#factors-to-consider}

**Sind die Daten bereits in Kampagnen organisiert?**

a. Die Daten müssen in Kampagnen unterteilt werden, damit sie synchronisiert werden können [!DNL Marketo Measure] um Touchpoints zu generieren. Wenn sie derzeit nicht in Kampagnen organisiert ist, möchten Sie bewerten, ob es sich lohnt, die Zeit und die Ressourcen zu nutzen, die zur Segmentierung der Daten in die entsprechenden Kampagnen erforderlich sind.

b. Das Datum, an dem das Mitglied zur Kampagne hinzugefügt oder als beantwortet markiert wurde, wird für das Touchpoint-Datum verwendet, daher muss dies ebenfalls korrekt sein. [!DNL Marketo Measure] bietet Problemumgehungen sowohl in SFDC als auch in MSD, um die Daten zu aktualisieren. Dies kann jedoch je nach Volumen zeitaufwendig sein.

**Ist die Menge an Daten, die in Kampagnen für alle Kanäle (Paid Search, Ereignisse, organische Inhalte usw.) zusammengefasst wird, ziemlich gleich?**

Es ist wichtig, ein ausgewogenes Bild der Attribution zu haben, um eine genaue und &quot;faire&quot;Berichterstattung zu erhalten. Wenn Sie beispielsweise nur Daten für historische Offline-Kanal-Bemühungen wie Ereignisse haben, werden die Daten von Natur aus in die Richtung geleitet, ohne dass historische Online-Daten diese ergänzen.

**Welche Granularität erwarten Sie?**

Im Grunde kennen Sie nur den Kanal-, Unterkanal- und Kampagnennamen.

**Welche Berichtsziele verfolgen Sie in Zukunft?**

Diese Daten werden begrenzt sein, daher ist es wichtig zu überlegen, wie Sie sie verwenden möchten. Es ist möglicherweise nicht sehr sinnvoll, historische Daten mit zukünftigen Daten zu vergleichen.

**Wie weit willst du zurück?**

[!DNL Marketo Measure] empfiehlt dringend, nicht über das Vorjahr hinauszugehen.

Dies ist ein Thema, das wir mit Ihnen [!DNL Marketo Measure] Kontakt zuerst. Wenn Sie sich mit dem oben stehenden Szenario befasst haben und fortfahren möchten, werden allgemeine Anweisungen (getrennt für [!DNL Salesforce] und [!DNL Microsoft Dynamics]) unten.

## Synchronisieren historischer Kampagnen in [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**Online:**

Um historische Online-Daten zu synchronisieren, müssen die Daten in Salesforce-Kampagnen organisiert sein, mit denen Sie dann synchronisieren [!DNL Marketo Measure] via [!DNL Salesforce] Kampagnensynchronisierungsregeln im [!DNL Marketo Measure] App. Es ist wichtig sicherzustellen, dass Touchpoints nach dem Datum, an dem Ihr JavaScript live geschaltet wurde, nicht aus diesen Kampagnen generiert werden. Der Grund dafür ist, dass doppelte Touchpoints vermieden werden. Nachdem das JavaScript live ist, werden Online-Bemühungen automatisch verfolgt, sodass wir sie nicht auch über eine SFDC-Kampagne verfolgen möchten. Um dieses Problem zu vermeiden, sollten Sie der Regel unbedingt ein Gefühl der Zeit hinzufügen. Vielleicht etwas wie &quot;Das Erstellungsdatum eines Kampagnenmitglieds ist kleiner als [Go-Live-Datum für JavaScript]&quot;.

![](assets/syncing-historical-data-1.png)

Die Kanalzuordnungskomponente für historische Online-Daten kann etwas schwierig sein. Wir möchten, dass Ihre aktuellen Online-Kanalregeln (aus dem Online-Regelblatt) so genau wie möglich übereinstimmen, um eine saubere Berichterstellung zu ermöglichen. Unten finden Sie ein Beispiel für die ideale Kanalzuordnung.

>[!NOTE]
>
>Diese Kanalzuordnung erfolgt im [!UICONTROL Offline-Kanäle] Abschnitt [!DNL Marketo Measure] App verwenden, da wir SFDC-Kampagnen verwenden.

| Salesforce-Kampagnentyp | Kanal | Unterkanal |
|---|---|---|
| Paid Search - AdWords | Bezahlte Suchergebnisse | AdWords |
| Paid Search - Bing | Bezahlte Suchergebnisse | Bing |
| Paid Search - Yahoo | Bezahlte Suchergebnisse | Yahoo |

Auf diese Weise hinzugefügte Online-Daten sind von Natur aus weniger granular als Online-Daten. [!DNL Marketo Measure] verfolgt über JavaScript. Beispielsweise werden Felder wie Formular-URL, Landingpage, Referrer-Seite usw. nicht ausgefüllt. Daher wird empfohlen, die Kampagnen nach Möglichkeit in jede Quelle zu unterteilen. Wie im obigen Beispiel gezeigt, müssen Sie für jede Quelle mehrere Kampagnentypen haben, um eine granularere Berichterstellung zu erhalten.

Möglicherweise ist es nicht möglich oder sinnvoll, die Anzahl der SFDC-Kampagnentypen festzulegen, um eine granulare Kanalzuordnung zu unterstützen. Daher können Sie einfach auf die Kanalebene zurückgreifen und untergeordnete Kanäle ignorieren. Wenn auch die Kanalebene nicht bekannt ist, können Sie einen Proxy-Kanal wie &quot;Historische Digitale Daten&quot;einrichten, damit Sie zumindest wissen, dass es sich um einen Online-Kontakt handelt.

Wenn Sie das Kontaktpunktdatum, das für diese historischen Online-Bemühungen gepusht wird, in großem Umfang bearbeiten müssen, verwenden Sie bitte die [!DNL Marketo Measure] custom &quot;[!UICONTROL Touchpoint-Datum für Massenaktualisierung]&quot;(Dies ist als benutzerdefiniertes Feld im Campaign-Objekt in SFDC verfügbar). Wenn die Kampagne eine kurze Zeitspanne hat, wäre es möglicherweise sinnvoll, das Touchpoint-Datum in einem täglichen Tagesintervall gebündelt zu bearbeiten. Es kann jedoch sinnvoll sein, eine wöchentliche Massenaktualisierung vorzunehmen, wenn die Kampagne eine längere Zeitspanne hat. Wenn Sie die Funktion &quot;Touchpoint-Datum-Massenaktualisierung&quot;nutzen, aktualisieren Sie die Kampagnensynchronisierungsregel, um das &quot;Touchpoint-Datum des Käufers&quot;im Datumsfeld zu verwenden. Beachten Sie, dass dazu möglicherweise kreative Elemente mit Ihren Kampagnensynchronisierungsregeln verwendet werden müssen, wenn dies nur für eine Kampagne oder zwei und nicht alle gilt.

**Offline:**

Historische Daten zu Offline-Marketing-Maßnahmen (die nicht über JavaScript verfolgt werden können) müssen ebenfalls in SFDC-Kampagnen organisiert werden. SFDC-Kampagnen sind der richtige Weg [!DNL Marketo Measure] verfolgt Offline-Bemühungen, unabhängig davon, ob es sich bei der Aktivität um eine &quot;historische&quot;oder eine &quot;aktuelle/Post-Aktivität&quot;handelt.[!DNL Marketo Measure] Implementierung&quot;folgen Sie demselben Kanal-Mapping, das Sie im ursprünglichen Offline-Kanal-Konfigurationstraining ausgewählt haben.

Verwenden Sie bei Bedarf die Schaltfläche &quot;Touchpoint-Datum-Massenaktualisierung&quot;, um das Touchpoint-Datum für Kampagnenmitglieder in großem Umfang zu bearbeiten. Wenn Sie beispielsweise nach dem Eintreten des Ereignisses SFDC-Kampagnen erstellen, sollten Sie die Massenbearbeitung für das richtige Datum durchführen. Wenn Sie die Funktion &quot;Touchpoint-Datum-Massenaktualisierung&quot;nutzen, aktualisieren Sie die Kampagnensynchronisierungsregel, um das &quot;Touchpoint-Datum des Käufers&quot;im Datumsfeld zu verwenden. Beachten Sie, dass dazu möglicherweise kreative Elemente mit Ihren Kampagnensynchronisierungsregeln verwendet werden müssen, wenn dies nur für eine Kampagne oder zwei und nicht alle gilt.

## Synchronisieren historischer Kampagnen in [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] kann rückwirkend Touchpoints für in der Vergangenheit aufgetretene Interaktionen generieren, sofern diese in Kampagnen innerhalb von [!DNL Dynamics].

Dies erfordert in der Regel die Arbeit im CRM, um historische Daten zu berücksichtigen. Die Handhabung unterscheidet sich auch bei Online-Bemühungen (verfolgt von JS) und Offline-Bemühungen (kann nicht von JS verfolgt werden).

Befolgen Sie die unten stehenden Anweisungen zum Organisieren von historischen Daten in [!DNL Dynamics] in einem Format, mit dem synchronisiert werden kann [!DNL Marketo Measure].

**Online:**

Historische digitale Daten müssen in [!DNL Dynamics] Kampagnen, um aufgestockt zu werden. Idealerweise ist diese Struktur bereits vorhanden.

Wenn die Daten an einem anderen Ort gespeichert sind (z. B. noch in der Marketing Automation), müssen sie in [!DNL Dynamics] und in die entsprechenden Kampagnen organisiert. Dann müssen Sie das Touchpoint-Datum berücksichtigen, da es das Datum der Vergangenheit widerspiegeln soll, nicht das Datum, an das Sie es gesendet haben [!DNL Dynamics]. Um dieses Datum zu überschreiben, können Sie das benutzerdefinierte Feld &quot;Touchpoint-Datum des Käufers&quot;verwenden, um das Datum zu ändern. Sie müssen dies dem Marketinglisten-Formular hinzufügen.

![](assets/syncing-historical-data-2.png)

Daher können Sie das Datum für alle Benutzer in dieser Marketingliste, die für das Touchpoint-Datum verwendet werden, in der Masse festlegen. Um genauere historische Daten zu erhalten, erstellen Sie mehrere Marketing-Listen für dieselbe Kampagne, von denen jede über ein eigenes Touchpoint-Datum verfügt. Wenn die Kampagne eine kurze Zeitspanne hat, wäre es möglicherweise sinnvoll, für jeden Tag eine Marketingliste zu erstellen. Wenn die Kampagne eine längere Zeitspanne hat, kann es sinnvoll sein, wöchentlich eine Marketingliste zu erstellen.

Weitere Informationen zur Synchronisierung von Marketinglisten finden Sie hier: [[!DNL Dynamics] Kampagnen und Marketinglisten](/help/marketo-measure-and-dynamics/dynamics-reporting/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>Wenn Sie aus irgendeinem Grund eine Kampagnen-Tracking-Online-Aktivität haben, die nach dem JavaScript-Live-Datum aktiv ist, stellen Sie sicher, dass Sie die[!UICONTROL Enddatum des Touchpoints]&quot; bis zum Datum, an dem das JS live geschaltet wurde. Dadurch soll verhindert werden, dass für dieselbe Interaktion doppelte Touchpoints vorhanden sind.

Überlegungen: Auf diese Weise hinzugefügte Online-Daten sind von Natur aus weniger detailliert als Online-Daten. [!DNL Marketo Measure] verfolgt über JavaScript. Beispielsweise werden Felder wie Formular-URL, Landingpage, Referrer-Seite usw. nicht ausgefüllt. Daher wird empfohlen, die Kampagnen nach Möglichkeit in jede Quelle zu unterteilen. Nachfolgend finden Sie ein Beispiel für eine ideale Zuordnung.

| Dynamics-Kampagnentyp | Kanal | Unterkanal |
|---|---|---|
| Paid Search - AdWords | Bezahlte Suchergebnisse | AdWords |
| Paid Search - Bing | Bezahlte Suchergebnisse | Bing |
| Paid Search - Yahoo | Bezahlte Suchergebnisse | Yahoo |

Wenn Sie keine Möglichkeit haben, eine Quelle zu identifizieren, oder es sich nicht lohnt, die Zeit und Mühe aufzuwenden, können Sie einen Kampagnentyp verwenden, der einem Kanal zugeordnet ist, der z. B. &quot;Legacy Digital&quot; oder &quot;Historische Website&quot; heißt.

**Offline:**

Um Touchpoints für Offline-Marketing-Maßnahmen aus der Vergangenheit zu haben, müssen die Daten in [!DNL Dynamics] Kampagnen und synchronisiert mit [!DNL Marketo Measure]. Der Prozess entspricht dem für aktuelle Offline-Kanäle (Synchronisieren der Kampagne über Marketinglisten oder Kampagnenantworten). Nachfolgend finden Sie ein Beispiel für die Kanalzuordnung.

| Dynamics-Kampagnentyp | Kanal | Unterkanal |
|---|---|---|
| Veranstaltungen - gesponserte Konferenzen | Ereignisse | Gesponserte Konferenzen |
| Ereignisse - Partnerereignisse | Ereignisse | Partnerereignisse |
| Ereignisse - gehostete Ereignisse | Ereignisse | Gehostete Ereignisse |
| Webinar - Partner-Webinar | Webinar | Partner-Webinar |

Wenn diese Daten nicht bereits in Kampagnen mit den richtigen Datumswerten organisiert sind, können Sie das Feld &quot;Touchpoint-Datum des Käufers&quot;verwenden, um das genaue Datum aus der Offline-Aktivität in der Vergangenheit widerzuspiegeln.

