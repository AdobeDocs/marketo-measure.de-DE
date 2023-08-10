---
unique-page-id: 18874704
description: FAQ zur Aktivitätszuordnung - [!DNL Marketo Measure] - Produktdokumentation
title: Häufig gestellte Fragen zur Aktivitätszuordnung
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 3%

---

# Häufig gestellte Fragen zur Aktivitätszuordnung {#activities-attribution-faq}

Die [!DNL Marketo Measure] Die Aktivitätsfunktion ermöglicht es uns, alle Ihre Aktivitätsdatensätze zu importieren und Touchpoints für sie zu generieren, sodass diese Aktivitäten eine Attribution erhalten. Der häufigste Anwendungsfall besteht darin, Aktivitäten des Sales-Teams zu verfolgen, da diese normalerweise einen Datensatz mit Telefonanrufen oder E-Mails erstellen, die an potenzielle Kunden gesendet werden. Weitere eindeutige Elemente, die verfolgt werden können, sind Inhaltsinteraktionen wie Asset-Downloads oder Videoansichten.

**Inwiefern unterscheidet sich dies von Offline-Kampagnen?**

Der größte Unterschied besteht darin, dass Kampagnen nur einen Touchpoint bereitstellen können, da Kampagnen nur einen Kampagnenmitglieder für jeden Lead oder Kontakt zulassen. Das bedeutet, dass Sie wiederkehrende Ereignisse wie ausgehende Aufrufe, Demos oder Webinar-Teilnehmer nicht verfolgen können, es sei denn, Sie erstellen individuelle Kampagnen für jede Gruppierung. Mit Aktivitäten können Sie jedes Ereignis messen.

**Gibt es einen Unterschied zwischen Aufgabe, Ereignissen und Aktivitäten?**

Das Activities-Objekt fungiert als Dachelement oder übergeordnetes Objekt über die Task- und Event-Objekte. Aktivitäten decken im Wesentlichen sowohl Aufgaben als auch Ereignisse ab. Aufgaben werden normalerweise verwendet, um schnelle einmalige Elemente wie einen Telefonanruf oder eine E-Mail aufzuzeichnen. Ereignisse werden in der Regel für Dinge verwendet, die ein Start- oder Enddatum haben können, z. B. Meetings oder Konferenzen.

**Wenn ich einen Lead oder Kontakt mit der gleichen wiederkehrenden Aufgabe wie eine E-Mail oder einen Aufruf habe, wird dann für all diese Kunden der &quot;Buyer Touchpoints&quot; angezeigt?**

Ja. Es gibt eine 1:1-Beziehung zwischen Ihren synchronisierten Aktivitäten und den erstellten Touchpoints.

**Woher weiß ich, welche Datensätze zur Erstellung von Touchpoints führen?**

Es wird empfohlen, zunächst Ihre Filter mithilfe des Objekts Aktivität in Ihrem CRM einzurichten. Basierend auf den Filterregeln erhalten Sie eine gute Vorstellung davon, wie viele Datensätze unter diese Kriterien fallen. Anschließend können Sie sie nach Bedarf verfeinern. Dies ist nicht erforderlich, bietet aber eine hilfreiche Möglichkeit, um zu verstehen, wie viele Aktivitäts-Touchpoints erstellt werden, sobald die Aktivitätsregeln eingerichtet wurden.

**Was ist das [!DNL Marketo Measure] Kampagnenname?**

Da diese Aktivitäten zu einem Touchpoint führen, [!DNL Marketo Measure] muss wissen, zu welchem Kanal und Subkanal sie gehören. Für jede Regel müssen Sie einen [!DNL Marketo Measure] Kampagnenname. Nach der Erstellung können Sie die CSV-Datei &quot;Online-Kanäle&quot;verwenden, um diese [!DNL Marketo Measure] Kampagnenname in den entsprechenden Kanal. Die [!DNL Marketo Measure] Der Kampagnenname wird auch im Touchpoint selbst im [!UICONTROL Anzeigenkampagnenname] -Feld.

**Welche anderen Touchpoint-Felder werden ausgefüllt?**

| **Touchpoint-Feld** | **Wert** |
|---|---|
| Lead/Kontakt | Alle Aktivitäten beziehen sich auf einen Lead oder Kontakt |
| Kampagne | channel.subchannel [[!DNL Marketo Measure]] |
| Touchpoint Quelle | CRM-Aktivität |
| Medium | Activity.Type |
| Touchpoint-Typ | Activity.Type |
| Name der Ad-Kampagne | [!DNL Marketo Measure] Kampagnenname |
| Anzeigeninhalt | Aktivitätsthema |
| Anzeigen-ID | Externe Aktivitäts-ID |
| Touchpoint-Datum | [custom - festgelegt in Apps] |

**Was passiert, wenn ich für jeden Vertriebsmitarbeiter eine andere Regel erstellen muss? Muss ich verschiedene [!DNL Marketo Measure] Kampagnen für jede?**

Nein, nicht. Wir haben das Konzept &quot;Dynamische Kampagnennamen&quot;eingeführt. Auf diese Weise können Sie die [!DNL Marketo Measure] Kampagnenname mit einem &quot;Ersatzparameter&quot;, der auf ein Feld aus dem Aktivitätsobjekt verweist. Wenn Sie beispielsweise eine [!DNL Marketo Measure] Kampagnenname mit dem Titel &quot;Ausgehender Aufruf&quot;, aber Sie möchten, dass der Vertriebsmitarbeiter am Ende steht, nehmen Sie den CRM-Feldnamen und rufen Sie die [!DNL Marketo Measure] Kampagnenname &quot;Ausgehender Aufruf&quot; {AssignedTo}&quot; oder &quot;Ausgehender Aufruf {CreatedBy}.&quot;

**Wie richte ich Aktivitäten im [!DNL Marketo Measure] App?**

Anweisungen zum Konfigurieren von Aktivitäten im [!UICONTROL Marketo] Die Kennungs-App finden Sie im Abschnitt [!DNL Marketo Measure] Aktivitäten unterstützen Artikel.

**Was bedeuten die unterschiedlichen Operatoren?**

* ist gleich: exakte Übereinstimmung mit dem Wert (auch: Social)
* enthält: Der Text befindet sich in der Mitte (auch: &#42;social&#42;)
* beginnt mit: Der Wert beginnt mit dem Text (auch: social)&#42;)
* endet mit: Der Wert endet mit dem Text (auch: &#42;social)
* entspricht beliebig: Es können mehrere Werte hinzugefügt werden, die durch Kommas getrennt sind. Wenn [!UICONTROL beginnt mit], [!UICONTROL endet mit], oder Operatoren enthält, müssen angewendet werden, verwenden Sie den Platzhalter (&#42;)
* größer als: wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet
* less than: wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet

**Welchen Kanal werden diese Aktivitäten nutzen?**

Sobald die Aktivitätsregel und die zugehörige [!DNL Marketo Measure] Kampagnenname, werden erstellt und Sie verwenden die Definitionen für Online-Kanäle , um diese Kampagnen unter dem richtigen Marketing-Kanal zu platzieren. [!DNL Marketo Measure] kann Kanäle nicht nur mit Medium und Quelle, sondern auch mit Kampagne definieren.

Im obigen Beispiel möchten Sie, um dem BDR-Kanal die Kampagne &quot;Ausgehender Aufruf {Zugeordneter Aufruf}&quot;zuzuweisen, eine Zeile in Ihre CSV-Datei &quot;Online-Kanäle&quot;für den BDR-Kanal mit der Kampagnendefinition &quot;Ausgehender Aufruf&quot;einfügen.&#42;&quot; - Das Sternchen steht für einen Platzhalterwert, sodass alle Kampagnen, die mit &quot;Ausgehender Aufruf&quot;beginnen, unter den BDR-Kanal fallen, anstatt für jeden Kampagnennamen eine separate Zeile erstellen zu müssen.
