---
description: Best Practices für API-Verbindungen - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für API-Verbindungen
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---

# Best Practices für API-Verbindungen {#best-practices-for-api-connections}

## Überblick {#overview}

[!DNL Marketo Measure] bietet API-Verbindungen mit [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]und LinkedIn. Diese API-Verbindungen ermöglichen [!DNL Marketo Measure] , um eine Vielzahl von Daten aus Ihren Anzeigenplattformen abzurufen, auf die dann in Ihren Kunden-Touchpoint-Daten berichtet werden kann. Eine wichtige Funktion dieser API-Verbindungen ist die Möglichkeit, Ausgabedaten automatisch abzurufen, wodurch Sie und Ihr Team Zeit und Mühe sparen, um Daten manuell für die ROI-Berichterstellung hochzuladen. Das Einrichten dieser API-Verbindungen ist für [!DNL Marketo Measure] um diese Kanäle zu verfolgen, sie bieten jedoch wertvolle detaillierte Details, die Ihre Berichterstellung verbessern.

Die [!DNL Marketo Measure] API-Verbindungen sind ein unschätzbarer Aspekt Ihres Kontos. Unsere Best Practices-Empfehlungen helfen Ihnen und Ihrem Team dabei, unsere Verbindungen umfassend zu nutzen.

## Best Practice {#best-practice}

Unabhängig von der Werbeplattform, die Sie verbinden, sollten Sie die folgenden Richtlinien beachten!

* Verwenden Sie einen Administrator, um eine Verbindung herzustellen.
* Sie können mehrere Werbekonten für eine Plattform verbinden.
* Alle möglichen Werbekonten anschließen, um die Ausgabenberichterstellung so weit wie möglich zu automatisieren
* Wenn verfügbar, implementieren Sie immer eine Tracking-Vorlage. Die Vorlage stellt sicher, dass, selbst wenn die Verbindung des Anzeigenkontos getrennt wird, [!DNL Marketo Measure] kann weiterhin detaillierte Anzeigendetails abrufen

So optimieren Sie jede [!DNL Marketo Measure] API verwenden, beachten Sie bitte die folgenden Best Practices.

**[!DNL Facebook]**: Verbindung mit automatischem Tagging

Exportieren Sie vor der Aktivierung des automatischen Tagging Ihren Anzeigenverlauf in eine CSV-Datei. Durch die Aktivierung der automatischen Tagging-Funktion werden der Konversionsverlauf und der Social-Testversand aller Anzeigen zurückgesetzt, die mit [!DNL Marketo Measure].

Durch Befolgung unserer Best-Practice-Empfehlung wird die Variable [!DNL Marketo Measure] [!DNL Facebook] Die API kann:

* Alle automatisch taggen [!DNL Facebook] Anzeigen mit den erforderlichen [!DNL Marketo Measure] parameter `_bf ={creative}`
* Informationen zu Anzeigenkosten für alle aktiven Benutzer herunterladen [!DNL Facebook] Anzeigen

>[!NOTE]
>
>Es gibt keine Tracking-Vorlage für [!DNL Facebook]verwendet die API den automatisch mit Tags versehenen Parameter (_bf), um die Anzeigendetails zu erfassen.

**AdWords**: Implementieren einer Tracking-Vorlage auf Kontoebene und Aktivieren der automatischen Tagging-Funktion

[!DNL Marketo Measure] empfiehlt die Verwendung einer Tracking-Vorlage auf Kontoebene, Kampagnenebene oder Anzeigengruppenebene, da sie das Hinzufügen und Abziehen von Parametern für alle Anzeigen ermöglicht, ohne dass das Risiko von Unterbrechungen oder Löschungen des Anzeigenverlaufs besteht.

Durch Befolgung unserer Best-Practice-Empfehlung wird die Variable [!DNL Marketo Measure] Die AdWords-API kann:

* Taggen Sie alle AdWords-Anzeigen automatisch mit dem [!DNL Marketo Measure] Parameter `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Informationen zu Anzeigenkosten für alle aktiven AdWords-Anzeigen herunterladen

**Bing**: Implementieren einer Tracking-Vorlage auf Kontoebene und Aktivieren der automatischen Tagging-Funktion

Es besteht kein Risiko, den Anzeigenverlauf bei der Einrichtung Ihrer [!DNL Bing] API-Verbindung, im Gegensatz zu einigen unserer anderen API-Verbindungen.

Durch Befolgung unserer Best-Practice-Empfehlung wird die Variable [!DNL Marketo Measure] Die Bing-API kann:
* Automatisches Tagging aller Bing Ads mit den folgenden Parametern von `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Informationen zu Anzeigenkosten für alle aktiven Bing-Anzeigen herunterladen

**linkedIn**: Verbindung mit automatischem Tagging

Durch die Aktivierung der automatischen Tagging-Funktion wird eine Freigabe neu erstellt und in einem neuen Kreativ platziert. Das alte Kreativ wird archiviert.

Durch Befolgung unserer Best-Practice-Empfehlung wird die Variable [!DNL Marketo Measure] Die linkedIn-API kann:

* Automatisches Taggen aller LinkedIn-Anzeigen, die vom Typ &quot;Sponsored Content&quot;gesponsert werden, mit den erforderlichen [!DNL Marketo Measure] parameter _bl={creativeId}. Dieser Parameter ruft die Kreativ-ID ab, die Folgendes ermöglicht: [!DNL Marketo Measure] , um die Kampagne und kreative Informationen zu lösen.
* Informationen zu Anzeigenkosten für alle aktiven und unterstützten [!DNL LinkedIn] Anzeigen

>[!NOTE]
>
>Es gibt keine Tracking-Vorlage für [!DNL LinkedIn]verwendet die API den automatisch mit Tags versehenen Parameter (_bl), um alle möglichen Anzeigendetails zu erfassen.

## Best Practice für die Wartung {#best-practice-for-maintenance}

Wenn Sie unsere Best Practices befolgen, werden Sie dennoch davor geschützt, Daten zu verlieren, wenn die Verbindung getrennt ist. Wir empfehlen Ihnen jedoch dennoch, Ihre Verbindung regelmäßig und monatlich nach Möglichkeit zu überprüfen. Dies ist eine einfache visuelle Überprüfung der [!UICONTROL Verbindungen] im Abschnitt [!DNL Marketo Measure] App verwenden, um sicherzustellen, dass keine roten Schlüsselsymbole vorhanden sind, wodurch ein nicht verbundenes Konto signalisiert wird.

Wenn ein mit der API verbundenes Konto getrennt wird, [!DNL Marketo Measure] kann keine Ausgabedaten in abrufen oder neue Anzeigen taggen. Deshalb empfehlen wir immer, nach Möglichkeit eine Tracking-Vorlage zu implementieren. Die Vorlage stellt sicher, dass, selbst wenn die Verbindung des Anzeigenkontos getrennt wird, [!DNL Marketo Measure] weiterhin in der Lage ist, die Anzeigen zu taggen und detaillierte Anzeigendetails abzurufen. Nach der erneuten Verbindung füllen die Ausgabedaten wieder aus und die Unterbrechung der gebührenpflichtigen Kanalberichte ist minimal.

Die Gründe für die Trennung und Neuautorisierung sind...

* Passwortänderung für das Personenkonto, mit dem die Verbindung hergestellt wurde
* Diese Person ist nicht mehr in der Firma
* Aktualisierungen der APIs

Wenn Ihr Team eines der oben genannten Szenarien durchlaufen hat, überprüfen Sie Ihre API-Verbindungen im Abschnitt [!DNL Marketo Measure] App verwenden, um sicherzustellen, dass sie nicht erneut autorisiert werden müssen.

>[!MORELIKETHIS]
>
>* [Integrierte Anzeigenplattformen (APIs)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [Auswirkungen der Angebotsmanagement-Tools [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API-Parameter - Erklärung](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Übersicht über die facebook API](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Integrationsübersicht](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Übersicht über die AdWords-Integration](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Erneutes Autorisieren von Connected API-Konten](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)

