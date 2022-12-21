---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 0%

---

# [!DNL Marketo Measure] Felder in Standard [!DNL Salesforce] Objekte {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen angezeigt, die[!DNL Marketo Measure]&quot; in unserer Dokumentation, sehen aber immer noch &quot;Bizible&quot; in Ihrem CRM. Wir arbeiten daran, diese Aktualisierung durchzuführen, und das Rebranding wird sich in Kürze in Ihrem CRM widerspiegeln.

Erfahren Sie mehr über die verschiedenen [!DNL Marketo Measure] Felder, die zu [!DNL Salesforce] Standardobjekte.

## Konto {#account}

Prädiktive Interaktionsbewertung: Dieses Feld wird mit unserer ABM-Funktion verwendet, um einen Punktstand in Bezug auf die Interaktion des Kontos bereitzustellen, und berücksichtigt viele Faktoren wie die Neuigkeit der Seitenansichten, die Anzahl der Kontakte, die mit dem Konto verbunden sind, gibt es eine geschlossene Opp-Funktion usw.

## Fall {#case}

Wir fügen dem Groß-/Kleinschreibung-Objekt Felder zu den Meilensteinen Erstkontakt und Lead-Erstellung hinzu. Dies ist für Kunden bestimmt, die das Objekt &quot;Case&quot;anstelle von &quot;Lead&quot;oder &quot;Kontakt&quot;verwenden und außerdem eine andere Möglichkeit bieten, die Daten anzuzeigen, falls ein Kunde nicht möchte, dass wir Touchpoint-Datensätze erstellen.

Touchpoint-Quelle (FT): Dies ist die Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Dies ist die Quelle der Touchinteraktion bei der Lead-Erstellung.

Marketingkanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketingkanal (LC): Dies ist der Marketing-Kanal der Touch-Interaktion bei der Lead-Erstellung.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

## Kampagne {#campaign}

Es wurden nur vier Felder hinzugefügt: eine Schaltfläche und eine Validierungsregel.

UniqueID: Dieses Feld wird intern verwendet, um die verschiedenen Kampagnen zu verfolgen, mit denen synchronisiert wird. [!DNL Marketo Measure].

Käufer-Touchpoints aktivieren: Dieses Feld dient zur tatsächlichen Synchronisierung von Kampagnen für die Einbeziehung von Offline-Attributen und historischen Daten.

Touchpoint-Startdatum: Dieses Feld wird zum Festlegen eines Anfangsdatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet.

Touchpoint-Enddatum: Dieses Feld wird zum Festlegen eines Enddatums für die Anwendung von Touchpoints auf historische Kampagnen verwendet. Ein gemeinsames Beispiel wäre die Einbeziehung digitaler Kampagnen im Vorfeld[!DNL Marketo Measure] und legen Sie dann das Enddatum als Tag fest, an dem das Skript angewendet wurde.

Massen-Update-Touchpoint-Datum (Schaltfläche): Diese Schaltfläche dient zur Verwaltung des Kontaktpunktdatums der Campaign-Mitglieder bei der Synchronisation der Kampagne, da wir entweder das Datum der Campaign-Mitgliedschaft oder das erste standardmäßige Antwortdatum referenzieren. Falls diese Datumsfelder keine genaue Darstellung des tatsächlichen Touchpoint-Datums darstellen, verwenden wir diese Schaltfläche, um das Touchpoint-Datum festzulegen.

Aktualisieren [!DNL Marketo Measure] Attribution (Validierungsregel): Diese Regel wird nach der Paketversion 6.0 nicht mehr unterstützt.

## Kampagnenmitglied {#campaign-member}

Es gibt 5 Felder und 1 Apex-Trigger, der mit dem Paket hinzugefügt wird.

Touchpoint-Status (Lead): Dies ist ein diagnostisches Feld für eine Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Lead-Datensatz erstellt wurde oder warum nicht.

Touchpoint-Status (Kontakt): Dies ist ein diagnostisches Feld für eine Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Kontaktdatensatz erstellt wurde oder warum nicht.

Touchpoint-Status (Möglichkeit): Dies ist ein diagnostisches Feld für eine Funktion, die nicht standardmäßig aktiviert ist. Wir verwenden dies, um zu verstehen, ob ein Touchpoint mit dem zugehörigen Opportunity-Datensatz erstellt wurde oder warum nicht.

Touchpoint-Statusdatum: Dies ist das Datum, an dem die diagnostischen Felder ausgefüllt wurden.

Touchpoint-Datum des Käufers: Dies hängt mit dem [!UICONTROL Bulk Update Touchpoint-Datum] im Campaign-Objekt. Wenn dies verwendet wird, wenden wir das definierte Touchpoint-Datum auf das Campaign-Mitglied an.

OnCampaignMemberDelete: Vorkonfiguriert, [!DNL Salesforce] wird nicht angezeigt, wenn Campaign-Mitglieder gelöscht werden, was Probleme mit präzisen Attributionsberichten verursachen kann. Wenn ein Campaign-Mitglied gelöscht wird, wird dies ausgelöst, um [!DNL Marketo Measure] um Touchpoints zu entfernen, die sich auf dieses nicht vorhandene Campaign-Mitglied beziehen.

## Kontakt {#contact}

Wir fügen dem Kontaktobjekt Felder für die Meilensteine Erstkontakt und Lead-Erstellung hinzu. Dies ist für Kunden vorgesehen, die die Attribution lieber direkt in Felder übertragen möchten, anstatt Touchpoint-Datensätze zu erstellen. Die meisten unserer Kunden nutzen die Touchpoint-Record-Route, aber auch diese Felder innerhalb ihrer Automatisierungsplattform.

Touchpoint-Quelle (FT): Dies ist die Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Dies ist die Quelle der Touchinteraktion bei der Lead-Erstellung.

Marketingkanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketingkanal (LC): Dies ist der Marketing-Kanal der Touch-Interaktion bei der Lead-Erstellung.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der [!UICONTROL Lead-Erstellung] Touch-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

BizibleID: Dies wird im Zusammenhang mit unserer Aktivitätszuordnung und der Integration von Calltrackingmetriken für die Kontaktverknüpfung mit dem Touchpoint verwendet.

## Lead {#lead}

Wir fügen dem Lead-Objekt Felder hinzu, die sich auf die Meilensteine Erstkontakt und Lead-Erstellung beziehen. Dies ist für Kunden vorgesehen, die die Attribution lieber direkt in Felder übertragen möchten, anstatt Touchpoint-Datensätze zu erstellen. Die meisten unserer Kunden nutzen die Touchpoint-Record-Route, aber auch diese Felder innerhalb ihrer Automatisierungsplattform.

Touchpoint-Quelle (FT): Dies ist die Quelle der Erstkontakt-Interaktion.

Touchpoint-Quelle (LC): Dies ist die Quelle der Touchinteraktion bei der Lead-Erstellung.

Marketingkanal (FT): Dies ist der Marketingkanal der Erstkontakt-Interaktion.

Marketingkanal (LC): Dies ist der Marketing-Kanal der Touch-Interaktion bei der Lead-Erstellung.

Anzeigenkampagnenname (FT): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Erstkontakt-Interaktion.

Anzeigenkampagnenname (LC): Dies ist die UTM-Kampagne, Anzeigenkampagne aus den Werbenetzwerken oder [!DNL Salesforce] Kampagne der Lead-Erstellungs-Touch-Interaktion.

Landingpage (FT): Dies ist die Landingpage der Erstkontakt-Interaktion.

Landingpage (LC): Dies ist die Landingpage der Lead-Erstellungskontakt-Interaktion.

Touchpoint-Datum (FT): Dies ist das Datum der Erstkontakt-Interaktion.

Touchpoint-Datum (LC): Dies ist das Datum der Interaktion mit dem Lead-Erstellungskontakt.

BizibleID: Dies wird im Zusammenhang mit unserer Aktivitätszuordnung und der Integration von Calltrackingmetriken für die Lead-Zuordnung zum Touchpoint verwendet.

## Konto {#account-1}

Dies wird für unser Mapping Lead-zu-Konto für unsere ABM-Funktion verwendet. Dieses Feld wird ausgefüllt, um die Nachschlagebeziehung zwischen den beiden Objekten zu erstellen.

## Chance {#opportunity}

[!DNL Marketo Measure] Opportunity Amount: Dieses Feld wird in dem Szenario verwendet, in dem ein benutzerdefiniertes Zahlenfeld für die Option genutzt wird. Wir ordnen diesen benutzerdefinierten Feldwert zu [!DNL Marketo Measure] Opportunity Amount using a workflow, and then read this field for our Revenue attribution fields on the Buyer Attribution Touchpoint object.

## Aktivität {#activity}

BizibleID: Dies ist für uns erforderlich, einen Touchpoint mit Aktivitäten für die Integration von Aktivitätsattributen und Calltracking-Metriken zu verknüpfen.

Touchpoint-Datum des Käufers: Dies ist ein Feld, das über einen Workflow ausgefüllt werden kann, um es als Datum für die Aktivitätszuordnung zu verwenden. Es wird für unsere Integration von Aufruffeteriken gefüllt, um zu erfahren, wann die Interaktion stattgefunden hat.
