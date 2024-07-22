---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] Berechtigungssätze - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Berechtigungssätze"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 3%

---

# [!DNL Marketo Measure]-Berechtigungssätze {#marketo-measure-permission-sets}

Erfahren Sie, wie Sie in Salesforce auf Berechtigungssätze vom Typ [!DNL Marketo Measure] zugreifen und diese zuweisen.

## [!DNL Marketo Measure]-Berechtigungssätze {#marketo-measure-permission-sets-1}

Im Paket [!DNL Marketo Measure] Salesforce sind drei Berechtigungssätze enthalten. Diese Berechtigungssätze bieten Zugriff auf [!DNL Marketo Measure] für Administratoren, Marketingexperten und Standardbenutzer.

So greifen Sie auf Berechtigungssätze in Salesforce zu und weisen sie zu:

1. Klicken Sie auf **[!UICONTROL Einrichten]**.
1. Klicken Sie am linken Rand auf **[!UICONTROL Benutzer]** und dann auf **[!UICONTROL Berechtigungssätze]**.
1. Wählen Sie den gewünschten [!DNL Marketo Measure] Berechtigungssatz aus.
1. Klicken Sie auf **[!UICONTROL Zuweisungen verwalten]** und dann auf **[!UICONTROL Zuweisungen hinzufügen]**.
1. Wählen Sie die Benutzer für den Berechtigungssatz aus und klicken Sie auf **[!UICONTROL Zuweisen]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Berechtigungssätze - Erklärung {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Administrator</strong></span></td> 
   <td><span>Ermöglicht einem SFDC-Administrator das Erstellen, Lesen, Schreiben und Löschen von Datensätzen aus [!DNL Marketo Measure] -Objekten. Für die Lizenz, unter der [!DNL Marketo Measure] Daten an SFDC sendet, sollte dieser Berechtigungssatz aktiviert sein. Außerdem wird empfohlen, dass diese Lizenz die Möglichkeit hat, konvertierte Leads in den Szenarien zu bearbeiten, in denen der Lead konvertiert wird, bevor [!DNL Marketo Measure] Daten auf den Datensatz anwendet. Dadurch wird eine Genauigkeit bei der Berichterstellung zwischen Salesforce und [!DNL Marketo Measure] sichergestellt. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Mehr dazu hier</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Marketingbenutzer</strong></span></td> 
   <td><span>Ermöglicht es Marketing-Benutzern, Datensätze aus [!DNL Marketo Measure] -Objekten zu lesen und zu schreiben. Für alle Mitglieder des Marketing-Teams sollte der Berechtigungssatz [!DNL Marketo Measure] Marketing-Benutzer aktiviert sein. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Standardbenutzer</strong></span></td> 
   <td><span>Ermöglicht dem Benutzer das Lesen von Datensätzen aus [!DNL Marketo Measure] -Objekten.</span></td> 
  </tr> 
 </tbody> 
</table>

Entwicklungsteams für eingehende Verkäufe und Kundenbetreuer können von [!DNL Marketo Measure] -Daten profitieren. Wenn diese Rollen [!DNL Marketo Measure] -Daten in Berichten verwenden möchten, aktivieren Sie den Berechtigungssatz [!DNL Marketo Measure] Standardbenutzer .

>[!NOTE]
>
>Darüber hinaus muss für den Benutzer, mit dem wir verbunden sind, das Profil &quot;Marketing-Benutzer&quot; [!DNL Salesforce] auf Benutzerebene aktiviert sein, damit wir auf das Campaign-Objekt zugreifen können. Um dies zu überprüfen, klicken Sie auf **[!UICONTROL Einrichten]** > **[!UICONTROL Benutzer verwalten]** > **[!UICONTROL Profile]** > **[!UICONTROL Marketing-Benutzer]** > **Zugewiesene Benutzer**.
