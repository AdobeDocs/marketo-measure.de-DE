---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Salesforce-Objekte - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Salesforce-Objekte"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 1%

---

# [!DNL Marketo Measure] Salesforce-Objekte {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen angezeigt, die[!DNL Marketo Measure]&quot; in unserer Dokumentation, sehen aber immer noch &quot;Bizible&quot; in Ihrem CRM. Wir arbeiten daran, diese Aktualisierung durchzuführen, und das Rebranding wird sich in Kürze in Ihrem CRM widerspiegeln.

Wann [!DNL Marketo Measure] installiert in [!DNL Salesforce] (SFDC), mehrere benutzerdefinierte [!DNL Marketo Measure] Objekte werden hinzugefügt. In diesem Artikel werden mehrere dieser benutzerdefinierten [!DNL Marketo Measure] Objekte. Einige Objekte, die [!DNL Marketo Measure] fügt [!DNL Salesforce] sind:

* [Käufer Touchpoint](#touchpoint)
* [Touchpoint der Käuferzuordnung](#attribution)
* [[!DNL Marketo Measure] Person](#person)
* [[!DNL Marketo Measure] A/B-Tests](#ab)
* [[!DNL Marketo Measure] Veranstaltungen](#events)

Touchpoints, die von den Dingen erfasst werden, die Sie verfolgen möchten, schreiben in die benutzerdefinierten Objekte, die durch die Installation der [!DNL Bizible Salesforce] Paket.

[!DNL Marketo Measure] Objekte beziehen sich auf bestimmte Standardwerte [!DNL Salesforce] Objekte. Auf diese Weise können Sie Berichte zu [!DNL Marketo Measure] und [!DNL Salesforce] Objekte zusammen. Die nachstehende Tabelle zeigt, welche [!DNL Salesforce] Objekt [!DNL Marketo Measure] Objekt bezieht sich auf .

![](assets/1-1.png)

## Käufer Touchpoint {#buyer-touchpoint}

Die [!UICONTROL Touchpoint des Käufers] (BT) Object erzählt die Marketinggeschichte einer Person. Es enthält alle Daten zu den Marketing-Touchpoints, die von Leads und Kontakten generiert wurden. Der BT zeigt Ihnen Informationen an, wie z. B., aus welchem Marketingkanal der Touchpoint stammte oder welche Ad Campaign diesen speziellen Lead/Kontakt zu Ihrer Website brachte.

Das BT-Objekt wird auf den Seiten &quot;Leads&quot;und &quot;Kontakte&quot;als **Verwandte Liste** (siehe Abbildung unten).

![](assets/2-1.png)

Die Liste &quot;BT Related&quot;zeigt alle Touchpoints an, die zum Lead oder Kontakt gehören. In der Liste sind benutzerdefinierte [!DNL Marketo Measure] Felder, die weitere Details zu jedem Touchpoint bereitstellen. Wenn Sie auf die Touchpoint-ID des Käufers klicken, gelangen Sie zur Seite &quot;Touchpoint-Detail des Käufers&quot;, auf der Sie weitere Details zum Touchpoint erhalten, wie z. B. die erste Webseite, die der Lead/Kontakt während der Websitzung besucht hat (**Landingpage**).

## Touchpoint der Käuferzuordnung {#buyer-attribution-touchpoint}

Die [!UICONTROL Touchpoint der Käuferzuordnung] Object erzählt die Geschichte der Marketing-Interaktionen Ihrer Kontakte im Zusammenhang mit einer Gelegenheit. Sie zeigt die *Attribution* Daten zu den Marketing-Touchpoints. Mit diesem Objekt können Sie sehen, wie viel Umsatzgutschrift jedem Marketing-Touchpoint zugeordnet wird. Der Typ des von Ihnen verwendeten Attributionsmodells bestimmt den Prozentsatz des Umsatzes, der Touchpoints zugeordnet wird.

Touchpoints der Käuferzuordnung (BAT) werden erst erstellt, nachdem eine Chance erstellt wurde, die sich auf Kontakte bezieht, die über Touchpoint-Daten (Buyer Touchpoint, BT) verfügen. BVT werden nicht ohne Gelegenheit erstellt. Sobald die Option erstellt wurde, verwendet das BAT-Objekt die [!DNL Salesforce] *Betrag* -Feld auf der Gelegenheit, um zu verstehen, wie viel Umsatz den Touchpoints zugeordnet werden soll.

A **Workflow** muss erstellt werden, wenn Sie eine [Feld für benutzerspezifischen Betrag](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) , um den Umsatz für das Opportunity-Objekt anzuzeigen. [!DNL Marketo Measure] kann die in benutzerdefinierten Feldern des Typs &quot;Betrag&quot;angezeigten Informationen nicht lesen und ist daher nicht in der Lage, Umsatzzuordnungsdaten für die Touchpoints zu füllen. Dieser Workflow verwendet **[!DNL Marketo Measure]Opportunity Amount** Feld, eines der [!DNL Marketo Measure] benutzerdefinierte Felder, um den Umsatzwert aus dem benutzerdefinierten Feld &quot;Betrag&quot;dem Feld &quot;Opportunity Amount&quot;zuzuordnen.

![](assets/3-1.png)

Das BAT-Objekt wird auf der [!UICONTROL Chancen], [!UICONTROL Kontakt]und [!UICONTROL Konto] Objekt als zugehörige Liste. Diese Liste zeigt alle Touchpoints mit den Attributionsdaten an, die zu einer Gelegenheit gehören. Durch Klicken auf die Touchpoint-ID der Käuferzuordnung gelangen Sie zur Seite &quot;Touchpoint-Detail der Käuferzuordnung&quot;. Hier können Sie spezifischere Attributionsdaten und Informationen darüber sehen, woher der Touchpoint stammt (ähnlich dem vom Käufer-Touchpoint-Objekt bereitgestellten Objekt).

## [!DNL Marketo Measure] Person {#marketo-measure-person}

Die [!DNL Marketo Measure] Personen-Objekt verknüpft die Lead- und Kontaktobjekte miteinander. Standardmäßig bietet Salesforce nicht die Möglichkeit, Berichte mit dem Lead- und Kontaktobjekt im selben Bericht zu erstellen. Durch Relation zum Lead- und Kontaktobjekt wird die [!DNL Marketo Measure] Mit Person können Sie über beide Objekte im selben Bericht Berichte erstellen. Dies ist besonders hilfreich, wenn ein Lead in einen Kontakt umgewandelt wurde. Auf [!DNL Marketo Measure] Personendatensatz: Sie sehen einen Nachschlagevorgang zum entsprechenden Lead- und/oder Kontaktdatensatz, eine zugehörige Liste der mit der Person verbundenen Touchpoints und die Personen-ID (die immer die E-Mail-Adresse des Leads/Kontakts ist). Seit [!DNL Marketo Measure] Person bezieht sich auf das Lead- und Kontaktobjekt. Es wird nie eine [!DNL Marketo Measure] Personendatensatz, der mit einem Touchpoint der Käuferzuordnung verknüpft ist. Nachfolgend finden Sie ein Beispiel für eine [!DNL Marketo Measure] Personendatensatz in Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure] A/B-Test {#marketo-measure-a-b-test}

Wenn Sie A/B-Tests durchlaufen [!DNL Optimizely] oder VWO (Visual Web Optimizer) können Sie diese Konten mit Ihren [!DNL Marketo Measure] -Konto, um A/B-Testdaten in Salesforce anzuzeigen. Die [!DNL Marketo Measure] Mit dem A/B-Test-Objekt können Sie im Wesentlichen A/B-Testdaten aus &quot;Optimizely/VWO&quot;abrufen und die Daten mit Leads und Kontakten verknüpfen.

![](assets/5.png)

Die [!DNL Marketo Measure] A/B-Testobjekt wird als zugehörige Liste unter [!UICONTROL Leads], [!UICONTROL Kontakte] und [!UICONTROL Chancen] Seiten. Die Liste überdeckt alle Experimente und Varianten, die Sie durch &quot;Optimizely&quot;oder &quot;VWO&quot;ausführen, und ermöglicht Ihnen, die Experimente/Varianten zu sehen, da sie sich auf bestimmte Leads und Kontakte beziehen.

## [!DNL Marketo Measure] Veranstaltungen {#marketo-measure-events}

Die [!DNL Marketo Measure] Mit dem Ereignisobjekt können Sie bestimmte Ereignisse auf Ihrer Website verfolgen. Um bestimmte Ereignisse auf Ihrer Website zu verfolgen, muss Ihren Seiten zusätzlich zum [!DNL Marketo Measure] JavaScript. Die erfassten Informationen werden im [!DNL Marketo Measure] Objektbezogene Liste, die im [!UICONTROL Leads], [!UICONTROL Kontakte] und [!UICONTROL Chancen] Seiten. Die [!DNL Marketo Measure] Ereignisobjekt *nicht* Verknüpfung zu Attributionsdaten herzustellen. Mit diesem Objekt soll ermittelt werden, ob Personen bestimmte Aktionen auf Ihrer Website ausführen.

## [!DNL Marketo Measure] Felder {#marketo-measure-fields}

Daten, die von der [!DNL Marketo Measure] JavaScript wird in die benutzerdefinierte [!DNL Marketo Measure] Felder in unserem [!DNL Marketo Measure] Objekte. Bestimmte Felder sind nur bei bestimmten Objekten vorhanden. Für ein Glossar aller [!DNL Marketo Measure] Felder, bitte [Hier klicken](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). Für eine Visualisierung, bei der [!DNL Marketo Measure] Objekt für jedes [!DNL Marketo Measure] Feld bezieht sich auf [Hier klicken](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] Berichte und Dashboards {#marketo-measure-reports-and-dashboards}

Die [!DNL Marketo Measure] Berichte und Dashboards, die zu Ihren [!DNL Salesforce] bietet vordefinierte Berichterstellungs- und Datenvisualisierungsfunktionen. Diese sind grundlegend [!DNL Marketo Measure] Berichte, mit denen Sie Touchpoint-Daten schnell organisieren, analysieren und verstehen können.
