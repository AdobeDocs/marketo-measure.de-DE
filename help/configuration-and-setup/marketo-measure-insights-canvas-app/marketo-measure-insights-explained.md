---
unique-page-id: 18874676
description: '[!DNL Marketo Measure] Insights erklärt - [!DNL Marketo Measure]'
title: Erläuterung von [!DNL Marketo Measure]-Insights
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Erläuterung von [!DNL Marketo Measure]-Insights {#marketo-measure-insights-explained}

Erfahren Sie mehr über die [!DNL Marketo Measure] Insights-Ansicht in [!DNL Salesforce], einschließlich der Darstellung der verschiedenen Symbole und der Verwendung der Funktion. Diese Funktion ist am hilfreichsten, um die ersten 20 Sitzungen eines Leads, Kontakts oder Kontos anzuzeigen.

Sobald jemand von der [!DNL Marketo Measure] JavaScript verfolgt wird und ein Formular auf Ihrer Website ausfüllt, wird die Person zu einem Lead in Ihrem System, und ihre digitalen Marketing-Daten werden an Ihre Salesforce (SFDC)-Organisation gesendet. In diesem Fall werden die Touchpoint-Daten im Abschnitt [!DNL Marketo Measure] Lead-Insights (eine Canvas-App) in den Objekten Lead/Kontakt/Opportunity/Konto angezeigt.

Zunächst sehen Sie im mittleren Teil Ihrer Einblicke die Anzahl der Sitzungen, die die Person auf Ihrer Website hatte. Sie können durch diese Sitzungen scrollen und beliebig navigieren.

![](assets/1.png)

Sie können sich die Zusammenfassung aller Ihrer Sitzungen ansehen, wenn Sie im mittleren oberen Teil Ihrer Einblicke auf „Alle“ klicken. Dort werden die Daten der einzelnen Sitzungen, der Kanal oder die Quelle für diese Sitzungen sowie eine Reihe von Symbolen zur Angabe weiterer Informationen angezeigt.

Als Erstes sehen Sie die FT- oder LC-Symbole. Diese stellen die Touchpoint-Position Ihrer aufgelisteten Sitzungen dar. FT steht insbesondere für First Touch und LC für Lead Creation. Sie können mehrere Sitzungen haben, aber nur ein Touchpoint kann der FT oder LC sein. Es werden nie mehrere FTs oder LCs gefunden, die einer Person zugeordnet sind.

Die Symbole, die wie Papier aussehen, zeigen an, dass eine Seitenansicht während der Sitzung stattgefunden hat. Wahrscheinlich enthält jede Sitzung dieses Symbol.

![](assets/2.png)

Das Symbol, das wie ein Becher aussieht, signalisiert, dass ein A/B-Test-Experiment stattgefunden hat. Wir integrieren zu diesem Zeitpunkt mit Optimizely und VWO. Mit dieser Integration können wir das Experiment und die Variante pushen, die der Benutzer in der jeweiligen Sitzung gesehen hat.

![](assets/3.png)

Wenn Sie auf eine bestimmte Sitzung klicken (Sie können dies tun, indem Sie auf das tatsächliche Datum der Sitzung oder im oberen mittleren Teil der gruppierten Sitzungen klicken), können Sie die Sitzungsdetails sehen. In jeder Sitzung können Sie alle spezifischen Seiten sehen, die der Benutzer gesehen hat, sortiert nach Datum und Uhrzeit.

![](assets/4.png)

Auf der rechten Seite jeder Sitzung sehen Sie mehr von den granularen Marketing-Daten, die die [!DNL Marketo Measure] in Ihre SFDC übertragen. In diesem Beispiel sehen Sie Anzeigengruppe, Anzeigeninhalt, Kampagne, Keyword, Medium. Sie können auch einen Bildlauf nach unten durchführen, um mehr der von uns bereitgestellten [!DNL Marketo Measure] anzuzeigen.

Sobald jemand unzählige Sitzungen hat, können Sie einige Filter in [!UICONTROL Insights] verwenden, um nach bestimmten Teilen seiner Interaktion auf Ihrer Site zu suchen. Sie können nach [!UICONTROL Touchpoint-Position] filtern.

Sie können auch nach Seitenansichten, AB-Tests oder Forms suchen.
