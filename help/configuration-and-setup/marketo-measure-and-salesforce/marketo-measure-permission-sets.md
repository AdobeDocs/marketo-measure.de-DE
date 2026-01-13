---
description: '[!DNL Marketo Measure] Berechtigungssätze - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure]-Berechtigungssätze'
exl-id: 84b7aa24-3934-4584-af05-02e804d00a98
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 4%

---


# [!DNL Marketo Measure]-Berechtigungssätze {#marketo-measure-permission-sets}

Erfahren Sie, wie Sie in Salesforce auf [!DNL Marketo Measure] Berechtigungssätze zugreifen und diese zuweisen können.

## [!DNL Marketo Measure]-Berechtigungssätze {#marketo-measure-permission-sets-1}

Im [!DNL Marketo Measure] Salesforce-Paket sind drei Berechtigungssätze enthalten. Diese Berechtigungssätze bieten Zugriff auf [!DNL Marketo Measure] für Administratoren, Marketing-Experten und Standardbenutzer.

So greifen Sie auf Berechtigungssätze in Salesforce zu und weisen diese zu:

1. Klicken Sie **[!UICONTROL Setup]**.
1. Klicken Sie am linken Rand auf **[!UICONTROL Benutzer]** und dann auf **[!UICONTROL Berechtigungssätze]**.
1. Wählen Sie den [!DNL Marketo Measure] Berechtigungssatz aus, den Sie zuweisen möchten.
1. Klicken Sie **[!UICONTROL Zuweisungen verwalten]** und dann **[!UICONTROL Zuweisungen hinzufügen]**.
1. Wählen Sie die Benutzer für den Berechtigungssatz aus und klicken Sie auf **[!UICONTROL Zuweisen]**.

   ![ 5](assets/1-5.png)

## [!DNL Marketo Measure] Berechtigungssätze - Erklärung {#marketo-measure-permission-sets-explained}

<table>
 <tbody>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Administrator</strong></span></td>
   <td><span>Ermöglicht einem SFDC-Administrator bzw. einer -Administratorin das Erstellen, Lesen, Schreiben und Löschen von Datensätzen aus [!DNL Marketo Measure]. Für die Lizenz, unter der [!DNL Marketo Measure] Daten an SFDC sendet, sollte dieser Berechtigungssatz aktiviert sein. Außerdem wird empfohlen, dass diese Lizenz in den Szenarien, in denen der Lead konvertiert wird, konvertierte Leads bearbeiten kann, bevor [!DNL Marketo Measure] Daten auf den Datensatz angewendet werden. Dadurch wird eine präzise Berichterstellung zwischen Salesforce und [!DNL Marketo Measure] sichergestellt. <a href="https://help.salesforce.com/articleView?id=release-notes.rn_sales_leads_view_converted.htm&amp;type=5&amp;release=206&amp;language=en_us">Mehr dazu hier</a>.</span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Marketingbenutzer</strong></span></td>
   <td><span>Ermöglicht es einem Marketing-Benutzer, Datensätze aus [!DNL Marketo Measure] Objekten zu lesen und zu schreiben. Für alle Mitglieder des Marketing-Teams sollte der Berechtigungssatz Marketing-Benutzer [!DNL Marketo Measure] aktiviert sein. <br></span></td>
  </tr>
  <tr>
   <td><span><strong>[!DNL Marketo Measure] Standardbenutzer</strong></span></td>
   <td><span>Ermöglicht Benutzenden, Datensätze aus [!DNL Marketo Measure] Objekten zu lesen.</span></td>
  </tr>
 </tbody>
</table>

Inbound-Vertriebs-Entwicklungsteams und Account-Manager können von [!DNL Marketo Measure] Daten profitieren. Wenn diese Rollen [!DNL Marketo Measure] Daten in Berichten verwenden möchten, aktivieren Sie den Berechtigungssatz „Standardbenutzer [!DNL Marketo Measure]&quot;.

>[!NOTE]
>Darüber hinaus muss für den Benutzer, über den wir verbunden sind, das [!DNL Salesforce] „Marketing-Benutzer“ auf Benutzerebene aktiviert sein, damit wir auf das Kampagnenobjekt zugreifen können. Um dies zu überprüfen, klicken Sie auf **[!UICONTROL Setup]** > **[!UICONTROL Benutzer verwalten]** > **[!UICONTROL Profile]** > **[!UICONTROL Marketing-Benutzer]** > **Zugewiesene Benutzer**.
