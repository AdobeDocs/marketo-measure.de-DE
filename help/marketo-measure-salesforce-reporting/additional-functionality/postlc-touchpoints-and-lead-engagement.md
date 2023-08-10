---
unique-page-id: 18874562
description: PostLC-Touchpoints und Lead-Interaktion - Marketo Measure - Produktdokumentation
title: PostLC-Touchpoints und Lead-Interaktion
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---

# PostLC-Touchpoints und Lead-Interaktion {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] Touchpoints nach der Lead-Erstellung (PostLC) stehen Kunden zur Verfügung, die Multi-Touch-Attributionsmodelle (W-Shape und höher) verwenden. Wenn ein Lead oder Kontakt zu Ihrer Website zurückkehrt und weiterhin Formulare ausfüllt, werden diese Formulare bei diesen Übermittlungen als PostLC-Touchpoints registriert. Mit diesen Touchpoints können Sie sehen, welche Inhalte Leads dazu bringen, lange nach der ersten Konversion weiterhin mit Ihrer Site zu interagieren. PostLC-Touchpoints teilen Attributionskredite mit allen zwischengeschalteten Touchpoints innerhalb einer Chance. Ein Zuordnungskredit von 10 % wird zwischengeschalteten Touchpoints zugewiesen und gleichmäßig auf alle Touches verteilt.

![](assets/1.png)

Sie können die Anzahl der PostLC-Touchpoints anpassen, die in [!DNL SFDC]. In der Regel wird empfohlen, bis zu fünf PostLC-Touchpoints hochzuladen. Jeder Touchpoint nimmt 1 KB in [!DNL SFDC].

>[!NOTE]
>
>Anweisungen zum Anpassen der PostLC-Touchpoint-Einstellungen finden Sie am Ende dieses Artikels.

PostLC-Touchpoints sind dynamisch. Als Lead oder Kontakt sendet PostLC-Formulare weiterhin. [!DNL Marketo Measure] aktualisiert die PostLC-Touchpoints in Ihrem CRM-System, um Ihnen die neuesten Formularübermittlungen anzuzeigen. Wenn Sie eine Beschränkung von 5 PostLC-Touchpoints festgelegt haben, [!DNL Marketo Measure] Drücken Sie immer die 5 _Zuletzt verwendet_ Touchpoints auf Ihr CRM.  In diesem Beispiel hat dieses Konto die PostLC-Grenze auf vier Touchpoints gesetzt. Dieses Lead hat bereits die maximale Anzahl von PostLC-Touchpoints erreicht, die es in Ihrem CRM-System haben kann. Der letzte PostLC Touch fand am 06.02.2018 statt. Sollte diese Person am folgenden Tag ein anderes Formular ausfüllen, [!DNL Marketo Measure] entfernt den ersten PostLC-Touchpoint vom 9.11.2017, um den neuesten Touchpoint vom 7.2.2018 hinzuzufügen.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] aktualisiert nur PostLC-Touchpoints auf Lead oder Kontakt und aktualisiert PostLC-Attributions-Touchpoints auf einer Opportunity nicht. Alle relevanten PostLC-Touchpoints auf einem Kontakt werden in die Gelegenheit aufgenommen.

## Ändern der PostLC-Touchpoint-Einstellungen {#how-to-change-postlc-touchpoint-settings}

Um die PostLC-Touchpoint-Einstellungen für Leads oder Kontakte anzupassen, folgen Sie den unten stehenden Anweisungen.

**Leads**

1. Melden Sie sich bei Ihrer [!DNL Marketo Measure] Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und gehen Sie zu [!UICONTROL Einstellungen].

1. Wählen Sie unter CRM die Option **[!UICONTROL Leads]**.

1. Geben Sie die Anzahl der postLC-Touchpoints ein, die Sie an Ihre Leads senden möchten, und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/3.png)

**Kontakte**

1. Melden Sie sich bei Ihrer [!DNL Marketo Measure] Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und gehen Sie zu [!UICONTROL Einstellungen].

1. Wählen Sie unter CRM die Option **[!UICONTROL Kontakte]**.

1. Geben Sie die Anzahl der postLC-Touchpoints ein, die Sie an Ihre Kontakte senden möchten, und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/4.png)
