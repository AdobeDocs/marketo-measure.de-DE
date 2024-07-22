---
description: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags - [!DNL Marketo Measure]
title: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 7%

---

# Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags {#best-practices-for-utilizing-a-custom-revenue-amount}

## Überblick {#overview}

Die Kernfunktion von [!DNL Marketo Measure] besteht darin, Marketing-Touchpoints auf der gesamten Journey des Käufers Umsatzkredite zuzuweisen. Der Schlüssel zur präzisen Umsatzzuordnung besteht darin, dass [!DNL Marketo Measure] auf den korrekten Umsatzbetrag einer Gelegenheit verweisen kann, die wiederum über die verschiedenen Attributionsmodelle über die Marketing-Touchpoints verteilt wird.

Sofern während der Implementierung nichts anderes angegeben wird, wird Ihre [!DNL Marketo Measure]-Instanz so eingestellt, dass sie auf den standardmäßigen Opportunity Amount (SFDC Default) für die Umsatzzuordnung verweist. Bei vielen [!DNL Marketo Measure] -Konten spiegelt dieses Feld jedoch nicht den genauen Umsatzbetrag für Chancen wider. In diesen Fällen bietet [!DNL Marketo Measure] die Möglichkeit, einen benutzerspezifischen Umsatzbetrag für [!DNL Marketo Measure] einzurichten, um auf die Attributions-Touchpoints (BAT) zu verweisen und diese zu verteilen.

## Best Practices {#best-practice}

Beachten Sie beim Einrichten eines benutzerspezifischen Umsatzbetrags die folgenden Best Practices, um sicherzustellen, dass Ihre [!DNL Marketo Measure]-Attributionsdaten korrekt und konsistent sind.

Folgendes sollte beachtet werden:

* Wählen Sie das Umsatzfeld aus, das für alle Chancen genau und genutzt ist.
   * ARR oder Gesamtauftragswert wird empfohlen
* Kein Formelfeld verwenden
* Wenn Sie einen benutzerspezifischen Umsatzbetrag für Währungsumrechnungen verwenden, ist stattdessen die Funktion [!UICONTROL Marketo Measure Mehrere Währungen] die bevorzugte Methode.
   * Die Funktion &quot;[!DNL Marketo Measure] Mehrere Währungen&quot;verweist auf die in &quot;[!DNL Salesforce]&quot;festgelegten Konversionsraten, um die Abstimmung zwischen den Währungsumrechnungen am besten sicherzustellen. Auf diese Weise können Sie weiterhin den Standard-Betrag (SFDC-Standard) oder ein anderes benutzerdefiniertes Feld &quot;Betrag&quot;verwenden, das sich auf die Konversionsraten von [!DNL Salesforce] bezieht.
* Wenn Sie das Feld Betrag aktualisieren, auf das Sie mit [!DNL Marketo Measure] verweisen möchten, verwenden Sie Data Loader, um vergangene Möglichkeiten zu aktualisieren, um sicherzustellen, dass Ihre Umsatzdaten konsistent sind und das richtige Feld über den Workflow aufgefüllt wird

## Best Practices für die Wartung {#best-practice-for-maintenance}

Durch die jährliche Überprüfung der Einrichtung Ihres Umsatzbetrags wird sichergestellt, dass Ihre Attributionsdaten korrekt sind und mit dem Rest der Umsatzberichte Ihres Unternehmens abgestimmt sind.

Wenn Sie einen benutzerdefinierten Umsatzbetrag verwenden, überprüfen Sie Ihre Umsatzeinstellungen wie folgt.

* Gehen Sie in Ihrem [!DNL Marketo Measure] -Konto zum Abschnitt &#39;[!UICONTROL Opportunities]&#39; unter CRM .
* Identifizieren Sie das Feld [!UICONTROL Benutzerdefinierter Opportunity Amount] , hier sollte Ihr Feld für die [!UICONTROL benutzerspezifische Umsatzbetrag-API] aufgeführt werden.
* Vergewissern Sie sich, dass das Feld weiterhin korrekt ist.
* Lassen Sie außerdem Ihren [!DNL Salesforce] Admin bestätigen, dass der Workflow &quot;Benutzerspezifischer Umsatzbetrag&quot;in [!DNL Salesforce] noch ausgeführt wird.

Abgesehen von einer jährlichen Überprüfung können gewisse organisatorische Änderungen die Notwendigkeit einer Überprüfung der Einrichtung Ihres Umsatzbetrags signalisieren..

* Wechsel in Ihrem Marketing-Team
* Änderungen am Feld &quot;Benutzerspezifischer Umsatz&quot;
* Organisationsänderungen bei der Berichterstattung über den Umsatz

>[!MORELIKETHIS]
>
>* [Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Verwenden des Datenladeprogramms zum Aktualisieren des benutzerdefinierten Felds &quot;Betrag&quot;](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Überblick über mehrere Währungen](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Einstellungen für mehrere Währungen](/help/advanced-marketo-measure-features/multi-currency/settings.md)
