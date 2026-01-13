---
description: '[!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekten - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Felder in Standard- [!DNL Salesforce] -Objekten'
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 99%

---


# [!DNL Marketo Measure]-Felder in Standard-Objekten von[!DNL Salesforce] {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Lernen Sie die verschiedenen [!DNL Marketo Measure]-Felder kennen, die zu [!DNL Salesforce]-Standardobjekten hinzugefügt werden.

## Konto {#account}

Prädiktive Interaktionsbewertung: Dieses Feld wird in Verbindung mit unserer ABM-Funktion verwendet, um einen Wert für die Interaktion des Kontos zu ermitteln. Dabei werden viele Faktoren berücksichtigt, z. B. die Häufigkeit der Seitenaufrufe, wie viele Kontakte mit dem Konto verbunden sind, ob es ein geschlossenes Konto gibt, usw.

## Kampagne {#campaign}

Es wurden nur vier Felder hinzugefügt, dazu eine Schaltfläche und eine Validierungsregel.

UniqueID: Dieses Feld wird intern verwendet, um die verschiedenen Kampagnen zu verfolgen, mit denen [!DNL Marketo Measure] synchronisiert wird.

Aktivieren von Buyer Touchpoints: Dieses Feld ist für die tatsächliche Synchronisierung von Kampagnen für die Einbeziehung der Offline-Attribution und historischer Daten.

Touchpoint-Startdatum: Dieses Feld wird zum Festlegen eines Anfangsdatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet.

Touchpoint-Enddatum: Dieses Feld wird zum Festlegen eines Enddatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet. Ein gängiges Beispiel wäre die Einbeziehung von digitalen Kampagnen vor [!DNL Marketo Measure] und die Festlegung des Enddatums auf den Tag, an dem das Skript angewendet wurde.

Massenaktualisierung des Touchpoint-Datums (Schaltfläche): Mit dieser Schaltfläche wird das Touchpoint-Datum der Kampagnen-Mitglieder bei der Synchronisierung der Kampagne verwaltet, da wir entweder das Datum der Kampagnen-Mitgliedschaft oder das erste standardmäßige Antwortdatum referenzieren. Falls diese Datumsfelder keine genaue Darstellung des tatsächlichen Touchpoint-Datums darstellen, verwenden wir diese Schaltfläche, um das Touchpoint-Datum festzulegen.

Update der [!DNL Marketo Measure]-Attribution (Validierungsregel): Diese Regel wird nach Paketversion 6.0 nicht mehr unterstützt.

## Kampagnenmitglied {#campaign-member}

Es gibt 5 Felder und 1 Apex-Trigger, der mit dem Paket hinzugefügt wird.

Touchpoint-Status (Lead): Dies ist ein Diagnosefeld im Zusammenhang mit einer Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint für den entsprechenden Lead-Eintrag erstellt wurde und wenn nicht, warum nicht.

Touchpoint-Status (Kontakt): Dies ist ein diagnostisches Feld für eine Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Kontakteintrag erstellt wurde und wenn nicht, warum nicht.

Touchpoint-Status (Opportunity): Dies ist ein Diagnosefeld im Zusammenhang mit einer Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Opportunity-Eintrag erstellt wurde und wenn nicht, warum.

Touchpoint-Statusdatum: Dies ist das Datum, an dem die Diagnosefelder ausgefüllt wurden.

Buyer-Touchpoint-Datum: Dies steht im Zusammenhang mit der Schaltfläche [!UICONTROL Massenaktualisierung des Touchpoint-Datums] aus dem Kampagnenobjekt. Wenn dies verwendet wird, wenden wir das definierte Touchpoint-Datum auf das Kampagnen-Mitglied an.

OnCampaignMemberDelete: Standardmäßig wird [!DNL Salesforce] nicht angezeigt, wenn Kampagnenmitglieder gelöscht werden, was zu Problemen beim genauen Attributions-Reporting führen kann. Wenn ein Kampagnenmitglied gelöscht wird, wird dies ausgelöst, um [!DNL Marketo Measure] zu informieren, damit Touchpoints entfernt werden, die mit diesem nicht mehr existierenden Kampagnenmitglied verbunden sind.

## Lead {#lead}

Das Feld „Bizible-Konto“ wird für unsere Lead-zu-Konto-Zuordnung für unsere ABM-Funktion verwendet. Dieses Feld wird ausgefüllt, um die Nachschlagebeziehung zwischen den beiden Objekten zu erstellen.

## Konto {#account-1}

Dies wird für unsere Lead-zu-Konto-Zuordnung für unsere ABM-Funktion verwendet. Dieses Feld wird ausgefüllt, um die Nachschlagebeziehung zwischen den beiden Objekten zu erstellen.

## Opportunity {#opportunity}

[!DNL Marketo Measure] Opportunity-Betrag: Dieses Feld wird in dem Szenario verwendet, in dem ein benutzerdefiniertes Betragsfeld für die Opportunity verwendet wird. Wir ordnen den Wert dieses benutzerdefinierten Feldes mithilfe eines Workflows dem [!DNL Marketo Measure]-Opportunity-Betrag zu und lesen dieses Feld dann für unsere Felder zur Umsatzattribution im Objekt „Buyer Attribution Touchpoint“.

## Aktivität {#activity}

BizibleID: Hierfür müssen wir einen Touchpoint mit Aktivitäten für unsere Integration von Aktivitätsattributen und Calltracking-Metriken verknüpfen.

Buyer-Touchpoint-Datum: Dies ist ein Feld, das über einen Workflow ausgefüllt werden kann, um das Datum für die Aktivitäts-Attribution zu verwenden. Es wird für unsere Calltrackingmetrics-Integration ausgefüllt, um zu wissen, wann die Interaktion stattgefunden hat.
