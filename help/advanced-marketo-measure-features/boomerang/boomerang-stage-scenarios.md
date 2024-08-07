---
unique-page-id: 18874692
description: Bomerang-Staging-Szenarien - [!DNL Marketo Measure]
title: Boomerang-Phasen-Szenarien
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: ea113b02b910fbc894311200aff83286636d4b32
workflow-type: tm+mt
source-wordcount: '1771'
ht-degree: 0%

---

# Boomerang-Phasen-Szenarien {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>Die Boomerang-Funktion ist nur für Tier-2- und -3-Kunden aktiviert. Wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer), um eine höhere Kontoebene anzufordern.

Im Folgenden finden Sie einige Beispiele für Bomerang-Staging-Szenarien, um zu verstehen, wie [!DNL Marketo Measure] in jeder Situation Touchpoints erstellt.

## Einzelne Lead-Szenarien {#single-lead-scenarios}

**Szenario 1: Standardmäßige Boomerang-Touchpoints für einen Lead**

Dies ist das einfachste Boomerang-Szenario. Die oberste Zeile (mit der Bezeichnung Lead 1) stellt die Journey der Leads dar und wie ihre Touchpoints auf dem Lead-Datensatz angezeigt werden. Das Ergebnis (als Opportunity bezeichnet) zeigt an, wie die Touchpoints der Leads in die Opportunity umgesetzt werden. Der Verlauf von Touchpoints wird in chronologischer Reihenfolge von links nach rechts erläutert.

In diesem Szenario hat sich ein Kunde dafür entschieden, seine **MQL**- und **SQL**-Bühnen mit Bomerangs verfolgen zu lassen. Jede Boomerang-Touchpoint-Position ist mit der Bühne und der Zahl beschriftet, in der sie auftritt (MQL-01, SQL-01, MQL-02). Der letzte Bomerang-Touchpoint für diese Phase hat die Touchpoint-Position &quot;(Letzter)&quot;.

Lead 1 wird dann in einen Kontakt mit einer Gelegenheit umgewandelt, der als OC-Kontakt gilt.

![](assets/1-1.png)

**Szenario 2: Bomerang-Touchpoints und benutzerdefinierte Phasen für einen Lead**

In diesem Szenario hat ein Kunde nur ausgewählt, die **SQL-Phase** mit Bomerang-Touchpoints zu verfolgen. MQL- und SAL-Bühnen werden weiterhin verfolgt, allerdings mit der Funktion [!DNL Marketo Measure] Benutzerdefinierte Bühne .

![](assets/2-1.png)

Beachten Sie, dass die MQL-Touchpoint-Position nicht mit einer Zahl beschriftet ist. Dies liegt daran, dass es nicht für die Verfolgung mit Boomerang-Touchpoints ausgewählt wurde. Beim Erstellen von Touchpoints für Bühnen, die im benutzerdefinierten Modell enthalten sind, aber nicht mit Boomerang verfolgt werden, nimmt [!DNL Marketo Measure] das letzte Vorkommen aus dieser Phase ein.

Für die SAL-Phase ignoriert [!DNL Marketo Measure] die ersten beiden Vorkommen dieser Phase. [!DNL Marketo Measure] erstellt nur einen SAL-Touchpoint für das Auftreten _last_ . Im obigen Beispiel geschieht dies direkt vor dem OC-Touchpoint.

Die SQL-Phase wird mit Boomerang-Touchpoints verfolgt und drei Touchpoints wurden entsprechend erstellt und beschriftet.

Lead 1 wird dann in einen Kontakt mit einer Gelegenheit umgewandelt, der als OC-Kontakt gilt.

**Szenario 3: Wenn Leads eine Bühne nicht erreichen/überspringen**

Dieses Szenario verwendet dieselben Kriterien wie Szenario 2. Ein Kunde hat sich entschieden, die SQL-Bühne nur mit Bomerang-Touchpoints zu verfolgen. MQL und SAL werden weiterhin verfolgt, jedoch mit der Funktion [!DNL Marketo Measure] Benutzerdefinierte Bühne .

![](assets/3.png)

In diesem Szenario wechselt der Lead nie zur SAL-Phase. Er wird in einen Kontakt umgewandelt, bevor er die SAL-Bühne erreicht, wodurch die SAL-Bühne im Wesentlichen &quot;übersprungen&quot;wird. In diesem Fall geht [!DNL Marketo Measure] davon aus, dass die SAL mit dem OC-Touchpoint auftritt und sowohl die SAL- als auch die OC-Position auf demselben Touchpoint angezeigt werden.

Lead 1 wird dann in einen Kontakt mit einer Gelegenheit umgewandelt, der als OC-Kontakt gilt.

## Szenarien mit mehreren Leads {#scenarios-with-multiple-leads}

In den folgenden Szenarien kann Boomerang Stages komplizierter werden, da wir uns ansehen, wie mehrere Leads die Opportunity-Journey beeinflussen können.

Die oberste Zeile (mit der Bezeichnung Lead 1 in Blau) stellt die Journey der einzelnen Leads dar und wie ihre Touchpoints auf dem Lead-Datensatz angezeigt werden. Dasselbe gilt für Lead 2 (in rosa) und Lead 3 (in orange). Das Ergebnis (als Opportunity bezeichnet) zeigt an, wie beide Touchpoints der Leads auf die Opportunity übersetzt werden. Der Verlauf von Touchpoints wird in chronologischer Reihenfolge von links nach rechts erläutert.

**Szenario 1: [!UICONTROL Drei Leads mit Chancen]**

In diesem Szenario hat sich ein Kunde entschieden, die **MQL** und **SAL-Bühnen** mit Bomerang-Touchpoints zu verfolgen. Die SQL-Phase wird von den standardmäßigen benutzerdefinierten Bühnen verfolgt.

![](assets/4.png)

Die FT- und LC-Touchpoints auf der Opportunity stammen aus Lead 1 (blau), da sie vor FT und LC von Lead 2 (rosa) auftraten. Der LC-Touchpoint für Lead 2 wird als &quot;Formular&quot;-Touchpoint auf der Opportunity angezeigt.

Die MQL-01 (Letzte) von Lead 2 wird die erste MQL auf der Opportunity. Die MQL-01 von Lead 1 wird nicht als Touchpoint für die Gelegenheit angezeigt, da die MQL von Lead 2 zuerst erfolgte. Die MQL-02 und MQL-03 von Lead 1 werden jedoch bei der Gelegenheit angezeigt.

Die SQL-Phase wird mit benutzerdefinierten Bühnen und nicht mit Bumerang-Bühnen verfolgt. Obwohl die SQL-Phase zwischen Lead 1 und Lead 2 drei Vorkommen aufweist, wird nur das letzte SQL-Vorkommen als Touchpoint auf der Opportunity einbezogen.

Der SAL-01 (Letzter) Touchpoint von Lead 1 wird als Touchpoint auf die Chancen übertragen. Lead 1 wird dann in einen Kontakt mit einer Gelegenheit umgewandelt, der als OC-Kontakt gilt. Der SAL-01 (Letzter)-Touchpoint von Lead 2 wird als Touchpoint erstellt, da diese Staging-Transition _nach_ dem OC-Kontakt auftrat.

Die Touchpoints FT, LC und MQL, SQL, SAL (orange) von Lead 3 erfolgten alle nach dem OC-Touchpoint auf der Opportunity. Diese Touchpoints sind in der Opportunity enthalten, werden jedoch als &quot;mittlere Touche&quot;betrachtet.

Wenn Lead 2 und 3 in Kontakte umgewandelt werden, erstellt [!DNL Marketo Measure] keinen weiteren OC-Touchpoint, da nur eine Opportunitätserstellung möglich ist.

**Szenario 2 - [!UICONTROL Drei Leads mit Chancen]**

In diesem Szenario hat sich ein Kunde entschieden, die **MQL**, **SQL** und **SAL**-Bühnen mit Bumerang-Touchpoints zu verfolgen.

Alle Touchpoints von Lead 1 sind auf der Opportunity von FT bis SAL-01 (Letzter) enthalten. Der LC-Touchpoint aus Lead 2 wird als Form-Touchpoint zwischen den Touchpoints LC und MQL-01 auf der Opportunity einbezogen.

![](assets/5.png)

Der MQL-01 (Letzter) von Lead 2 ist schließlich der MQL-04 (Letzter) Touchpoint auf der Opportunity. Da in diesem Szenario mehrere Leads-Journey innerhalb einer Chance betrachtet werden, kann sich die Positionierung und Nummerierung der Touchpoints der Leads ändern, wenn sie als Touchpoints auf der Opportunity übersetzt werden. Auf ähnliche Weise wird SQL-01 (Letzter) von Lead 2 zum SQL-04 (Letzter) auf der Opp. Die SAL-01 (Letzte) von Lead 2 wird ebenfalls zur SAL-02 (Letzte) der Chance.

Es sind nur 2 SAL-Touchpoints in der Opportunity enthalten. [!DNL Marketo Measure] versucht nicht, Touchpoints für Staging-Transitionen zu erzwingen/zu erstellen, wenn sie nicht aufgetreten sind.

Die Touchpoint-Journey von Lead 3 beginnt kurz vor dem OC-Kontakt, aber lange nachdem Lead 1 und Lead 2 ihre FT- und LC-Berührung hatten. In diesem Fall werden die FT- und LC-Daten von Lead 3 als Form-Touchpoint auf der Opportunity angezeigt. Lead 1 wird dann in einen Kontakt mit einer Gelegenheit umgewandelt, der als OC-Kontakt gilt.

MQL-, SQL- und SAL-Touches von Lead 3 treten alle gleichzeitig auf, nachdem das OC berühren. Da sie nach dem OC-Touchpoint auftraten, wird dieser Touchpoint als Form/Middle Touch auf der Opportunity und nicht als Bomerang-Staging-Transition angezeigt.

**Szenario 2a - Webbesuch Boomerang Touchpoints**

In diesem Szenario hat sich ein Kunde entschieden, die **MQL**, **SQL** und **SAL**-Bühnen mit Bumerang-Touchpoints zu verfolgen. Dieses Szenario ist mit dem oben genannten Szenario fast identisch, mit einigen Ausnahmen.

![](assets/6.png)

Alle Touchpoints von Lead 1 werden in die Gelegenheit aufgenommen, von FT bis SAL-01 (Letzter). Der LC-Touchpoint aus Lead 2 wird als Form-Touchpoint zwischen den Touchpoints LC und MQL-01 auf der Opportunity einbezogen.

Lead 2 MQL-01 (Letzter) (Webbesuch) wird nicht als Touchpoint auf der Opp erstellt. Dies liegt daran, dass dieser Touchpoint ein Webbesuch war, der nach dem letzten Vorkommen der SQL-Phase stattfindet, und nicht dazu beiträgt, die Chancen vorwärts zu bringen.

Die Phase von Lead 1 ändert sich in SAL und wird dann in Kontakt mit Chancen umgewandelt. In diesem Fall werden die Positionen SAL-01 (Letzter) und OC im selben Touchpoint kombiniert.

Der FT,LC-Touch von Lead 3 wird als Form-Touchpoint auf der Opp erstellt. Als Touchpoints werden nur Formularelemente erstellt, die nach dem Tippen des OC auf das Formular angewendet werden. Aus diesem Grund werden die Transitionen der Stufe SQL-01 (Letzter) und SAL-01 (Letzter) für Lead 2 nicht als Touchpoints erstellt, da es sich bei diesen Touchpoints um Webbesuche handelte.

Die MQL-, SQL- und SAL-Touchpoints von Lead 3 sind als Touchpoint enthalten, da es sich um eine Aktion zum Ausfüllen von Formularen handelte.

**Szenario 3 - Boomerang-Attributionsgewichtung**

In diesem Szenario hat sich ein Kunde entschieden, die **MQL**, **SQL** und **SAL**-Bühnen mit Bumerang-Touchpoints zu verfolgen.

![](assets/7.png)

Die FT- und LC-Touchpoints auf der Opportunity stammen aus Lead 1 (blau), da sie vor FT und LC von Lead 2 (rosa) auftraten. Der LC-Touchpoint für Lead 2 wird als &quot;Formular&quot;-Touchpoint auf der Opportunity angezeigt.

Die MQL-01 (Letzte) von Lead 2 wird zur ersten MQL auf der Opportunity. Die MQL-01 von Lead 1 wird nicht als Touchpoint für die Gelegenheit angezeigt, da die MQL von Lead 2 zuerst erfolgte.

Die SQL-01 (Letzte) von Lead 2 wird zu SQL-01 auf der Opportunity. Die SQL-01 auf Lead 1 wird nicht als Touchpoint für die Chance erscheinen, da SQL-01 auf Lead 2 zuerst stattgefunden hat.

Beachten Sie, dass Lead 1-Bumerangs zwischen MQL und SQL einige Male vor dem endgültigen Erreichen der SAL-Bühne. SQL-01, MQL-02, SQL-02, MQL-03, SQL-03 _wird nicht_ als Touchpoints auf die Chance aufgenommen, da diese Staging-Transitionen nicht dazu beitragen, die Chancen im Journey weiter zu verbessern.

Der SAL-01 (Letzter) Touchpoint von Lead 1 ist der nächste Touchpoint, der in die Opp-Funktion aufgenommen wird. Lead 1 wandelt sich dann in einen Kontakt mit einer Gelegenheit um und schafft so den OC-Kontaktpunkt.

Die Touchpoints von Lead 3s FT und LC und MQL, SQL und SAL erscheinen als Formulareingriff auf die Chancen.

Der SQL-01-Touchpoint von Lead 2 wird nicht als Touchpoint auf der Opp einbezogen, da er nach dem OC-Touchpoint aufgetreten ist. Außerdem erfolgte die SQL-Staging-Transition von Lead 2 _nach der finalen SAL-Staging-Transition_ und trägt nicht dazu bei, die Opportunity-Journey vorwärts zu treiben.

## Opportunity-Szenarios {#opportunity-scenarios}

**Szenario 1 - Kontakte mit Opportunity und Boomerang Tracking**

In diesem Szenario hat sich ein Kunde entschieden, die **Übergänge der Demo- und Verhandlungsphase** auf dem **Kontakt** zu verfolgen. Jede Bomerang-Bühne kann bis zu zwei Touchpoints erhalten. Der Unterschied zwischen Staging-Transitionen bei einem Kontakt- und Staging-Übergang auf einem Lead besteht darin, dass Transitionen der Kontaktstufe als Boomerang-Touchpoints auf dem Opportunity _nach_ des OC-Touchpoints angezeigt werden können. Dies gilt nicht für Staging-Transitionen, die auf dem Lead auftreten, da sie als Form-Touchpoint angezeigt werden.

![](assets/8.png)

In diesem Beispiel werden die Transitionen der Demo- und Verhandlungsphase von Contact 1 als Demo-01- und Verhandlungs-01-Touchpoints für die Chancen einbezogen. Die Demostage-Transition von Contact 2 erfolgt _nach_ Kontakt 1&#39;s und wird als Demo-02 (Letzter)-Touchpoint auf der Opportunity angezeigt.

Beachten Sie, dass es keinen zweiten Übergang zur Verhandlungsphase gibt. Die Chance springt sofort von Demo-02 (Letzter) in die Phase der &#39;Close Won&#39;. In diesem Fall enthält [!DNL Marketo Measure] die Transition der Verhandlungen mit dem Touchpoint &quot;Geschlossene Woche&quot;.
