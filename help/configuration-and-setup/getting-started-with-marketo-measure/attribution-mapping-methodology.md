---
description: Attributionszuordnungsmethodik - [!DNL Marketo Measure]
title: Attributionszuordnungsmethode
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---


# Attributionszuordnungsmethode {#attribution-mapping-methodology}

Die Attributionszuordnungsmethodik ist der Prozess der Suche nach bestimmten Objekten in Ihrem CRM (Kontakte, Opportunities, Konten), um Attributions-Touchpoints für die zugehörige Opportunity zu erstellen. Mit anderen Worten: Es ist der [!DNL Marketo Measure] Weg zu verstehen, welche Touchpoints in das Attributionsmodell basierend auf den Prozessen Ihres aktuellen CRM aufgenommen werden sollen.

## Konto-ID-Zuordnung {#account-id-mapping}

Standardmäßig stellt [!DNL Marketo Measure] die Zuordnung der Konto-ID bereit. Das bedeutet, dass [!DNL Marketo Measure] das Konto und seine Marketing-Informationen für Kontakte betrachtet, um Attribution Touchpoints zu erstellen, die mit der Opportunity verbunden sind. Nachfolgend finden Sie eine einfache Darstellung dieses Prozesses.

![&#x200B; 1](assets/1-1.png)

Beachten Sie, dass **nicht alle** Touchpoints Ihrer Kontakte als Attribution Touchpoints in die Opportunity übertragen werden. Die Zeitleiste der Opportunity (Datum des ersten Kontakts - Abschlussdatum) bestimmt, ob ein Touchpoint als Influencer auf die Opportunity zählt. Wenn also ein Touchpoint bei Kontakt A auftritt, nachdem die Opportunity geschlossen wurde, ist sie gewonnen/verloren und [!DNL Marketo Measure] diesen Touchpoint nicht an die Opportunity weiterleiten. Diese Zeitleistenprozedur wird bei allen anderen Attributionsobjektzuordnungen befolgt.

Positiv:: Diese Attributionsmethode ist für die meisten Unternehmen sehr effektiv. Das Marketing-Team muss sich nicht darauf verlassen, dass das Vertriebs-Team alle Kontakte mit einer bestimmten Opportunity verknüpft (was oft ein Problem ist). Darüber hinaus können, selbst wenn ein Vertriebs-Team Kontaktrollen zuordnet, viele Interaktionen anderer Kontakte mit Marketing-Materialien fehlen. Schließlich unterstützt diese Methode die ABM-Strategie, die darauf abzielt, die Gesamtheit eines Kontos zu beeinflussen, anstatt bestimmte Einflussnehmer.

Negativ:: Wenn es starke Marketing- und Sales-SLAs gibt, die definieren, wer wofür angerechnet werden soll, dann könnte diese Methode problematisch sein. Wenn Personen keine Account-Hierarchien verwenden, um bestimmte Geschäftseinheiten innerhalb eines größeren Accounts zu definieren (z. B.: IBM), können darüber hinaus Marketing-Interaktionen, die für eine Business Unit spezifisch sind, über andere Business Unit-Opportunitys verteilt werden.

## Zuordnung der Kontaktrolle der Opportunity {#opportunity-contact-role-mapping}

>[!NOTE]
>
>Zuordnungsmethoden für Kontaktrollen sind nur für diejenigen verfügbar, die Salesforce als CRM verwenden. Es ist nicht für Microsoft Dynamics-Benutzer verfügbar, da in diesem CRM kein Kontaktrollen-Objekt vorhanden ist.

Während die meisten Kunden die Konto-ID-Zuordnung verwenden, können [!DNL Marketo Measure] in einer Opportunity die Kontaktrollen (mit der Opportunity verknüpfte Kontakte) nachschlagen, um den Attributionsprozess aufzuschlüsseln. Das bedeutet, dass [!DNL Marketo Measure] nur Marketing-Interaktionen pushen, die mit den Kontaktrollen der Opportunity als Attribution-Touchpoints für Käufer verknüpft sind. Nachfolgend finden Sie eine Darstellung dieses Prozesses.

![&#x200B; 1](assets/2-1.png)

Positiv:: Wenn Ihr Team über einen klar definierten Prozess für Kontaktrollen verfügt, kann diese Art der Attributionszuordnung ideal für Sie sein. Es hilft, Vertrieb und Marketing etwas mehr aufeinander abzustimmen, da jeder vollständig verstehen würde, wie die Attribution aufgeschlüsselt ist. Dieser Prozess ist auch hilfreich, wenn Unternehmen mehrere Geschäftsbereiche innerhalb eines großen Unternehmens ansprechen und gleichzeitig verschiedene Produkte verkaufen.

Negativ:: Wenn jedoch kein Prozess für Kontaktrollen eingerichtet ist, verliert das Marketing eine Menge Marketing-Daten und das Team erhält am Ende viel weniger Anerkennung für seine Marketing-Bemühungen, die Chancen beeinflussen.

## Opportunity Primäre Kontaktrollen-Zuordnung {#opportunity-primary-contact-role-mapping}

Neben der bloßen Betrachtung der Kontaktrollen auf die Opportunity können [!DNL Marketo Measure] sich noch mehr darauf konzentrieren, nur die Primären Kontakte auf eine Opportunity zu betrachten. Mit diesem Setup im Hinterkopf greift [!DNL Marketo Measure] nur den Marketing-Touchpoint, der den primären Kontakten bei einer Opportunity zugeordnet ist, und überträgt diese Informationen in die Attributionsgeschichte dieser spezifischen Opportunity. Siehe die Abbildung unten.

![Attributionszuordnungsdiagramm nur mit primären Kontaktrollen](assets/3.png)

Positiv:: Wenn Ihr Team nur daran interessiert ist, den Marketing-Einfluss auf Kontakte zu verstehen, die bei der Opportunity als „primär“ festgelegt wurden, passt diese Art der Zuordnung am besten zum Team.

Negativ:: Dies ist sicherlich der am wenigsten verwendete Zuordnungsprozess und kann den Marketing-Einfluss stark untergraben, der die Nadel über andere Kontakte auf eine Opportunity bewegt.
