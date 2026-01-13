---
description: Verlorene Vertriebschancen nach Marketing-Kanal geschlossen - [!DNL Marketo Measure]
title: Geschlossene verlorene Opportunitys nach Marketingkanal
exl-id: 010169fc-f7e7-4ab2-92fe-87e4250dd536
feature: Channels, Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 3%

---


# Geschlossene verlorene Opportunitys nach Marketingkanal {#closed-lost-opportunities-by-marketing-channel}

Obwohl dieser Bericht von Ihren Opportunity-Stadien abhängen kann, wird in diesem Bericht aufgezeigt, welche Marketing-Kanäle zu Opportunitys beigetragen haben, die nicht geschlossen wurden.

1. Klicken Sie auf **[!UICONTROL Registerkarte]** Berichte“ in Salesforce und wählen Sie **[!UICONTROL Neuer Bericht]** aus.

   ![Registerkarte &quot;Salesforce-Berichte“ mit hervorgehobener Schaltfläche „Neuer Bericht“](assets/1-3.jpg)

1. Wählen Sie in der Schnellsuche unter „Bizible Attribution“ den Berichtstyp **[!UICONTROL Bizible Attribution Touchpoint mit Opportunity]** und klicken Sie dann auf **[!UICONTROL Erstellen]**.

   ![Auswahl des Berichtstyps mit der Option Bizible Attribution Touchpoint mit Opportunity](assets/2-3.jpg)

1. Zeigen Sie am Anfang des Berichts &quot;[!UICONTROL Alle Bizible Attribution Touchpoints]&quot; an und passen Sie das Datumsfeld an den Zeitrahmen an, für den Sie einen Bericht erstellen möchten. In unserem Beispiel geht es um „All Time“. Ändern Sie außerdem das Berichtsformat von Tabellenformat zu Zusammenfassung.

   ![Berichtsfilter mit allen Bizible Attribution Touchpoints mit der Datumsbereichsauswahl](assets/3-3.jpg)

   ![Optionen für das Berichtsformat mit ausgewähltem Zusammenfassungsformat](assets/4-2.jpg)

1. Jetzt fügen wir dem Bericht Felder hinzu. Geben Sie in der Schnellsuche auf der linken Seite „Marketing-Kanal“ ein und fügen Sie ihn zur Gruppierung „Zusammenfassung“ im Bericht hinzu.

   ![Report Builder mit dem Feld „Marketing-Kanal“, das der Gruppierungsübersicht hinzugefügt wird](assets/5.jpg)

1. Als Nächstes fügen wir einen Filter hinzu, um nur abgeschlossene verlorene Opportunities zu betrachten. Suchen Sie in der Schnellsuche auf der linken Seite nach dem Feld „Staging“ und ziehen Sie es in den Filterbereich.

   ![Filterbereich des Berichts, in den das Feld „Phase“ gezogen wurde](assets/6.jpg)

1. Von dort aus wählen Sie die Lupe aus, um die Stadien auszuwählen, die Sie für „Closed Lost“-Gelegenheiten verwenden. In unserem Fall verwenden wir die standardmäßige „Closed Lost“-Benennung.

   ![Staging-Filterauswahl mit der Option für geschlossene verlorene Stadien](assets/7.jpg)

1. Führen Sie nun den Bericht aus!

   Dies ist ein Bericht zu Opportunitys, der vom Marketing-Kanal zusammengefasst wird, um die abgeschlossenen verlorenen Opportunitys kanalübergreifend zu messen. In diesem Bericht können Sie nachvollziehen, welche Kanäle möglicherweise nicht die gewünschte Leistung erbringen. Sie können beliebige Filter oder Felder hinzufügen, über die Sie einen Bericht erstellen möchten.

>[!MORELIKETHIS]
>[[!DNL Marketo Measure] Tutorials: Zusätzliche SFDC-Berichte](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/addtional-salesforce-reports)
