---
description: Kampagnensynchronisierungstermine - [!DNL Marketo Measure]
title: Kampagnensynchronisierungsdaten
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 5%

---


# Kampagnensynchronisierungsdaten {#campaign-sync-dates}

Erfahren Sie, was die Funktion Synchronisierungstermine in Campaign bewirkt und bieten Sie einige Anwendungsfälle für diese Funktion.

>[!NOTE]
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

**[!DNL Marketo Measure]Paket erforderlich: 6.9 oder höher**

Diese Funktion besteht aus zwei einfachen Datumsfeldern im [!DNL Salesforce] Campaign-Objekt:

* Touchpoint-Startdatum
* Touchpoint-Enddatum

Sobald Käufer-Touchpoints für eine bestimmte Kampagne aktiviert sind, können Sie bei Kampagnensynchronisierungsterminen Touchpoint-Datumsparameter für die jeweilige Kampagne festlegen. Wenn Sie also ein Touchpoint-Enddatum vom 1. März 2017 hinzufügen, erstellt [!DNL Marketo Measure] nur Touchpoints für Kampagnenmitglieder, die vor diesem Datum zur Kampagne hinzugefügt wurden. [!DNL Marketo Measure] werden keine Touchpoints für Kampagnenmitglieder erstellen, die nach dem 1. März 2017 hinzugefügt wurden.

![Salesforce-Kampagne mit den Feldern „Touchpoint-Startdatum“ und „Enddatum“](assets/1.gif)

Wenn Sie einer Kampagne ein Touchpoint-Startdatum hinzufügen (z. B. am 1. Januar 2017), erstellen [!DNL Marketo Measure] auch keine Touchpoints für Kampagnenmitglieder, die der Kampagne vor dem 1. Januar 2017 hinzugefügt wurden. Sie müssen kein Touchpoint-Startdatum hinzufügen, wenn Sie ein Touchpoint-Enddatum hinzufügen, und umgekehrt.

## Anwendungsszenarien {#use-cases}

**Aufstockung der Touchpoints**

Es kann vorkommen, dass es einem Marketing-Team nicht gelingt, zu einem bestimmten Marketing-Aufwand UTM-Parameter hinzuzufügen. Mit Synchronisierungsterminen für Kampagnen können Sie (wenn Sie SFDC-Kampagnen für Online-Aktivitäten verwenden) einige verpasste Daten aufstocken. Angenommen, Sie führen eine E-Mail-Kampagne aus, die am 1. Mai begonnen hat, aber Ihr Team hat erst am 15. Mai UTM-Parameter zu dieser E-Mail-Kampagne hinzugefügt. Wenn Sie E-Mail-Konversionen über eine SFDC-Kampagne verfolgen, können Sie für diese Kampagne das Enddatum des 15. Mai festlegen und Touchpoints für „Responded“-Kampagnenmitglieder aktivieren. Diese Aktion weist [!DNL Marketo Measure] an, für alle diese Antworten bis zum 15. Mai Touchpoints zu erstellen.

**Rückwirkende Touchpoints für Kampagnenmitgliedschaften**

Wenn Sie Neukunde von [!DNL Marketo Measure] sind, möchten Sie möglicherweise einige der Marketing-Daten mitbringen, die Sie über SFDC Campaign verfolgt haben. Wenn Sie jedoch Touchpoints für Ihre Online-SFDC-Kampagnen aktivieren, könnte dies das Problem der doppelten Zählung der Attribution verursachen, da [!DNL Marketo Measure] automatisch Touchpoints für Ihre Online-Marketing-Maßnahmen erstellt. Um eine doppelte Zählung von Daten zu vermeiden, können Sie mithilfe der Touchpoint-Enddaten von Campaign eine Begrenzung für die Touchpoint-Daten festlegen, die von [!DNL Marketo Measure] in der SFDC-Kampagne erstellt wurden. Wenn Sie beispielsweise rückwirkende Konversionen für eine Social-Media-Kampagne hinzufügen möchten, die Sie in SFDC verfolgt haben, aber Sie wissen, dass Sie am 1. Juli die [!DNL Marketo Measure] JavaScript hinzugefügt haben (die Online-Touchpoints erstellt), können Sie die Social-Media-SFDC-Kampagne so bearbeiten, dass sie ein Touchpoint-Enddatum enthält, das dem 1. Juli entspricht, und Buyer-Touchpoints für diese Kampagne aktivieren.

Es kann viele weitere Anwendungsfälle für Touchpoint-Enddaten geben. Wenn Sie Hilfe beim Ermitteln einer bestimmten Situation benötigen, wenden Sie sich bitte an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
