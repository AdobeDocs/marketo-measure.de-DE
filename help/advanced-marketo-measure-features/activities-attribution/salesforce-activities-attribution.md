---
unique-page-id: 18874708
description: Salesforce Activities-Zuordnung - [!DNL Marketo Measure]
title: Salesforce Activities-Zuordnung
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Salesforce Activities-Zuordnung {#salesforce-activities-attribution}

Die [!DNL Marketo Measure] Bei der Integration von Salesforce-Aktivitäten werden bestimmte Aufgaben- und Ereignisdatensätze in Ihr Attributionsmodell eingefügt. Beginnen Sie, Dinge wie Verkaufs-E-Mails oder Verkaufs-Telefonanrufe zu verfolgen, die nicht gebührend gutgeschrieben wurden. Gehen Sie zum Konfigurieren der Aktivitätsregel zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Gehen Sie von dort in den **[!UICONTROL Einstellungen]** und klicken Sie auf **[!UICONTROL Tätigkeiten]** Registerkarte.

![](assets/1.png)

Zunächst führen wir ein neues Konzept ein, das als [!DNL Marketo Measure] Kampagne. Für jede von Ihnen definierte Regel werden die Datensätze in einem [!DNL Marketo Measure] Kampagne, die Sie benennen können. Fügen Sie nach Bedarf mehrere Kampagnen hinzu. Stellen Sie sich vor, Sie würden die Effektivität einer Outbound-Verkaufskampagne neben einer Paid Media-Kampagne messen!

Sie werden das [!DNL Marketo Measure] Kampagnenname , um uns mitzuteilen, welchem Kanal er zugeordnet werden soll. Wenn Sie noch an ausgehende Verkäufe denken, sollten möglicherweise alle ausgehenden Vertriebskampagnen in einem BDR-Kanal platziert werden.

Machen Sie sich mit dieser Hierarchie vertraut:

* Kanal
   * Unterkanal
      * Kampagne
      * Kampagne
   * Unterkanal
      * Kampagne

>[!TIP]
>
>Wenn Sie beispielsweise eine eindeutige Kampagne für jeden Vertriebsmitarbeiter einrichten möchten, verwenden Sie dynamische Ersatzparameter, um die Variable [!DNL Marketo Measure] Kampagnenname. Im selben Beispiel können Sie `"Outbound Sales - {AssignedTo}"` und ändert es in etwa `"Outbound Sales - Jill"` oder `"Outbound Sales - Jack."`

![](assets/2.png)

Einmal [!DNL Marketo Measure] Kampagnenname festgelegt ist, ist es Zeit, Ihre Aktivitätsregeln einzurichten.

Die Regeln dienen als Filter, um uns mitzuteilen, welche Datensätze für die Zuordnung infrage kommen. Angenommen, Sie erstellen einen Bericht in Ihrem CRM-System mit einer ähnlichen Logik, um diesen Bericht zu generieren. Sie haben die Flexibilität, eine Kombination aus und/oder Anweisungen und verschiedenen Operatoren wie `matches any`, `contains`, `starts with`, `ends with`, `is equal to`. Definieren `and` -Anweisungen innerhalb einer Boxed-Regel oder -Ebene `or` -Anweisungen außerhalb des -Felds.

![](assets/3.png)

>[!NOTE]
>
>Formelfelder können nicht in Ihren Regeln verwendet werden und werden nicht in der Auswahlliste angezeigt. Da Formeln im Hintergrund berechnet werden und einen Datensatz nicht ändern, [!DNL Marketo Measure] kann nicht erkennen, ob ein Datensatz zu einer Regel passt oder nicht.
>
>Stellen Sie sicher, dass die richtigen Werte für ID-Felder wie CrmEvent.CreatedById verwendet werden. [!DNL Salesforce IDs] sind 18 Zeichen lang ( 0054H000007WmrfQAC).

Wählen Sie schließlich eines Ihrer Datums- oder Datums-/Uhrzeitfelder aus, das als Touchpoint-Datum des Käufers verwendet werden soll. Es können sowohl Standard- als auch benutzerdefinierte Felder ausgewählt werden.

>[!TIP]
>
>Mit der Paketinstallation, [!DNL Marketo Measure] enthält ein benutzerdefiniertes Feld für das Touchpoint-Datum des Käufers im Aktivitätendatensatz. Wenn Sie ein dynamisches Datum verwenden möchten, z. B. das Datum, an dem sich ein Status ändert, können Sie einen CRM-Workflow verwenden, um das &quot;Touchpoint-Datum des Käufers&quot;festzulegen und in diesem Schritt hier das Touchpoint-Datum des Käufers auszuwählen.

![](assets/4.png)

Vergessen Sie nicht, verschiedene Regeln für Aufgaben oder Ereignisse festzulegen. Sie müssen wissen, welches Objekt Ihr Sales-Team zur Aufzeichnung seiner Aktivitäten verwendet.

![](assets/5.png)

Sie werden diese neuen Touchpoints wahrscheinlich in ihre entsprechenden [Marketingkanal](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20Channels){target="_blank"}. Definieren Sie dazu den Kanal mit dem soeben erstellten neuen Kampagnen-Mapping.

>[!TIP]
>
>Verwenden Sie beim Hinzufügen einer Kanaldefinition Platzhalterwerte, um Operatoren leichter anzugeben, z. B.:
>
>beginnt mit ( Outbound&#42; )
>
enthält ( &#42;Ausgehend&#42; )
>
endet mit ( &#42;Ausgehend )
>
Keine Wildcard bedeutet im Grunde &quot;ist gleich&quot;. Daher sollten Sie sie nach Bedarf verwenden.

| **Operator** | **Anwendungsfall** |
|---|---|
| ist gleich | Einzelwert - genaue Übereinstimmung |
| Enthält | Einzelwert - enthält Wert |
| Entspricht allen | Mehrere Werte - genaue Übereinstimmung |
| Entspricht allen (enthält) | Mehrere Werte - &#42;value&#42;, &#42;Wert, &#42;value&#42; |

![](assets/6.png)

Und nicht zuletzt haben Sie die Möglichkeit, die Kosten für Ihre neuen Kanäle anzugeben. Die [Hochladen von Marketing-Ausgaben](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} ermöglicht es Ihnen, Ihre Ausgaben auf Kanal-, Unterkanal- oder Kampagnenebene anzugeben. Mit dem neuen [!DNL Marketo Measure] Kampagnen können Sie diese zugehörigen Kosten pro Monat hinzufügen und dann den ROI für jede Kampagne sehen!

![](assets/7.png)

>[!MORELIKETHIS]
>
[FAQ zur Aktivitätszuordnung](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
