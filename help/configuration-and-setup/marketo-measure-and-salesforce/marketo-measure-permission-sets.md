---
unique-page-id: 18874789
description: "[!DNL Marketo Measure] Berechtigungssätze - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Berechtigungssätze"
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 1%

---

# [!DNL Marketo Measure] Berechtigungssätze {#marketo-measure-permission-sets}

Erfahren Sie, wie Sie auf zugreifen und zuweisen [!DNL Marketo Measure] Berechtigungssätze in Salesforce.

## [!DNL Marketo Measure] Berechtigungssätze {#marketo-measure-permission-sets-1}

Drei Berechtigungssätze sind im [!DNL Marketo Measure] Salesforce-Paket. Diese Berechtigungssätze bieten Zugriff auf [!DNL Marketo Measure] für Administratoren, Marketingexperten und Standardbenutzer.

So greifen Sie auf Berechtigungssätze in Salesforce zu und weisen sie zu:

1. Klicken **[!UICONTROL Einrichtung]**.
1. Klicken Sie am linken Rand auf **[!UICONTROL Benutzer]**, dann **[!UICONTROL Berechtigungssätze]**.
1. Wählen Sie die [!DNL Marketo Measure] Berechtigungssatz, den Sie zuweisen möchten.
1. Klicken **[!UICONTROL Zuweisungen verwalten]**, dann **[!UICONTROL Zuweisungen hinzufügen]**.
1. Wählen Sie die Benutzer für den Berechtigungssatz aus und klicken Sie auf **[!UICONTROL Zuweisen]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Erläuterung der Berechtigungssätze {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Administrator</strong></span></td> 
   <td><span>Ermöglicht einem SFDC-Administrator das Erstellen, Lesen, Schreiben und Löschen von Datensätzen aus [!DNL Marketo Measure] Objekte. Die Lizenz, unter der [!DNL Marketo Measure] sendet Daten an SFDC, sollte dieser Berechtigungssatz aktiviert sein. Darüber hinaus wird empfohlen, dass diese Lizenz die Möglichkeit hat, konvertierte Leads in den Szenarien zu bearbeiten, in denen das Lead vor [!DNL Marketo Measure] Anwenden von Daten auf den Datensatz. Dadurch wird die Genauigkeit der Berichterstattung zwischen Salesforce und [!DNL Marketo Measure]. <a href="http://releasenotes.docs.salesforce.com/en-us/spring17/release-notes/rn_sales_leads_view_converted.htm">Mehr dazu hier</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Marketingbenutzer</strong></span></td> 
   <td><span>Marketing-Benutzer können Datensätze aus lesen und schreiben [!DNL Marketo Measure] Objekte. Alle Mitglieder des Marketing-Teams sollten über die [!DNL Marketo Measure] Berechtigungssatz für Marketing-Benutzer aktiviert. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Standardbenutzer</strong></span></td> 
   <td><span>Ermöglicht dem Benutzer das Lesen von Datensätzen aus [!DNL Marketo Measure] Objekte.</span></td> 
  </tr> 
 </tbody> 
</table>

Entwicklungsteams für eingehende Verkäufe und Kundenbetreuer können von [!DNL Marketo Measure] Daten. Wenn diese Rollen [!DNL Marketo Measure] -Daten in der Berichterstellung aktivieren Sie die [!DNL Marketo Measure] Standardberechtigungssatz für Benutzer.

>[!NOTE]
>
>Darüber hinaus muss der Benutzer, mit dem wir verbunden sind, über den &quot;Marketing-Benutzer&quot;verfügen. [!DNL Salesforce] Profil auf Benutzerebene aktiviert, damit wir auf das Campaign-Objekt zugreifen können. Um dies zu überprüfen, klicken Sie auf **[!UICONTROL Einrichtung]** > **[!UICONTROL Benutzer verwalten]** > **[!UICONTROL Profile]** > **[!UICONTROL Marketing-Benutzer]** > **Zugewiesene Benutzer**.
