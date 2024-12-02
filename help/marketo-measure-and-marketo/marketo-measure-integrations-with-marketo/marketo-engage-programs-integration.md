---
unique-page-id: 42762729
description: '[!DNL Marketo Engage] Programmintegration - [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage] Programmintegration'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 2%

---

# [!DNL Marketo Engage] Programmintegration {#marketo-engage-programs-integration}

Durch die Integration von [!DNL Marketo Measure] in [!DNL Marketo Engage] Programme können unsere Kunden anfangen, Touchpoints für die Attribution-Verfolgung über die Marketo-Programmmitgliedschaften zu erstellen. Mit dieser Funktion können Marketingexperten Programmmitgliedschaften aus E-Mail- oder Interaktionsprogrammen verfolgen, die ansonsten nicht vom JavaScript [!DNL Marketo Measure] angezeigt werden und innerhalb der Attribution-Journey gemessen werden sollten.

## Verfügbarkeit {#availability}

Alle Ebenen.

## Anforderungen {#requirements}

* Marketo-Produktionsinstanz
* Salesforce- oder Microsoft Dynamics-Produktionsinstanz
* Beliebiges bezahltes [!DNL Marketo Measure]-Abonnement
* Marketo People Sync aktiviert ([!DNL Marketo Measure] Einstellungen)
* Marketo-Programme aktiviert ([!DNL Marketo Measure] Einstellungen)

## Einrichten {#setup}

**Regeln**

1. Um Regeln für Marketo-Programme einzurichten, navigieren Sie zu **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Programme]** . Klicken Sie auf das Symbol **+** , um mit der Erstellung Ihrer ersten Regel zu beginnen.

   ![](assets/one.png)

   ![](assets/two.png)

1. Sie können optional einen Namen für die Regel festlegen, wenn es hilfreich ist, diese zu verfolgen. Wählen Sie zunächst das Feld aus, um Ihre Regel aus der Liste der Felder Programm- und Programmmitgliedschaft zu definieren. Fahren Sie mit dem Erstellen der Regel fort, indem Sie den Operator und den erwarteten Wert auswählen, nach dem geprüft werden soll.

   ![](assets/three.png)

1. Fügen Sie innerhalb desselben Felds eine weitere Anweisung hinzu, um ein &quot;und&quot;-Kriterium in der Regel einzurichten, oder klicken Sie auf das &quot;+&quot;-Symbol außerhalb des Felds, um eine &quot;oder&quot;-Anweisung einzurichten.

   ![](assets/four.png)

1. Wählen Sie aus, welches Datums- oder Datums-/Uhrzeitfeld für die Zuordnung zum Touchpoint-Datum verwendet werden soll. Um die Liste der in Marketo verfügbaren Werte anzuzeigen, geben Sie eine geschweifte Klammer `{` ein. Daraufhin werden die verfügbaren Felder angezeigt.

   ![](assets/five.png)

   >[!NOTE]
   >
   >Wenn Ihre Regel das Aktivitätsdatum oder das Datum erfassen möchte, an dem ein Programmmitglied einen bestimmten Status erreicht hat, sollten Sie die Aktivitätsintegration [!DNL Marketo Engage] verwenden und eine Regel für den Aktivitätstyp &quot;Änderungsstatus in Progression&quot;einrichten.

   ![](assets/six.png)

Ihre fertige Regel sollte ungefähr so aussehen:

## Test {#test}

Nachdem Sie einige Regeln erstellt haben, sollten Sie sie testen, um zu überprüfen, ob Ihre Anweisung mit Ihren Programmen übereinstimmt.

1. Um einen Test auszuführen, klicken Sie auf die Schaltfläche **[!UICONTROL TEST]** , wie unten dargestellt.

   ![](assets/seven.png)

1. Es wird ein Modal angezeigt, in das Sie die Programm-ID aus Marketo eingeben können.

   ![](assets/eight.png)

   Sobald Sie die ID eingeben und auf die Schaltfläche [!UICONTROL Test] klicken, durchläuft unsere Regel-Engine jede Regel und bestimmt, ob das Programm einer der Regeln entspricht oder nicht. Im folgenden Beispiel sehen Sie, dass Programm 1002 mit dem Namen [!DNL Marketo Measure] Ebook 5 Programmmitglieder hat und aufgrund der angezeigten Regel berechtigt ist.

   Die Regeln werden mit einer Stichprobengröße von 5.000 Mitgliedern ausgeführt. Wenn Ihr Programm mehr als 5000 Mitglieder umfasst, ist es möglich, dass wir nicht die Kompatibilität aller Mitglieder überprüfen. Dieses Tool dient einfach dazu, die korrekte Erstellung von Regeln zu überprüfen.

   ![](assets/nine.png)

   Sie können auf die Anzahl der Mitglieder klicken, um eine Liste der Personen-IDs von Marketo anzuzeigen, die für das Programm infrage kommen.

   ![](assets/ten.png)

## Kanalzuordnung {#channel-mapping}

In der Liste der Marketo-Programmkanäle möchten Sie die Werte den benutzerdefinierten Marketingkanälen [!DNL Marketo Measure] zuordnen, die Sie in den Einstellungen erstellt haben. Alle von diesen Programmen generierten Touchpoints übernehmen die Kanal- und Subkanalnamen, die Sie hier auswählen.

1. Navigieren Sie zunächst zu **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Offline-Kanäle]**.

1. Oben haben Sie die Möglichkeit, Ihren CRM-Kampagnentypen zuzuordnen, und unten sehen Sie die Optionen für Ihre Marketo-Programmkanäle.

1. Wählen Sie zunächst den Kanal aus, der dem Wert zugeordnet werden soll, und wählen Sie dann optional den Unterkanal aus. Wenn Sie fertig sind, klicken Sie unten auf **[!UICONTROL Speichern]** .

   ![](assets/eleven.png)

## Programmkosten {#program-costs}

Durch den Datenimport von Marketo-Programmen werden die Kosten automatisch aus den Kosten des Zeitraums heruntergeladen und die in Marketo gemeldeten Kosten werden über den gesamten zugewiesenen Monat verteilt. Wenn beispielsweise für Januar 2021 1000 USD gemeldet werden, werden die 1000 USD auf 31 Tage aufgeteilt. Die Kosten finden Sie in [!DNL Marketo Measure Discover].

## Funktionsweise {#how-it-works}

**Feldzuordnungen**

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>biz_ad_campaigns</th> 
   <th>Marketo</th> 
  </tr> 
  <tr> 
   <td>ID</td> 
   <td>id</td> 
  </tr> 
  <tr> 
   <td>IS_DELETED</td> 
   <td>(Prüfung, ob das Programm weiterhin über die API existiert)</td> 
  </tr> 
  <tr> 
   <td><p>NAME</p></td> 
   <td>name</td> 
  </tr> 
 </tbody> 
</table>

| biz_campaign_members | Marketo |
|---|---|
| ID | &quot;MarketoProgramMembership&quot;_ProgramId_Lead-ID |
| MODIFIED_DATE | updatedAt |
| CREATED_DATE | membershipDate |
| LEAD_ID | ID (Listenmitgliedschaft) |
| LEAD_EMAIL | E-Mail (Listenmitgliedschaft) |
| STATUS | progressionStatus |
| HAS_RESPONDED | progressStatus |
| CAMPAIGN_NAME | programName |
| CAMPAIGN_ID | programId |
| CAMPAIGN_TYPE | Kanal |

## Cookie-Zuordnung {#cookie-mapping}

Aufgrund der Integration von [!DNL Marketo Measure] mit Marketo wird nun auch die [!DNL Marketo Measure] Cookie-ID zugeordnet und mit der [!DNL Marketo Munchkin Id] synchronisiert. Dies hilft, die Lücke zu schließen, um den anonymen Erstkontakt einer Web-Sitzung zuzuordnen, anstatt sowohl FT- als auch LC-Touches einer Marketo-Aktivität zuzuordnen. Stellen Sie sich dieses Szenario vor:

Markieren Sie Klicks auf eine [!DNL Facebook] -Anzeige und landet auf wayneenterprises.com , wo er mit [!DNL Marketo Measure] Id 123 und [!DNL Marketo Munchkin Id] 456 gekocht wird. Es wird kein Formular ausgefüllt.

Das Marketing-Team von Wayne Enterprises sendet eine E-Mail-Benachrichtigung an bestimmte Zielkontakte, von denen einer `mark@email.com` ist.

`mark@email.com` erhält die E-Mail und klickt durch und landet auf wayneenterprises.com. Dies wird `mark@email.com's` zweiter Besuch bei `wayneenterprise.com` mit denselben Cookie-IDs, es wurde jedoch kein Formular ausgefüllt, sodass [!DNL Marketo Measure] immer noch ein anonymer Besucher ist.

Das Marketingteam von Web-Unternehmen erstellt eine Marketo-Aktivitätsregel, um Touchpoints für den Aktivitätstyp &quot;Klick-E-Mail&quot;zu generieren.

Mit der heutigen Implementierung würde ein einzelner FT- und LC-Touchpoint für `mark@email.com` aus der Marketo-Aktivität aus dem Aktivitätstyp &quot;E-Mail klicken&quot;erstellt.

Mit dieser Verbesserung des Cookie-Mappings würde der FT zurück gehen und der [!DNL Facebook] -Anzeige gutgeschrieben und der LC würde der E-Mail gutgeschrieben.

>[!NOTE]
>
>Beim Verhalten der Cookie-Zuordnung finden Sie möglicherweise einige LC-Touchpoints, die von einem Webbesuch stammen. Es ist möglich, dass ein Lead in Marketo ohne zugehörige Aktivität angezeigt wurde, dass dann [!DNL Marketo Measure] diesen Lead heruntergeladen hat, mit den zugehörigen Cookies übereinstimmt und dann auf die neueste Websitzung verfolgt wurde, selbst wenn keine Formularaktivität vorhanden war, durch die der Lead erstellt wurde.

## FAQs {#faq}

**Wie setze ich das Touchpoint-Datum auf das Progressionsdatum oder das Datum, an dem die Statusänderung meinem Programmmitglied zugestoßen ist?**

Wenn Ihre Regel das Aktivitätsdatum oder das Datum erfassen möchte, an dem ein Programmmitglied einen bestimmten Status erreicht hat, sollten Sie die Aktivitätsintegration [!DNL Marketo Engage] verwenden und eine Regel für den Aktivitätstyp &quot;Änderungsstatus in Progression&quot;einrichten. Andernfalls wird durch die [!DNL Marketo Engage] Programmintegration nur das Mitgliedsdatum zur Verfügung gestellt, d. h. das erste Datum, an dem die Marketo-Person in das Programm aufgenommen wurde, selbst wenn mehrere Status vorliegen.

**Kann ich eine Auswahlliste mit Datumsoptionen für das Touchpoint-Datum abrufen?**

Um die automatische Vervollständigung Trigger, geben Sie zunächst eine geschweifte Klammer `{` in das Textfeld ein. Daraufhin werden die verfügbaren Felder angezeigt.

**Wenn ich Marketo-Programmregeln erstelle und auch CRM-Kampagnenregeln verwende, werden diese dann doppelt gezählt?**

Es hängt von Ihrer Regeldefinition ab, aber möglicherweise ja. Sie möchten Ihren Regelsatz so bewerten, dass Sie keine Regeln für ein Programm und eine Kampagne haben, da wir die Duplizierung nicht deduplizieren oder für ähnliche Mitgliedschaften nicht erkennen. Eine mögliche Lösung besteht darin, Ihre Kampagnenregeln in Programme zu kopieren, wenn Sie möchten, dass Marketo Ihre einzige Wahrheitsquelle ist, und dann die Kampagnenregeln zu entfernen. Eine weitere Möglichkeit besteht darin, in Ihren Regeln ein &quot;CreatedOn&quot;- oder &quot;CreatedDate&quot;-Kriterium hinzuzufügen, damit Regeln, die vor einem bestimmten Datum liegen, nach einem bestimmten Datum Kampagnenregeln verwenden und Regeln nach einem bestimmten Datum auf Programmregeln zurückgreifen. Es gibt viele Problemumgehungen, aber es wird eine gewisse Planung und Koordinierung erfordern.

**Sind benutzerdefinierte Felder für die Programmmitgliedschaft von Marketo verfügbar, die definiert werden können?**

Aufgrund technischer Einschränkungen können wir vorerst keine benutzerdefinierten Felder für die Programmmitgliedschaft unterstützen. Sobald diese Felder über zusätzliche Marketo-APIs verfügbar sind, werden sie uns angezeigt und für Sie sichtbar.

**Woher weiß ich, ob ich Programme oder Aktivitäten verwende?**

Die [!DNL Marketo Engage] Programmintegration ist eine einfache Möglichkeit, Touchpoints zu generieren, je nachdem, ob eine Person Programmmitglied eines Programms ist oder nicht. Wenn Sie eine Regel definieren möchten, die auf dem Zeitpunkt basiert, zu dem eine Person zu einem bestimmten Programmstatus wechselt, ist die [!DNL Marketo Engage] Aktivitätsintegration das gewünschte Setup, insbesondere der Aktivitätstyp &quot;Status in Progression ändern&quot;.
