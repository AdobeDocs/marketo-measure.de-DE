---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1292'
ht-degree: 2%

---

# [!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;Bizible&quot;in Ihrem CRM. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure] Felder, die zu [!DNL Salesforce] Standardobjekte

## Konto {#account}

Prädiktive Interaktionsbewertung: Dieses Feld wird mit unserer ABM-Funktion verwendet, um einen Punktstand in Bezug auf die Interaktion des Kontos bereitzustellen und viele Faktoren wie die Neuigkeit der Seitenansichten, die Anzahl der Kontakte, die mit dem Konto verbunden sind, gibt es geschlossene Kontakte usw. zu berücksichtigen.

## Fall {#case}

Wir fügen dem Groß-/Kleinschreibung-Objekt Felder zu den Meilensteinen Erstkontakt und Lead-Erstellung hinzu. Dies ist für Kunden bestimmt, die das Objekt &quot;Case&quot;anstelle von &quot;Lead&quot;oder &quot;Kontakt&quot;verwenden und außerdem eine andere Möglichkeit bieten, die Daten anzuzeigen, falls ein Kunde nicht möchte, dass wir Touchpoint-Datensätze erstellen.

Touchpoint-Quelle (FT): Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Quelle der Touch-Interaktion bei der Lead-Erstellung.

Marketing-Kanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketing-Kanal (LC): Dies ist der Marketing-Kanal der Lead-Erstellungskontakt-Interaktion.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

## Kampagne {#campaign}

Es wurden nur vier Felder hinzugefügt: eine Schaltfläche und eine Validierungsregel.

UniqueID: Dieses Feld wird intern verwendet, um die verschiedenen Kampagnen zu verfolgen, mit denen synchronisiert wird. [!DNL Marketo Measure].

Käufer-Touchpoints aktivieren: Dieses Feld dient zur tatsächlichen Synchronisierung von Kampagnen für die Einbeziehung von Offline-Attributionen und historische Daten.

Touchpoint-Startdatum: Dieses Feld wird zum Festlegen eines Anfangsdatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet.

Enddatum des Touchpoints: Dieses Feld wird zum Festlegen eines Enddatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet. Ein gemeinsames Beispiel wäre die Einbeziehung digitaler Kampagnen im Vorfeld[!DNL Marketo Measure] und legen Sie dann das Enddatum als Tag fest, an dem das Skript angewendet wurde.

Touchpoint-Datum der Massenaktualisierung (Schaltfläche): Mit dieser Schaltfläche wird das Kontaktpunktdatum der Campaign-Mitglieder bei der Synchronisierung der Kampagne verwaltet, da wir entweder das Datum der Campaign-Mitgliedschaft oder das erste standardmäßige Antwortdatum referenzieren. Falls diese Datumsfelder keine genaue Darstellung des tatsächlichen Touchpoint-Datums darstellen, verwenden wir diese Schaltfläche, um das Touchpoint-Datum festzulegen.

Aktualisieren [!DNL Marketo Measure] Attribution (Validierungsregel): Diese Regel wird nach Paketversion 6.0 nicht mehr unterstützt.

## Kampagnenmitglied {#campaign-member}

Es gibt 5 Felder und 1 Apex-Trigger, der mit dem Paket hinzugefügt wird.

Touchpoint-Status (Lead): Dies ist ein Diagnosefeld im Zusammenhang mit einer Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Lead-Datensatz erstellt wurde oder warum nicht.

Touchpoint-Status (Kontakt): Dies ist ein diagnostisches Feld für eine Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Kontaktdatensatz erstellt wurde oder warum nicht.

Touchpoint-Status (Möglichkeit): Dies ist ein Diagnosefeld im Zusammenhang mit einer Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Opportunity-Datensatz erstellt wurde oder warum nicht.

Touchpoint-Statusdatum: Dies ist das Datum, an dem die Diagnosefelder ausgefüllt wurden.

Touchpoint-Datum des Käufers: Dies bezieht sich auf das [!UICONTROL Bulk Update Touchpoint-Datum] im Campaign-Objekt. Wenn dies verwendet wird, wenden wir das definierte Touchpoint-Datum auf das Campaign-Mitglied an.

OnCampaignMemberDelete: Vorkonfiguriert, [!DNL Salesforce] wird nicht angezeigt, wenn Campaign-Mitglieder gelöscht werden, was Probleme mit präzisen Attributionsberichten verursachen kann. Wenn ein Campaign-Mitglied gelöscht wird, wird dies ausgelöst, um [!DNL Marketo Measure] um Touchpoints zu entfernen, die sich auf dieses nicht vorhandene Campaign-Mitglied beziehen.

## Kontakt {#contact}

Wir fügen dem Kontaktobjekt Felder für die Meilensteine Erstkontakt und Lead-Erstellung hinzu. Dies ist für Kunden vorgesehen, die die Attribution lieber direkt in Felder übertragen möchten, anstatt Touchpoint-Datensätze zu erstellen. Die meisten unserer Kunden nutzen die Touchpoint-Record-Route, aber auch diese Felder innerhalb ihrer Automatisierungsplattform.

Touchpoint-Quelle (FT): Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Quelle der Touch-Interaktion bei der Lead-Erstellung.

Marketing-Kanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketing-Kanal (LC): Dies ist der Marketing-Kanal der Lead-Erstellungskontakt-Interaktion.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

BizibleID: Diese wird im Zusammenhang mit der Integration unserer Aktivitätszuordnung und Calltrackingmetriken für die Kontaktverknüpfung mit dem Touchpoint verwendet.

## Lead {#lead}

Wir fügen dem Lead-Objekt Felder hinzu, die sich auf die Meilensteine Erstkontakt und Lead-Erstellung beziehen. Dies ist für Kunden vorgesehen, die die Attribution lieber direkt in Felder übertragen möchten, anstatt Touchpoint-Datensätze zu erstellen. Die meisten unserer Kunden nutzen die Touchpoint-Record-Route, aber auch diese Felder innerhalb ihrer Automatisierungsplattform.

Touchpoint-Quelle (FT): Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Quelle der Touch-Interaktion bei der Lead-Erstellung.

Marketing-Kanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketing-Kanal (LC): Dies ist der Marketing-Kanal der Lead-Erstellungskontakt-Interaktion.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Lead-Erstellungskontakt-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der Lead-Erstellungskontakt-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

BizibleID: Diese wird im Zusammenhang mit der Integration unserer Aktivitätszuordnung und Calltrackingmetriken für die Lead-Zuordnung zum Touchpoint verwendet.

## Konto {#account-1}

Dies wird für unser Mapping Lead-zu-Konto für unsere ABM-Funktion verwendet. Dieses Feld wird ausgefüllt, um die Nachschlagebeziehung zwischen den beiden Objekten zu erstellen.

## Opportunity {#opportunity}

[!DNL Marketo Measure] Opportunity Amount: Dieses Feld wird in dem Szenario verwendet, in dem ein benutzerdefiniertes Zahlenfeld für die Option verwendet wird. Wir ordnen diesen benutzerdefinierten Feldwert zu [!DNL Marketo Measure] Opportunity Amount using a workflow, and then read this field for our Revenue attribution fields on the Buyer Attribution Touchpoint object.

## Aktivität {#activity}

BizibleID: Hierfür müssen wir einen Touchpoint mit Aktivitäten für unsere Integration von Aktivitätsattributen und Calltracking-Metriken verknüpfen.

Touchpoint-Datum des Käufers: Dies ist ein Feld, das über einen Workflow ausgefüllt werden kann, der als Datum für die Aktivitätszuordnung verwendet wird. Es wird für unsere Integration von Aufruffetmetriken gefüllt, um zu erfahren, wann die Interaktion stattgefunden hat.
