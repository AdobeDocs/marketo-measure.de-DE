---
description: Anleitung zum Testen der Marketo Measure-Integration mit einer Salesforce Sandbox für Marketo Measure-Benutzende
title: Testen der Marketo Measure-Integration mit einer Salesforce-Sandbox
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 10%

---

# Testen der Marketo Measure-Integration mit einer Salesforce-Sandbox {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Eine der [!DNL Marketo Measure] Kernfunktionen ist die Möglichkeit, Ihre digitalen Marketing-Maßnahmen durch Aktionen auf Ihrer Website zu verfolgen und diese Daten dann über Leads und Kontakte an Ihre [!DNL Salesforce org] zu übertragen. In der Regel werden jedoch keine eingehenden Leads von Ihrer Website innerhalb einer Sandbox-Integration erstellt, sodass der Datenfokus ausschließlich aus der Offline-Perspektive erfolgt.

Im Folgenden finden Sie die beiden Quellen, die für beide Testphasen referenziert werden. [Schritte 1-](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&language=en_US&type=5) und [Schritte 5-6](/help/channel-tracking-and-setup/syncing-offline-campaigns.md). Es wird empfohlen, diese Dokumente zu lesen, da sie in einigen Bereichen mehr Details enthalten.

1. Einige Leads müssen Sie in einer CSV-Datei erstellen, damit Sie sie in eine Kampagne hochladen können. Um dies zu erreichen, exportieren Sie einige Leads über einen Bericht in Ihrer Produktions-Salesforce. Andernfalls können Sie Leads manuell in einer Excel-Datei erstellen und diese dann als CSV zum Import speichern. Man braucht nur etwa 20 Datensätze. Die Datei muss die folgenden Spalten aufweisen:

   1. E-Mail
   1. Unternehmen
   1. Nachname
   1. Vorname (optional, aber empfohlen)

1. Melden Sie sich bei Ihrer Sandbox-Umgebung an.
1. Erstellen Sie eine Testkampagne. Verwenden Sie einen Kampagnentyp wie Ereignis oder Newsletter.
1. Laden Sie nach der Erstellung der Kampagne Leads als Kampagnenmitglieder hoch, indem Sie **[!UICONTROL Mitglieder verwalten]** > **[!UICONTROL Mitglieder hinzufügen]** > **[!UICONTROL Dateien importieren]** auswählen.
1. Wenn dies abgeschlossen ist, kehren Sie zum Kampagnenseiten-Layout zurück und geben Sie „Käufer-Touchpoints aktivieren“ ein Auswahllistenfeld an. Wählen Sie den Wert: **[!UICONTROL Alle Kampagnenmitglieder einschließen]**.

Danach wird eine Synchronisation zwischen [!DNL Marketo Measure] und [!DNL Salesforce] gestartet und Touchpoints werden auf die Lead-Datensätze angewendet. Wir empfehlen, am nächsten Tag einen Bericht mit dem Namen &quot;Buyer Touchpoint on Leads“ im Ordner &quot;[!UICONTROL &#x200B; Touchpoints-Berichte“ auf &#x200B;] Registerkarte „Berichte“ zu verwenden. Wenn der Bericht für jeden Lead einen Touchpoint ausfüllt, ist dies ein Zeichen für Erfolg.
