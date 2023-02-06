---
unique-page-id: 18874773
description: Einrichten und Reporting von A/B-Tests - [!DNL Marketo Measure] - Produktdokumentation
title: Einrichten und Reporting von A/B-Tests
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---

# Einrichten und Reporting von A/B-Tests {#a-b-testing-set-up-and-reporting}

Die [!DNL Marketo Measure] Mit der A/B-Test-Integration können Sie die Auswirkungen Ihrer [Optimizely](https://optimizely.com/){target="_blank"} und VWO-Site-Experimente. In diesem Artikel finden Sie Anweisungen zum Hinzufügen von [!DNL Marketo Measure] Abschnitte A/B-Tests zum Lead, [!UICONTROL Kontakt], Groß-/Kleinschreibung und [!UICONTROL Chancen] Seitenlayouts. Wir werden auch allgemeine Berichtspraktiken und Empfehlungen für die Ausführung von [!DNL Marketo Measure] A/B-Berichtstypen.

## Einrichten {#set-up}

Fügen Sie die [!DNL Marketo Measure] Abschnitte zu A/B-Tests zu Lead, Kontakt, Fall und Chancen. [!DNL Marketo Measure] Mit der A/B-Test-Integration können Sie die Auswirkungen Ihrer [Optimizely](https://optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} Site-Experimente.

1. Überprüfen der Verwendung des Pakets [!DNL Marketo Measure] v3.9 oder höher. Gehen Sie dazu wie folgt vor: [!UICONTROL Salesforce] >[!UICONTROL Einrichten] > [!UICONTROL Installierte Packages].
1. Bearbeiten Sie das Layout der Lead-Seite und fügen Sie die **[!DNL Marketo Measure]A/B-Tests** Zugehörige Liste der Seiten.

   ![](assets/1.png)

1. Klicken Sie auf [!UICONTROL Schraubenschlüssel] Schaltfläche. Entfernen Sie das Feld &quot;Kennung&quot; aus der Liste der ausgewählten Felder. Hinzufügen **[!UICONTROL Experiment]**, **[!UICONTROL Variante]** und **[!UICONTROL DateReport]** -Felder. Ändern Sie &quot;[!UICONTROL Sortieren nach]&quot; **[!UICONTROL Datum gemeldet]** und wählen Sie **[!UICONTROL Absteigend]** in der Dropdown-Liste.

   ![](assets/2.png)

1. under [!UICONTROL Schaltflächen], deaktivieren **[!UICONTROL Neu]**.

   ![](assets/3.png)

1. Wenden Sie sich an [!DNL Marketo Measure] rep oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} , um die Funktion zu aktivieren.

## Berichterstellung {#reporting}

Kunden haben Zugriff auf verschiedene [!DNL Marketo Measure] A/B-Berichtstypen, mit denen Sie über A/B-Tests in Bezug auf Leads, Kontakte und Chancen berichten können:

* [!DNL Marketo Measure] A/BTests
* [!DNL Marketo Measure] A/BTests mit Kontakt
* [!DNL Marketo Measure] A/BTests mit Lead
* [!DNL Marketo Measure] A/BTests mit Chancen

![](assets/4.png)

A/B-Berichtstypen werden verwendet, um zu melden, für welche Lead oder Kontakt oder Gelegenheit ein A/B-Test durchgeführt wurde. Darüber hinaus können diese Berichte Ihnen den Umsatz zeigen, der mit einer Opportunity verbunden ist, die einem A/B-Test ausgesetzt war.

Beachten Sie, dass &quot;Optimizely/VWO&quot;eine Inhaltsvarianten-Plattform und kein Marketing-Kanal ist. Daher [!DNL Marketo Measure] A/B-Berichtstypen werden anders verwendet als Käufer-Touchpoint-Berichte. Mit den Berichtstypen für Käufer-Touchpoints können Sie nachvollziehen, welcher Marketing-Kanal (z. B. Paid Advertising, Web-Direktwerbung, Social) einen Lead oder Kontakt zu einer bestimmten Seite geführt hat. Allerdings [!DNL Marketo Measure] A/B-Berichtstypen können nicht verwendet werden, um Berichte darüber zu erstellen, wie eine Variante einen Lead oder eine Gelegenheit beeinflusst hat. Da es sich bei einer A/B-Test-Variante nicht um einen Kanal handelt, werden im Touchpoint des Käufers keine Details zur Variante angezeigt.

Im Folgenden finden Sie einige gängige Felder, die wir für die Berichterstellung zu A/B-Tests empfehlen, um Klarheit und Einblicke zu verbessern:

* Lead konvertiert
* Experiment
* Experimentkennung
* Variation
* Variations-ID
* Datum gemeldet

## [!DNL Salesforce] Beispielberichte {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B-Test mit Lead**

![](assets/5.png)

**[!DNL Marketo Measure]A/B-Test mit Opportunity**

![](assets/6.png)
