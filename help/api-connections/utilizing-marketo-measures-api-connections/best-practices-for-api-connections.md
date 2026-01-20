---
description: Best Practices für API-Verbindungen – [!DNL Marketo Measure]
title: Best Practices für API-Verbindungen
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 97%

---

# Best Practices für API-Verbindungen {#best-practices-for-api-connections}

## Überblick {#overview}

[!DNL Marketo Measure] ermöglicht API-Verbindungen mit [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads] und LinkedIn. Diese API-Verbindungen ermöglichen es [!DNL Marketo Measure], eine Vielzahl von Daten aus Ihren Werbeanzeigenplattformen abzurufen, zu denen dann in Ihren Buyer Touchpoint-Daten berichtet werden kann. Eine Schlüsselfunktion dieser API-Verbindungen ist die Möglichkeit, Ausgabedaten automatisch abzurufen, wodurch Sie und Ihr Team Zeit und Mühe sparen, Daten manuell für die ROI-Berichterstellung hochzuladen. Für [!DNL Marketo Measure] ist das Einrichten dieser API-Verbindungen für das Nachverfolgen von Kanälen nicht erforderlich, sie bieten jedoch wertvolle detaillierte Informationen, die Ihre Berichterstellung verbessern.

Die [!DNL Marketo Measure] API-Verbindungen sind ein unschätzbarer Aspekt Ihres Kontos. Unsere Best Practices-Empfehlungen helfen Ihnen und Ihrem Team dabei, unsere Verbindungen umfassend zu nutzen.

## Best Practices {#best-practice}

Unabhängig von der Werbeplattform, die Sie verbinden, sollten Sie die folgenden Richtlinien beachten.

* Verwenden Sie Admins für die Verbindung
* Sie können mehrere Werbekonten für eine Plattform verbinden.
* Sie sollten alle möglichen Werbekonten anschließen, um die Ausgabenberichterstellung so weit wie möglich zu automatisieren.
* Wenn verfügbar, implementieren Sie immer eine Tracking-Vorlage. Die Vorlage stellt sicher, dass selbst dann, wenn die Verbindung des Werbekontos getrennt wird, [!DNL Marketo Measure] weiterhin detaillierte Werbeanzeigendetails abrufen kann

Um jede [!DNL Marketo Measure]-API zu optimieren, beachten Sie die folgenden Best Practices.

**[!DNL Facebook]**: Verbindung mit automatischem Tagging

Exportieren Sie vor der Aktivierung des automatischen Taggings Ihren Werbeanzeigenverlauf in eine CSV-Datei. Durch die Aktivierung der automatischen Tagging-Funktion werden der Konversionsverlauf und der Social Proof aller Werbeanzeigen zurückgesetzt, die mit Tags für [!DNL Marketo Measure] versehen sind.

Durch Befolgung unserer Best-Practice-Empfehlung wird die [!DNL Marketo Measure] [!DNL Facebook]-API in der Lage sein:

* Alle Werbeanzeigen für [!DNL Facebook] automatisch mit den erforderlichen [!DNL Marketo Measure]-Parametern zu taggen `_bf ={creative}`
* Informationen zu Werbeanzeigenkosten für alle aktiven [!DNL Facebook]-Werbeanzeigen herunterzuladen

>[!NOTE]
>
>Es gibt keine Tracking-Vorlage für [!DNL Facebook]. Die API basiert auf dem automatisch mit Tags versehenen Parameter (_bf), um die Werbeanzeigendetails zu erfassen.

**AdWords**: Implementieren Sie eine Tracking-Vorlage auf Kontoebene und aktivieren Sie das automatische Tagging

[!DNL Marketo Measure] empfiehlt, eine Tracking-Vorlage auf Konto-, Kampagnen- oder Werbeanzeigengruppen-Ebene zu verwenden, damit die Parameter aller Werbeanzeigen hinzugefügt oder entfernt werden können, ohne Risiko einer Unterbrechung oder Löschung des Werbeverlaufs.

Durch Befolgung unserer Best-Practice-Empfehlung wird die [!DNL Marketo Measure]-AdWords-API in der Lage sein:

* Alle AdWords-Werbeanzeigen automatisch mit den [!DNL Marketo Measure]-Parametern von `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}` zu taggen
* Informationen zu Werbeanzeigenkosten für alle aktiven AdWords-Werbeanzeigen herunterzuladen

**Bing**: Implementieren Sie eine Tracking-Vorlage auf Kontoebene und aktivieren Sie das automatische Tagging

Es besteht kein Risiko, den Werbeanzeigenverlauf bei der Einrichtung Ihrer [!DNL Bing]-API-Verbindung zu verlieren, im Gegensatz zu einigen unserer anderen API-Verbindungen.

Durch Befolgung unserer Best-Practice-Empfehlung wird die [!DNL Marketo Measure]-Bing-API in der Lage sein:
* Alle Bing-Werbeanzeigen mit den folgenden Parametern von `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}` automatisch zu taggen
* Informationen zu Werbeanzeigenkosten für alle aktiven Bing-Werbeanzeigen herunterzuladen

**LinkedIn**: Verbindung mit automatischem Tagging

Durch die Aktivierung der automatischen Tagging-Funktion wird eine Freigabe neu erstellt und in einem neuen Werbemittel platziert. Das alte Werbemittel wird archiviert.

Durch Befolgung unserer Best-Practice-Empfehlung wird die [!DNL Marketo Measure]-LinkedIn-API in der Lage sein:

* Alle LinkedIn-Anzeigen, bei denen es sich um vom Anzeigentyp gesponserte Inhalte handelt, mit dem erforderlichen [!DNL Marketo Measure] _bl={creativeId} automatisch taggen. Dieser Parameter ruft die Werbemittel-ID ab, damit [!DNL Marketo Measure] die Kampagnen- und Kreativinformationen auflösen kann.
* Herunterladen von Informationen zu Werbeanzeigenkosten für alle aktiven und unterstützten [!DNL LinkedIn]-Werbeanzeigen

>[!NOTE]
>
>Es gibt keine Tracking-Vorlage für [!DNL LinkedIn], sondern die API verwendet den automatisch mit Tags versehenen Parameter (_bl), um alle möglichen Werbeanzeigendetails zu erfassen.

## Best Practices für die Wartung {#best-practice-for-maintenance}

Wenn Sie unsere Best Practices befolgen, werden Sie davor geschützt, Daten zu verlieren, wenn die Verbindung getrennt ist. Wir empfehlen Ihnen jedoch dennoch, Ihre Verbindung regelmäßig (im Idealfall monatlich) zu überprüfen. Dabei handelt es sich um eine einfache visuelle Überprüfung des Abschnitts [!UICONTROL Verbindungen] in der [!DNL Marketo Measure]-App, um sicherzustellen, dass keine roten Schlüsselsymbole vorhanden sind. Diese weisen auf ein nicht verbundenes Konto hin.

Wenn ein mit der API verbundenes Konto getrennt wird, kann [!DNL Marketo Measure] keine Ausgabedaten abrufen oder neue Werbeanzeigen taggen. Deshalb empfehlen wir immer, nach Möglichkeit eine Tracking-Vorlage zu implementieren. Die Vorlage stellt sicher, dass selbst dann, wenn die Verbindung des Werbekontos getrennt wird, [!DNL Marketo Measure] weiterhin Werbeanzeigen taggen und detaillierte Werbeanzeigendetails abrufen kann. Nach der erneuten Verbindung werden die Ausgabedaten wieder ausgefüllt und die Unterbrechung der Berichterstellung für Paid-Kanäle ist minimal.

Die Gründe für die Trennung und Neuautorisierung können sein ...

* Passwortänderung für das verbundene Konto
* Diese Person ist nicht mehr in der Firma
* Aktualisierungen an den APIs

Wenn Ihr Team eines der oben genannten Szenarien durchlaufen hat, überprüfen Sie Ihre API-Verbindungen in der [!DNL Marketo Measure]-Anwendung, um sicherzustellen, dass sie nicht erneut autorisiert werden müssen.

>[!MORELIKETHIS]
>
>* [Integrierte Anzeigenplattformen (APIs)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [Wie sich Bid-Management-Tools auswirken [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API-Parameter – Erklärung](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Übersicht über die Facebook-API](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Integrationsübersicht](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Übersicht über die AdWords-Integration](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Erneutes Autorisieren von verbundenen API-Accounts](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
