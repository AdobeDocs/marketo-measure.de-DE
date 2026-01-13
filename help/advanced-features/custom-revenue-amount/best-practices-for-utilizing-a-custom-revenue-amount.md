---
description: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags - [!DNL Marketo Measure]
title: Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 7%

---


# Best Practices für die Verwendung eines benutzerdefinierten Umsatzbetrags {#best-practices-for-utilizing-a-custom-revenue-amount}

## Überblick {#overview}

Die Kernfunktionalität von [!DNL Marketo Measure] besteht in der Möglichkeit, den Marketing-Touchpoints während der gesamten Journey des Käufers Umsatzgutschriften zuzuweisen. Der Schlüssel zu einer korrekten Umsatzzuordnung besteht in der Möglichkeit für [!DNL Marketo Measure], den richtigen Umsatzbetrag für eine Opportunity zu referenzieren, der wiederum über die verschiedenen Attributionsmodelle auf die Marketing-Touchpoints verteilt wird.

Sofern bei der Implementierung nicht anders angegeben, wird Ihre [!DNL Marketo Measure]-Instanz so eingestellt, dass sie für die Umsatzzuordnung auf den standardmäßigen Opportunity-Betrag (SFDC-Standard) verweist. Bei vielen [!DNL Marketo Measure]-Konten entspricht dieses Feld jedoch nicht dem genauen Umsatzbetrag für Opportunities. In diesen Fällen bietet [!DNL Marketo Measure] die Möglichkeit, einen benutzerdefinierten Umsatzbetrag für [!DNL Marketo Measure] einzurichten, der referenziert und auf die Attribution Touchpoints (BATs) verteilt werden kann.

## Best Practices {#best-practice}

Beachten Sie beim Einrichten eines benutzerdefinierten Umsatzbetrags die folgenden Best Practices, um sicherzustellen, dass Ihre [!DNL Marketo Measure] Attributionsdaten korrekt und konsistent sind!

Folgendes sollte beachtet werden:

* Wählen Sie das Umsatzfeld aus, das präzise und für alle Opportunities genutzt ist.
   * ARR oder Gesamtauftragswert wird empfohlen
* Keine Formelfelder verwenden
* Wenn Sie einen benutzerdefinierten Umsatzbetrag für Währungsumrechnungen verwenden, ist stattdessen die Funktion [!UICONTROL Mehrere Marketo Measure] zu bevorzugen.
   * Die Funktion Mehrere Währungen [!DNL Marketo Measure] verweist auf die in [!DNL Salesforce] festgelegten Konversionsraten, um eine optimale Abstimmung zwischen den Währungsumrechnungen sicherzustellen. Auf diese Weise können Sie weiterhin das standardmäßige „Betrag“ (SFDC-Standard) oder ein anderes benutzerdefiniertes Betragsfeld verwenden, das sich auf die [!DNL Salesforce] Konversionsraten bezieht.
* Wenn Sie das Betragsfeld aktualisieren, auf das Sie verweisen [!DNL Marketo Measure], verwenden Sie den Data Loader, um vergangene Opportunities zu aktualisieren, um sicherzustellen, dass Ihre Umsatzdaten konsistent sind und das richtige Feld über den Workflow ausgefüllt wird

## Best Practices für die Wartung {#best-practice-for-maintenance}

Durch die jährliche Überprüfung der Einrichtung Ihres Umsatzbetrags wird sichergestellt, dass Ihre Attributionsdaten korrekt sind und mit dem Rest der Umsatzberichterstattung Ihres Unternehmens übereinstimmen.

Wenn Sie einen benutzerdefinierten Umsatzbetrag verwenden, überprüfen Sie Ihre Umsatzeinstellungen wie folgt.

* Rufen Sie in Ihrem [!DNL Marketo Measure]-Konto den Abschnitt [!UICONTROL Opportunities] unter CRM auf.
* Identifizieren Sie das Feld [!UICONTROL Benutzerdefinierter Opportunity]Betrag“, in dem Ihr [!UICONTROL benutzerdefinierter Umsatzbetrag-API]Feld aufgeführt werden sollte.
* Vergewissern Sie sich, dass dies weiterhin das richtige Feld ist
* Bitten Sie Ihren [!DNL Salesforce] außerdem, zu bestätigen, dass der Workflow Benutzerdefinierter Umsatzbetrag in [!DNL Salesforce] noch ausgeführt wird

Neben einer jährlichen Überprüfung können bestimmte organisatorische Änderungen auch darauf hindeuten, dass Sie Ihren Umsatzbetrag überprüfen müssen…

* Wechsel in Ihrem Marketing-Team
* Änderungen am Feld Benutzerdefinierter Umsatz
* Organisatorische Änderungen bei der Berichterstattung über den Umsatz

>[!MORELIKETHIS]
> [Verwenden eines benutzerdefinierten Felds für den Umsatzbetrag](/help/advanced-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
> [Verwenden des Datenladers zum Aktualisieren des benutzerdefinierten Betragsfelds](/help/advanced-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
> [Überblick über mehrere Währungen](/help/advanced-features/multi-currency/overview.md)
> [Währungsübergreifende Einstellungen](/help/advanced-features/multi-currency/settings.md)
