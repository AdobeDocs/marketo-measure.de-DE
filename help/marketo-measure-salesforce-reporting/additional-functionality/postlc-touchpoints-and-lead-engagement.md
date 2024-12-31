---
unique-page-id: 18874562
description: PostLC-Touchpoints und Lead-Interaktion - Marketo Measure - Produktdokumentation
title: PostLC-Touchpoints und Lead-Interaktion
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---

# PostLC-Touchpoints und Lead-Interaktion {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] Post-Lead Creation (PostLC)-Touchpoints sind für Kundinnen und Kunden verfügbar, die Multi-Touch-Attributionsmodelle (W-Shape und höher) verwenden. Wenn ein Lead oder Kontakt zu Ihrer Website zurückkehrt und weiterhin Formulare ausfüllt, registrieren sich diese Formularübermittlungen als PostLC-Touchpoints. Mit diesen Touchpoints können Sie sehen, welche Inhalte dazu führen, dass Leads noch lange nach ihrer ersten Konversion weiterhin mit Ihrer Site interagieren. PostLC-Touchpoints teilen sich das Attributionsguthaben mit allen zwischengeschalteten Touchpoints innerhalb einer Opportunity; 10 % Attributionsguthaben werden zwischengeschalteten Touchpoints zugewiesen und gleichmäßig auf alle Touches verteilt.

![](assets/1.png)

Sie können die Anzahl der PostLC-Touchpoints anpassen, die in [!DNL SFDC] angezeigt werden. Normalerweise empfehlen wir, bis zu fünf PostLC-Touchpoints zu pushen. Jeder Touchpoint benötigt [!DNL SFDC] 1 KB.

>[!NOTE]
>
>Eine Anleitung zum Anpassen der PostLC-Touchpoint-Einstellungen finden Sie am Ende dieses Artikels.

PostLC-Touchpoints sind dynamisch. Wenn ein Lead oder Kontakt weiterhin PostLC-Formulare sendet, aktualisiert [!DNL Marketo Measure] die PostLC-Touchpoints in Ihrem CRM, um Ihnen die neuesten Formularübermittlungen anzuzeigen. Wenn Sie ein Limit von 5 PostLC-Touchpoints festgelegt haben, übertragen [!DNL Marketo Measure] immer die fünf (_)_ Touchpoints an Ihr CRM.  In diesem Beispiel hat dieses Konto sein PostLC-Limit auf vier Touchpoints festgelegt. Dieser Lead hat bereits die maximale Anzahl von PostLC-Touchpoints erreicht, die er in Ihrem CRM haben kann. Der letzte PostLC Touch war am 2/6/2018. Wenn diese Person am folgenden Tag ein anderes Formular ausfüllen sollte, entfernt [!DNL Marketo Measure] den ersten PostLC-Touchpoint vom 11/9/2017, um den neuesten Touchpoint vom 2/7/2018 hinzuzufügen.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] aktualisiert nur PostLC-Touchpoints auf dem Lead oder Kontakt und aktualisiert keine PostLC-Attribution-Touchpoints auf einer Opportunity. Alle relevanten PostLC-Touchpoints eines Kontakts sind in der Opportunity enthalten.

## So ändern Sie die PostLC-Touchpoint-Einstellungen {#how-to-change-postlc-touchpoint-settings}

Gehen Sie wie folgt vor, um die PostLC-Touchpoint-Einstellungen für Ihre Leads oder Kontakte anzupassen.

**Leads**

1. Melden Sie sich bei Ihrem [!DNL Marketo Measure]-Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} an und gehen Sie zu [!UICONTROL Einstellungen].

1. Wählen Sie unter CRM **[!UICONTROL Leads]** aus.

1. Geben Sie die Anzahl der PostLC-Touchpoints ein, die Sie an Ihre Leads senden möchten, und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/3.png)

**Kontakte**

1. Melden Sie sich bei Ihrem [!DNL Marketo Measure]-Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} an und gehen Sie zu [!UICONTROL Einstellungen].

1. Wählen Sie unter CRM die Option **[!UICONTROL Kontakte]**.

1. Geben Sie die Anzahl der PostLC-Touchpoints ein, die Sie an Ihre Kontakte senden möchten, und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/4.png)
