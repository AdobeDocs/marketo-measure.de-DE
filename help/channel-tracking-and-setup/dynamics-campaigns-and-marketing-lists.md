---
description: Anleitung für Dynamics-Kampagnen und Marketing-Listen für Marketo Measure-Benutzende
title: Dynamics-Kampagnen und Marketing-Listen
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 3%

---

# Dynamics-Kampagnen und Marketing-Listen {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/custom-campaign-sync.md){target="_blank"} zu verwenden.

## Kampagnen {#campaigns}

Dynamics-Kampagnen eignen sich gut zur Verfolgung von Offline-Marketing-Aktivitäten und zur Aufnahme in die Omni-Channel-Journey. Kampagnen müssen sich auf Leads oder Kontakte beziehen und können entweder über Kampagnenantworten oder Marketing-Listen auf die Kampagne übertragen werden.

## Kampagnenantworten {#campaign-responses}

Wenn Leads oder Kontakte direkt zu einer Kampagne hinzugefügt werden, werden sie als Kampagnenreaktionsdatensatz eingegeben.

![Wenn Leads oder Kontakte direkt zu einer Kampagne hinzugefügt werden, werden sie eingegeben](assets/dynamics-lists-1.png)

## Touchpoints aktivieren {#enable-touchpoints}

Um diese Datensätze in die Touchpoint-Journey aufzunehmen, gibt es einige Optionen für die Typen der Campaign-Antworten, die synchronisiert werden sollen. Im Kampagnendatensatz sollte ein benutzerdefiniertes Feld der installierten Lösung mit der Bezeichnung „Käuferkontaktpunkte aktivieren[!UICONTROL  vorhanden ]. Wenn dies nicht angezeigt wird, muss das Feld über den Formulareditor hinzugefügt werden.

![Um diese Datensätze in die Touchpoint-Journey aufzunehmen, gibt es einige](assets/dynamics-lists-10.png)

Sie können auswählen, ob alle Datensätze, die eine Kampagnenreaktion haben, in die Kampagne einbezogen werden sollen, oder nur diejenigen mit der Antwort „Interessant“. Standardmäßig können Sie die Kampagnenantworten überhaupt nicht einbeziehen. Sie können das Feld entweder leer lassen oder es explizit ausschließen.

[!DNL Marketo Measure] unterstützt keine benutzerdefinierten Antwortwerte.

![Marketo Measure unterstützt keine benutzerdefinierten Antwortwerte.](assets/dynamics-lists-2.png)

Dies sind die Stock-Antwortwerte für die Kampagnenantwort:

![Dies sind die Standard-Antwortwerte für die Kampagnenreaktion:](assets/dynamics-lists-3.png)

Je nach Ihrer Auswahl können diese Datensätze jetzt für Touchpoints auf der Lead-, Kontakt- oder Opportunity-Journey verwendet werden. Wenn sie sich qualifizieren, wird ein „Dynamics Campaign“-Touchpoint auf der Journey angezeigt.

Eine Campaign-Antwort wird möglicherweise nicht angezeigt, weil für den Lead/Kontakt bereits eine Aktivität des Erstkontakts und/oder Lead-Erstellungs-Kontakts aufgezeichnet wurde und die Funktion „PostLC“ deaktiviert ist oder ihre maximale Anzahl an Touchpoints erreicht hat.

## Touchpoint-Datum {#touchpoint-date}

Das Touchpoint-Datum für eine Kampagne ist in der Regel das Datum, an dem die Kampagnenantwort zur Kampagne hinzugefügt wurde. Es kann überschrieben werden, wenn das benutzerdefinierte Feld der installierten Lösung mit der Bezeichnung &quot;Buyer Touchpoint-Datum“ ausgefüllt ist. Wenn dies nicht angezeigt wird, muss das Feld über den Formulareditor hinzugefügt werden.

Ein gängiges Beispiel für die Verwendung dieses Felds sind Ereignisse, bei denen dem CRM-System Tage nach dem Ereignis eine Liste mit Abzeichen-Scans von einem Ereignis hinzugefügt wird. Die Benutzenden können also das Buyer Touchpoint-Datum tatsächlich zurück in den Zeitpunkt ändern, zu dem das Ereignis aufgetreten ist.

![Ein gängiges Beispiel für die Verwendung dieses Felds sind Ereignisse, bei denen eine Liste](assets/dynamics-lists-4.png)

## Marketing-Listen {#marketing-lists}

Marketing-Listen sind eine weitere Möglichkeit, Leads oder Kontakte in eine Marketing-Journey aufzunehmen. Marketing-Listen sind für eine Gruppe von Leads oder Kontakten eindeutig, d. h. der Benutzer muss auswählen, ob seine Liste eine Gruppe von Leads oder eine Gruppe von Kontakten ist.

[!DNL Marketo Measure] unterstützt nur statische Marketing-Listen. Dynamische Marketing-Listen werden nicht unterstützt, da für die Verarbeitung das Änderungsdatum eines Datensatzes überprüft werden muss. Da jedoch eine dynamische Liste häufig wechselt, gibt es kein Änderungsdatum, an dem [!DNL Marketo Measure] geprüft werden können. Dies würde ein ständiges Herunterladen des gesamten Datensatzes über den Tag hinweg erfordern.

![Marketo Measure unterstützt nur statische Marketing-Listen. Wir unterstützen das nicht](assets/dynamics-lists-5.png)

Der obige Screenshot ist eine Marketing-Liste für Leads. Marketing-Listen sind mit Kampagnen verknüpft und können mit mehreren Kampagnen verknüpft werden. Sofern Sie nicht jeweils nur eine Marketing-Liste für eine Kampagne erstellen, empfiehlt [!DNL Marketo Measure] nicht, dass Kundinnen und Kunden Marketing-Listen verwenden, um ihre Kampagnen zu verfolgen. Es ist unwahrscheinlich, dass dieselbe exakte Liste von Leads/Kontakten für Touchpoints in mehreren Kampagnen infrage kommt.

## Touchpoints aktivieren {#enable-touchpoints-1}

Um eine Marketing-Liste für Touchpoints zu aktivieren, gibt es eine separate Einstellung im Kampagnendatensatz mit der Bezeichnung &quot;[!UICONTROL Marketing-Listen synchronisieren], was ein einfacher Ja-/Nein-Schalter ist. Wenn dies nicht angezeigt wird, muss das Feld über den Formulareditor hinzugefügt werden. Im Kampagnendatensatz können Sie sehen, welche Marketing-Listen mit der Kampagne verknüpft sind, sodass Sie wissen, wie viele Listen Sie aktivieren.

![Um eine Marketing-Liste für Touchpoints zu aktivieren, gibt es eine separate Einstellung](assets/legacy-processes-10.png)

## Touchpoint-Datum {#touchpoint-date-1}

Das Touchpoint-Datum für eine Marketing-Liste ist in der Regel das Erstellungsdatum des Listenmitglieds, d. h. das Datum, an dem der Lead oder Kontakt zur Marketing-Liste hinzugefügt wurde. Es kann überschrieben werden, wenn das benutzerdefinierte Feld der installierten Lösung mit der Bezeichnung &quot;Buyer Touchpoint-Datum“ ausgefüllt ist. Wenn dies nicht angezeigt wird, muss das Feld über den Formulareditor hinzugefügt werden.

![Das Touchpoint-Datum für eine Marketing-Liste ist normalerweise das erstellte ListMember](assets/dynamics-lists-6.png)

## Kanalzuordnung {#channel-mapping}

Dynamics-Kampagnen werden in Ihren benutzerdefinierten Marketing-Kanälen mithilfe des Felds Kampagnentyp zusammengefasst. Diese können im Menü „Dynamics-Anpassungen“ geändert werden.

Die Werte im Menü Kampagnentyp werden in die [!DNL Marketo Measure] übernommen. **[!UICONTROL Mein]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Offline-Kanäle]**.

Für jeden Kampagnentyp kann er einer Kanal- und Unterkanal-Kombination zugeordnet werden, sodass jeder Touchpoint, der von der Kampagne abgeleitet wird, den richtigen zugeordneten Kanal und Unterkanal hat.

![Für jeden Kampagnentyp kann er einem Kanal zugeordnet werden und](assets/dynamics-lists-7.png)

![Für jeden Kampagnentyp kann er einem Kanal zugeordnet werden und](assets/dynamics-lists-8.png)

## Kampagnensynchronisierungsdatum {#campaign-sync-date}

Dies ist nicht für Dynamics-Kunden verfügbar

## FAQs {#faq}

**Können Touchpoints auf Marketing-Listen aktiviert werden oder nur auf Kampagnen in Dynamics?**

Sie können eine Marketing-Liste aktivieren, sie muss jedoch mit einer Kampagne verknüpft sein, da die Option zum Synchronisieren einer Marketing-Liste in der Kampagne verfügbar ist.

**Können wir in einer Kampagne Antworten und Marketing-Listen für Kampagnen verwenden?**

Ja.
