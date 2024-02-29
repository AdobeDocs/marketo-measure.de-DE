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

Erfahren Sie, wie Sie auf zugreifen und zuweisen [!DNL Marketo Measure] Berechtigungssätze in Salesforce.

## [!DNL Marketo Measure]-Berechtigungssätze {#marketo-measure-permission-sets-1}

Im [!DNL Marketo Measure] Salesforce-Paket. Diese Berechtigungssätze bieten Zugriff auf [!DNL Marketo Measure] für Administratoren, Marketingexperten und Standardbenutzer.

So greifen Sie auf Berechtigungssätze in Salesforce zu und weisen sie zu:

1. Klicks **[!UICONTROL Einrichtung]**.
1. Klicken Sie am linken Rand auf **[!UICONTROL Benutzer]**, dann **[!UICONTROL Berechtigungssätze]**.
1. Wählen Sie die [!DNL Marketo Measure] Berechtigungssatz, den Sie zuweisen möchten.
1. Klicks **[!UICONTROL Zuweisungen verwalten]**, dann **[!UICONTROL Zuweisungen hinzufügen]**.
1. Wählen Sie die Benutzer für den Berechtigungssatz aus und klicken Sie auf **[!UICONTROL Zuweisen]**.

   ![](assets/1-5.png)

## [!DNL Marketo Measure] Erläuterung der Berechtigungssätze {#marketo-measure-permission-sets-explained}

<table> 
 <tbody> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Administrator</strong></span></td> 
   <td><span>Ermöglicht einem SFDC-Administrator das Erstellen, Lesen, Schreiben und Löschen von Datensätzen aus [!DNL Marketo Measure] Objekte. Die Lizenz, unter der [!DNL Marketo Measure] sendet Daten an SFDC, sollte dieser Berechtigungssatz aktiviert sein. Außerdem wird empfohlen, dass diese Lizenz die Möglichkeit hat, konvertierte Leads in den Szenarien zu bearbeiten, in denen das Lead konvertiert wird, bevor [!DNL Marketo Measure] Anwenden von Daten auf den Datensatz. Dadurch wird die Genauigkeit der Berichterstattung zwischen Salesforce und [!DNL Marketo Measure]. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Mehr dazu hier</a>.</span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Marketingbenutzer</strong></span></td> 
   <td><span>Marketing-Benutzer können Datensätze aus lesen und schreiben [!DNL Marketo Measure] Objekte. Alle Mitglieder des Marketing-Teams sollten über die [!DNL Marketo Measure] Berechtigungssatz für Marketing-Benutzer aktiviert. <br></span></td> 
  </tr> 
  <tr> 
   <td><span><strong>[!DNL Marketo Measure] Standardbenutzer</strong></span></td> 
   <td><span>Ermöglicht es einem Benutzer, Datensätze aus [!DNL Marketo Measure] Objekte.</span></td> 
  </tr> 
 </tbody> 
</table>

Entwicklungsteams für eingehende Verkäufe und Kundenbetreuer können von [!DNL Marketo Measure] Daten. Wenn diese Rollen [!DNL Marketo Measure] -Daten in der Berichterstellung aktivieren Sie die [!DNL Marketo Measure] Standardberechtigungssatz für Benutzer.

>[!NOTE]
>
>Darüber hinaus muss der Benutzer, über den wir verbunden sind, über den &quot;Marketing-Benutzer&quot;verfügen. [!DNL Salesforce] Auf Benutzerebene aktiviertes Profil für den Zugriff auf das Campaign-Objekt. Um dies zu überprüfen, klicken Sie auf **[!UICONTROL Einrichtung]** > **[!UICONTROL Benutzer verwalten]** > **[!UICONTROL Profile]** > **[!UICONTROL Marketing-Benutzer]** > **Zugewiesene Benutzer**.
