---
description: Best Practices für die Segmentierung – [!DNL Marketo Measure] – Produktdokumentation
title: Best Practices für die Segmentierung
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 88%

---

# Best Practices für die Segmentierung {#best-practices-for-segmentation}

## Überblick {#overview}

Mit der Segmentierungsfunktion von [!DNL Marketo Measure] können Sie Regeln (d. h. im Grunde Filter) basierend auf Ihren CRM-Feldern definieren, um sie in einzelne Segmente zu gruppieren. Diese Segmente stehen dann in Ihren Discover-Dashboards sowie in Ihren [!DNL Salesforce]-Berichten zur Verfügung.

Die Segmentierung ist für die Nutzung Ihres [!DNL Marketo Measure]-Kontos von entscheidender Bedeutung. Dies gilt insbesondere innerhalb Ihrer Discover-Pinnwände. Da die Discover-Pinnwände von [!DNL Marketo Measure] auf einen vorab festgelegten Filtersatz beschränkt sind, können Sie mithilfe der Segmentierung Daten in Discover ähnlich wie in Ihren [!DNL Salesforce]-Berichten aufgliedern.

Bei der Push-Übertragung nach [!DNL Salesforce] werden Segmentwerte in das Feld „Segment“ geschrieben, die sich in einem beliebigen Buyer-Touchpoint-Berichtstyp befinden können. Dies ermöglicht einheitliche Berichte über beide Plattformen hinweg. Das Segment findet sich auch in den „Touchpoint-Details“ eines beliebigen Touchpoints.

Wenn an [!UICONTROL Discover], werden Segmente als verfügbare Filter im Dropdown-Menü Filter angezeigt, das sich auf allen Pinnwänden befindet.

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob die Segmentierung zum ersten Mal definiert oder nur die zuvor eingerichtete Segmentierung überprüft wird.

* Achten Sie auf Einfachheit. 
* Richten Sie den Segmentnamen an die Nomenklatur Ihres Unternehmens aus, d. h. Kategorie = Filtername, Segment = Filterwert.
* Verwenden Sie keine Formelfelder in Ihren Regeln
* Erstellen Sie die Segmentierung möglichst für Lead/Kontakt und für Opportunity, um eine Verwendung über den gesamten Trichter hinweg sicherzustellen
   * Wenn Sie Marketo Measure Ultimate-Kunde sind und Ihr Standard-Dashboard-Objekt auf &quot;Kontakt&quot;festgelegt haben, verwenden Sie nicht die folgenden beiden für &quot;Lead&quot;([Mehr dazu hier](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
   * Nicht jede Segmentkategorie wird über den gesamten Trichter ausgerichtet
      * Die Segmentkategorie „Opportunity-Typ“ bezieht sich beispielsweise nicht auf Leads. Bei einem Segment, das mit „Region“ verknüpft ist, handelt es sich jedoch wahrscheinlich um eine Kategorie, die im gesamten Trichter definiert werden kann
* Denken Sie darüber nach, wie Sie Ihre Daten derzeit darstellen möchten – ob im CRM-System oder in einem BI-Tool – und erwägen Sie eine entsprechende Segmenterstellung in [!DNL Marketo Measure], sodass dieselben Berichte in Discover verfügbar sind

## Best Practice für die Wartung {#best-practice-for-maintenance}

Indem Sie Ihre Segmentierung mindestens zweimal jährlich überprüfen, stellen Sie sicher, dass die Segmentierung auf dem neuesten Stand ist. Als Best Practice empfehlen wir, Ihre Regeln auf der Registerkarte [!UICONTROL Segmente] der [!DNL Marketo Measure]-Kontoeinstellungen zu überprüfen und Berichte in [!DNL Salesforce] abzurufen, um Ihre in Aktion befindlichen Segmente zu prüfen. Diese Schritte geben Ihnen und Ihrem Team nicht nur ein sicheres Gefühl in Bezug auf die Segmentierung, sondern anschließend auch bei Ihren [!DNL Marketo Measure]-Berichten.

Andere mögliche Gründe für eine Überprüfung Ihrer Segmentierung:

* Wechsel in Ihrem Marketing-Team
* Änderungen an Feldern, die zur Definition Ihrer Segmente verwendet werden
* Ergänzungen oder Änderungen bei bereits eingerichteten Segmenten

>[!MORELIKETHIS]
>
>[Einrichten der benutzerdefinierten Segmentierung](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
