---
unique-page-id: 18874582
description: „[!DNL Marketo Measure]-Salesforce-Objekte - [!DNL Marketo Measure] - Produktdokumentation“
title: „[!DNL Marketo Measure]-Salesforce-Objekte“
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '949'
ht-degree: 100%

---

# [!DNL Marketo Measure]-Salesforce-Objekte {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in unserer Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Bei der Installation von [!DNL Marketo Measure] in [!DNL Salesforce] (SFDC) werden mehrere benutzerdefinierte [!DNL Marketo Measure]-Objekte hinzugefügt. In diesem Artikel werden mehrere dieser benutzerdefinierten [!DNL Marketo Measure]-Objekte erläutert. Einige Objekte, die von [!DNL Marketo Measure] zu [!DNL Salesforce] hinzugefügt werden:

* [Buyer Touchpoint](#touchpoint)
* [Buyer Attribution Touchpoint](#attribution)
* [[!DNL Marketo Measure]-Person](#person)
* [[!DNL Marketo Measure]-A/B-Tests](#ab)
* [[!DNL Marketo Measure]-Ereignisse](#events)

Touchpoints, die von den Dingen erfasst werden, die Sie verfolgen möchten, schreiben in die benutzerdefinierten Objekte, die bei der Installation des [!DNL Bizible Salesforce]-Pakets erstellt wurden.

[!DNL Marketo Measure]-Objekte beziehen sich auf bestimmte [!DNL Salesforce]-Standardobjekte. Auf diese Weise können Sie gemeinsame Berichte zu [!DNL Marketo Measure]- und [!DNL Salesforce]-Objekten erstellen. Folgende Tabelle zeigt, auf welches [!DNL Salesforce]-Objekt sich das [!DNL Marketo Measure]-Objekt bezieht.

![](assets/1-1.png)

## Buyer Touchpoint {#buyer-touchpoint}

Das [!UICONTROL Buyer Touchpoint] (BT)-Objekt erzählt die Marketing-Geschichte einer Person. Es enthält alle Daten zu den von Leads und Kontakten generierten Marketing-Touchpoints. Der BT zeigt Ihnen Informationen an, wie z. B., aus welchem Marketing-Kanal der Touchpoint stammt oder über welche Anzeigenkampagnen dieser spezielle Lead/Kontakt zu Ihrer Website gelangt ist.

Das BT-Objekt wird auf den Seiten „Leads“ und „Kontakte“ als **zugehörige Liste** angezeigt (siehe Abbildung unten).

![](assets/2-1.png)

Die BT-bezogene Liste zeigt alle Touchpoints an, die zu dem Lead oder Kontakt gehören. Die Liste enthält benutzerdefinierte [!DNL Marketo Measure]-Felder mit weiteren Details zu den einzelnen Touchpoints. Wenn Sie auf die Buyer Touchpoint-ID klicken, gelangen Sie zur Seite „Buyer Touchpoint-Details“, auf der Sie weitere Details zum Touchpoint erhalten, wie z. B. die erste Web-Seite, die der Lead/Kontakt während der Web-Sitzung besucht hat (**Landingpage**).

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Das [!UICONTROL Buyer Attribution Touchpoint]-Objekt liefert Informationen zu den Marketing-Interaktionen Ihrer Kontakte im Zusammenhang mit einer Opportunity. Es zeigt die *Attributions*-Daten zu den Marketing-Touchpoints an. Mit diesem Objekt können Sie erkennen, wie viel Umsatz-Credits jedem Marketing-Touchpoint zugeordnet sind. Der Typ des von Ihnen verwendeten Attributionsmodells bestimmt den Prozentsatz des den Touchpoints zugeordneten Umsatzes.

Buyer Attribution Touchpoints (BAT) werden erst erstellt, nachdem eine Gelegenheit für Kontakte erstellt wurde, die über Buyer Touchpoint(BT)-Daten verfügen. BATs werden nicht ohne eine Opportunity erstellt. Sobald die Opportunity erstellt wurde, verwendet das BAT-Objekt das [!DNL Salesforce]-Feld *Betrag* für die Opportunity, um zu ermitteln, wie viel Umsatz den Touchpoints zugeordnet werden soll.

Es muss ein **Workflow** erstellt werden, wenn Sie ein [benutzerdefiniertes Betragsfeld](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) nutzen, um den Umsatz für das Opportunity-Objekt anzuzeigen. [!DNL Marketo Measure] kann die in benutzerdefinierten Feldern des Typs „Betrag“ angezeigten Informationen nicht lesen und Umsatzzuordnungsdaten nicht für die Touchpoints eingeben. Dieser Workflow verwendet das **[!DNL Marketo Measure]-Feld „Anzahl Opportunitys“**, eines der benutzerdefinierten [!DNL Marketo Measure]-Felder, um den Umsatzwert aus dem benutzerdefinierten Feld „Betrag“ dem Feld „Anzahl Opportunitys“ zuzuordnen.

![](assets/3-1.png)

Das BAT-Objekt wird in den Objekten [!UICONTROL Opportunity], [!UICONTROL Kontakt] und [!UICONTROL Konto] als zugehörige Liste angezeigt. Diese Liste zeigt alle Touchpoints mit den Attributionsdaten an, die zu einer Opportunity gehören. Durch Klicken auf die Buyer Attribution Touchpoint-ID gelangen Sie zur Seite „Buyer Attribution Touchpoint-Details“. Hier werden spezifischere Attributionsdaten und Informationen darüber angezeigt, woher der Touchpoint stammt (ähnlich wie das vom Buyer Touchpoint-Objekt bereitgestellte Objekt).

## [!DNL Marketo Measure]-Person {#marketo-measure-person}

Das Objekt „[!DNL Marketo Measure]-Person“ verknüpft die Lead- und Kontaktobjekte miteinander. Standardmäßig bietet Salesforce nicht die Möglichkeit, Berichte mit dem Lead- und Kontaktobjekt im selben Bericht zu erstellen. Durch Verknüpfung mit dem Lead- und Kontaktobjekt ermöglicht Ihnen die [!DNL Marketo Measure]-Person, einen Bericht für beide Objekte im selben Bericht zu erstellen. Dies ist besonders hilfreich, wenn ein Lead in einen Kontakt konvertiert wurde. In einem [!DNL Marketo Measure]-Personeneintrag finden Sie eine Übersicht über den entsprechenden Lead- und/oder Kontakteintrag, eine zugehörige Liste der mit der Person verknüpften Touchpoints und die Personen-ID (immer die E-Mail-Adresse des Leads/Kontakts). Da die [!DNL Marketo Measure]-Person mit dem Lead- und Kontaktobjekt verbunden ist, gibt es niemals einen [!DNL Marketo Measure]-Personeneintrag, der mit einem Buyer Attribution Touchpoint verknüpft ist. Nachfolgend finden Sie ein Beispiel für einen [!DNL Marketo Measure]-Personeneintrag in Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure]-A/B-Test {#marketo-measure-a-b-test}

Bei der Durchführung von A/B-Tests mit [!DNL Optimizely] oder VWO (Visual Web Optimizer) können Sie diese Konten mit Ihrem [!DNL Marketo Measure]-Konto verknüpfen, um die A/B-Testdaten in Salesforce anzuzeigen. Mit dem [!DNL Marketo Measure]-A/B-Testobjekt können Sie A/B-Testdaten aus Optimizely/VW0 abrufen und mit Leads und Kontakten verknüpfen.

![](assets/5.png)

Das [!DNL Marketo Measure]-A/B-Test-Objekt wird als zugehörige Liste auf den Seiten [!UICONTROL Leads], [!UICONTROL Kontakte] und [!UICONTROL Opportunitys] angezeigt. Die Liste enthält alle Experimente und Varianten, die Sie über Optimizely bzw. VWO ausführen, und ermöglicht Ihnen zu sehen, wie sich Experimente/Varianten auf bestimmte Leads und Kontakte beziehen.

## [!DNL Marketo Measure]-Ereignisse {#marketo-measure-events}

Mit dem Objekt „[!DNL Marketo Measure]-Ereignisse“ können Sie bestimmte Ereignisse auf Ihrer Website nachverfolgen. Um bestimmte Ereignisse auf Ihrer Website zu verfolgen, muss zusätzlich zu [!DNL Marketo Measure] Javascript ein benutzerdefinierter Code zu Ihren Seiten hinzugefügt werden. Die erfassten Informationen werden in der zugehörigen Liste des [!DNL Marketo Measure]-Objekts auf den Seiten [!UICONTROL Leads], [!UICONTROL Kontakte] und [!UICONTROL Opportunitys] angezeigt. Das [!DNL Marketo Measure]-Ereignisobjekt ist *nicht* mit Attributionsdaten verknüpft. Mit diesem Objekt soll ermittelt werden, ob Personen bestimmte Aktionen auf Ihrer Website ausführen.

## [!DNL Marketo Measure]-Felder {#marketo-measure-fields}

Die vom [!DNL Marketo Measure]-Javascript erfassten Daten werden in die benutzerdefinierten [!DNL Marketo Measure]-Felder in unseren [!DNL Marketo Measure]-Objekten verschoben. Bestimmte Felder sind nur bei bestimmten Objekten vorhanden. Für ein Glossar aller [!DNL Marketo Measure]-Felder [klicken Sie hier](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). Um anzuzeigen, auf welches [!DNL Marketo Measure]-Objekt sich jedes [!DNL Marketo Measure]-Feld bezieht, [klicken Sie hier](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure]-Berichte und -Dashboards {#marketo-measure-reports-and-dashboards}

Die [!DNL Marketo Measure]-Berichte und -Dashboards, die zu Ihrem [!DNL Salesforce] hinzugefügt wurden, bieten vorkonfigurierte Berichterstellungs- und Datenvisualisierungsfunktionen. Dies sind grundlegende [!DNL Marketo Measure]-Berichte, mit denen Sie Touchpoint-Daten schnell organisieren, analysieren und verstehen können.
