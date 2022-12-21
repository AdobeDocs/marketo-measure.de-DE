---
unique-page-id: 18874614
description: Leads mit dem Bericht zu Touchpoints für Käufer - [!DNL Marketo Measure] - Produktdokumentation
title: Leads mit dem Bericht "Kunden-Touchpoints"
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# Leads mit dem Bericht &quot;Kunden-Touchpoints&quot; {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen angezeigt, die[!DNL Marketo Measure]&quot; in unserer Dokumentation, sehen aber weiterhin &quot;[!DNL Bizible]&quot; in Ihrem CRM-System. Wir arbeiten daran, diese Aktualisierung durchzuführen, und das Rebranding wird sich in Kürze in Ihrem CRM widerspiegeln.

Standardmäßig stehen Ihnen viele Berichterstellungsfunktionen zur Verfügung, wenn es um Folgendes geht: [!DNL Marketo Measure], es gibt jedoch einige zusätzliche Berichtstypen, die wir empfehlen zu erstellen. Erfahren Sie unten, wie Sie mit dem Berichtstyp &quot;Touchpoints für Käufer&quot;eine inklusive Leads erstellen.

1. Navigieren Sie zur Einrichtungsoption unter [!DNL Salesforce]. Erweitern Sie von dort die Gruppierung &quot;Erstellen&quot;und wählen Sie **[!UICONTROL Berichtstypen]**.

   ![](assets/1.jpg)

1. Auswählen **[!UICONTROL Neuer benutzerdefinierter Berichtstyp]**.

   ![](assets/2.jpg)

1. Legen Sie das primäre Objekt als &quot;Leads&quot;und in der Eingabe &quot;Beschriftung für Berichtstyp&quot;die Option &quot;Leads mit Käufer-Touchpoints - Inclusive&quot;fest. Speichern Sie den Bericht in der Kategorie &quot;Leads&quot;und ändern Sie den Bereitstellungsstatus in **[!UICONTROL Bereitgestellt]**. Wählen Sie anschließend **[!UICONTROL Nächste]**.

   ![](assets/3.jpg)

1. Wählen Sie für die Objektbeziehungen die **[!DNL Marketo Measure]Personen** -Objekt als sekundäres Objekt. Wählen Sie für die A-zu-B-Beziehung den Wert &quot;Jeder A-Datensatz muss mindestens einen zugehörigen &quot;B&quot;-Datensatz aufweisen.&quot; Von dort aus beziehen Sie das Objekt &quot;Käufer Touchpoint&quot;und wählen dieselbe Beziehung zwischen den Objekten B und C aus.

   ![](assets/4.jpg)

1. Speichern und erstellen Sie einige Berichte!
