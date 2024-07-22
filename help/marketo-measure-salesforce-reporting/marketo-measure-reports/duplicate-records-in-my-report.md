---
unique-page-id: 18874634
description: Duplizieren von Datensätzen in meinem Bericht - [!DNL Marketo Measure]
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
>Sie sehen möglicherweise Anweisungen mit &quot;[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;[!DNL Bizible]&quot; in Ihrem CRM-System. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Wenn Sie in die [!DNL Marketo Measure] Berichte in [!DNL Salesforce] eintauchen, können Sie beginnen, &#39;doppelte&#39; Datensätze in Ihren Berichten zu finden. Dieses Gefühl wird Ihnen wahrscheinlich bei der Überprüfung von vordefinierten Berichten zu [!DNL Marketo Measure] begegnen.

Bei der Berichterstellung mit dem Touchpoints-Objekt des Käufers oder dem Buyer Attribution Touchpoint-Objekt müssen Sie wissen, dass Sie nicht mehr über die Anzahl der Leads, Kontakte oder Gelegenheiten berichten, sondern vielmehr über die Anzahl der Touchpoints des Käufers oder der Käufers, die mit diesen Standardobjekten (Leads, Kontakte, Chancen) verknüpft sind.

Nehmen wir als Beispiel den folgenden Bericht:

Dies ist ein Bericht vom Typ **Kontakte mit Kunden-Touchpoints** . Auch dies bedeutet, dass wir uns die Anzahl der Touchpoints ansehen, die einem einzelnen Kontakt zugeordnet sind.

![](assets/1.gif)

Wie Sie sehen können, scheint es drei James Williams-Kontakte in dem Bericht zu geben, und deshalb denken Sie vielleicht: &quot;Duplikate!&quot;

Dieser Bericht zeigt jedoch die Anzahl der Touchpoints im Zusammenhang mit James. Im Bericht sehen Sie, dass James über einen individuellen FT (Erstkontakt), einen einzelnen LC, ein Formular (Lead Creation Touch) und einen PostLC-Touchpoint (eine Formularübermittlung, die nach dem LC-Touchpoint erfolgt) verfügt.

Wenn Sie die Anzahl der Kontakte verstehen möchten, können Sie dann die Felder &quot;Zählung - Erstkontakt&quot;, &quot;Kontaktanzahl - Erstellung zählen&quot;oder &quot;Anzahl U-förmig&quot;verwenden, um zu verstehen, wie viele Kontakte Marketinginteraktionen hatten.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: SFDC-Lagerberichte](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
