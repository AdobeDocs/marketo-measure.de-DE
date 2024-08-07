---
unique-page-id: 18874614
description: Leads mit dem Bericht zu Touchpoints für Käufer - [!DNL Marketo Measure]
title: Leads mit dem Bericht "Kunden-Touchpoints"
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 8%

---

# Leads mit dem Bericht &quot;Kunden-Touchpoints&quot; {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>Sie sehen möglicherweise Anweisungen mit &quot;[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;[!DNL Bizible]&quot; in Ihrem CRM-System. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Standardmäßig stehen Ihnen viele Berichterstellungsfunktionen zur Verfügung, wenn es um [!DNL Marketo Measure] geht. Es werden jedoch einige zusätzliche Berichtstypen empfohlen. Erfahren Sie unten, wie Sie mit dem Berichtstyp &quot;Touchpoints für Käufer&quot;eine inklusive Leads erstellen.

1. Navigieren Sie in [!DNL Salesforce] zu Ihrer Einrichtungsoption. Erweitern Sie von dort die Gruppierung &quot;Erstellen&quot;und wählen Sie **[!UICONTROL Berichtstypen]** aus.

   ![](assets/1.jpg)

1. Wählen Sie **[!UICONTROL Neuer benutzerdefinierter Berichtstyp]** aus.

   ![](assets/2.jpg)

1. Legen Sie das primäre Objekt als &quot;Leads&quot;und in der Eingabe &quot;Beschriftung für Berichtstyp&quot;die Option &quot;Leads mit Käufer-Touchpoints - Inclusive&quot;fest. Speichern Sie den Bericht in der Kategorie &quot;Leads&quot;und ändern Sie den Bereitstellungsstatus in **[!UICONTROL Bereitgestellt]**. Wählen Sie dann **[!UICONTROL Weiter]** aus.

   ![](assets/3.jpg)

1. Wählen Sie für die Objektbeziehungen das Objekt **[!DNL Marketo Measure]Persons** als sekundäres Objekt aus. Wählen Sie für die A-zu-B-Beziehung den Wert &quot;Jeder A-Datensatz muss mindestens einen zugehörigen &quot;B&quot;-Datensatz aufweisen.&quot; Von dort aus werden Sie das Objekt &quot;Buyer Touchpoint&quot;verknüpfen und dieselbe Beziehung zwischen den Objekten B und C auswählen.

   ![](assets/4.jpg)

1. Speichern und erstellen Sie einige Berichte!
