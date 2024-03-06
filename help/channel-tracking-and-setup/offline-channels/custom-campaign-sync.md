---
unique-page-id: 18874588
description: Benutzerdefinierte Kampagnensynchronisierung - [!DNL Marketo Measure]
title: Synchronisierung benutzerspezifischer Kampagnen
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Synchronisierung benutzerspezifischer Kampagnen {#custom-campaign-sync}

Heute mit dem installierten [!DNL Marketo Measure] -Paket können Sie angeben, welche Kampagnen als zulässigen Touchpoint einbezogen werden sollen. Es gibt mehrere Hürden dafür, wie es zuvor existierte. Einmal die [!DNL Marketo Measure] im CRM-System installiert ist, kann es einige Zeit dauern, bis die Validierung durch Ihr Sicherheitsteam erfolgt. Darüber hinaus ist die Verwendung einer einzelnen Auswahlliste im Campaign-Objekt nicht flexibel. Mit dieser neuen Funktion ist keine Paketinstallation erforderlich, um mit der Verwendung der Datensätze von Campaign und Campaign-Mitgliedern zu beginnen. Regeln können erstellt werden, um genau zu definieren, welche Datensätze erstellt werden können, um genau zu definieren, welche Datensätze zulässig sind.

## Anforderungen {#requirements}

* Die Kampagnensynchronisierung ist in allen Ebenen verfügbar
* Um Daten zu importieren, müssen Sie Ihr CRM-System weiterhin mit Ihrem [!DNL Marketo Measure] account

## Funktionsweise {#how-it-works}

1. Mit AccountAdmin-Berechtigungen können Sie zu **[!UICONTROL Einstellungen]** > **[!UICONTROL Kampagnen]** und sehen Sie sich die Benutzeroberfläche mit Regeln für Campaign-Mitglieder synchronisieren an.
1. Klicken Sie auf **+** -Symbol, um mit der Erstellung einer Regel zu beginnen.

   ![](assets/1-1.png)

1. Sie können eine Regel aus [!UICONTROL Kampagne] oder [!UICONTROL Campaign-Mitglied] -Felder. Füllen Sie den Rest der Regel mit dem Operator und Wert aus, den wir überprüfen sollen. Im folgenden Beispiel wird nach einer bestimmten Kampagne mit ihrem Namen gesucht.

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, [!DNL Marketo Measure] kann nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.

1. Wählen Sie das Touchpoint-Datum aus. Die Liste der möglichen Datumsangaben wird angezeigt, nachdem Sie eine geschweifte Klammer eingegeben haben `{` - können Sie das Datum auswählen, das Sie für alle Touchpoints anwenden möchten, die aus der Regel erstellt wurden.

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >Wenn Sie benutzerspezifische Kampagnensynchronisierungsregeln verwenden, [!DNL Marketo Measure] liest keine Aktualisierungen, die Sie mit der Schaltfläche Touchpoint-Datum für die Massenaktualisierung vorgenommen haben.

1. Klicken Sie auf das Häkchen und fügen Sie dann bei Bedarf zusätzliche Regeln für zusätzliche Kampagnen hinzu.

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >Nachdem nun Regeln neben der CRM-Synchronisierung definiert sind, beginnen die angegebenen Regeln natürlich mit Konflikten. Wenn Sie sich dafür entscheiden, weiterhin die benutzerdefinierte Kampagnensynchronisierung zu verwenden _und_ Beim Typ der CRM-Synchronisierung ist es wichtig, Regeln zu erstellen, damit Ihre CRM-Synchronisierungstypen nicht ignoriert werden.

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >Wenn Sie erwägen, den Benutzer der [!UICONTROL CRM-Synchronisierungstyp]ist es ideal, Regeln zu erstellen, die nicht auf den &quot;Synchronisierungstyp&quot;verweisen, aber _still_ die aktuellen CRM-Touchpoints beibehalten. Auf diese Weise funktionieren die Regeln immer noch, wenn/wenn dieser Wechsel erfolgt.

Hier ist ein Beispiel dafür, wie dies aussehen würde, sodass keine vorhandenen CRM-Touchpoints verloren gehen:

## Validierung {#validation}

Sie können die Touchpoint-Einträge für die Käuferzuordnung und die Käuferzuordnung in der Kampagne einfach überprüfen, um sicherzustellen, dass die Regeln ordnungsgemäß funktionieren. Hier ist ein BAT, das [!DNL Marketo Measure] mit dem entsprechenden dynamischen Touchpoint-Datum erstellt wurde, das aus der Kampagne abgerufen wurde. Das Feld Erstellungsdatum befindet sich in der Abbildung darunter.

![](assets/6-1.png)

## Testverfahren {#testing}

1. Die Funktion zur Kampagnensynchronisierung verfügt über eine Testfunktion, mit der Sie überprüfen können, ob die von Ihnen erstellten Regeln tatsächlich den Campaign-Kriterien entsprechen. Klicken Sie zunächst auf die Schaltfläche [!UICONTROL Test] Schaltfläche. Die Regeln müssen zuerst gespeichert werden, bevor Sie mit dem Testen beginnen können.

   ![](assets/7-1.png)

   Es wird ein Popup-Fenster angezeigt, in dem Sie eine Kampagnen-ID eingeben können (entweder 15 oder 18 Zeichen aus dem CRM), die getestet werden soll. Es geht darum, die Kampagnen-ID aus dem CRM-System einzugeben, das Sie synchronisieren wollten, um sicherzustellen, dass sie mit der von Ihnen erstellten Regel übereinstimmt.

   ![](assets/8-1.png)

1. Nachdem Sie auf [!UICONTROL Test]angezeigt, sehen Sie den Namen der Kampagne und die Anzahl der Campaign-Mitglieder, die für Touchpoints berechtigt sind. Unten wird eine Tabelle mit allen Regeln angezeigt, die mit Ihrer Kampagnen-ID übereinstimmen. Es werden nur die Übereinstimmungen angezeigt.

   ![](assets/9.png)

1. Sie können auch auf die Anzahl der Mitglieder klicken, um eine Liste der Leads und Kontakte sowie deren IDs anzuzeigen, die Teil der Kampagnenregel sind. Dies ist nur ein Beispielsatz, der bis zu 50 angezeigt wird, sodass Sie eine Vorstellung davon erhalten, welche Datensätze qualifiziert sind.

   ![](assets/10.png)
