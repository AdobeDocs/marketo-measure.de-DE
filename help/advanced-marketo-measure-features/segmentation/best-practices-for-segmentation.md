---
description: Best Practices für die Segmentierung - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für die Segmentierung
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Best Practices für die Segmentierung {#best-practices-for-segmentation}

## Überblick {#overview}

[!DNL Marketo Measure] Mit der Segmentierung können Sie Regeln definieren, die im Wesentlichen Filter sind und auf Ihren CRM-Feldern basieren, um sie in einzelne Segmente zu gruppieren. Diese Segmente stehen dann in Ihren Discover-Dashboards sowie in Ihren [!DNL Salesforce] Berichterstellung.

Die Segmentierung ist für die Nutzung Ihrer [!DNL Marketo Measure] -Konto, insbesondere in Ihren Discover-Foren. Da die [!DNL Marketo Measure] Discover-Pinnwände sind auf einen vorab festgelegten Filtersatz beschränkt. Die Segmentierung bietet Ihnen die Möglichkeit, Ihre Daten in Discover ähnlich wie in Ihren [!DNL Salesforce] Berichterstellung.

Wenn an [!DNL Salesforce], werden Segmentwerte in das Feld &quot;Segment&quot;geschrieben und befinden sich in einem beliebigen Buyer-Touchpoint-Berichtstyp. Dies ermöglicht eine einheitliche Berichterstattung über beide Plattformen hinweg. Das Segment kann auch in &quot;Touchpoint-Detail&quot;eines beliebigen Touchpoints gefunden werden.

Wenn Segmente in Discover gepusht werden, werden sie als verfügbare Filter im Dropdown-Menü &quot;Filter&quot;auf allen Pinnwänden angezeigt.

## Best Practice {#best-practice}

Beachten Sie die folgenden Best Practices, unabhängig davon, ob Sie die Segmentierung zum ersten Mal definieren oder nur die zuvor eingerichtete Segmentierung überprüfen.

* Halten Sie es einfach!
* Richten Sie Ihren Segmentnamen an die Nomenklatur Ihres Unternehmens aus, d. h. die Kategorie = Filtername, Segment = Filterwert
* Verwenden Sie keine Formelfelder in Ihren Regeln.
* Erstellen Sie nach Möglichkeit die Segmentierung sowohl für Lead/Kontakt als auch für Chancen , damit Sie sie über den gesamten Trichter hinweg verwenden können.
   * Nicht jede Segmentkategorie wird im gesamten Trichter ausgerichtet
      * Eine Segmentkategorie &quot;Opportunity Type&quot;bezieht sich beispielsweise nicht auf Leads. Ein Segment, das mit &quot;Region&quot;verknüpft ist, ist jedoch wahrscheinlich eine Kategorie, die im gesamten Trichter definiert werden kann
* Denken Sie daran, wie Sie Ihre Daten derzeit austeilen möchten, unabhängig davon, ob sie sich im CRM-System oder in einem BI-Tool befinden, und erwägen Sie, dies als Segment in [!DNL Marketo Measure] sodass Sie dieselbe Berichterstellung in Discover haben können

## Best Practice für die Wartung {#best-practice-for-maintenance}

Wenn Sie Ihre Segmentierung mindestens zweimal jährlich überprüfen, wird sichergestellt, dass Ihre Segmentierung auf dem neuesten Stand ist. Als Best Practice empfehlen wir, Ihre Regeln im Abschnitt[!UICONTROL Segmente]Registerkarte &#39; Ihres [!DNL Marketo Measure] Kontoeinstellungen sowie das Abrufen von Berichten in [!DNL Salesforce] , um Ihre in Aktion befindlichen Segmente zu überprüfen. Diese Schritte helfen Ihnen und Ihrem Team dabei, sich auf Ihre Segmentierung und anschließend auf Ihre [!DNL Marketo Measure] Berichterstellung.

Weitere Gründe dafür könnten eine Überprüfung Ihrer Segmentierung Trigger haben...

* Umsatz in Ihrem Marketing-Team
* Änderungen an Feldern, die zur Definition Ihrer Segmente verwendet werden
* Ergänzungen oder Änderungen zu den bereits eingerichteten Segmenten

>[!MORELIKETHIS]
>
>[Einrichten der benutzerdefinierten Segmentierung](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
