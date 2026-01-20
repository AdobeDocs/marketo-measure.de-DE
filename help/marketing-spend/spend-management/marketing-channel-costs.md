---
unique-page-id: 18874602
description: Kosten des Marketing-Kanals - [!DNL Marketo Measure]
title: Marketingkanal-Kosten
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 1%

---

# Marketingkanal-Kosten {#marketing-channel-costs}

Einer der grundlegendsten Vorteile der Verwendung von [!DNL Marketo Measure] ist die Möglichkeit, Marketing-Maßnahmen direkt mit den Auswirkungen auf den Umsatz zu verbinden - mit der gewünschten Granularität. Auf der Touchpoint-Ebene lässt sich der Return on Investment erkennen. Um diesen Vorteil nutzen zu können, müssen die Kanalkosten in die [!DNL Marketo Measure]-App hochgeladen werden. ROI-Berichte werden automatisch erstellt und sind im Dashboard **Marketing-ROI“** [experience.adobe.com/marketo-measure verfügbar](https://experience.adobe.com/marketo-measure){target="_blank"}.

[Klicken Sie hier, um direkt zu den Anweisungen zu navigieren.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

Mit der Funktion „Marketingausgaben [!DNL Marketo Measure]&quot; können Kundinnen und Kunden ihre Ausgaben über alle Kanäle, Unterkanäle und Kampagnen hochladen. Je mehr Daten von Kunden hinzugefügt werden, desto mehr ROI-Berichte werden im Dashboard Umsatzzuordnung angezeigt.

Kosten, die gemeldet und von direkten Anzeigenverbindungen importiert werden, werden automatisch auf der detailliertesten Ebene abgerufen und müssen nicht hochgeladen werden. Dazu gehören unsere aktuellen Integrationen mit Google AdWords, Bing Ads, DoubleClick und Facebook.

[Klicken Sie hier, um direkt zur häufig gestellten Frage zu gelangen.](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## Definitionen {#definitions}

**Ausgaben nach Kampagne**

Auf der detailliertesten Ebene können Kunden Ausgaben nach einzelnen Kampagnen eingeben, die innerhalb ihres jeweiligen Kanals gruppiert sind. Für CRM-Kampagnen hat [!DNL Marketo Measure] die Kampagnen-ID in eine separate Spalte eingefügt, mit der Sie Offline-Kampagnenausgaben aus Ihrem CRM dieser Tabelle zuordnen können. Durch das Hinzufügen von Ausgaben auf dieser Ebene können Kunden den Kampagnen-ROI anzeigen und die Leistung nach Kampagnen optimieren.

Die Summe aller Kampagnen muss nicht die Summe der im Unterkanal oder Kanal eingegebenen Werte ergeben, sie kann jedoch nicht mehr als die im Unterkanal oder Kanal eingegebenen Werte betragen. Wenn die Summe kleiner ist als der im Unterkanal oder Kanal eingegebene Wert, fügt [!DNL Marketo Measure] automatisch eine Zeile für „Sonstige“ hinzu, um die Differenz zu decken und etwaige Lücken zu füllen.

**Ausgaben nach Unterkanal**

Auf höherer Ebene können Kunden Ausgaben nach Unterkanal eingeben, der unter seinem Kanal gruppiert ist. Durch Hinzufügen der Ausgaben auf dieser Ebene können Kunden den ROI des Unterkanals anzeigen und die Leistung nach Unterkanal optimieren.

Die Summe aller Unterkanäle muss nicht die Summe der am Kanal eingegebenen Werte ergeben, sie kann jedoch nicht mehr als die am Kanal eingegebenen Werte betragen. Wenn die Summe kleiner ist als der im Kanal eingegebene Wert, fügt [!DNL Marketo Measure] automatisch eine Zeile für „Sonstige“ hinzu, um die Differenz zu decken und etwaige Lücken zu füllen.

**Ausgaben nach Kanal**

Auf der höchsten Ebene können Kunden Ausgaben nach Kanal eingeben. Durch das Hinzufügen von Ausgaben auf dieser Ebene können Kunden den Kanal-ROI anzeigen und die Leistung nach Kanal optimieren.

**Datumsauswahl**

Der standardmäßige Datumsbereich beginnt am Startdatum mit [!DNL Marketo Measure] bis zum aktuellen Monat. Um sicherzustellen, dass die Kosten korrekt bleiben, können Sie keine Kosten für zukünftige Monate eingeben, aber Sie können Kosten für Monate vor Ihrer Partnerschaft mit [!DNL Marketo Measure] eingeben.

**Filter**

Um Ihre Ergebnisse in der Tabelle mit den Marketingausgaben einzugrenzen, wählen Sie oben einen Kanal aus, um andere Kanäle auszufiltern. Dies ist hilfreich, wenn Sie ein Team haben, das sich auf einen einzelnen Kanal konzentriert.

**Durchsuchen**

Verwenden Sie das Suchfeld, um übereinstimmenden Text aus Kanälen, Unterkanälen oder Kampagnen zu finden.

**Aktuelle Kosten herunterladen**

Die heruntergeladene CSV-Datei ruft die Ergebnisse aus Ihrem aktuellen Bildschirm ab, d. h. alle angewendeten Datumsangaben, Filter oder Suchen werden wie vorliegend heruntergeladen.

**CSV hochladen**

Unabhängig davon, welche Ansicht im Browser angezeigt wird, können Sie jede CSV-Datei hochladen, wenn es sich um eine gefilterte Ansicht oder die Standardansicht mit allen Daten und Kanälen handelt.

Der häufigste Fehler, der auftritt, ist das Format der Datumsspalten. Dies geschieht, wenn das Datumsformat geändert wird, und kann absichtlich auftreten, wenn zwischen Excel- und/oder Google-Arbeitsblättern gewechselt wird. Beachten Sie, dass das Datum MM-YY sein sollte, also Sep-12 und nicht Sept-12 oder Mai-12 und nicht 05-12.

## Vorbereitung {#before-you-begin}

[!DNL Marketo Measure] verfügt über 13 Standardkanäle, die verwendet oder erweitert werden können. Darüber hinaus können bis zu 40 Online- und Offline-Kanäle erstellt werden, um Ihre einzigartige Marketing-Struktur zu berücksichtigen. Darauf aufbauend können insgesamt 200 Unterkanäle erstellt werden, um auch diese Online- und Offline-Kanäle zu unterstützen.

[!DNL Marketo Measure] werden automatisch Marketingkanalkosten von Plattformen herunterladen, mit denen es eine API-Integration hat, z. B. Bing Ads und Google AdWords. Kosten für Plattformen, die nicht mit [!DNL Marketo Measure] integriert sind, müssen manuell hochgeladen werden. Die Marketing-Kanäle sollten eingerichtet werden, bevor die Kostendaten hochgeladen werden.

## Marketing-Kosten werden hochgeladen {#uploading-marketing-costs}

Sobald Marketing-Kanäle und -Regeln eingerichtet oder aktualisiert wurden, können die zugehörigen Kosten hochgeladen werden. Gehen Sie dazu wie folgt vor:

**Schritt 1: Navigieren Sie in der [!DNL Marketo Measure]-App zur Seite „Marketing-Ausgaben“**

Klicken Sie im Menü **[!UICONTROL Mein Konto]** auf **[!UICONTROL Einstellungen]** und navigieren Sie dann zur Option **[!UICONTROL Marketingausgaben]** in der linken Seitenleiste unter dem Abschnitt **[!UICONTROL Reporting]**.

![](assets/1.png)

**Schritt 2: Laden Sie die CSV-Datei Aktuelle Kosten herunter**

Navigieren Sie rechts im Bildschirm und klicken Sie auf **[!UICONTROL Aktuelle Kosten herunterladen].** Mit dieser Option können Sie eine Tabelle im CSV-Format herunterladen.

![](assets/2.png)

**Schritt 3: Öffnen Sie die CSV-Datei und nehmen Sie Änderungen vor**

Sie können die Datei importieren und mithilfe von Google Sheets, Apple Numbers, Microsoft Excel oder einer anderen Software öffnen. [!DNL Marketo Measure] empfiehlt die Verwendung von Google Sheets.

Nehmen Sie nach dem Import der Tabelle die gewünschten Änderungen vor, z. B. Kosten zu Kanälen und Unterkanälen hinzufügen oder vorhandene Informationen aktualisieren.

Überprüfen Sie die Logikregeln in Ihrem Blatt. Jede Zeile sollte einen Kanal und einen seiner Unterkanäle enthalten, die durch einen Punkt (.) am Ende getrennt sind. Es ist wichtig, dieses Format konsistent zu verwenden.

Um beispielsweise Facebook als Unterkanal und Social als Kanal anzugeben, sollte die Regel wie folgt geschrieben werden: „Social.Facebook“. Um ein Offline-Ereignis zu verfolgen, sollte die Kanalsyntax wie folgt lauten: „Events.Big Conference.“ Beispiele sind in der Abbildung unten dargestellt:

![](assets/3.png)

_Zusätzliche Hinweise_:

Ändern Sie keine Datumsangaben in der Tabelle, da dies beim Hochladen des Dokuments zu Problemen führen kann.

Lassen Sie kein Feld leer. Auch wenn kein Dollarwert hinzuzufügen ist, geben Sie 0 $ als Dollarbetrag ein.

Die Kosten für Bing Ads und Google AdWords müssen nicht eingegeben oder aktualisiert werden, da [!DNL Marketo Measure] diese Daten automatisch aus seiner API-Verbindung mit diesen Plattformen abruft.

**Schritt 4: Speichern Sie die Datei im CSV-Format**

Wenn Sie in Google Sheets arbeiten, laden Sie unbedingt zuerst die Datei herunter. Schließen Sie keine monatlichen Daten aus bzw. löschen Sie sie nicht, da dies beim späteren Hochladen der CSV-Datei in [!DNL Marketo Measure] zu Problemen führt.

**Schritt 5: CSV-Datei hochladen**

Gehen Sie zum Abschnitt **[!UICONTROL Kosten]** der [!DNL Marketo Measure]-App und klicken Sie auf **[!UICONTROL Upload.CSV]**. Das System wird aktualisiert und zeigt die neuen Informationen an.

## FAQs {#faq}

**Warum werden Zahlen in der CSV-Datei angezeigt**

Wenn kein Wert auf einer höheren Ebene wie Kanal oder Unterkanal eingegeben wird, addieren [!DNL Marketo Measure] automatisch die untergeordneten Ebenen für Sie, die angezeigt werden, sobald Ihre Datei hochgeladen wurde. Wenn die Summe der untergeordneten Elemente kleiner ist als der für das übergeordnete Element eingegebene Wert, fügt [!DNL Marketo Measure] eine Zeile „Sonstige“ hinzu, um die Differenz in der Summe anzuzeigen.

**Wie werden die Kampagnen in der Liste bestimmt, die ich sehe?**

Im Moment listen unsere Ergebnisse die Kampagnen auf, denen ein Touchpoint gutgeschrieben wurde. Wenn eine Kampagne aktiv war, wird diese anhand des Touchpoint-Datums angezeigt, an dem sie stattgefunden hat.

**Es gibt zu viele Zeilen und Spalten, um durchzugehen - kann ich die Ansicht konsolidieren?**

Mit der Möglichkeit, den Datumsbereich zu ändern, den Kanal zu filtern oder nach Werten zu suchen, können Sie die Ergebnisse der Tabelle konsolidieren, sodass sie Ihren Anforderungen besser entsprechen.

**Warum kann ich keine Datei hochladen?**

Wir verfügen über verschiedene Berechtigungssätze in der [!DNL Marketo Measure]-App. Um eine Datei hochzuladen, müssen Sie „AccountAdmin“ sein. Um dies zu umgehen, fordern Sie Zugriff von Ihrem Kontoadministrator an oder bitten Sie Ihren Kontoadministrator, die Datei in Ihrem Namen hochzuladen. Eine Liste der Benutzer und ihrer Rollen finden Sie unter **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Kontobenutzer anzeigen/hinzufügen]**.
