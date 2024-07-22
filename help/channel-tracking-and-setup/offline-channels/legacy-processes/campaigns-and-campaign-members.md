---
unique-page-id: 18874578
description: Kampagnen und Kampagnenmitglieder – [!DNL Marketo Measure]
title: Kampagnen und Kampagnenmitglieder
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
feature: Channels
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 100%

---

# Kampagnen und Kampagnenmitglieder {#campaigns-and-campaign-members}

[!DNL Salesforce]-Kampagnen dienen dazu, Listen von Leads und Kontakten zu verfolgen, die mit einem Marketing-Programm oder einer Aktivität verbunden sind. Hierbei handelte es sich in der Regel um Webinare, Registrierungen oder z. B. Messebesuche. Marketing-Fachleute können auswählen, ob eine Kampagne einer Touchpoint-Journey gutgeschrieben werden soll oder nicht.

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

## Aktivieren von Touchpoints {#enabling-touchpoints}

Das Paket [!DNL Marketo Measure] [!DNL Salesforce] enthält ein Feld mit der Bezeichnung „Buyer Touchpoints aktivieren“ für das Kampagnenobjekt. Nachdem das Feld zum Seiten-Layout hinzugefügt wurde, sieht es in etwa so aus:

![](assets/1.png)

Die in der Auswahlliste verfügbaren Optionen sind:

![](assets/2.png)

* Alle Kampagnen-Mitglieder einschließen: Jeder Lead oder Kontakt, der zur Kampagne hinzugefügt wird, erhält einen Touchpoint, der dieser Kampagne zugeordnet ist.
* Nur „beantwortete“ Kampagnenmitglieder einschließen – Nur Leads oder Kontakte mit dem Status „Beantwortet“ der Kampagne erhalten einen Touchpoint, der mit dieser Kampagne verknüpft ist.
* Alle Kampagnenmitglieder ausschließen – Keiner der Leads oder Kontakte erhält einen mit dieser Kampagne verbundenen Touchpoint.

Beachten Sie, dass Kampagnenmitglieder eine E-Mail-Adresse haben müssen, die mit ihrem Eintrag verknüpft ist, damit [!DNL Marketo Measure] einen Touchpoint erstellen kann. Ohne eine E-Mail-Adresse wird [!DNL Marketo Measure] dem Kampagnenmitglied keinen Touchpoint zuweisen.

## Kampagnensynchronisierungsdaten {#campaign-sync-dates}

Mit der Installation des Pakets enthält [!DNL Marketo Measure] außerdem zwei Datumsfelder für das Kampagnenobjekt: Touchpoint-Startdatum und Touchpoint-Enddatum.

Diese Daten zeigen [!DNL Marketo Measure] wann wir beginnen oder aufhören sollten, Kampagnenmitglieder aus der Kampagne in die Touchpoint-Journey aufzunehmen. Sie können entweder ein Datum, beides oder gar kein Datum festlegen.

## Anwendungsbeispiel für das Touchpoint-Startdatum {#use-case-for-touchpoint-start-date}

Das Startdatum kann verwendet werden, wenn eine vorhandene Kampagne zum Tracking von Leads und Kontakten verwendet wird. Die Benutzenden möchten jedoch erst mit der Messung beginnen, wenn neue Systeme oder Prozesse vorhanden sind. Daher entscheiden sie sich, ein Startdatum festzulegen, sobald [!DNL Marketo Measure] mit dem Tracking dieser Kampagnenmitglieder beginnen soll.

## Anwendungsbeispiel für das Touchpoint-Enddatum {#use-case-for-touchpoint-end-date}

Wenn Sie vor der Verwendung von [!DNL Marketo Measure] eine Marketing-Automatisierungsplattform verwendet haben, die die digitalen Interaktionen von Leads (z. B. das Einreichen von Formularen) verfolgt hat, und diese Leads dann in eine [!DNL Saleforce]-Kampagne hochgeladen haben, können Sie das Feld „Touchpoint-Enddatum“ verwenden. Sie würden das Touchpoint-Enddatum als Ihr Startdatum mit [!DNL Marketo Measure] festlegen und Buyer Touchpoints aktivieren. Dann würde jede digitale Interaktion dieser Leads als Touchpoint erstellt werden. Der Grund, warum Sie das Touchpoint-Enddatum mit [!DNL Marketo Measure] auf Ihr Startdatum setzen, ist, dass wir diese digitalen Interaktionen in Zukunft über unser JavaScript verfolgen werden.

![](assets/3.png)

## Kampagnenmitglieder {#campaign-members}

Kampagnenmitglieder sind unter [!UICONTROL Kampagnen] verschachtelt und beziehen sich auf einen Lead oder Kontakt. Ein Lead oder ein Kontakt kann nur einmal zu einer Kampagne hinzugefügt werden, was je nach Anwendungsfall der Kampagne problematisch sein kann. Beim Synchronisieren einer Kampagne wird die Kampagnenmitgliedschaft als Marketing-Aktivität verwendet, die in die Touchpoint-Journey eingefügt und wie ein Ausfüllen des Formulars behandelt wird.

## Buyer-Touchpoint-Status {#buyer-touchpoint-status}

Wenn diese Funktion aktiviert ist, wird [!DNL Marketo Measure] dem Kampagnenmitglied einen Statuswert in 4 verschiedenen Feldern zuweisen, die im installierten Paket enthalten sind: Touchpoint-Status (Lead), Touchpoint-Status (Kontakt), Touchpoint-Status (Opportunity) und Touchpoint-Statusdatum. So können Kundinnen und Kunden überprüfen, ob ein Touchpoint als Buyer Touchpoint oder Buyer Attribution Touchpoint erstellt wurde, je nachdem, auf welches Objekt er sich bezieht. Das Touchpoint-Statusdatum ist einfach das letzte Datum, an dem der Status des Kampagnenmitglieds aktualisiert wurde.

![](assets/4.png)

## Buyer-Touchpoint-Datum {#buyer-touchpoint-date}

Mit der Installation des Pakets enthält [!DNL Marketo Measure] auch ein Feld auf dem Kampagnenmitglied mit der Bezeichnung „Buyer-Touchpoint-Datum“. Damit können die Benutzenden das Datum überschreiben, das [!DNL Marketo Measure] für das Touchpoint-Datum im Touchpoint-Eintrag verwenden würde.

Dies könnte erforderlich sein, wenn eine Liste Tage/Wochen/Monate nach dem tatsächlichen Eintreten eines Ereignisses hochgeladen wurde. Es gibt Möglichkeiten, alle Einträge gleichzeitig zu aktualisieren, wie nachfolgend beschrieben.

![](assets/5.png)

Um zu wissen, ob Sie das Buyer-Touchpoint-Datum verwenden müssen oder nicht, sehen Sie hier, wie die Daten von [!DNL Marketo Measure] abhängig vom [!UICONTROL Synchronisationstyp], der für die Kampagne ausgewählt wurde, bestimmt werden.

Wenn der [!UICONTROL Synchronisationstyp] auf „Alle Kampagnenmitglieder einbeziehen“ festgelegt ist, hat das Setzen des Touchpoint-Datums Priorität von oben nach unten:

* Buyer-Touchpoint-Datum
* Kampagnenmitglied-Erstellungsdatum

Wenn der [!UICONTROL Synchronisationstyp] auf „Nur ,Beantwortete’ Kampagnenmitglieder einbeziehen“ festgelegt ist, hat das Setzen des Touchpoint-Datums Priorität von oben nach unten:

* Buyer-Touchpoint-Datum
* Datum der ersten Antwort
   * Das Datum der ersten Antwort wird automatisch festgelegt, sobald der Status auf „Beantwortet“ geändert wird. Es handelt sich um ein [!DNL Salesforce]-Standardfeld, das nicht geändert werden kann.

* Kampagnenmitglied-Erstellungsdatum

## Massenaktualisierung des Touchpoint-Datums {#bulk-update-touchpoint-date}

Das Massenaktualisierung des Touchpoint-Datums ist im installierten [!DNL Marketo Measure] [!DNL Salesforce]-Paket enthalten, und die Schaltfläche muss dem Seiten-Layout hinzugefügt werden.

![](assets/6.png)

Wenn eine große Anzahl von Kampagnenmitgliedseinträgen aktualisiert werden muss, können Sie die Schaltfläche [!UICONTROL Massenaktualisierung des Touchpoint-Datums] zur Massenbearbeitung verwenden.

Wenn es spezielle Anwendungsfälle gibt, die diese Schnittstelle nicht abdeckt, können Sie auch den [Data Loader](https://dataloader.io/){target="_blank"} verwenden, um die Einträge zu exportieren, die Änderungen vorzunehmen und die Einträge dann wieder hochzuladen.

Suchen Sie zunächst nach den Einträgen und filtern Sie die Einträge, für die Sie ein Buyer-Touchpoint-Datum festlegen möchten.

>[!CAUTION]
>
>Es gibt eine Suche, die nicht funktioniert, die im folgenden Beispiel angezeigt wird. Die Benutzeroberfläche unterstützt nicht die Suche nach „null“ für Buyer Touchpoint-Daten (die folgende Suche würde nicht funktionieren):

![](assets/7.png)

Wenn Sie die Suche nicht benötigen und die Daten nur auf jeden Eintrag eines Kampagnenmitglieds anwenden möchten, verwenden Sie das Kontrollkästchen „[!UICONTROL Alle Einträge einbeziehen]“ (siehe Screenshot unten), das alle Einträge auf allen Seiten überprüft.

Wählen Sie in der Kalenderauswahl Datum und Uhrzeit aus. Wenn Sie das aktuelle Datum/Uhrzeit auswählen möchten, klicken Sie auf Datum/Uhrzeit, die neben der Kalenderauswahl angezeigt wird.

Sobald Sie das Datum und die Uhrzeit festgelegt haben, klicken Sie auf die Schaltfläche **[!UICONTROL Ausgewählte Einträge aktualisieren]**, um die Änderungen zu übernehmen.

![](assets/8.png)

## Kampagnenkosten {#campaign-costs}

Informationen zu Kampagnenkosten finden Sie [in diesem Artikel](/help/marketing-spend/spend-management/crm-campaign-costs.md){target="_blank"}.

## Entfernung eines Kampagnenmitglieds {#campaign-member-removal}

Die Art und Weise, wie [!DNL Marketo Measure] über alle gelöschten Einträge in Salesforce auf dem Laufenden bleibt, ob es sich nun um gelöschte Leads, Konten oder Opportunitys handelt, besteht darin, diese Einträge in der API zu sehen und zu verfolgen, ob ein Eintrag als „IsDeleted“ markiert ist. Leider hat Salesforce bei den Kampagnenmitgliedern eine andere Methode eingeführt, um diese Mitglieder aus einer Kampagne zu löschen. Sie werden nämlich nur als „entfernt“ und nicht als „gelöscht“ markiert, sodass das Problem darin bestand, dass die Touchpoints in Salesforce, die mit den gelöschten Kampagnenmitgliedern verbunden waren, immer noch existierten.

Um dieses Problem zu umgehen, hat [!DNL Marketo Measure] ein [!DNL Marketo Measure]-Verlaufsobjekt und einen Trigger erstellt, um zu verfolgen, wann Kampagnenmitglieder entfernt werden, und dann den entsprechenden Touchpoint zu löschen. **Sie benötigen das [!DNL Marketo Measure]-Marketing-Analyse-Paket V6.15 oder höher**, um diese Funktion zu nutzen.

>[!CAUTION]
>
>Beachten Sie, dass dieser Trigger keine Kampagnenmitglieder nachverfolgt, die in der Vergangenheit entfernt wurden. Daher funktioniert dies nur zukünftig. Wenn Sie eine große Anzahl von Touchpoints früherer Kampagnenmitglieder entfernen müssen, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: Kampagnenobjektfelder](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
>
>[[!DNL Marketo Measure] Tutorials: Zuordnen von Offline-Kanälen](https://experienceleague.adobe.com/de/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
