---
description: Attributionsleitfaden für Salesforce-Aktivitäten für Marketo Measure-Benutzende
title: Attribution von Salesforce-Aktivitäten
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# Attribution von Salesforce-Aktivitäten {#salesforce-activities-attribution}

Durch die Integration von [!DNL Marketo Measure] Salesforce-Aktivitäten werden spezifische Aufgaben- und Ereignisdatensätze in Ihr Attributionsmodell integriert. Beginnen Sie damit, Dinge wie Verkaufs-E-Mails oder Verkaufs-Telefonanrufe zu verfolgen, die nicht die gebührende Gutschrift erhielten. Die Aktivitätsregel kann unter [experience.adobe.com/marketo-measure konfiguriert ](https://experience.adobe.com/marketo-measure){target="_blank"}. Navigieren Sie von dort zur Registerkarte **[!UICONTROL Einstellungen]** und klicken Sie auf die Registerkarte **[!UICONTROL Aktivitäten]**.

![Die Integration von Marketo Measure Salesforce-Aktivitäten führt zu bestimmten Aufgaben und ](assets/activities-attribution-10.png)

Zu Beginn führen wir ein neues Konzept ein, das als [!DNL Marketo Measure]-Kampagne bezeichnet wird. Für jede Regel, die Sie definieren, gruppieren Sie die Datensätze in einer [!DNL Marketo Measure] Kampagne, die Sie benennen können. Fügen Sie bei Bedarf mehrere Kampagnen hinzu. Stellen Sie sich vor, Sie messen die Effektivität einer Outbound-Kampagne neben einer Paid-Media-Kampagne!

Sie verwenden diesen [!DNL Marketo Measure] Kampagnennamen, um uns mitzuteilen, welchem Kanal er zugeordnet werden soll. Wenn Sie immer noch über ausgehende Verkäufe nachdenken, sollten vielleicht alle ausgehenden Verkaufskampagnen in einem BDR-Kanal sitzen.

Machen Sie sich mit dieser Hierarchie vertraut:

* Kanal
   * Unterkanal
      * Kampagne
      * Kampagne
   * Unterkanal
      * Kampagne

>[!TIP]
>
>Wenn Sie beispielsweise für jeden Vertriebsmitarbeiter eine eindeutige Kampagne festlegen möchten, füllen Sie den Namen der [!DNL Marketo Measure]-Kampagne mit dynamischen Ersatzparametern aus. Im selben Beispiel können Sie `"Outbound Sales - {AssignedTo}"` eingeben und es ändert sich in etwas wie `"Outbound Sales - Jill"` oder `"Outbound Sales - Jack."`

![Wenn Sie für jeden Vertriebsmitarbeiter eine eindeutige Kampagne festlegen möchten](assets/activities-attribution-11.png)

Nachdem Sie Ihren [!DNL Marketo Measure]-Kampagnennamen festgelegt haben, können Sie Ihre Aktivitätsregeln einrichten.

Die Regeln dienen als Filter, um anzugeben, welche Datensätze für die Attribution infrage kommen. Stellen Sie sich vor, Sie erstellen einen Bericht in Ihrem CRM mit einer ähnlichen Logik, um diesen Bericht zu generieren. Sie haben die Flexibilität, eine Kombination aus - und/oder -Anweisungen und verschiedenen Operatoren wie `matches any`, `contains`, `starts with`, `ends with` und `is equal to` zu verwenden. Definieren Sie `and` Anweisungen in einer Boxed-Regel oder Layer-`or` außerhalb des Boxes.

![Die Regeln dienen als Filter, um anzugeben, welche Datensätze verwendet werden](assets/activities-attribution-12.png)

>[!NOTE]
>
>Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, können [!DNL Marketo Measure] nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.
>
>Stellen Sie sicher, dass Sie die richtigen Werte für ID-Felder wie „CrmEvent.CreatedById“ verwenden. [!DNL Salesforce IDs] sind 18 Zeichen lang ( 0054H000007WmrfQAC).

Wählen Sie abschließend eines Ihrer Datums- oder Datums-/Uhrzeitfelder als Buyer Touchpoint-Datum aus. Es können entweder standardmäßige und benutzerdefinierte Felder ausgewählt werden.

>[!TIP]
>
>Bei der Paketinstallation fügt [!DNL Marketo Measure] dem Aktivitätsdatensatz ein benutzerdefiniertes Buyer Touchpoint-Datumsfeld hinzu. Wenn Sie ein dynamisches Datum verwenden möchten, z. B. das Datum, an dem sich ein Status ändert, können Sie mithilfe eines CRM-Workflows das &quot;Buyer Touchpoint-Datum“ festlegen und dann in diesem Schritt das Buyer Touchpoint-Datum auswählen.

![Bei der Paketinstallation enthält Marketo Measure eine benutzerdefinierte Buyer Touchpoint](assets/activities-attribution-13.png)

Vergessen Sie nicht, andere Regeln für Aufgaben oder Ereignisse festzulegen. Sie müssen wissen, welches Objekt Ihr Vertriebsteam verwendet, um seine Aktivitäten aufzuzeichnen.

![Vergessen Sie nicht, andere Regeln für Aufgaben oder Ereignisse festzulegen. Sie](assets/activities-attribution-5.png)

Sie sollten diese neuen Touchpoints wahrscheinlich in ihrem entsprechenden [Marketing-Kanal“ ](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=channels.Online%20channels){target="_blank"}. Definieren Sie dazu den Kanal mit seiner neuen Kampagnen-Zuordnung, die gerade erstellt wurde.

>[!TIP]
>
>Nutzen Sie beim Hinzufügen einer Kanaldefinition Platzhalterwerte, um die Darstellung von Operatoren zu vereinfachen. Beispiel:
>
>beginnt mit ( Ausgehend&#42; )
>
>enthält ( &#42;Outbound&#42; )
>
>endet mit ( &#42;Outbound )
>
>Kein Platzhalter bedeutet im Grunde „ist gleich“. Daher sollten Sie darauf achten, dass Sie ihn bei Bedarf verwenden.

| **Operator** | **Anwendungsfall** |
|---|---|
| ist gleich | Einzelwert - exakte Übereinstimmung |
| Enthält | Einzelwert - enthält Wert |
| Entspricht allen | Mehrere Werte - Exakte Übereinstimmung |
| stimmt überein mit „any“ (enthält) | Mehrere Werte - &#42;value&#42;, &#42;value, &#42;value&#42; |

![| stimmt überein mit „any“ (enthält) | Mehrere Werte - &amp;42;Wert&amp;42;, &amp;42;Wert, &amp;42;Wert&amp;42; |](assets/activities-attribution-8.png)

Und nicht zuletzt haben Sie die Möglichkeit, Kosten für Ihre neuen Kanäle einzutragen. Mit [ Upload von Marketing](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"}Ausgaben können Sie Ihre Ausgaben auf Kanal-, Unterkanal- oder Kampagnenebene eingeben. Mit Ihren neuen [!DNL Marketo Measure]-Kampagnen können Sie diese zugehörigen Kosten nach Monat hinzufügen und dann den ROI für jede Kampagne anzeigen!

![Und nicht zuletzt haben Sie die Möglichkeit, Kosten einzutragen](assets/activities-attribution-9.png)

>[!MORELIKETHIS]
>
>[Häufig gestellte Fragen zur Aktivitätszuordnung](/help/channel-tracking-and-setup/activities-attribution-faq.md)
