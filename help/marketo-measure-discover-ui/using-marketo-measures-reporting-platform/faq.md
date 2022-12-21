---
unique-page-id: 18874660
description: FAQs - [!DNL Marketo Measure] - Produktdokumentation
title: FAQs
exl-id: f1896bf8-2216-427e-ac3e-98d87efede76
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 0%

---

# FAQs {#faq}

[!DNL Marketo Measure Discover]: Häufig gestellte Fragen.

**Wie speichere ich die Filter in einem Bericht?**

Wie heute werden Abfrageergebnisse in der URL gespeichert und können mit der kopierten URL gespeichert oder freigegeben werden.

**Wie verwende ich vordefinierte Datumsbereiche wie &quot;Letztes Jahr&quot;oder &quot;Aktuelles Quartal&quot;?**

Anstatt voreingestellte Datumsbereiche zu verwenden, wurde jetzt eine flexiblere Datumsfunktion hinzugefügt. Sie können weiterhin &quot;Letztes Jahr&quot;festlegen, Sie haben jedoch die Möglichkeit, &quot;Letztes 1 Jahr&quot;auszuwählen, d. h. die letzten 365 Tage ab heute oder &quot;Letztes 1 vollständiges Jahr&quot;, d. h. das letzte vollständige Jahr vom 1.01. bis 31.12. Eine weitere gute Verwendung der neuen Datumsauswahl besteht darin, einen relativen Datumsbereich festzulegen, der in der Regel ein rollierendes Zeitfenster für ein bewegtes Datum bietet.

**Wie erhalte ich CPL- oder CPC-Daten?**

Diese Metriken finden Sie nur auf der Paid Media-Pinnwand.

**Warum zeigen Sie keine Seitenansichten auf dem Wachstumsbrett an?**

Eines der Merkmale des Wachstumsboards ist, dass Sie die Trenddiagramme nicht nach Dimensionen wie Kanal oder Kampagne gruppieren können. Diese Daten stehen nicht auf Seitenansichtsebene zur Verfügung, da Seitenansichten nicht immer eine Quelle wie Kanal oder Kampagne haben, da sie mitten in Webbesuchen stattfinden. Verwenden Sie Paid Media oder Web Traffic, um Daten zu Seitenansichten anzuzeigen.

**Wenn ich die Gruppierung ändere, entsprechen die Summen nicht immer dem gleichen Betrag. Warum ist das so?**

Werte gibt es nicht für jede einzelne Datenhierarchie, da die Hierarchie nicht immer ein klarer Schnittfluss ist. Unabhängig davon, ob die Kosten selbst gemeldet oder von einem Anzeigen-Provider importiert werden, können die Gesamtkosten für Kanal 1 1 10.000 USD betragen, aber nach einzelner Kampagne wurden nur insgesamt 5.500 USD gemeldet. Wenn sich die Gruppierung zwischen Kanal und Kampagne ändert, variieren die Summen.

**Was ist &quot;stimmt mit einem Benutzerattribut überein&quot;in den Filteroperatoren?**

Benutzerattribute werden auf Benutzer wie Unternehmens-ID, Vorname oder Nachname angewendet. Da unsere Benutzer Sie sind (unsere Kunden) und nicht Ihre Kunden, können Benutzerattribute in der [!DNL Marketo Measure Discover] Erlebnis. Sie können diese Option ignorieren. Wir arbeiten an einem besseren benutzerdefinierten Filtererlebnis, das Filter entfernt, die nicht für unsere Kunden gelten.

**Wie kommt es, dass einige Standarddatumsbereiche den ersten des folgenden Monats durchlaufen?**

Auch wenn der Datumsbereich nicht immer intuitiv ist, enthält die standardmäßige Filter-Benutzeroberfläche den hilfreichen &quot;Vor&quot;-Text, der dem Enddatum entspricht. Dies sollte Sie daran erinnern, dass das Enddatum, das Sie verwenden, 1 Tag außerhalb des gewünschten Bereichs liegen sollte.

**Welches Attributionsmodell wird für Leads und Kontakte verwendet?**

Touchpoints des Käufers, die Leads und Kontakten zugeordnet sind, werden bis zum Touch der Lead-Erstellung gemessen. Daher werden das Modell &quot;Erstkontakt&quot;, &quot;Lead-Erstellung&quot;und &quot;U-förmig&quot;empfohlen. Wenn Sie das Attributionsmodell in W-förmig oder Full Path ändern, wird automatisch ein U-förmiges Modell für Leads und Kontakte angewendet.

**Warum sind meine Kacheln &quot;Besuche&quot;, &quot;Unique Visits&quot;und &quot;Forms&quot;auf dem Wachstumsboard leer?**

Wenn diese Kacheln in Ihrer Ansicht zufällig 0 oder leer sind, bedeutet dies, dass die Kacheln nicht für Ihr Konto bereitgestellt werden. Wenden Sie sich an Ihren Success Manager, wenn Sie Fragen dazu haben.

**Was bedeutet bei Leads im Zeitverlauf und Kontakten im Zeitverlauf die Anzahl?**

Es verwendet die Touchpoint-Zählungen, die vom ausgewählten Attributionsmodell verteilt werden. Dies ist die Gesamtzahl der über einen bestimmten Zeitraum verteilten Leads und Zählungen. Es handelt sich nicht um eine eindeutige Anzahl.

**Zeigt das Diagramm für Formular-URLs nach Kanal im Content Marketing Webbesuche oder Formulardateien an?**

Diese werden nur in Formularen nachverfolgt.

**Welchen Nutzen hat Discover im Vergleich zur Maßnahme?**

[!DNL Marketo Measure Discover] bietet bessere Funktionen, wie z. B. Drillthroughs, und bessere Filterung, wie z. B. Subkanäle und Kanäle. Wir werden die Maßnahme auch 2019 einige Zeit aufheben.

**In Measurement konnte ich nach Anzeigengruppe und Konto filtern, wenn diese nach Anzeigenkonten gefiltert wurden. Wie kann ich dies in Discover sehen?**

Dies ist nur mit der Paid Media-Pinnwand verfügbar.

**Wie unterscheidet sich der Kohortenfunnel vom Passport-Trichter?**

Mit dem Kohortentrichter können Sie die Konversionsrate Ihrer Verkaufstrichter anzeigen und die Auswirkungen zwischen verschiedenen Phasen messen. Sie können die Phase, die Sie messen möchten, mithilfe der Filter auswählen, um die Konversionsrate von dieser Phase bis zu allen nachfolgenden Phasen anzuzeigen. Der Pass zeigt alle Leads/Kontakte und Chancen an, die innerhalb eines bestimmten Zeitraums durch jede Pipeline-Phase gegangen sind.

**Wie werden Inhalte auf der Paid Media-Pinnwand bestimmt?**

Auf jeder Pinnwandkachel wurde ein Filter hinzugefügt, der nur Daten enthält, bei denen ein bekannter Werbeanbieter aus Facebook, Google, Bing, LinkedIn oder DoubleClick vorhanden ist, da unsere Integration es uns ermöglicht, die Anzeigendaten aus diesen Quellen zu beziehen. Darüber hinaus wurde ein unscharfer Name hinzugefügt, der mit Kanälen und Subkanälen für Anzeige, gebührenpflichtige Suche, gebührenpflichtige Suche, gebührenpflichtige Social, PPC, SEM, gebührenpflichtige Mobilgeräte, gebührenpflichtige Twitter, Adroll, Terminus, Madison Logic, Madisonlogic und Demandbase übereinstimmt.

**Was ist der Unterschied zwischen Besuchen und individuellen Besuchen?**

Unique Visits sind eine Untergruppe von Besuchen. Während Besuche eine Zählung jedes Site-Besuchs darstellen, sind individuelle Besuche eindeutige Cookies dieser Site-Besuche. Eine Person kann mehrere individuelle Besuche berücksichtigen, wenn sie mit einer anderen Cookie-ID zurückkehrt.

**Zählt Touchpoint die Anzahl der Touchpoints der Käuferzuordnung oder der Touchpoints der Käuferzuordnung?**

Es handelt sich um eine Zählung dessen, was wir &quot;rohe&quot;Touchpoints nennen, oder &quot;Benutzer-Touchpoints&quot;, bei denen es sich um ein Aggregat beider Touchpoints handelt, sowie Touches, die zu keinem Touchpoint auf Lead/Kontakt oder Chancen führten.

**Warum werden bei der Filterung nach URL nur 0,00 USD für die Kacheln &quot;Kosten pro&quot;angezeigt?**

Dies ist das erwartete Verhalten aufgrund der Tatsache, dass wir keine nach URL segmentierten Kosten haben, sodass es in diesem Szenario nicht anwendbar ist.

**Warum werden nicht alle Segmentoptionen für meine Kategoriefilter angezeigt?**

Im Filter Segmente werden nur die Segmente angezeigt, denen gültige Datensätze zugeordnet sind. Wenn beispielsweise keine Datensätze mit dem Segment &quot;Sonstige&quot;vorhanden sind, wird &quot;Sonstige&quot;nicht als Option angezeigt.

**Does [!DNL Marketo Measure Discover] den GB18030-Zeichensatz unterstützen?**

Discover verwendet Tools von Drittanbietern und unterstützt derzeit den GB18030-Zeichensatz nicht.

**Warum wird beim Laden von Discover der Fehler 401 mit der Meldung &quot;Sie sind nicht authentifiziert, um diese Seite anzuzeigen&quot;angezeigt?**

[!DNL Marketo Measure Discover] erfordert die ordnungsgemäße Anzeige von Drittanbieter-Cookies. Um Discover zu verwenden, aktivieren Sie bitte Drittanbieter-Cookies in Ihrem Browser und aktualisieren Sie die Seite.

>[!NOTE]
>
>Einige Browser, einschließlich Chrome in Inkognito, deaktivieren standardmäßig Drittanbieter-Cookies.

![](assets/faq-1.png)