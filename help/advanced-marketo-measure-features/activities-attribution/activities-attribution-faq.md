---
unique-page-id: 18874704
description: FAQ zur Aktivitätszuordnung - [!DNL Marketo Measure]
title: Häufig gestellte Fragen zur Aktivitätszuordnung
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: e5931d783d8aad9ab0b32b4e30bbbfdfd46230dd
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 2%

---

# Häufig gestellte Fragen zur Aktivitätszuordnung {#activities-attribution-faq}

[!DNL Marketo Measure] Aktivitäten importiert alle Ihre Aktivitätsdatensätze und generiert Touchpoints für sie, sodass diese Aktivitäten eine Attribution erhalten können. Der häufigste Anwendungsfall besteht darin, Aktivitäten des Sales-Teams zu verfolgen, da diese normalerweise einen Datensatz mit Telefonanrufen oder E-Mails erstellen, die an potenzielle Kunden gesendet werden. Weitere eindeutige Elemente, die verfolgt werden können, sind Inhaltsinteraktionen wie Asset-Downloads oder Videoansichten.

>[!AVAILABILITY]
>
>Diese Funktion ist nur für Tier-2-Kunden aktiviert. Wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer), um eine höhere Kontoebene anzufordern.

**Inwiefern unterscheidet sich dies von Offline-Kampagnen?**

Der größte Unterschied besteht darin, dass Kampagnen nur einen Touchpoint bereitstellen können, da Kampagnen nur einen Kampagnenmitglieder für jeden Lead oder Kontakt zulassen. Das bedeutet, dass Sie wiederkehrende Ereignisse wie ausgehende Aufrufe, Demos oder Webinar-Teilnehmer nicht verfolgen können, es sei denn, Sie erstellen individuelle Kampagnen für jede Gruppierung. Mit Aktivitäten können Sie jedes Ereignis messen.

**Gibt es einen Unterschied zwischen Aufgabe, Ereignissen und Aktivitäten?**

Das Activities-Objekt fungiert als Dachelement oder übergeordnetes Objekt über die Task- und Event-Objekte. Aktivitäten decken im Wesentlichen sowohl Aufgaben als auch Ereignisse ab. Aufgaben werden normalerweise verwendet, um schnelle einmalige Elemente wie einen Telefonanruf oder eine E-Mail aufzuzeichnen. Ereignisse werden in der Regel für Dinge verwendet, die ein Start- oder Enddatum haben können, z. B. Meetings oder Konferenzen.

**Wenn ich einen Lead oder Kontakt mit derselben wiederkehrenden Aufgabe habe, sehe ich dann für all diese Kunden Touchpoints für Käufer?**

Ja. Es besteht eine 1:1-Beziehung zwischen Ihren synchronisierten Aktivitäten und den erstellten Touchpoints.

**Woher weiß ich, welche Datensätze zur Erstellung von Touchpoints führen?**

Es wird empfohlen, zunächst Ihre Filter mithilfe des Objekts Aktivität in Ihrem CRM einzurichten. Basierend auf den Filterregeln erhalten Sie so eine gute Vorstellung davon, wie viele Datensätze unter diese Kriterien fallen. Anschließend können Sie sie nach Bedarf verfeinern. Dies ist nicht erforderlich, bietet aber eine hilfreiche Möglichkeit, um zu verstehen, wie viele Aktivitäts-Touchpoints erstellt werden, sobald die Aktivitätsregeln eingerichtet wurden.

**Was ist der [!DNL Marketo Measure] Kampagnenname?**

Da diese Aktivitäten zu einem Touchpoint führen, muss [!DNL Marketo Measure] wissen, zu welchem Kanal und Unterkanal sie gehören. Für jede Regel müssen Sie einen [!DNL Marketo Measure] Kampagnennamen angeben. Nachdem dies erstellt wurde, verwenden Sie die CSV &quot;Online-Kanäle&quot;, um diesen [!DNL Marketo Measure] Kampagnennamen dem entsprechenden Kanal zuzuordnen. Der Kampagnenname &quot;[!DNL Marketo Measure]&quot; wird auch im Touchpoint selbst im Feld [!UICONTROL Anzeigenkampagnenname] angezeigt.

**Welche anderen Touchpoint-Felder werden ausgefüllt?**

| **Touchpoint-Feld** | **Wert** |
|---|---|
| Lead/Kontakt | Alle Aktivitäten beziehen sich auf einen Lead oder Kontakt |
| Kampagne | channel.subchannel [[!DNL Marketo Measure]] |
| Touchpoint-Quelle | CRM-Aktivität |
| Medium | Activity.Type |
| Touchpoint-Typ | Activity.Type |
| Name der Anzeigenkampagne | [!DNL Marketo Measure] Kampagnenname |
| Anzeigeninhalt | Aktivitätsthema |
| Anzeigen-ID | Externe Aktivitäts-ID |
| Touchpoint-Datum | [custom - festgelegt in apps] |

**Was passiert, wenn ich für jeden Vertriebsmitarbeiter eine andere Regel erstellen muss? Muss ich für jede Kampagne unterschiedliche [!DNL Marketo Measure] Kampagnen erstellen?**

Nein, nicht. Mit &quot;Namen dynamischer Kampagnen&quot;können Sie einen Teil (oder alle) des [!DNL Marketo Measure] Kampagnennamens mit einem &quot;Ersatzparameter&quot;ausfüllen, der auf ein Feld aus dem Aktivitätsobjekt verweist. Wenn Sie beispielsweise über einen &quot;[!DNL Marketo Measure]&quot;-Kampagnennamen mit dem Titel &quot;Ausgehender Aufruf&quot; verfügen, der Vertriebsmitarbeiter jedoch am Ende stehen soll, nehmen Sie den CRM-Feldnamen und rufen Sie den Kampagnennamen &quot;[!DNL Marketo Measure] Ausgehender Aufruf {AssignedTo}&quot; oder &quot;Ausgehender Aufruf {CreatedBy}&quot; auf.

**Wie richte ich Aktivitäten in der [!DNL Marketo Measure]-App ein?**

Anweisungen zum Konfigurieren von Aktivitäten innerhalb der [!UICONTROL Marketo] Measure App finden Sie im Artikel [!DNL Marketo Measure] Activities-Unterstützung .

**Was bedeuten die verschiedenen Operatoren?**

* ist gleich: exakte Übereinstimmung mit dem Wert (auch: Social)
* enthält: Der Text befindet sich in der Mitte (auch: &#42;social&#42;)
* beginnt mit: Der Wert beginnt mit dem Text (auch: social&#42;)
* endet mit: Der Wert endet mit dem Text (auch: &#42;social).
* entspricht beliebig: Es können mehrere Werte hinzugefügt werden, die kommagetrennt sind. Wenn [!UICONTROL mit ] beginnt, [!UICONTROL mit ] endet oder die Operatoren enthält angewendet werden müssen, verwenden Sie den Platzhalter (&#42;)
* größer als: wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet
* less than: wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet

**Welchen Kanal nehmen diese Aktivitäten in Anspruch?**

Wenn die Aktivitätsregel und der entsprechende [!DNL Marketo Measure] Kampagnenname erstellt werden, verwenden Sie die Definitionen für Online-Kanäle , um diese Kampagnen unter dem richtigen Marketing-Kanal zu platzieren. [!DNL Marketo Measure] kann Kanäle nicht nur mit Medium und Quelle, sondern auch mit Kampagne definieren.

Um im obigen Beispiel die Kampagne &quot;Outbound Call {Assigned To}&quot;dem BDR-Kanal zuzuweisen, fügen Sie eine Zeile in Ihre CSV-Datei für Online-Kanäle für den BDR-Kanal mit der Kampagnendefinition &quot;Outbound Call&#42;&quot; ein - das Sternchen bedeutet einen Platzhalterwert. Daher fallen alle Kampagnen, die mit &quot;Outbound Call&quot;beginnen, unter den BDR-Kanal, anstatt für jeden Kampagnennamen eine separate Zeile erstellen zu müssen. .
