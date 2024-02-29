---
unique-page-id: 18874765
description: Testen der Marketo Measure-Integration mit einer Salesforce-Sandbox - [!DNL Marketo Measure]
title: Testen der Marketo Measure-Integration mit einer Salesforce-Sandbox
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Testen der Marketo Measure-Integration mit einer Salesforce-Sandbox {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;Bizible&quot;in Ihrem CRM. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Eines der [!DNL Marketo Measure] Kernfunktionen sind die Fähigkeit, Ihre digitalen Marketingbemühungen durch Aktionen auf Ihrer Website zu verfolgen und diese Daten dann in Ihre Produktion zu übertragen. [!DNL Salesforce org] durch Leads und Kontakte. In der Regel werden jedoch keine eingehenden Leads von Ihrer Website innerhalb einer Sandbox-Integration erstellt, sodass der Fokus auf Daten von einer rein Offline-Perspektive aus liegt.

Im Folgenden finden Sie die beiden Quellen, auf die in beiden Testphasen verwiesen wird. [Schritte 1-4](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&amp;language=en_US&amp;type=5) und [Schritte 5-6](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md). Es wird empfohlen, diese Dokumente zu überprüfen, da sie in einigen Bereichen detaillierter sind.

1. Sie müssen einige Leads in einer CSV-Datei erstellen, damit Sie sie in eine Kampagne hochladen können. Dies lässt sich erreichen, indem Sie einige Leads über einen Bericht in Ihrer Produktions-Salesforce exportieren. Andernfalls können Sie Leads in einer Excel-Datei manuell erstellen und dann als CSV-Datei für den Import speichern. Man braucht nur etwa 20 Datensätze. Die Datei muss die folgenden Spalten enthalten:

   1. E-Mail
   1. Unternehmen
   1. Nachname
   1. Vorname (optional, jedoch empfohlen)

1. Melden Sie sich bei Ihrer Sandbox-Umgebung an.
1. Erstellen Sie eine Testkampagne. Verwenden Sie einen Kampagnentyp wie Ereignis oder Newsletter.
1. Laden Sie nach der Erstellung der Kampagne Leads als Campaign-Mitglieder hoch, indem Sie **[!UICONTROL Mitglieder verwalten]** > **[!UICONTROL Mitglieder hinzufügen]** > **[!UICONTROL Importieren von Dateien]**.
1. Nachdem dies abgeschlossen ist, wählen Sie im Campaign-Seitenlayout &quot;Käufer-Touchpoints aktivieren&quot;, bei dem es sich um ein Picklist-Feld handelt. Wählen Sie den Wert aus: **[!UICONTROL Alle Campaign-Mitglieder einschließen]**.

Danach wird eine Synchronisation zwischen [!DNL Marketo Measure] und [!DNL Salesforce] und wendet Touchpoints auf die Lead-Datensätze an. Es wird empfohlen, am nächsten Tag einen Bericht mit dem Namen &quot;Buyer Touchpoint on Leads&quot;im [!UICONTROL Touchpoints-Berichte des Käufers] auf der Registerkarte Berichte . Wenn der Bericht einen Touchpoint für jeden Lead ausfüllt, ist dies ein Zeichen für Erfolg.
