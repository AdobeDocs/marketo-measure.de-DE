---
unique-page-id: 18874684
description: Kampagnensynchronisierungsdaten - [!DNL Marketo Measure]
title: Kampagnensynchronisierungsdaten
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Kampagnensynchronisierungsdaten {#campaign-sync-dates}

Erfahren Sie mehr über die Funktion &quot;Daten zur Kampagnensynchronisierung&quot;und bieten Sie einige Anwendungsfälle für diese Funktion an.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir empfehlen Benutzern, die [neuer, verbesserter In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

**[!DNL Marketo Measure]Paket erforderlich: 6.9 oder höher**

Diese Funktion besteht aus zwei einfachen Datumsfeldern auf der [!DNL Salesforce] Kampagnenobjekt:

* Startdatum des Touchpoints
* Enddatum des Touchpoints

Sobald die Touchpoints des Käufers für eine bestimmte Kampagne aktiviert sind, können Sie mit den Datumsangaben zur Kampagnensynchronisierung die Parameter für das Touchpoint-Datum in der jeweiligen Kampagne festlegen. Wenn Sie also ein Touchpoint-Enddatum vom 1. März 2017 hinzufügen würden, dann [!DNL Marketo Measure] erstellt Touchpoints nur für Campaign-Mitglieder, die der Kampagne vor diesem Datum hinzugefügt wurden. [!DNL Marketo Measure] erstellt keine Touchpoints für Kampagnenmitglieder, die nach dem 1. März 2017 hinzugefügt wurden.

![](assets/1.gif)

Wenn Sie in einer Kampagne ein Touchpoint-Startdatum hinzufügen würden (z. B. 1. Januar 2017), dann [!DNL Marketo Measure] erstellt keine Touchpoints für Campaign-Mitglieder, die vor dem 1. Januar 2017 zur Kampagne hinzugefügt wurden. Sie müssen kein Touchpoint-Startdatum hinzufügen, wenn Sie ein Touchpoint-Enddatum hinzufügen und umgekehrt.

## Anwendungsfälle {#use-cases}

**Touchpoints zurückfüllen**

Manchmal kann es vorkommen, dass ein Marketing-Team die Hinzufügung von utm -Parametern zu einer bestimmten Marketing-Maßnahme verpasst. Mit den Datumsangaben zur Kampagnensynchronisierung können Sie (wenn Sie SFDC-Kampagnen für Online-Bemühungen verwenden) einige verpasste Daten zurückfüllen. Nehmen wir an, Sie führen eine E-Mail-Kampagne aus, die am 1. Mai begonnen hat. Ihr Team hat jedoch bis zum 15. Mai in dieser E-Mail-Kampagne keine utm-Parameter hinzugefügt. Wenn Sie E-Mail-Konversionen über eine SFDC-Kampagne verfolgen, können Sie für diese Kampagne ein Touchpoint-Enddatum des 15. Mai festlegen und Touchpoints für &quot;Respondierte&quot;Mitglieder der Kampagne aktivieren. Diese Aktion zeigt Folgendes an: [!DNL Marketo Measure] um Touchpoints für alle Antworten bis zum 15. Mai zu erstellen.

**Touchpoints der rückwirkenden Kampagnenmitgliedschaft**

Wenn Sie ein neues [!DNL Marketo Measure] -Kunde, können Sie daran interessiert sein, einige der Marketing-Daten einzubringen, die Sie über SFDC-Kampagnen verfolgt haben. Wenn Sie jedoch Touchpoints für Ihre Online-SFDC-Kampagnen aktivieren würden, könnte es zu einer doppelten Zählung kommen, da [!DNL Marketo Measure] erstellt automatisch Touchpoints für Ihre Online-Marketing-Maßnahmen. Um eine doppelte Zählung der Daten zu vermeiden, können Sie mithilfe von Campaign Touchpoint-Enddaten eine Begrenzung für die Touchpoint-Daten festlegen, die von [!DNL Marketo Measure] in der SFDC-Kampagne. Wenn Sie beispielsweise rückwirkende Konversionen für eine Social-Kampagne hinzufügen möchten, die Sie in SFDC verfolgt haben, wissen Sie jedoch, dass Sie die [!DNL Marketo Measure] JavaScript (zur Erstellung von Online-Touchpoints) am 1. Juli können Sie die Social SFDC-Kampagne bearbeiten, um ein Touchpoint-Enddatum zu enthalten, das dem 1. Juli entspricht, und Käufer-Touchpoints für diese Kampagne aktivieren.

Es kann viele andere Anwendungsfälle für Touchpoint-Enddaten geben. Wenn Sie Hilfe bei der Ermittlung einer bestimmten Situation benötigen, wenden Sie sich bitte an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
