---
description: Anleitung für Boomerang-Szenarien für Marketo Measure-Anwender
title: Boomerang-Phasen-Szenarien
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1872'
ht-degree: 0%

---

# Boomerang-Phasen-Szenarien {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>Die Boomerang-Funktion ist nur für Kunden der Ebenen 2 und 3 aktiviert. Um eine höhere Kontoebene anzufordern, wenden Sie sich an das Adobe Account Team (Ihren Account Manager).

Im Folgenden finden Sie einige Beispiele für Bumerang-Stadium-Szenarien, um zu verstehen, wie [!DNL Marketo Measure] in jeder Situation Touchpoints erstellt.

## Einzelne Lead-Szenarien {#single-lead-scenarios}

**Szenario 1: Standard-Boomerang-Touchpoints für einen Lead**

Dies ist das einfachste Boomerang-Szenario. Die obere Zeile (mit Lead 1 beschriftet) stellt die Journey der einzelnen Leads dar und wie ihre Touchpoints auf dem Lead-Datensatz erscheinen. Die Untergrenze (mit Opportunity bezeichnet) zeigt an, wie sich die Touchpoints der Leads auf die Opportunity auswirken. Der Verlauf der Touchpoints wird in chronologischer Hinsicht von links nach rechts erklärt.

In diesem Szenario hat ein Kunde ausgewählt, dass seine **MQL**- und **SQL**-Stadien mit Boomerangs verfolgt werden. Jede Touchpoint-Position in Boomerang ist mit dem Stadium und der Nummer gekennzeichnet, in der sie auftritt (MQL-01, SQL-01, MQL-02). Der letzte Boomerang-Touchpoint für diese Phase hat „(Last)“ in der Touchpoint-Position.

Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt, der als OC Touch gilt.

![Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt.](assets/boomerang-stages-18.png)

**Szenario 2: Boomerang-Touchpoints UND benutzerdefinierte Stadien für einen Lead**

In diesem Szenario hat sich ein Kunde nur dafür entschieden, die **SQL-Phase** mit Boomerang-Touchpoints zu verfolgen. MQL- und SQL-Stadien werden weiterhin verfolgt, jedoch mit der Funktion „Benutzerdefiniertes Stadium [!DNL Marketo Measure]&quot;.

![In diesem Szenario hat sich ein Kunde nur dafür entschieden, die SQL zu verfolgen](assets/boomerang-stages-19.png)

Beachten Sie, dass die MQL-Touchpoint-Position nicht mit einer Zahl gekennzeichnet ist. Dies liegt daran, dass es nicht für das Tracking mit Boomerang-Touchpoints ausgewählt wurde. Beim Erstellen von Touchpoints für Stadien, die im benutzerdefinierten Modell enthalten sind, aber nicht mit Boomerang verfolgt werden, nimmt [!DNL Marketo Measure] das letzte Vorkommen aus diesem Stadium.

Für die SAL-Phase ignoriert [!DNL Marketo Measure] die ersten beiden Vorkommen dieser Phase. [!DNL Marketo Measure] erstellt nur einen SAL-Touchpoint für das _letzte_ Vorkommen. Im obigen Beispiel geschieht dies direkt vor dem OC-Touchpoint.

Die SQL-Phase wird mit Boomerang-Touchpoints verfolgt, und drei Touchpoints wurden entsprechend erstellt und gekennzeichnet.

Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt, der als OC Touch gilt.

**Szenario 3: Wenn Leads eine Phase nicht erreichen/überspringen**

Dieses Szenario verwendet dieselben Kriterien wie Szenario 2. Ein Kunde hat sich nur dafür entschieden, das SQL-Stadium mit Boomerang-Touchpoints zu verfolgen. MQL und SQL werden weiterhin verfolgt, jedoch mit der [!DNL Marketo Measure] Custom Staging-Funktion.

![Dieses Szenario verwendet dieselben Kriterien wie Szenario 2. Ein Kunde hat](assets/boomerang-stages-20.png)

In diesem Szenario wechselt der Lead nie tatsächlich in die SQL-Phase. Es wandelt sich in einen Kontakt um, bevor es die SAL-Stufe erreicht, und „überspringt“ im Wesentlichen die SAL-Stufe. In diesem Fall geht [!DNL Marketo Measure] davon aus, dass die SAL mit dem OC-Touchpoint erfolgt und sowohl die SAL- als auch die OC-Position auf demselben Touchpoint erscheinen.

Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt, der als OC Touch gilt.

## Szenarien mit mehreren Leads {#scenarios-with-multiple-leads}

In den folgenden Szenarien können Boomerang-Stadien komplizierter werden, da wir untersuchen, wie mehrere Leads die Opportunity-Journey beeinflussen können.

Die obere Zeile (mit der Beschriftung Lead 1, in Blau) stellt die Journey der einzelnen Leads dar und wie ihre Touchpoints auf dem Lead-Datensatz erscheinen. Dasselbe gilt für das Blei 2 (in Rosa) und das Blei 3 (in Orange). Die Untergrenze (mit Opportunity bezeichnet) zeigt an, wie sich beide Touchpoints dieser Leads auf die Opportunity auswirken. Der Verlauf der Touchpoints wird in chronologischer Hinsicht von links nach rechts erklärt.

**Szenario 1: [!UICONTROL Drei Leads mit Opportunity]**

In diesem Szenario hat sich ein Kunde dafür entschieden, die **MQL**- und **SAL-Stadien** mit Boomerang-Touchpoints zu verfolgen. Die SQL-Phase wird von den standardmäßigen benutzerdefinierten Phasen verfolgt.

![In diesem Szenario hat sich ein Kunde dafür entschieden, die MQL zu verfolgen und](assets/boomerang-stages-21.png)

Die FT- und LC-Touchpoints für die Opportunity stammen aus Lead 1 (blau), da sie vor dem FT und LC von Lead 2 (rosa) stattfanden. Der LC-Touchpoint für Lead 2 wird als „Formular“-Touchpoint auf der Opportunity angezeigt.

Die MQL-01 (Letzte) von Lead 2 wird die erste MQL für die Opportunity. Die MQL-01 von Lead 1 wird nicht als Touchpoint auf der Opportunity angezeigt, da die MQL von Lead 2 zuerst stattgefunden hat. Allerdings werden MQL-02 und MQL-03 von Lead 1 auf der Opportunity angezeigt.

Die SQL-Phase wird mit benutzerdefinierten Stadien verfolgt, nicht mit Boomerang-Stadien. Obwohl es drei Vorkommnisse der SQL-Phase zwischen Lead 1 und Lead 2 gibt, wird nur das letzte SQL-Vorkommnis als Touchpoint in die Opportunity aufgenommen.

Der SAL-01-Touchpoint (Letzter) von Lead 1 wird als Touchpoint auf die Opportunity übertragen. Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt, der als OC Touch gilt. Der SAL-01-Touchpoint (Letzter) von Lead 2 wird als Touchpoint erstellt, da dieser Stadienübergang (_) nach_ OC-Touch erfolgt ist.

Die FT-, LC- und MQL-, SQL-, SAL-Touchpoints (orange) von Lead 3 erfolgten alle nach dem OC-Touchpoint auf der Opportunity. Diese Touchpoints sind in der Opportunity enthalten, gelten aber als „Middle Touches“.

Wenn Lead 2 und 3 in Kontakte umgewandelt werden, erstellen [!DNL Marketo Measure] keinen weiteren OC-Touchpoint, da es nur eine Phase der Opportunity-Erstellung geben kann.

**Szenario 2 - [!UICONTROL Drei Leads mit Opportunity]**

In diesem Szenario hat sich ein Kunde dafür entschieden, die **MQL**, **SQL** und **SAL** mit Boomerang-Touchpoints zu verfolgen.

Alle Touchpoints von Lead 1 sind in der Opportunity enthalten, von FT bis SAL-01 (Letzte). Der LC-Touchpoint von Lead 2 wird als Formular-Touchpoint zwischen dem LC und den MQL-01-Touchpoints auf der Opportunity eingefügt.

![Alle Touchpoints von Lead 1 sind in der Opportunity enthalten, von](assets/boomerang-stages-22.png)

Das MQL-01 (Letzte) von Lead 2 wird schließlich der MQL-04 (Letzte) Touchpoint auf der Opportunity. Da in diesem Szenario die Journey mehrerer Leads innerhalb einer Opportunity betrachtet werden, können sich Positionierung und Nummerierung der Touchpoints der Leads ändern, wenn sie als Touchpoints für die Opportunity übersetzt werden. Ähnlich wird SQL-01 (Letzte) von Lead 2 zum SQL-04 (Letzte) auf der Opportunity. Lead 2&#39;s SAL-01 (Letzte) wird auch SAL-02 (Letzte) der Opportunity.

Es sind nur zwei SSL-Touchpoints in der Opportunity enthalten. [!DNL Marketo Measure] wird nicht versuchen, Touchpoints für Staging-Übergänge zu erzwingen/zu erstellen, wenn diese nicht bereits stattgefunden haben.

Das Touchpoint-Journey von Lead 3 beginnt kurz vor dem Touch des OC, aber lange nachdem Lead 1 und Lead 2 ihren FT- und LC-Touch hatten. In diesem Fall erscheinen die FT und LC von Lead 3 als Formular-Touchpoint auf der Opportunity. Lead 1 wird dann in einen Kontakt mit einer Opportunity umgewandelt, der als OC Touch gilt.

Die MQL-, SQL- und SAL-Touches von Lead 3 erfolgen alle gleichzeitig nach der OC-Touch-Touch-Touch-Technologie. Da sie nach dem OC-Touchpoint erfolgt sind, erscheint dieser Touchpoint als Form/Middle Touch auf der Opportunity und nicht als Boomerang-Stadienübergang.

**Szenario 2a - Boomerang-Touchpoints für Web-Besuche**

In diesem Szenario hat sich ein Kunde dafür entschieden, die **MQL**, **SQL** und **SAL** mit Boomerang-Touchpoints zu verfolgen. Dieses Szenario ist mit wenigen Ausnahmen fast identisch mit dem oben beschriebenen.

![In diesem Szenario hat sich ein Kunde dafür entschieden, MQL, SQL ](assets/boomerang-stages-23.png)

Alle Touchpoints von Lead 1 werden bei der Opportunity berücksichtigt, von FT bis SAL-01 (Letzte). Der LC-Touchpoint von Lead 2 wird als Formular-Touchpoint zwischen dem LC und den MQL-01-Touchpoints auf der Opportunity eingefügt.

Lead 2&#39;s MQL-01 (Letzter) (Web Visit) wird nicht als Touchpoint auf der Opportunity erstellt. Dies liegt daran, dass dieser Touchpoint ein Web-Besuch war, der nach dem letzten Auftreten der SQL-Phase erfolgt und nicht dazu beiträgt, die Opportunity voranzutreiben.

Das Stadium von Lead 1 ändert sich in SAL und wird dann in einen Kontakt mit einer Opportunity umgewandelt. In diesem Fall werden die Positionen SAL-01 (Letzter) und OC im selben Touchpoint kombiniert.

Der FT- und LC-Touch von Lead 3 wird als Formular-Touchpoint auf der Opportunity erstellt. Nach dem OC Touch werden nur noch Aktionen zum Ausfüllen von Formularen als Touchpoints erstellt. Aus diesem Grund werden die Transitionen der SQL-01-Phase (Letzte) und der SQL-01-Phase (Letzte) für Lead 2 nicht als Touchpoints erstellt, da es sich bei diesen Touchpoints um Web-Besuche handelte.

Die MQL-, SQL-, SQL-Touches von Lead 3 sind als Touchpoint enthalten, da es sich um eine Aktion zum Ausfüllen eines Formulars handelte.

**Szenario 3 - Boomerang-Attributionsgewichtung**

In diesem Szenario hat sich ein Kunde dafür entschieden, die **MQL**, **SQL** und **SAL** mit Boomerang-Touchpoints zu verfolgen.

![In diesem Szenario hat sich ein Kunde dafür entschieden, MQL, SQL ](assets/boomerang-stages-25.png)

Die FT- und LC-Touchpoints für die Opportunity stammen aus Lead 1 (blau), da sie vor dem FT und LC von Lead 2 (rosa) stattfanden. Der LC-Touchpoint für Lead 2 erscheint als „Formular“-Touchpoint auf der Opportunity.

Die MQL-01 (Letzte) von Lead 2 wird zur ersten MQL auf der Opportunity. Die MQL-01 von Lead 1 wird nicht als Touchpoint auf der Opportunity angezeigt, da die MQL von Lead 2 zuerst stattgefunden hat.

Die SQL-01 (Letzte) von Lead 2 wird bei der Opportunity zu SQL-01. SQL-01 auf Lead 1 wird nicht als Touchpoint auf der Opportunity angezeigt, da SQL-01 auf Lead 2 zuerst stattgefunden hat.

Beachten Sie, dass Lead 1 einige Male zwischen MQL und SQL liegt, bevor das SQL-Stadium endgültig erreicht wird. SQL-01, MQL-02, SQL-02, MQL-03, SQL-03 _wird nicht_ Touchpoints der Opportunity einbezogen, da diese Staging-Übergänge nicht dazu beitragen, die Opportunity im Journey voranzutreiben.

Der SAL-01 (Letzter) Touchpoint von Lead 1 ist der nächste Touchpoint, der in die Opportunity aufgenommen wird. Lead 1 wandelt sich dann in einen Kontakt mit einer Opportunity um und erstellt den OC Touchpoint.

FT und LC von Lead 3 und die Touchpoints für MQL, SQL und SQL erscheinen als Form Touches bei der Opportunity.

Der SQL-01-Touchpoint (Letzter) von Lead 2 wird nicht als Touchpoint in die Opportunity aufgenommen, da er nach dem OC-Touchpoint erfolgte. Außerdem erfolgte der SQL-Staging-Übergang von Lead 2 _nach dem letzten SQL-Staging-Übergang_ und trägt nicht dazu bei, das Opportunity-Journey voranzutreiben.

## Opportunity-Szenarien {#opportunity-scenarios}

**Szenario 1 - Kontakte mit Opportunity- und Boomerang-Tracking**

In diesem Szenario hat sich ein Kunde dafür entschieden, die Übergänge **Demo- und Verhandlungsphase** auf der **Kontakt** zu verfolgen. Jede Boomerang-Phase kann bis zu zwei Touchpoints erhalten. Der Unterschied zwischen Stufenübergängen eines Kontakts und Stufenübergängen eines Leads besteht darin, dass die Übergänge der Kontaktstufe als Boomerang-Touchpoints auf der Opportunity (_)_ OC-Touchpoint erscheinen können. Dies gilt nicht für Stadium-Übergänge, die am Lead auftreten, da diese als Formular-Touchpoint erscheinen.

![In diesem Szenario hat sich ein Kunde dafür entschieden, die Demo zu verfolgen und](assets/boomerang-stages-25.png)

In diesem Beispiel werden die Übergänge von Demo und Verhandlungsphase von Kontakt 1 als Touchpoints Demo-01 und Verhandlungs-01 für die Opportunity einbezogen. Der Übergang des Demo-Stadiums von Kontakt 2 erfolgt _nach_ Kontakt 1 und wird als Demo-02 (letzter) Touchpoint auf der Opportunity angezeigt.

Beachten Sie, dass es keinen zweiten Übergang zur Verhandlungsphase gibt. Die Opportunity springt sofort von Demo-02 (Letzte) zu Close Won. In diesem Fall umfasst [!DNL Marketo Measure] die Verhandlungstransition mit dem Touchpoint „Abgeschlossen gewonnen“.
