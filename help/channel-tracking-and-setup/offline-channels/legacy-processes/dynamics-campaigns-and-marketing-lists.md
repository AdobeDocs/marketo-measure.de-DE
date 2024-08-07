---
unique-page-id: 18874610
description: Dynamics-Kampagnen und Marketinglisten - [!DNL Marketo Measure]
title: Dynamics-Kampagnen und Marketing-Listen
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 3%

---

# Dynamics-Kampagnen und Marketing-Listen {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>Dieser Artikel behandelt einen veralteten Prozess. Wir ermutigen die Benutzenden, den [neuen, verbesserten In-App-Prozess](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} zu verwenden.

## Kampagnen {#campaigns}

Dynamics-Kampagnen eignen sich gut zum Verfolgen von Offline-Marketingaktivitäten und deren Einbeziehung in die Omni-Channel-Journey. Kampagnen müssen sich auf Leads oder Kontakte beziehen und können entweder über Kampagnenantworten oder Marketinglisten in die Kampagne aggregiert werden.

## Kampagnenantworten {#campaign-responses}

Wenn Leads oder Kontakte direkt zu einer Kampagne hinzugefügt werden, werden sie als Campaign-Antwortdatensatz eingegeben.

![](assets/1.png)

## Aktivieren von Touchpoints {#enable-touchpoints}

Um diese Datensätze in die Touchpoint-Journey einzubeziehen, gibt es einige Optionen für die zu synchronisierenden Kampagnenreaktionstypen. Im Campaign-Datensatz sollte ein benutzerdefiniertes Feld aus der installierten Lösung mit der Bezeichnung &quot;[!UICONTROL Käufer-Touchpoints aktivieren]&quot;vorhanden sein. Wenn dies nicht angezeigt wird, muss das Feld über den Formular-Editor hinzugefügt werden.

![](assets/2.png)

Sie können festlegen, dass alle Datensätze, die eine Kampagnenantwort haben, in die Kampagne aufgenommen werden sollen, oder nur solche mit der Antwort &quot;Interessant&quot;. Standardmäßig können die Kampagnenantworten überhaupt nicht einbezogen werden. Sie können das Feld entweder leer lassen oder es explizit ausschließen.

[!DNL Marketo Measure] unterstützt keine benutzerdefinierten Antwortwerte.

![](assets/3.png)

Dies sind die Lagerantwortwerte für die Campaign-Antwort:

![](assets/4.png)

Je nach Auswahl sind diese Datensätze nun für Touchpoints im Journey &quot;Lead&quot;, &quot;Kontakt&quot;oder &quot;Chancen&quot;geeignet. Wenn sie sich qualifizieren, wird auf der Journey ein &quot;Dynamics Campaign&quot;-Touchpoint angezeigt.

Ein Grund dafür, dass eine Kampagnenantwort möglicherweise nicht angezeigt wird, ist, dass die Aktivität Erstkontakt und/oder Lead-Erstellungskontakt bereits für den Lead/Kontakt aufgezeichnet wurde und die Funktion &quot;PostLC&quot;deaktiviert ist oder ihre maximale Anzahl an Touchpoints erreicht hat.

## Touchpoint-Datum {#touchpoint-date}

Das Touchpoint-Datum für eine Kampagne bezieht sich normalerweise auf das Datum, an dem die Kampagnenantwort zur Kampagne hinzugefügt wurde. Sie kann überschrieben werden, wenn das benutzerdefinierte Feld aus der installierten Lösung mit der Bezeichnung &quot;Buyer Touchpoint Date&quot;ausgefüllt wird. Wenn dies nicht angezeigt wird, muss das Feld über den Formular-Editor hinzugefügt werden.

Ein gängiges Beispiel bei Verwendung dieses Felds ist die Verwendung von Ereignissen, bei denen eine Badge-Liste von einem Ereignis aus dem CRM-System hinzugefügt wird, Tage nach dem Ereignis, sodass der Benutzer das Buyer Touchpoint-Datum in den Zeitpunkt des Ereignisses zurücksetzen kann.

![](assets/5.png)

## Marketinglisten {#marketing-lists}

Marketinglisten bieten eine weitere Möglichkeit, Leads oder Kontakte in eine Marketing-Journey aufzunehmen. Marketing-Listen sind für eine Gruppe von Leads oder Kontakten eindeutig, d. h. der Benutzer muss auswählen, ob es sich bei seiner Liste um Leads oder eine Gruppe von Kontakten handelt.

[!DNL Marketo Measure] unterstützt nur statische Marketinglisten. Dynamische Marketinglisten werden nicht unterstützt, da für unsere Verarbeitung das Änderungsdatum eines Datensatzes geprüft werden muss. Da sich jedoch häufig eine dynamische Liste ändert, gibt es kein Änderungsdatum, mit dem [!DNL Marketo Measure] verglichen werden kann. Dies würde einen konstanten Download des gesamten Datensatzes über den Tag hinweg erfordern.

![](assets/6.png)

Der obige Screenshot ist eine Marketingliste für Leads. Marketinglisten sind mit Kampagnen verknüpft und können mehreren Kampagnen zugeordnet werden. Sofern Sie nicht immer nur eine Marketingliste für eine Kampagne erstellen, empfiehlt [!DNL Marketo Measure] nicht, dass Kunden zur Verfolgung ihrer Kampagnen Marketinglisten verwenden. Es ist unwahrscheinlich, dass dieselbe genaue Liste von Leads/Kontakten für Touchpoints in mehreren Kampagnen geeignet ist.

## Aktivieren von Touchpoints {#enable-touchpoints-1}

Um eine Marketing-Liste für Touchpoints zu aktivieren, gibt es eine separate Einstellung im Campaign-Datensatz mit der Bezeichnung &quot;[!UICONTROL Marketinglisten synchronisieren]&quot;, die ein einfacher Ja/Nein-Schalter ist. Wenn dies nicht angezeigt wird, muss das Feld über den Formular-Editor hinzugefügt werden. Im Campaign-Datensatz können Sie sehen, welche Marketinglisten mit der Kampagne verbunden sind, sodass Sie wissen, wie viele Listen Sie aktivieren.

![](assets/7.png)

## Touchpoint-Datum {#touchpoint-date-1}

Das Touchpoint-Datum für eine Marketing-Liste ist normalerweise das von ListMember erstellte Datum, sodass das Datum, an dem der Lead oder Kontakt zur Marketing-Liste hinzugefügt wurde, Sie kann überschrieben werden, wenn das benutzerdefinierte Feld aus der installierten Lösung mit der Bezeichnung &quot;Buyer Touchpoint Date&quot;ausgefüllt wird. Wenn dies nicht angezeigt wird, muss das Feld über den Formular-Editor hinzugefügt werden.

![](assets/8.png)

## Kanalzuordnung {#channel-mapping}

Dynamics-Kampagnen werden in Ihren benutzerdefinierten Marketing-Kanälen mithilfe des Felds Kampagnentyp zusammengefasst. Diese können im Menü Dynamics-Anpassungen geändert werden.

Die Werte im Menü &quot;Kampagnentyp&quot;werden in die [!DNL Marketo Measure] -Anwendung gezogen. **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Offline-Kanäle]**.

Für jeden Kampagnentyp kann er einer Kombination aus Kanal und Subkanal zugeordnet werden, sodass jeder aus der Kampagne abgeleitete Touchpoint über den korrekten zugeordneten Kanal und Subkanal verfügt.

![](assets/9.png)

![](assets/10.png)

## Kampagnensynchronisierungsdatum {#campaign-sync-date}

Dies ist für Dynamics-Kunden nicht verfügbar.

## FAQs {#faq}

**Können wir Touchpoints in Marketing-Listen oder nur Kampagnen in Dynamics aktivieren?**

Sie können eine Marketingliste aktivieren, sie muss jedoch mit einer Kampagne verbunden sein, da die Option zur Synchronisierung einer Marketingliste in der Kampagne verwendet wird.

**Können Kampagnenantworten UND Marketinglisten in einer Kampagne verwendet werden?**

Ja.
