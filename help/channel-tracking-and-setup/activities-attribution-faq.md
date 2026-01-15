---
description: Häufig gestellte Fragen zu Aktivitäten Attribution für Marketo Measure-Anwender
title: Häufig gestellte Fragen zur Aktivitätszuordnung
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 3%

---

# Häufig gestellte Fragen zur Aktivitätszuordnung {#activities-attribution-faq}

[!DNL Marketo Measure] Aktivitäten importiert alle Ihre Aktivitätsdatensätze und generiert Touchpoints für sie, sodass diese Aktivitäten eine Attribution erhalten können. Der häufigste Anwendungsfall besteht darin, Aktivitäten des Sales-Teams zu verfolgen, da diese in der Regel einen Datensatz mit Telefonanrufen oder E-Mails erstellen, die an Interessenten gesendet werden. Andere einzigartige Dinge, die verfolgt werden können, sind Inhaltsinteraktionen wie Asset-Downloads oder Videoansichten.

**Wie unterscheidet sich dies von Offline-Kampagnen?**

Der größte Unterschied besteht darin, dass Kampagnen nur einen Touchpoint bereitstellen können, da Kampagnen für jeden Lead oder Kontakt nur ein Kampagnenmitglied zulassen. Sie können also wiederkehrende Ereignisse wie ausgehende Anrufe, Demos oder Webinar-Teilnehmer nur verfolgen, wenn Sie für jede Gruppierung individuelle Kampagnen erstellen. Aktivitäten ermöglichen es Ihnen, jedes Ereignis zu messen.

**Gibt es einen Unterschied zwischen Aufgaben, Ereignissen und Aktivitäten?**

Das Aktivitätsobjekt fungiert über die Aufgaben- und Ereignisobjekte als Übergeordnetes Objekt. Aktivitäten umfassen im Wesentlichen sowohl Aufgaben als auch Ereignisse. Aufgaben werden normalerweise verwendet, um schnelle einmalige Elemente aufzuzeichnen, wie z. B. einen Telefonanruf oder eine E-Mail. Ereignisse werden normalerweise für Ereignisse mit einem Start- oder Enddatum verwendet, z. B. Meetings oder Konferenzen.

**Wenn ich einen Lead oder Kontakt mit derselben wiederkehrenden Aufgabe habe, sehe ich Käufer-Touchpoints für alle diese Aufgaben?**

Ja. Es besteht eine 1:1-Beziehung zwischen Ihren synchronisierten Aktivitäten und den erstellten Touchpoints.

**Wie weiß ich, welche Datensätze zur Erstellung von Touchpoints führen?**

Es empfiehlt sich, zuerst die Filter mit dem Aktivitätsobjekt in Ihrem CRM einzurichten. Basierend auf den Filterregeln erhalten Sie eine gute Vorstellung davon, wie viele Datensätze unter diese Kriterien fallen. Anschließend können Sie sie bei Bedarf verfeinern. Dies ist nicht erforderlich, aber eine hilfreiche Möglichkeit für Benutzende zu verstehen, wie viele Aktivitäts-Touchpoints erstellt werden, sobald die Aktivitätsregeln eingerichtet wurden.

**Wie lautet der Name der [!DNL Marketo Measure] Kampagne?**

Da diese Aktivitäten zu einem Touchpoint führen, müssen [!DNL Marketo Measure] wissen zu welchem Kanal und Unterkanal sie gehören. Für jede Regel müssen Sie einen [!DNL Marketo Measure] Kampagnennamen angeben. Nachdem dieser erstellt wurde, verwenden Sie die CSV-Datei für Online-Kanäle , um diesen [!DNL Marketo Measure] Kampagnennamen seinem entsprechenden Kanal zuzuordnen. Der [!DNL Marketo Measure] Kampagnenname wird auch auf dem Touchpoint selbst im Feld [!UICONTROL Anzeigenkampagnenname] angezeigt.

**Welche anderen Touchpoint-Felder werden ausgefüllt?**

| **Touchpoint-** | **Wert** |
|---|---|
| Lead/Kontakt | Alle Aktivitäten sind mit einem Lead oder Kontakt verbunden |
| Kampagne | channel.subchannel [[!DNL Marketo Measure]] |
| Touchpoint-Quelle | CRM-Aktivität |
| Medium | Activity.Type |
| Touchpoint-Typ | Activity.Type |
| Name der Anzeigenkampagne | Name der [!DNL Marketo Measure] Kampagne |
| Anzeigeninhalt | Betreff der Aktivität |
| Werbe-ID | Externe Aktivitäts-ID |
| Touchpoint-Datum | [Benutzerdefiniert - in Programmen festgelegt] |

**Was passiert, wenn ich für jeden Vertriebsmitarbeiter eine andere Regel erstellen muss? Muss ich für jede [!DNL Marketo Measure] unterschiedliche Campaign-Instanzen erstellen?**

Nein, das tun Sie nicht. Mit „Dynamische Kampagnennamen“ können Sie einen Teil (oder alle) des [!DNL Marketo Measure] Kampagnennamens mithilfe eines „Ersetzungsparameters“ ausfüllen, der auf ein Feld aus dem Aktivitätsobjekt verweist. Wenn Sie beispielsweise über einen [!DNL Marketo Measure] Kampagnennamen mit dem Titel „Ausgehender Aufruf“ verfügen, der Vertriebsmitarbeiter jedoch am Ende sein soll, nehmen Sie den CRM-Feldnamen und rufen Sie den [!DNL Marketo Measure] Kampagnennamen „Ausgehender {AssignedTo}&quot; oder „Ausgehender {CreatedBy}&quot; auf.

**Wie richte ich in der [!DNL Marketo Measure] App Aktivitäten ein?**

Eine Anleitung zum Konfigurieren von Aktivitäten in der [!UICONTROL Marketo] Measure-App finden Sie im Artikel Unterstützung von [!DNL Marketo Measure]-Aktivitäten .

**Was bedeuten die verschiedenen Operatoren?**

* Ist gleich: Exakte Übereinstimmung mit dem Wert (auch: Social)
* Enthält: Der Text befindet sich in der Mitte (auch: &#42;social&#42;)
* Beginnt mit: Der Wert beginnt mit dem Text (auch: social&#42;)
* Endet mit: Der Wert endet mit dem Text (auch: &#42;social)
* Stimmt überein mit „any“: Es können mehrere Werte hinzugefügt werden, die durch Kommas getrennt sind. Wenn [!UICONTROL beginnt mit], [!UICONTROL endet mit] oder contains-Operatoren angewendet werden müssen, verwenden Sie den Platzhalter (&#42;)
* Größer als: Wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet
* Kleiner als: Wird für numerische Felder oder Datums-/Uhrzeitfelder verwendet

**Welchen Kanal nutzen diese Aktivitäten?**

Wenn die Aktivitätsregel und der entsprechende [!DNL Marketo Measure] Kampagnenname erstellt wurden, verwenden Sie die Online-Kanaldefinitionen, um diese Kampagnen unter dem richtigen Marketing-Kanal zu platzieren. [!DNL Marketo Measure] können Kanäle nicht nur über Medium und Quelle, sondern auch über Campaign definieren.

Um im obigen Beispiel die Kampagne „Outbound Call {Assigned To}&quot; dem BDR-Kanal zuzuweisen, fügen Sie eine Zeile in Ihre Online-Kanal-CSV für den BDR-Kanal mit der Kampagnendefinition „Outbound Call&#42;&quot; ein - das Sternchen bezeichnet einen Platzhalterwert, sodass alle Kampagnen, die mit „Outbound Call“ beginnen, unter den BDR-Kanal fallen, anstatt für jeden Kampagnennamen eine separate Zeile erstellen zu müssen.
