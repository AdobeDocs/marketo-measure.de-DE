---
description: Doppelte Datensätze im Handbuch Mein Bericht für Marketo Measure-Anwender
title: Doppelte Einträge in meinem Bericht
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 9%

---

# Doppelte Einträge in meinem Bericht {#duplicate-records-in-my-report}

>[!NOTE]
>
>Möglicherweise werden in der Dokumentation Anweisungen für &quot;[!DNL Marketo Measure]&quot; angezeigt, in Ihrem CRM-System wird jedoch weiterhin &quot;[!DNL Bizible]&quot; angezeigt. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Wenn Sie in [!DNL Marketo Measure] in die [!DNL Salesforce] Berichte eintauchen, finden Sie möglicherweise „doppelte“ Einträge in Ihren Berichten. Dies wird Ihnen wahrscheinlich beim Überprüfen [!DNL Marketo Measure] vordefinierten Berichte auffallen.

Bei der Berichterstellung mit dem Objekt der Käufer-Touchpoints oder dem Buyer Attribution Touchpoint-Objekt ist es wichtig zu verstehen, dass Sie nicht mehr über die Anzahl der Leads, Kontakte oder Vertriebschancen berichten, sondern vielmehr über die Anzahl der Käufer-Touchpoints oder der Käufer-Attribution-Touchpoints, die mit diesen Standardobjekten (Leads, Kontakte, Vertriebschancen) verknüpft sind.

Nehmen wir den folgenden Bericht als Beispiel:

Dies ist ein Bericht **Kontakte mit Käufer-Touchpoints**. Dies bedeutet wiederum, dass wir die Anzahl der Touchpoints prüfen, die mit einem einzelnen Kontakt verbunden sind.

![Dies ist ein Bericht zu Kontakten mit Käuferkontaktpunkten. Auch dies bedeutet Folgendes](assets/marketo-reports-1.gif)

Wie Sie sehen können, sieht es so aus, als gäbe es drei James Williams Kontakte im Bericht, und daher könnten Sie denken, „Duplikate!“

Dieser Bericht zeigt jedoch die Anzahl der Touchpoints im Zusammenhang mit James an. Innerhalb des Berichts können Sie sehen, dass James einen individuellen FT (First Touch), einen individuellen LC, ein Formular (Lead Creation Touch) und einen PostLC Touchpoint (eine Formularübermittlung, die nach dem LC Touchpoint erfolgt) hat.

Wenn Sie die „Anzahl der Kontakte“ verstehen möchten, können Sie die Felder „Anzahl - Erstkontakt“, „Kontakt zur Lead-Erstellung zählen“ oder „U-förmig zählen“ verwenden, um zu verstehen, wie viele Kontakte Marketing-Interaktionen hatten.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Stock-SFDC-Berichte](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
