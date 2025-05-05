---
unique-page-id: 18874634
description: Doppelte Einträge in meinem Bericht - [!DNL Marketo Measure]
title: Doppelte Datensätze in meinem Bericht
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 10%

---

# Doppelte Datensätze in meinem Bericht {#duplicate-records-in-my-report}

>[!NOTE]
>
>Möglicherweise werden in der Dokumentation Anweisungen für &quot;[!DNL Marketo Measure]&quot; angezeigt, in Ihrem CRM-System wird jedoch weiterhin &quot;[!DNL Bizible]&quot; angezeigt. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Wenn Sie in [!DNL Salesforce] in die [!DNL Marketo Measure] Berichte eintauchen, finden Sie möglicherweise „doppelte“ Einträge in Ihren Berichten. Dies wird Ihnen wahrscheinlich beim Überprüfen [!DNL Marketo Measure] vordefinierten Berichte auffallen.

Bei der Berichterstellung mit dem Objekt der Käufer-Touchpoints oder dem Buyer Attribution Touchpoint-Objekt ist es wichtig zu verstehen, dass Sie nicht mehr über die Anzahl der Leads, Kontakte oder Vertriebschancen berichten, sondern vielmehr über die Anzahl der Käufer-Touchpoints oder der Käufer-Attribution-Touchpoints, die mit diesen Standardobjekten (Leads, Kontakte, Vertriebschancen) verknüpft sind.

Nehmen wir den folgenden Bericht als Beispiel:

Dies ist ein Bericht **Kontakte mit Käufer-Touchpoints**. Dies bedeutet wiederum, dass wir die Anzahl der Touchpoints prüfen, die mit einem einzelnen Kontakt verbunden sind.

![](assets/1.gif)

Wie Sie sehen können, sieht es so aus, als gäbe es drei James Williams Kontakte im Bericht, und daher könnten Sie denken, „Duplikate!“

Dieser Bericht zeigt jedoch die Anzahl der Touchpoints im Zusammenhang mit James an. Innerhalb des Berichts können Sie sehen, dass James einen individuellen FT (First Touch), einen individuellen LC, ein Formular (Lead Creation Touch) und einen PostLC Touchpoint (eine Formularübermittlung, die nach dem LC Touchpoint erfolgt) hat.

Wenn Sie die „Anzahl der Kontakte“ verstehen möchten, können Sie die Felder „Anzahl - Erstkontakt“, „Kontakt zur Lead-Erstellung zählen“ oder „U-förmig zählen“ verwenden, um zu verstehen, wie viele Kontakte Marketing-Interaktionen hatten.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Stock-SFDC-Berichte](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
