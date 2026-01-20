---
unique-page-id: 18874588
description: Benutzerdefinierte Kampagnensynchronisierung - [!DNL Marketo Measure]
title: Synchronisierung benutzerspezifischer Kampagnen
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Synchronisierung benutzerspezifischer Kampagnen {#custom-campaign-sync}

Heute können Sie mit dem installierten [!DNL Marketo Measure] angeben, welche Kampagnen als Touchpoint einbezogen werden sollen. Da gibt es mehrere Hürden zu überwinden. Nachdem das [!DNL Marketo Measure] im CRM installiert wurde, kann es einige Zeit dauern, bis es von Ihrem Sicherheits-Team genehmigt wird. Darüber hinaus mangelt es an Flexibilität bei der Verwendung einer einzigen Auswahlliste für das Campaign-Objekt. Mit dieser neuen Funktion ist keine Paketinstallation erforderlich, um mit der Verwendung von Kampagnen- und Kampagnenmitglied-Datensätzen zu beginnen. Sie können Regeln erstellen, um genau zu definieren, welche Datensätze erstellt werden können, um genau zu definieren, welche Datensätze geeignet sind.

## Anforderungen {#requirements}

* Die Kampagnensynchronisierung ist in allen Ebenen verfügbar
* Um Daten zu importieren, müssen Sie weiterhin Ihr CRM mit Ihrem [!DNL Marketo Measure]-Konto verbinden

## Funktionsweise {#how-it-works}

1. Mit AccountAdmin-Berechtigungen können Sie zu **[!UICONTROL Einstellungen]** > **[!UICONTROL Kampagnen]** navigieren und die Regelbenutzeroberfläche Kampagnenmitglieder synchronisieren sehen.
1. Klicken Sie auf das Symbol **+** , um mit der Erstellung einer Regel zu beginnen.

   ![](assets/1-1.png)

1. Sie können eine Regel aus den Feldern [!UICONTROL Kampagne] oder [!UICONTROL Kampagnenmitglied] erstellen. Füllen Sie den Rest der Regel mit dem Operator und dem Wert aus, den wir validieren sollen. Im folgenden Beispiel prüfen wir anhand des Namens nach einer bestimmten Kampagne.

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, können [!DNL Marketo Measure] nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.

1. Wählen Sie das Touchpoint-Datum aus. Die Liste der möglichen Daten wird angezeigt, nachdem Sie eine geschweifte Klammer `{` eingegeben haben. Wählen Sie dann das Datum aus, das auf alle Touchpoints angewendet werden soll, die aus der Regel erstellt wurden.

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >Wenn Sie benutzerdefinierte Kampagnen-Synchronisierungsregeln verwenden, lesen [!DNL Marketo Measure] keine Aktualisierungen, die Sie mit der Schaltfläche Massen-Update des Touchpoint-Datums vorgenommen haben.

1. Klicken Sie auf das Häkchen und fügen Sie dann bei Bedarf zusätzliche Regeln für weitere Kampagnen hinzu.

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >Nachdem nun neben der CRM-Synchronisierung Regeln definiert sind, geraten die angegebenen Regeln natürlich in Konflikt. Wenn Sie sich dafür entscheiden, weiterhin sowohl den benutzerdefinierten Kampagnensynchronisierungstyp _als auch_ CRM-Synchronisierungstyp zu verwenden, ist es wichtig, Regeln zu erstellen, damit Ihre CRM-Synchronisierungstypen nicht ignoriert werden.

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >Wenn Sie erwägen, den Benutzer des [!UICONTROL CRM-Synchronisierungstyps] letztendlich zu stoppen, ist es ideal, Regeln zu erstellen, die nicht auf den „Synchronisierungstyp“ verweisen, aber _weiterhin_ die aktuellen CRM-Touchpoints beibehalten. Auf diese Weise funktionieren die Regeln immer noch, wenn/wenn dieser Wechsel erfolgt.

Hier ist ein Beispiel, wie das aussehen würde, damit keine vorhandenen CRM-Touchpoints verloren gehen:

## Validierung {#validation}

Sie können in Campaign einfach die Buyer Touchpoints und Buyer Attribution Touchpoint-Datensätze überprüfen, um sicherzustellen, dass die Regeln ordnungsgemäß funktionieren. Im Folgenden finden Sie eine BAT, die mit dem entsprechenden dynamischen Touchpoint-Datum erstellt und aus der Kampagne abgerufen [!DNL Marketo Measure]. Das Feld Erstellungsdatum befindet sich im Bild darunter.

![](assets/6-1.png)

## Wird getestet {#testing}

1. Die Funktion Kampagnensynchronisierung verfügt über eine Testfunktion, mit der Sie überprüfen können, ob die von Ihnen erstellten Regeln tatsächlich den Kampagnenkriterien entsprechen. Klicken Sie zunächst auf die Schaltfläche [!UICONTROL Test]. Die Regeln müssen zuerst gespeichert werden, bevor Sie mit dem Testen beginnen können.

   ![](assets/7-1.png)

   Es wird ein Popup angezeigt, in dem Sie eine Kampagnen-ID (entweder 15 oder 18 Zeichen aus dem CRM) zum Testen eingeben können. Der Punkt ist, die Kampagnen-ID aus dem CRM einzugeben, das Sie synchronisieren wollten, um sicherzustellen, dass sie mit der von Ihnen erstellten Regel übereinstimmt.

   ![](assets/8-1.png)

1. Nachdem Sie auf [!UICONTROL Test] geklickt haben, sehen Sie den Namen der Kampagne und die Anzahl der Kampagnenmitglieder, die für Touchpoints infrage kommen. Darunter wird eine Tabelle mit allen Regeln angezeigt, die Ihrer Kampagnen-ID entsprechen. Nur die Übereinstimmungen werden angezeigt.

   ![](assets/9.png)

1. Sie können auch auf die Anzahl der Mitglieder klicken, um eine Liste der Leads und Kontakte und ihrer IDs anzuzeigen, die Teil der Kampagnenregel-Eignung sind. Dies ist nur ein Beispielsatz und zeigt bis zu 50 an, damit Sie eine Vorstellung davon erhalten, welche Datensätze qualifiziert sind.

   ![](assets/10.png)
