---
description: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 0%

---

# Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags {#best-practices-for-utilizing-a-custom-revenue-amount}

## Überblick {#overview}

Die Kernfunktionen von [!DNL Marketo Measure] ist die Möglichkeit, Marketing-Touchpoints auf der gesamten Journey des Käufers Umsatzgutschriften zuzuweisen. Der Schlüssel zur präzisen Umsatzzuordnung ist die Möglichkeit für [!DNL Marketo Measure] , um auf den korrekten Umsatzbetrag einer Gelegenheit zu verweisen, die wiederum über die verschiedenen Attributionsmodelle über die Marketing-Touchpoints verteilt wird.

Sofern während der Implementierung nichts anderes angegeben wird, wird Ihre [!DNL Marketo Measure] -Instanz auf den standardmäßigen Opportunity Amount (SFDC Default) für die Umsatzzuordnung verweist. Für viele [!DNL Marketo Measure] berücksichtigt, spiegelt dieses Feld nicht den genauen Umsatzbetrag für Chancen wider. In diesen Fällen [!DNL Marketo Measure] bietet die Möglichkeit, einen benutzerdefinierten Umsatzbetrag für [!DNL Marketo Measure] , um auf die Attributions-Touchpoints (BVT) zu verweisen und sie über sie zu verteilen.

## Best Practice {#best-practice}

Beachten Sie beim Einrichten eines benutzerdefinierten Umsatzbetrags die folgenden Best Practices, um Ihre [!DNL Marketo Measure] Attributionsdaten sind genau und konsistent!

Folgendes sollte beachtet werden:

* Wählen Sie das Umsatzfeld aus, das für alle Chancen genau und genutzt ist.
   * ARR oder Gesamtauftragswert wird empfohlen
* Kein Formelfeld verwenden
* Wenn Sie einen benutzerdefinierten Umsatzbetrag für Währungsumrechnungen verwenden, wird die Variable [!UICONTROL Marketo messen mehrerer Währungen] -Funktion ist stattdessen die bevorzugte Methode.
   * Die [!DNL Marketo Measure] Die Funktion für mehrere Währungen verweist auf die in [!DNL Salesforce] , um die Abstimmung zwischen Währungsumrechnungen am besten sicherzustellen. Auf diese Weise können Sie den Standardbetrag &quot;Betrag&quot;(SFDC-Standard) oder ein anderes benutzerdefiniertes Feld, das sich auf die [!DNL Salesforce] Konversionsraten.
* Wenn Sie das Feld Betrag aktualisieren, das Sie möchten [!DNL Marketo Measure] Verwenden Sie zum Referenzieren Data Loader, um vergangene Möglichkeiten zu aktualisieren, um sicherzustellen, dass Ihre Umsatzdaten konsistent sind und das richtige Feld über den Workflow aufgefüllt wird.

## Best Practice für die Wartung {#best-practice-for-maintenance}

Durch die jährliche Überprüfung der Einrichtung Ihres Umsatzbetrags wird sichergestellt, dass Ihre Attributionsdaten korrekt sind und mit dem Rest der Umsatzberichte Ihres Unternehmens abgestimmt sind.

Wenn Sie einen benutzerdefinierten Umsatzbetrag verwenden, überprüfen Sie Ihre Umsatzeinstellungen wie folgt.

* In [!DNL Marketo Measure] -Konto, navigieren Sie zum[!UICONTROL Chancen]&#39; unter CRM
* Identifizieren Sie die [!UICONTROL Benutzerdefinierter Opportunity-Betrag] Feld, hier Ihre [!UICONTROL Benutzerdefinierte UmsatzAPI] -Feld sollte aufgelistet werden
* Vergewissern Sie sich, dass das Feld weiterhin korrekt ist.
* Außerdem sollten Sie [!DNL Salesforce] Admin bestätigen, dass der Workflow &quot;Benutzerspezifischer Umsatzbetrag&quot;in [!DNL Salesforce] wird noch ausgeführt

Abgesehen von einer jährlichen Überprüfung können gewisse organisatorische Änderungen die Notwendigkeit einer Überprüfung der Einrichtung Ihres Umsatzbetrags signalisieren..

* Umsatz in Ihrem Marketing-Team
* Änderungen am Feld &quot;Benutzerspezifischer Umsatz&quot;
* Organisationsänderungen bei der Berichterstattung über den Umsatz

>[!MORELIKETHIS]
>
>* [Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Verwenden von Data Loader zum Aktualisieren des benutzerdefinierten Felds &quot;Betrag&quot;](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Übersicht über mehrere Währungen](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Einstellungen für mehrere Währungen](/help/advanced-marketo-measure-features/multi-currency/settings.md)

