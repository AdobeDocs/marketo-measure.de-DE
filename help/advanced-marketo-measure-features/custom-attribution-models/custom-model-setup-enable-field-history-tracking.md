---
unique-page-id: 18874777
description: Benutzerdefinierte Modelleinrichtung - Feldverlauf-Tracking aktivieren - [!DNL Marketo Measure] - Produktdokumentation
title: Benutzerdefinierte Modelleinrichtung - Feldverlauf-Tracking aktivieren
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Benutzerdefinierte Modelleinrichtung: Feldverlauf-Tracking aktivieren {#custom-model-setup-enable-field-history-tracking}

## Warum und wann die Verfolgung des Feldverlaufs aktiviert wird {#why-and-when-to-enable-field-history-tracking}

Wenn Sie sich dafür entscheiden, ein benutzerdefiniertes Feld als Phase in Ihr benutzerdefiniertes Attributionsmodell einzuschließen, verfolgen Sie den Feldverlauf **muss aktiviert sein** für dieses Feld. Durch die Aktivierung des Trackings des Feldverlaufs können Sie [!DNL Salesforce] , um jedes Mal zu verfolgen, wenn das benutzerdefinierte Feld bearbeitet wird, indem Sie einen Datensatz in der Tabelle Verlauf verfolgen erstellen. [!DNL Marketo Measure] kann diese Tabelle herunterladen und diese Informationen verwenden, um die Zeit und den Tag zu messen, an dem eine &quot;Transition&quot;aufgetreten ist. Ohne Feldverlauf-Tracking [!DNL Marketo Measure] kann Änderungen in Bezug auf dieses Feld nicht verfolgen.

Wenn nur [!UICONTROL Lead-Status] oder Opportunity Stages im benutzerdefinierten Modell verwendet werden, ist es nicht erforderlich, die Verfolgung des Feldverlaufs zu aktivieren, da sie automatisch als Phasenübergang verfolgt wird.

Befolgen Sie die unten stehenden Anweisungen, um die Verfolgung des Feldverlaufs zu aktivieren.

## Feldverlauf-Tracking aktivieren {#enable-field-history-tracking}

>[!NOTE]
>
>Sie müssen Systemadministrator sein, um diese Änderungen an den Feldern im Objekt &quot;Lead/Kontakt/Chancen&quot;vornehmen zu können.

1. Gehen Sie zum Objekt, in dem sich das benutzerdefinierte Feld befindet, und klicken Sie auf die Schaltfläche **[!UICONTROL Verlaufsverfolgung festlegen]** Schaltfläche.

   ![](assets/1.png)

1. Wählen Sie die Felder aus, für die Sie Änderungen verfolgen möchten.

   ![](assets/2.png)

[!DNL Marketo Measure] kann einen Datensatz nur dann erneut importieren, wenn er feststellt, dass der Datensatz vor kurzem geändert wurde. Formelfelder ändern einen Datensatz technisch nicht, wenn er sich ändert, da er die Berechnung im Hintergrund durchführt. Wir haben Probleme festgestellt, bei denen eine Regel übersprungen wird, weil [!DNL Marketo Measure] hat die Datensatzänderung nicht gesehen, daher wird empfohlen, **keine Formelfelder in Regeldefinitionen verwenden**. Die Lösung besteht darin, ein Textfeld zu erstellen und dieses Feld mit einem Workflow zu füllen, der jedes Mal, wenn der Datensatz bearbeitet wird oder den Kriterien entspricht, den richtigen Wert oder die richtige Berechnung enthält. Dies setzt voraus, dass alle Datensätze bearbeitet werden, damit der Workflow rückwirkend alte Datensätze bearbeiten kann.
